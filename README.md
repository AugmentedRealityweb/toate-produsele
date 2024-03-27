<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Swipe pentru Modele 3D</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f0f0f0;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
        }
        .swipe-container {
            width: 200px; /* Lățimea iframe-ului */
            height: 240px; /* Înălțimea iframe-ului */
            position: relative;
            overflow: hidden;
            border-radius: 10px;
        }
        iframe {
            width: 100%;
            height: 100%;
            border: none;
        }
        .navigation {
            display: flex;
            justify-content: space-between;
            position: absolute;
            top: 50%;
            left: 0;
            width: 100%;
            transform: translateY(-50%);
        }
        .nav-button {
            background: none;
            border: none;
            font-size: 24px;
            cursor: pointer;
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
    let currentModel = 0;
    const models = [
        "https://augmentedrealityweb.github.io/AF1/index.html",
        "https://augmentedrealityweb.github.io/Chanel/index.html",
        "https://augmentedrealityweb.github.io/Guler-Cervical/index.html",
        "https://augmentedrealityweb.github.io/Jordan/index.html",
        "https://augmentedrealityweb.github.io/Scaun-Ikea/index.html",
        "https://augmentedrealityweb.github.io/Nike/index.html"
    ];
    const swipeContainer = document.getElementById('swipe-container');
    const iframe = document.createElement('iframe');
    iframe.src = models[currentModel];
    swipeContainer.appendChild(iframe);

    function changeModel(newIndex) {
        currentModel = newIndex;
        iframe.src = models[currentModel];
    }

    document.getElementById('next-button').addEventListener('click', function() {
        if (currentModel < models.length - 1) {
            changeModel(currentModel + 1);
        }
    });

    document.getElementById('prev-button').addEventListener('click', function() {
        if (currentModel > 0) {
            changeModel(currentModel - 1);
        }
    });
});
</script>
</body>
