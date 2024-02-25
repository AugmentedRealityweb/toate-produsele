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
        .image-link {
            display: flex;
            flex-direction: column;
            align-items: center;
            margin: 20px;
        }
        img {
            width: 200px; /* Sau orice altă dimensiune */
            height: auto;
            border-radius: 10px; /* Opțional, pentru colțuri rotunjite */
            transition: transform 0.2s; /* Animație pentru efect de hover */
        }
        img:hover {
            transform: scale(1.05); /* Mărește imaginea puțin când utilizatorul trece cu mouse-ul peste */
        }
        .image-text {
            margin-top: 10px;
            text-align: center;
            color: white; /* Schimbă culoarea textului dacă este necesar pentru a se potrivi cu fundalul */
            font-size: 16px; /* Ajustează mărimea textului după preferințe */
        }
    </style>
</head>
<body>

<div class="image-link">
    <a href="https://augmentedrealityweb.github.io/Produse/">
        <img src="AirForce 1.jpg" alt="AirForce 1">
    </a>
    <div class="image-text">Încălțăminte (apasă pentru modele 3D)</div>
</div>

<div class="image-link">
    <a href="https://augmentedrealityweb.github.io/Guler-Cervical/">
        <img src="guler.jpg" alt="Guler">
    </a>
    <div class="image-text">Guler Cervical (apasă pentru modele 3D)</div>
</div>

<!-- Aici începe noul bloc div adăugat -->
<div class="image-link">
    <a href="https://augmentedrealityweb.github.io/Noodle/">
        <img src="poza.jpg" alt="Noodle Pack">
    </a>
    <div class="image-text">Noodle Pack (apasă pentru model 3D)</div>
</div>
<!-- Aici se termină noul bloc div adăugat -->

</body>
</html>
