<!DOCTYPE html>
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
        .chat-widget {
            position: fixed;
            bottom: 20px;
            right: 20px;
            width: 350px; /* Adjust as needed */
            height: 500px; /* Adjust as needed */
            border: 2px solid #0078d7;
            border-radius: 10px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
            overflow: hidden;
            display: flex;
            flex-direction: column;
            background-color: #ffffff;
        }
        .chat-widget-header {
            background-color: #0078d7;
            color: #ffffff;
            padding: 10px;
            text-align: center;
            font-size: 18px;
            font-weight: bold;
        }
        .chat-widget-body {
            flex: 1;
            padding: 10px;
            overflow-y: auto;
            display: flex;
            flex-direction: column;
        }
        .chat-widget-input {
            display: flex;
            border-top: 1px solid #ddd;
            padding: 10px;
        }
        .chat-widget-input input {
            flex: 1;
            padding: 10px;
            border: 1px solid #ddd;
            border-radius: 5px;
            font-size: 16px;
        }
        .chat-widget-input button {
            padding: 10px 15px;
            margin-left: 10px;
            border: none;
            background-color: #0078d7;
            color: #ffffff;
            border-radius: 5px;
            cursor: pointer;
            font-size: 16px;
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

<div class="chat-widget">
    <div class="chat-widget-header">Chat with Us</div>
    <div class="chat-widget-body" id="chat-widget-body">
        <!-- Messages will be displayed here -->
    </div>
    <div class="chat-widget-input">
        <input type="text" id="chat-input" placeholder="Type a message...">
        <button onclick="sendMessage()">Send</button>
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

    // Chatbot functionality
    const chatBody = document.getElementById('chat-widget-body');

    function addMessage(content, sender) {
        const message = document.createElement('div');
        message.style.marginBottom = '10px';
        message.innerHTML = `<strong>${sender}:</strong> ${content}`;
        chatBody.appendChild(message);
        chatBody.scrollTop = chatBody.scrollHeight;
    }

    async function sendMessage() {
        const input = document.getElementById('chat-input');
        const message = input.value.trim();
        if (message === '') return;

        addMessage(message, 'You');
        input.value = '';

        // Endpoint URL al API-ului OpenAI pentru assistant completions
        const apiUrl = 'https://api.openai.com/v1/assistants/asst_KDj6DfoROEc3Wn1TeAW3Zbtu/messages';

        // Cheia API OpenAI
        const apiKey = 'sk-botdetestapi-os1KzH2miGGIKgNvoON3T3BlbkFJlT2nTJbq3PcXh4WMeVvF';

        const response = await fetch(apiUrl, {
            method: 'POST',
            headers: {
                'Content-Type': 'application/json',
                'Authorization': `Bearer ${apiKey}`
            },
            body: JSON.stringify({
                input: message,
                vector_store_id: "vs_g4f0PbUB2LOLYFCgB3501D03"
            }),
        });

        if (response.ok) {
            const data = await response.json();
            const reply = data.message.content.trim();
            addMessage(reply, 'Bot');
        } else {
            const errorText = await response.text();
            addMessage(`Sorry, something went wrong. ${errorText}`, 'Bot');
        }
    }
});
</script>

</body>
</html>
