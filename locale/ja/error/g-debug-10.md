<div class="framebox-container-container">
<div class="framebox-container">
{% framebox height="100%" %}
<style>
.lifecycle-diagram.register,
.lifecycle-diagram .diagram-refresh,
.lifecycle-diagram .diagram-close,
.lifecycle-diagram.register .controlled,
.lifecycle-diagram .cog-new {
  opacity: 0;
}
</style>
{% endframebox %}
</div>
</div>

次の HTML をご覧ください。

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

これは Service Worker を登録し、3 秒後に犬の画像を追加します。
