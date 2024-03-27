<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Swipe între seturi de Modele 3D</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-image: url('fundal.jpg'); /* Aici adaugi imaginea ta de fundal */
            background-size: cover;
            background-position: center;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
        }
        .swipe-container {
            display: flex;
            justify-content: space-between;
            width: 420px; /* Modificat pentru a găzdui două iframe-uri */
            position: relative;
        }
        iframe {
            width: 200px; /* Lățimea unui iframe */
            height: 240px; /* Înălțimea iframe-ului */
            border: none;
            margin: 10px; /* Adaugă spațiu între modele */
        }
        .navigation {
            display: flex;
            justify-content: space-between;
            position: absolute;
            top: 50%;
            width: 100%;
            transform: translateY(-50%);
        }
        .nav-button {
            background: #fff; /* Schimbat pentru vizibilitate */
            border: 1px solid #ccc; /* Adaugă un contur butonului */
            border-radius: 50%; /* Buton circular */
            font-size: 24px;
            cursor: pointer;
            opacity: 0.8;
        }
    </style>
</head>
<body>

<div class="swipe-container" id="swipe-container">
    <div class="navigation">
        <button class="nav-button" id="prev-button">&#10094;</button>
        <button class="nav-button" id="next-button">&#10095;</button>
    </div>
</div>

<script>
document.addEventListener("DOMContentLoaded", function() {
    let currentSet = 0;
    const models = [
        ["https://augmentedrealityweb.github.io/AF1/index.html", "https://augmentedrealityweb.github.io/Chanel/index.html"],
        ["https://augmentedrealityweb.github.io/Guler-Cervical/index.html", "https://augmentedrealityweb.github.io/Jordan/index.html"],
        ["https://augmentedrealityweb.github.io/Scaun-Ikea/index.html", "https://augmentedrealityweb.github.io/Nike/index.html"]
    ];
    const swipeContainer = document.getElementById('swipe-container');

    function loadModels(setIndex) {
        swipeContainer.innerHTML = ''; // Curăță containerul pentru noile modele
        models[setIndex].forEach(modelUrl => {
            const iframe = document.createElement('iframe');
            iframe.src = modelUrl;
            swipeContainer.appendChild(iframe);
        });
        // Readaugă butoanele de navigație
        swipeContainer.innerHTML += '<div class="navigation"><button class="nav-button" id="prev-button">&#10094;</button><button class="nav-button" id="next-button">&#10095;</button></div>';
        addNavigationListeners(); // Reinițializează ascultătorii pentru butoane
    }

    function addNavigationListeners() {
        document.getElementById('next-button').addEventListener('click', function() {
            if (currentSet < models.length - 1) {
                currentSet++;
                loadModels(currentSet);
            }
        });

        document.getElementById('prev-button').addEventListener('click', function() {
            if (currentSet > 0) {
                currentSet--;
                loadModels(currentSet);
            }
        });
    }

    loadModels(currentSet); // Încarcă primul set de modele
});
</script>
</body>
