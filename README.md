<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>AI Chatbot</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f7f7f7;
            color: #333;
        }
        header {
            background-color: #007bff;
            color: #fff;
            padding: 20px;
            text-align: center;
        }
        h1 {
            margin: 10px 0;
        }
        .chat-container {
            max-width: 800px;
            margin: 20px auto;
            background-color: #fff;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
            padding: 20px;
            overflow-y: auto;
            height: 400px;
        }
        .chat-message {
            margin-bottom: 10px;
        }
        .user-message {
            text-align: right;
            color: #007bff;
        }
        .bot-message {
            text-align: left;
            color: #28a745;
        }
        .input-container {
            max-width: 800px;
            margin: 20px auto;
            padding: 20px;
            background-color: #fff;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }
        input[type="text"] {
            width: 100%;
            padding: 10px;
            border: 1px solid #ccc;
            border-radius: 5px;
        }
        input[type="submit"] {
            background-color: #007bff;
            color: #fff;
            border: none;
            padding: 10px 20px;
            border-radius: 5px;
            cursor: pointer;
        }
    </style>
</head>
<body>

<header>
    <h1>AI Chatbot</h1>
    <p>Welcome to the AI Chatbot! Ask me anything.</p>
</header>

<div class="chat-container" id="chatContainer">
    <!-- Chat messages will be displayed here -->
</div>

<div class="input-container">
    <form id="chatForm">
        <input type="text" id="userInput" placeholder="Type your message here...">
        <input type="submit" value="Send">
    </form>
</div>

<script>
    const chatForm = document.getElementById('chatForm');
    const chatContainer = document.getElementById('chatContainer');

    chatForm.addEventListener('submit', function(event) {
        event.preventDefault();
        const userInput = document.getElementById('userInput').value.trim();
        if (userInput !== '') {
            displayMessage(userInput, 'user');
            // Call function to send user input to the AI chatbot backend and get response
            // For demonstration purposes, let's assume the bot responds immediately
            setTimeout(function() {
                const botResponse = 'This is a response from the AI chatbot.';
                displayMessage(botResponse, 'bot');
            }, 1000);
            document.getElementById('userInput').value = '';
        }
    });

    function displayMessage(message, sender) {
        const messageElement = document.createElement('div');
        messageElement.classList.add('chat-message');
        messageElement.classList.add(sender + '-message');
        messageElement.textContent = message;
        chatContainer.appendChild(messageElement);
        chatContainer.scrollTop = chatContainer.scrollHeight; // Scroll to bottom
    }
</script>

</body>
</html>
