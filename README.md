# index.html
<html>
  <head>
    <script src="https://ajax.googleapis.com"></script>
  </head>
  <body>
    <h2>IP Address Logger & Verifier</h2>
    <div>
      <p>IP Address: <span id="ip"></span></p>
      <p>ISP: <span id="isp"></span></p>
      <p>Country: <span id="country"></span></p>
      <p>Region: <span id="region"></span></p>
      <p>City: <span id="city"></span></p>
      <p>ZIP Code: <span id="zip"></span></p>
      <p>Latitude: <span id="lat"></span></p>
      <p>Longitude: <span id="lon"></span></p>
      <p>Timezone: <span id="timezone"></span></p>
    </div>
    <script>
      // Fetch IP information from the API
      fetch('https://ipapi.co/json/')
        .then(response => response.json())
        .then(data => {
          // Populate HTML elements with the fetched data
          document.getElementById('ip').textContent = data.ip;
          document.getElementById('isp').textContent = data.org;
          document.getElementById('country').textContent = data.country_name;
          document.getElementById('region').textContent = data.region;
          document.getElementById('city').textContent = data.city;
          document.getElementById('zip').textContent = data.postal;
          document.getElementById('lat').textContent = data.latitude;
          document.getElementById('lon').textContent = data.longitude;
          document.getElementById('timezone').textContent = data.timezone;
        })
        .catch(error => {
          console.error('Error fetching IP information:', error);
        });
    </script>
  </body>
</html>
