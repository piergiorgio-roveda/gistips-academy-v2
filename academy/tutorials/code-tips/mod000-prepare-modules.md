# MOD000 - Prepare modules

In your code, you can see in codepen.io Pen editor:

```
var map = L.map('map').setView([51.505, -0.09], 13);

L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
    attribution: '&copy; <a href="https://www.openstreetmap.org/copyright">OpenStreetMap</a> contributors'
}).addTo(map);
```

but if you are in your website, this code is like this:

```
<!DOCTYPE html>
<html>
  <head>

    <title>Quick Start - Leaflet</title>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="shortcut icon" type="image/x-icon" href="docs/images/favicon.ico" />

    <!-- Pen settings External Stylesheets -->
    <link rel="stylesheet" href="https://unpkg.com/leaflet@1.7.1/dist/leaflet.css" />

    <!--Box CSS di codepen.io Pen editor-->
    <style>
      #mapid {
        height: 200px;
      }
    </style>

  </head>
  <body>

    <div id="mapid"></div>

    <!-- Pen settings External Scripts -->
    <script src="https://unpkg.com/leaflet@1.7.1/dist/leaflet.js" ></script>

    <!--Box JS di codepen.io Pen editor-->
    <script>

      var map = L.map('mapid').setView([51.505, -0.09], 13);

      L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
        attribution: '&copy; <a href="https://www.openstreetmap.org/copyright">OpenStreetMap</a> contributors'
      }).addTo(map);

    </script>

  </body>
</html>
```

See this example stand-alone.

{% embed url="https://piergiorgio-roveda.github.io/gistips-academy/gis/tutorials/mod000.html" %}

But the "Box JS di codepen.io Pen editor" can be an "External Scripts". This code can be put in separate Javascript file, then isert as "External Scripts". Also "Box CSS di codepen.io Pen editor" can be put in "External Stylesheets".

Now create:

*
