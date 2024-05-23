<html lang="ro">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Swipe pentru Modele 3D</title>
  <style>
    body {
      margin: 0;
      padding: 0;
      display: flex;
      align-items: center;
      justify-content: center;
      height: 100vh;
      background-color: #f0f0f0;
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

    #chatbot-iframe {
      width: 350px; /* Adjust as needed */
      height: 500px; /* Adjust as needed */
      position: fixed;
      bottom: 10px;
      right: 10px;
      border: none;
      border-radius: 20px;
      box-shadow: 0 0 0px rgba(0, 0, 0, 0.1);
    }
  </style>
</head>
<body>
  <iframe src="https://steli.vercel.app" title="Chatbot"></iframe>

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
