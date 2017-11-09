<div class="framebox-container-container">
<div class="framebox-container">
{% framebox height="100%" %}
<style>
.option00,
.option01 {
  opacity: 0;
}
</style>
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
