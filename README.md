<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Modele 3D</title>
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
            align-items: center;
            height: 100vh;
        }
        .models-container {
            display: flex;
            flex-wrap: wrap;
            justify-content: space-around;
            width: 660px; /* Ajustează această lățime în funcție de nevoile tale */
        }
        .model {
            margin: 10px;
            text-align: center;
        }
        .model-name {
            margin-top: 5px;
            color: white;
        }
    </style>
</head>
<body>

<div class="models-container">
    <div class="model">
        <iframe src="https://augmentedrealityweb.github.io/AF1/index.html" width="200" height="240" style="overflow: hidden; border: none; transform: scale(1); transform-origin: 0 0; border-radius: 80px;"></iframe>
        <div class="model-name">AirForce1</div>
    </div>
    <div class="model">
        <iframe src="https://augmentedrealityweb.github.io/Chanel/index.html" width="200" height="240" style="overflow: hidden; border: none; transform: scale(1); transform-origin: 0 0; border-radius: 80px;"></iframe>
        <div class="model-name">Poșetă Chanel</div>
    </div>
    <div class="model">
        <iframe src="https://augmentedrealityweb.github.io/Guler-Cervical/index.html" width="200" height="240" style="overflow: hidden; border: none; transform: scale(1); transform-origin: 0 0; border-radius: 80px;"></iframe>
        <div class="model-name">Guler Cervical</div>
    </div>
    <div class="model">
        <iframe src="https://augmentedrealityweb.github.io/Jordan/index.html" width="200" height="240" style="overflow: hidden; border: none; transform: scale(1); transform-origin: 0 0; border-radius: 80px;"></iframe>
        <div class="model-name">AirJordan</div>
    </div>
    <div class="model">
        <iframe src="https://augmentedrealityweb.github.io/Scaun-Ikea/index.html" width="200" height="240" style="overflow: hidden; border: none; transform: scale(1); transform-origin: 0 0; border-radius: 80px;"></iframe>
        <div class="model-name">Scaun Ikea</div>
    </div>
    <div class="model">
        <iframe src="https://augmentedrealityweb.github.io/Nike/index.html" width="200" height="240" style="overflow: hidden; border: none; transform: scale(1); transform-origin: 0 0; border-radius: 80px;"></iframe>
        <div class="model-name">Nike Metcon 4</div>
    </div>
</div>
</body>
