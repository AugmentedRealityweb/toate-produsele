<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Modele AR Showcase</title>
    <style>
        body {
            margin: 0;
            padding: 0;
            background-image: url('fundal.jpg');
            background-size: cover;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            height: 100vh;
        }
        .images-container {
            display: flex;
            flex-wrap: wrap;
            justify-content: center; /* Centrează modelele */
            width: 80%;
            max-width: 1200px; /* Ajustează după preferințe */
        }
        .image-link {
            display: flex;
            flex-direction: column;
            align-items: center;
            margin: 20px;
            flex-basis: calc(33.333% - 50px); /* 3 pe rând, ajustează marja */
        }
        img {
            width: 100%;
            height: auto;
            border-radius: 10px;
            transition: transform 0.2s;
        }
        img:hover {
            transform: scale(1.05);
        }
        .image-text {
            margin-top: 10px;
            text-align: center;
            color: white;
            font-size: 13px; /* Ajustează după preferințe */
        }   
        /* Media Queries */
        @media (max-width: 768px) {
            .image-link {
                flex-basis: calc(50% - 40px); /* 2 pe rând pentru ecrane mai mici */
            }
            .image-text {
                font-size: 14px; /* Text mai mic pentru ecrane mai mici */
            }
        }   
        @media (max-width: 270px) {
            .image-link {
                flex-basis: 100%; /* 1 pe rând pentru telefoane */
                margin: 10px 0; /* Reducem marja pentru telefoane */
            }
            .image-text {
                font-size: 10px; /* Text și mai mic pentru telefoane */
            }
        }
    </style>
</head>
<body>
<div class="images-container">
    <div class="image-link">
        <a href="https://augmentedrealityweb.github.io/Jordan/">
            <img src="pozaJordan.jpg" alt="pozaJordan">
        </a>
        <div class="image-text">Jordan Air 200E (apasă pentru model 3D)</div>
    </div>
    <div class="image-link">
        <a href="https://augmentedrealityweb.github.io/Nike/">
            <img src="pozaNike.jpg" alt="pozaNike">
        </a>
        <div class="image-text">Nike Free Metcon (apasă pentru model 3D)</div>
    </div>

    <div class="image-link">
        <a href="https://augmentedrealityweb.github.io/AF1/">
            <img src="AirForce 1.jpg" alt="AirForce 1">
        </a>
        <div class="image-text">Nike AF1 (apasă pentru model 3D)</div>
    </div>
    <div class="image-link">
        <a href="https://augmentedrealityweb.github.io/Guler-Cervical/">
            <img src="guler.jpg" alt="Guler">
        </a>
        <div class="image-text">Guler Cervical (apasă pentru model 3D)</div>
    </div>

    <div class="image-link">
        <a href="https://augmentedrealityweb.github.io/Noodle/">
            <img src="poza.jpg" alt="Noodle Pack">
        </a>
        <div class="image-text">Noodle Pack (apasă pentru model 3D)</div>
    </div>
    <div class="image-link">
        <a href="https://augmentedrealityweb.github.io/Scaun-Ikea/">
            <img src="Scaun.jpg" alt="Scaun Ikea">
        </a>
        <div class="image-text">Scaun Ikea (apasă pentru model 3D)</div>
    </div>
</div>
</body>
</html>
