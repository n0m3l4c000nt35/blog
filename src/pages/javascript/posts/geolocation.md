---
layout: ../../../layouts/BlogLayout.astro
title: Geolocation
---

# Geolocation

```javascript
function successCallback(position) {
  // Log the position object
  console.log(`Position: ${JSON.stringify(position)}`);
  // Log the timestamp
  console.log(`Timestamp: ${position.timestamp}`);
  // Log the coordinates
  console.log(`Coords: ${JSON.stringify(position.coords)}`);
  // Log the accuracy
  console.log(`Accuracy: ${position.coords.accuracy}`);
  // Log the altitude
  console.log(`Altitude: ${position.coords.altitude}`);
  // Log the altitude accuracy
  console.log(`Altitude Accuracy: ${position.coords.altitudeAccuracy}`);
  // Log the heading
  console.log(`Heading: ${position.coords.heading}`);
  // Log the latitude
  console.log(`Latitude: ${position.coords.latitude}`);
  // Log the longitude
  console.log(`Longitude: ${position.coords.longitude}`);
  // Log the speed
  console.log(`Speed: ${position.coords.speed}`);
}

function errorCallback(error) {
  console.error(`Error: ${error.message}`);
}

const options = {
  enableHighAccuracy: true,
  timeout: 5000,
  maximumAge: 0,
};

navigator.geolocation.getCurrentPosition(
  successCallback,
  errorCallback,
  options
);
```

<hr>

<p class="link-back-container">
  <a class="link-back" href="/blog/javascript">Volver</a>
</p>

<style>
  .link-back-container {
    margin: 0;
  }

  .link-back {
    color: var(--color-text);
    text-decoration: none;
    cursor: pointer;
  }

  .link-back:hover {
    color: crimson
  }

  pre code {
    background: #232136;
    color: #fff;
    border-radius: 8px;
    padding: 1rem 1.2rem;
    display: block;
    font-size: 1.05rem;
    font-family: 'Fira Mono', 'Consolas', 'Menlo', monospace;
    line-height: 1.6;
    box-shadow: 0 2px 8px rgba(0,0,0,0.04);
    overflow-x: auto;
  }

  pre code:hover {
    background: #343152ff;
  }
  
  pre {
    background: #232136;
    border-radius: 8px;
    margin: 1.2rem 0;
    padding: 0;
    box-shadow: 0 2px 8px rgba(0,0,0,0.04);
    overflow-x: auto;
  }
</style>
