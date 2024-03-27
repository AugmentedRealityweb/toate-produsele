<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Navigare Modele 3D</title>
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
            display: flex;
            justify-content: center;
            align-items: center;
            gap: 10px;
        }
        iframe {
            width: 200px;
            height: 240px;
            border: none;
            border-radius: 10px;
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
    let currentGroupIndex = 0;
    const modelGroups = [
        ["https://augmentedrealityweb.github.io/AF1/index.html", "https://augmentedrealityweb.github.io/Chanel/index.html"],
        ["https://augmentedrealityweb.github.io/Guler-Cervical/index.html", "https://augmentedrealityweb.github.io/Jordan/index.html"],
        ["https://augmentedrealityweb.github.io/Scaun-Ikea/index.html", "https://augmentedrealityweb.github.io/Nike/index.html"]
    ];
    const swipeContainer = document.getElementById('swipe-container');

    function loadModelGroup(groupIndex) {
        swipeContainer.innerHTML = ''; // Clear the container
        modelGroups[groupIndex].forEach(modelUrl => {
            const iframe = document.createElement('iframe');
            iframe.src = modelUrl;
            swipeContainer.appendChild(iframe);
        });
    }

    loadModelGroup(currentGroupIndex); // Load the first group initially

    document.getElementById('next-button').addEventListener('click', function() {
        if (currentGroupIndex < modelGroups.length - 1) {
            currentGroupIndex++;
            loadModelGroup(currentGroupIndex);
        }
    });

    document.getElementById('prev-button').addEventListener('click', function() {
        if (currentGroupIndex > 0) {
            currentGroupIndex--;
            loadModelGroup(currentGroupIndex);
        }
    });
});
</script>
</body>
