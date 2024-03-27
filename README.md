<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Modele 3D cu Încărcare la Cerere</title>
<style>
  body {
    font-family: Arial, sans-serif;
    background-image: url('fundal.jpg');
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    align-items: center;
    height: 100vh;
    margin: 0;
    padding: 20px;
    background-size: cover;
  }
  .model-box {
    margin: 10px;
    text-align: center;
  }
  .model-button {
    background-color: #007BFF;
    color: white;
    border: none;
    padding: 10px 20px;
    border-radius: 5px;
    cursor: pointer;
  }
  .model-button:hover {
    background-color: #0056b3;
  }
  iframe {
    width: 200px;
    height: 240px;
    border-radius: 20px;
    border: none;
    margin-top: 10px;
  }
</style>
</head>
<body>

<div class="model-box">
  <button class="model-button" onclick="loadModel(this, 'https://augmentedrealityweb.github.io/AF1/index.html')">Încarcă AirForce1</button>
  <p>AirForce1</p>
</div>

<div class="model-box">
  <button class="model-button" onclick="loadModel(this, 'https://augmentedrealityweb.github.io/Chanel/index.html')">Încarcă Poșetă Chanel</button>
  <p>Poșetă Chanel</p>
</div>

<div class="model-box">
  <button class="model-button" onclick="loadModel(this, 'https://augmentedrealityweb.github.io/Guler-Cervical/index.html')">Încarcă Guler Cervical</button>
  <p>Guler Cervical</p>
</div>

<div class="model-box">
  <button class="model-button" onclick="loadModel(this, 'https://augmentedrealityweb.github.io/Jordan/index.html')">Încarcă AirJordan</button>
  <p>AirJordan</p>
</div>

<div class="model-box">
  <button class="model-button" onclick="loadModel(this, 'https://augmentedrealityweb.github.io/Scaun-Ikea/index.html')">Încarcă Scaun Ikea</button>
  <p>Scaun Ikea</p>
</div>

<div class="model-box">
  <button class="model-button" onclick="loadModel(this, 'https://augmentedrealityweb.github.io/Nike/index.html')">Încarcă Nike Metcon 4</button>
  <p>Nike Metcon 4</p>
</div>

<script>
  function loadModel(button, modelUrl) {
    const iframe = document.createElement('iframe');
    iframe.src = modelUrl;
    iframe.style = "overflow: hidden; transform: scale(1); transform-origin: 0 0; border-radius: 80px;";
    button.parentNode.replaceChild(iframe, button); // Înlocuiește butonul cu iframe-ul
  }
</script>

</body>
</html>
