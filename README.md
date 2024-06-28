<html lang="ro">
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
            background-image: url('fundal13.jpg');
            background-size: cover;
            background-position: center;
        }
        .swipe-container {
            display: flex;
            flex-direction: column;
            align-items: center;
            width: 200px; /* Adjust this as needed */
            overflow: hidden;
            position: relative;
            margin-left: 17px;
        }
        iframe {
            width: 200px;
            height: 240px;
            border: none;
            border-radius: 30%;
            margin-bottom: 60px; /* Space between models */
        }
        .navigation {
            display: flex;
            justify-content: space-between;
            position: absolute;
            top: calc(50% - 30px);
            width: 100%;
            transform: translateY(-50%);
        }
        .nav-button {
            background-color: #007BFF; /* Bootstrap primary color for reference */
            color: white;
            border: none;
            border-radius: 50%;
            width: 40px;
            height: 40px;
            cursor: pointer;
            opacity: 0.8;
            transition: opacity 0.3s ease;
        }
        .nav-button:hover {
            opacity: 1;
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
        ["https://augmentedrealityweb.github.io/AF1/index.html", "https://augmentedrealityweb.github.io/Nike/index.html"],
        ["https://augmentedrealityweb.github.io/Jordan/index.html", "https://augmentedrealityweb.github.io/Guler-Cervical/index.html"],
        ["https://augmentedrealityweb.github.io/Scaun-Ikea/index.html", "https://augmentedrealityweb.github.io/Chanel/index.html"]
    ];

    function loadModels(setIndex) {
        const swipeContainer = document.getElementById('swipe-container');
        swipeContainer.innerHTML = ''; // Clear the container before loading new models

        // Adding the navigation buttons back to the swipe container
        const navigation = document.createElement('div');
        navigation.className = 'navigation';
        swipeContainer.appendChild(navigation);

        models[setIndex].forEach(modelUrl => {
            const iframe = document.createElement('iframe');
            iframe.src = modelUrl;
            swipeContainer.insertBefore(iframe, navigation); // Insert models before the navigation
        });

        // Re-adding event listeners to the navigation buttons
        const nextButton = document.createElement('button');
        nextButton.className = 'nav-button';
        nextButton.id = 'next-button';
        nextButton.innerHTML = '&#10095;';
        navigation.appendChild(nextButton);

        const prevButton = document.createElement('button');
        prevButton.className = 'nav-button';
        prevButton.id = 'prev-button';
        prevButton.innerHTML = '&#10094;';
        navigation.insertBefore(prevButton, navigation.firstChild);

        // Event listeners for buttons
        nextButton.addEventListener('click', function() {
            if (currentSet === models.length - 1) {
                currentSet = 0; // Reset to the first set of models if at the end
            } else {
                currentSet++; // Otherwise, increment to the next set
            }
            loadModels(currentSet);
        });

        prevButton.addEventListener('click', function() {
            if (currentSet === 0) {
                currentSet = models.length - 1; // Go to the last set of models if at the beginning
            } else {
                currentSet--; // Otherwise, decrement to the previous set
            }
            loadModels(currentSet);
        });
    }
    loadModels(currentSet); // Initial load of models
});
</script>
 <script>!function(window){const host="https://app.heygen.com",url=host+"/guest/streaming-embed?share=eyJxdWFsaXR5IjoiaGlnaCIsImF2YXRhck5hbWUiOiJMaWx5X3B1YmxpY19wcm8xXzIwMjMwNjE0%0D%0AIiwidm9pY2UiOnsidm9pY2VfaWQiOiIyMzJlM2JiMjlmM2I0NWQ2OTVmODczNTAzYWY3MDY4YyJ9%0D%0ALCJwcmV2aWV3SW1nIjoiaHR0cHM6Ly9maWxlcy5oZXlnZW4uYWkvYXZhdGFyL3YzLzUxMjY3YzBm%0D%0AMGYyMDQ1NTE4YThjNjZiYjE3MDliZjJhXzI2NTQvcHJldmlld190YXJnZXQud2VicCIsIm5lZWRS%0D%0AZW1vdmVCYWNrZ3JvdW5kIjp0cnVlLCJ1c2VybmFtZSI6IjU1NmRiNDU2YzA4MTQ2NzZhNzhhY2Rj%0D%0AMGExYzFlYTIxIn0%3D&inIFrame=1",clientWidth=document.body.clientWidth,wrapDiv=document.createElement("div");wrapDiv.id="heygen-streaming-embed";const container=document.createElement("div");container.id="heygen-streaming-container";const stylesheet=document.createElement("style");stylesheet.innerHTML=`\n  #heygen-streaming-embed {\n    z-index: 9999;\n    position: fixed;\n    left: 40px;\n    bottom: 40px;\n    width: 200px;\n    height: 200px;\n    border-radius: 50%;\n    border: 2px solid #fff;\n    box-shadow: 0px 8px 24px 0px rgba(0, 0, 0, 0.12);\n    transition: all linear 0.1s;\n    overflow: hidden;\n\n    opacity: 0;\n    visibility: hidden;\n  }\n  #heygen-streaming-embed.show {\n    opacity: 1;\n    visibility: visible;\n  }\n  #heygen-streaming-embed.expand {\n    ${clientWidth<540?"height: 266px; width: 96%; left: 50%; transform: translateX(-50%);":"height: 366px; width: calc(366px * 16 / 9);"}\n    border: 0;\n    border-radius: 8px;\n  }\n  #heygen-streaming-container {\n    width: 100%;\n    height: 100%;\n  }\n  #heygen-streaming-container iframe {\n    width: 100%;\n    height: 100%;\n    border: 0;\n  }\n  `;const iframe=document.createElement("iframe");iframe.allowFullscreen=!1,iframe.title="Streaming Embed",iframe.role="dialog",iframe.src=url;let visible=!1,initial=!1;window.addEventListener("message",(e=>{e.origin===host&&e.data&&e.data.type&&"streaming-embed"===e.data.type&&("init"===e.data.action?(initial=!0,wrapDiv.classList.toggle("show",initial)):"show"===e.data.action?(visible=!0,wrapDiv.classList.toggle("expand",visible)):"hide"===e.data.action&&(visible=!1,wrapDiv.classList.toggle("expand",visible)))})),container.appendChild(iframe),wrapDiv.appendChild(stylesheet),wrapDiv.appendChild(container),document.body.appendChild(wrapDiv)}(globalThis);</script>
</body>
</html>
