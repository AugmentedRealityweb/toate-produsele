<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Modele AR Optimizate</title>
<style>
  body {
    margin: 0;
    padding: 0;
    font-family: Arial, sans-serif;
    background-image: url('fundal.jpg');
    background-size: cover;
    background-position: center;
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
    height: 100vh;
  }
  .model-container {
    width: 200px;
    margin: 10px;
    text-align: center;
  }
  iframe {
    display: none;
    width: 200px;
    height: 240px;
    overflow: hidden;
    border: none;
    transform: scale(1);
    transform-origin: 0 0;
    margin-top: 10px;
    border-radius: 80px;
  }
  .activate-model {
    display: block;
    margin: 0 auto 10px auto;
    padding: 10px 20px;
    background-color: #007BFF;
    color: white;
    border: none;
    border-radius: 20px;
    cursor: pointer;
  }
</style>
</head>
<body>

<div class="model-container">
  <button class="activate-model" data-model-id="AirForce1">Activează AirForce1</button>
  <div id="AirForce1" style="display:none;">
    <iframe src="https://augmentedrealityweb.github.io/AF1/index.html"></iframe>
  </div>
  AirForce1
</div>

<div class="model-container">
  <button class="activate-model" data-model-id="Chanel">Activează Poșetă Chanel</button>
  <div id="Chanel" style="display:none;">
    <iframe src="https://augmentedrealityweb.github.io/Chanel/index.html"></iframe>
  </div>
  Poșetă Chanel
</div>

<div class="model-container">
  <button class="activate-model" data-model-id="GulerCervical">Activează Guler Cervical</button>
  <div id="GulerCervical" style="display:none;">
    <iframe src="https://augmentedrealityweb.github.io/Guler-Cervical/index.html"></iframe>
  </div>
  Guler Cervical
</div>

<div class="model-container">
  <button class="activate-model" data-model-id="AirJordan">Activează AirJordan</button>
  <div id="AirJordan" style="display:none;">
    <iframe src="https://augmentedrealityweb.github.io/Jordan/index.html"></iframe>
  </div>
  AirJordan
</div>

<div class="model-container">
  <button class="activate-model" data-model-id="ScaunIkea">Activează Scaun Ikea</button>
  <div id="ScaunIkea" style="display:none;">
    <iframe src="https://augmentedrealityweb.github.io/Scaun-Ikea/index.html"></iframe>
  </div>
  Scaun Ikea
</div>

<div class="model-container">
  <button class="activate-model" data-model-id="NikeMetcon4">Activează Nike Metcon 4</button>
  <div id="NikeMetcon4" style="display:none;">
    <iframe src="https://augmentedrealityweb.github.io/Nike/index.html"></iframe>
  </div>
  Nike Metcon 4
</div>

<script>
  document.addEventListener('DOMContentLoaded', function () {
    document.querySelectorAll('.activate-model').forEach(button => {
      button.addEventListener('click', function () {
        const modelId = this.getAttribute('data-model-id');
        const modelContainer = document.querySelector(`#${modelId}`);
        if (modelContainer.style.display === 'none') {
          modelContainer.style.display = 'block';
        } else {
          modelContainer.style.display = 'none';
        }
      });
    });
  });
</script>

</body>
