<div class="framebox-container-container">
<div class="framebox-container">
{% framebox height="100%" %}
<link href="" rel="stylesheet">
<script src="" defer></script>
<script src="" defer></script>
<script src="" defer></script>
<style></style>
<svg></svg>
<svg></svg>

<script></script>
{% endframebox %}
</div>
</div>

Take this HTML:

    <!DOCTYPE html>
    An image will appear here in 3 seconds:
    <script>
      navigator.serviceWorker.register('/sw.js')
        .then(reg => console.log('SW registered!', reg))
        .catch(err => console.log('Boo!', err));

      setTimeout(() => {
        const img = new Image();
        img.src = '/dog.svg';
        document.body.appendChild(img);
      }, 3000);
    </script>

It registers a service worker, and adds image of a dog after 3 seconds.

Here's its service worker, `sw.js`:

    self.addEventListener('install', event => {
      console.log('V1 installing…');

      // cache a cat SVG
      event.waitUntil(
        caches.open('static-v1').then(cache => cache.add('/cat.svg'))
      );
    });

    self.addEventListener('activate', event => {
      console.log('V1 now ready to handle fetches!');
    });

    self.addEventListener('fetch', event => {
      const url = new URL(event.request.url);

      // serve the cat SVG from the cache if the request is
      // same-origin and the path is '/dog.svg'
      if (url.origin == location.origin && url.pathname == '/dog.svg') {
        event.respondWith(caches.match('/cat.svg'));
      }
    });

It caches an image of a cat, and serves it whenever there's a request for
`/dog.svg`. However, if you [run the above
example](https://cdn.rawgit.com/jakearchibald/80368b84ac1ae8e229fc90b3fe826301/raw/ad55049bee9b11d47f1f7d19a73bf3306d156f43/){:
.external}, you'll see a dog the first time you load the page. Hit refresh, and
you'll see the cat.

Note: Cats are better than dogs. They just *are*.

### Scope and control

The default scope of a service worker registration is `./` relative to the
script URL. This means if you register a service worker at
`//example.com/foo/bar.js` it has a default scope of `//example.com/foo/`.

We call pages, workers, and shared workers `clients`. Your service worker can
only control clients that are in-scope. Once a client is "controlled", its
fetches go through the in-scope service worker. You can detect if a client is
controlled via `navigator.serviceWorker.controller` which will be null or a
service worker instance.

### Download, parse, and execute

Your very first service worker downloads when you call `.register()`. If your
script fails to download, parse, or throws an error in its initial execution,
the register promise rejects, and the service worker is discarded.

Chrome's DevTools shows the error in the console, and in the service worker
section of the application tab:

<figure>
  <img src="images/register-fail.png" class="browser-screenshot" alt="Error displayed in service worker DevTools tab">
</figure>
