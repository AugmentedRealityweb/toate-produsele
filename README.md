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
            flex-direction: column; /* O coloană cu mai multe rânduri */
            max-height: 720px; /* Ajustează în funcție de înălțimea totală dorită */
        }
        .model-row {
            display: flex;
            justify-content: center; /* Ajustează pentru a centra modelele pe orizontală */
            margin-bottom: 20px; /* Distanța între rânduri */
        }
        .model {
            margin: 0 10px; /* Spațiere între modele */
            text-align: center;
        }
        .model-name {
            color: white;
            margin-top: 5px;
        }
    </style>
</head>
<body>

<div class="models-container">
    <!-- Primul rând -->
    <div class="model-row">
        <div class="model">
            <iframe src="https://augmentedrealityweb.github.io/AF1/index.html" width="200" height="240" style="border: none; border-radius: 80px;"></iframe>
            <div class="model-name">AirForce1</div>
        </div>
        <div class="model">
            <iframe src="https://augmentedrealityweb.github.io/Chanel/index.html" width="200" height="240" style="border: none; border-radius: 80px;"></iframe>
            <div class="model-name">Poșetă Chanel</div>
        </div>
    </div>
    
    <!-- Al doilea rând -->
    <div class="model-row">
        <div class="model">
            <iframe src="https://augmentedrealityweb.github.io/Guler-Cervical/index.html" width="200" height="240" style="border: none; border-radius: 80px;"></iframe>
            <div class="model-name">Guler Cervical</div>
        </div>
        <div class="model">
            <iframe src="https://augmentedrealityweb.github.io/Jordan/index.html" width="200" height="240" style="border: none; border-radius: 80px;"></iframe>
            <div class="model-name">AirJordan</div>
        </div>
    </div>
    
    <!-- Al treilea rând -->
    <div class="model-row">
        <div class="model">
            <iframe src="https://augmentedrealityweb.github.io/Scaun-Ikea/index.html" width="200" height="240" style="border: none; border-radius: 80px;"></iframe>
            <div class="model-name">Scaun Ikea</div>
        </div>
        <div class="model">
            <iframe src="https://augmentedrealityweb.github.io/Nike/index.html" width="200" height="240" style="border: none; border-radius: 80px;"></iframe>
            <div class="model-name">Nike Metcon 4</div>
        </div>
    </div>
</div>
</body>
