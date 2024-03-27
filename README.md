<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Swipe pentru Modele 3D</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-image: url('fundal.jpg');
            background-size: cover;
            background-position: center;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
        }
        .swipe-container {
            width: 200px; /* Lățimea iframe-ului */
            height: 240px; /* Înălțimea iframe-ului */
            overflow: hidden;
            position: relative;
            border-radius: 80px;
        }
        iframe {
            width: 200px;
            height: 240px;
            border: none;
            border-radius: 80px;
        }
    </style>
</head>
<body>

<div class="swipe-container" id="swipe-container"></div>

<script>
    const modelUrls = [
        "https://augmentedrealityweb.github.io/AF1/index.html",
        "https://augmentedrealityweb.github.io/Chanel/index.html",
        "https://augmentedrealityweb.github.io/Guler-Cervical/index.html",
        "https://augmentedrealityweb.github.io/Jordan/index.html",
        "https://augmentedrealityweb.github.io/Scaun-Ikea/index.html",
        "https://augmentedrealityweb.github.io/Nike/index.html"
    ];
    let currentIndex = 0;

    function loadModel(index) {
        const container = document.getElementById('swipe-container');
        container.innerHTML = ''; // Golește containerul
        const iframe = document.createElement('iframe');
        iframe.src = modelUrls[index];
        container.appendChild(iframe);
    }

    function nextModel() {
        currentIndex = (currentIndex + 1) % modelUrls.length; // Treci la următorul model
        loadModel(currentIndex);
    }

    function prevModel() {
        currentIndex = (currentIndex - 1 + modelUrls.length) % modelUrls.length; // Treci la modelul precedent
        loadModel(currentIndex);
    }

    document.getElementById('swipe-container').addEventListener('touchstart', handleTouchStart, false);        
    document.getElementById('swipe-container').addEventListener('touchmove', handleTouchMove, false);

    let x1 = null;
    let y1 = null;

    function handleTouchStart(evt) {
        const firstTouch = evt.touches[0];                                      
        x1 = firstTouch.clientX;                                      
        y1 = firstTouch.clientY;                                      
    };                                                

    function handleTouchMove(evt) {
        if (!x1 || !y1) {
            return false;
        }

        let x2 = evt.touches[0].clientX;
        let y2 = evt.touches[0].clientY;

        let xDiff = x2 - x1;
        let yDiff = y2 - y1;

        if (Math.abs(xDiff) > Math.abs(yDiff)) {/*most significant*/
            if (xDiff > 0) {
                prevModel(); /* swipe right */
            } else {
                nextModel(); /* swipe left */
            }                       
        } 
        /* reset values */
        x1 = null;
        y1 = null;                                             
    };

    loadModel(currentIndex); // Încarcă primul model la încărcarea paginii
</script>
</body>
