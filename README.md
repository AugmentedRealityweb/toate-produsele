<!DOCTYPE html>
<html lang="ro">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Chatbot și Modele 3D</title>
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
            flex-direction: column;
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
        #chatbox {
            width: 300px;
            height: 400px;
            border: 1px solid #ccc;
            padding: 10px;
            overflow-y: scroll;
            background-color: white;
            margin-top: 20px;
            border-radius: 10px;
            box-shadow: 0 4px 8px rgba(0,0,0,0.1);
        }
        #userInput {
            width: calc(100% - 20px);
            padding: 10px;
            margin-top: 10px;
            border-radius: 5px;
            border: 1px solid #ccc;
        }
        .message {
            margin: 10px 0;
        }
        .user-message {
            text-align: right;
        }
        .bot-message {
            text-align: left;
        }
        .message p {
            display: inline-block;
            padding: 10px;
            border-radius: 10px;
            max-width: 80%;
        }
        .user-message p {
            background-color: #007BFF;
            color: white;
        }
        .bot-message p {
            background-color: #f1f1f1;
            color: black;
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

<div id="chatbox"></div>
<input type="text" id="userInput" placeholder="Type your message here..." />
<button onclick="sendMessage()">Send</button>

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

async function sendMessage() {
    const userInput = document.getElementById('userInput').value;
    const response = await fetch('https://7a33e74f-aec9-4287-b712-b754d5384964-00-2qz0sbny3vwzg.kirk.replit.dev/webhook', {
        method: 'POST',
        headers: { 'Content-Type': 'application/json' },
        body: JSON.stringify({ message: userInput })
    });
    const data = await response.json();
    document.getElementById('chatbox').innerHTML += `<div class="message user-message"><p>${userInput}</p></div>`;
    document.getElementById('chatbox').innerHTML += `<div class="message bot-message"><p>${data.fulfillmentText}</p></div>`;
    document.getElementById('userInput').value = '';
    document.getElementById('chatbox').scrollTop = document.getElementById('chatbox').scrollHeight;
}
</script>
</body>
</html>
