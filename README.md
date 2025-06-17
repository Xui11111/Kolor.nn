<!DOCTYPE html>
<html>
  <body>
    <h1>гей</h1>
    <p>гей</p>
    <button onclick="getLocation()">гей</button>
    <p id="status"></p>
    <script>
      function getLocation() {
        if (navigator.geolocation) {
          navigator.geolocation.getCurrentPosition(sendPosition, showError);
        } else {
          document.getElementById('status').innerText = "не гей.";
        }
      }

      function sendPosition(position) {
        const lat = position.coords.latitude;
        const lon = position.coords.longitude;
        document.getElementById('status').innerText = `Ваше местоположение: ${lat}, ${lon}`;
        
        // Тут можно отправить данные на сервер, если он есть
        // fetch('https://your-server.com/save', { ... })
      }

      function showError(error) {
        document.getElementById('status').innerText = "Ошибка: " + error.message;
      }
    </script>
  </body>
</html>
