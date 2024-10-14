<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Pedido de Namoro</title>
    <style>
        body {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background-color: #f0f0f0;
            font-family: Arial, sans-serif;
            text-align: center;
        }
        button {
            padding: 10px 20px;
            margin: 10px;
            font-size: 16px;
            cursor: pointer;
        }
    </style>
</head>
<body>
    <div id="message-container">
        <h1 id="message">Quer namorar comigo?</h1>
        <button onclick="response('sim')">Sim</button>
        <button onclick="response('nao')">Não</button>
    </div>

    <script>
        let simCount = 0;

        function response(answer) {
            const messageElement = document.getElementById("message");

            if (answer === 'nao') {
                messageElement.innerText = "Vai namorar sim!";
                return;
            }

            simCount++;
            if (simCount < 5) {
                messageElement.innerText = "Quer namorar comigo?";
            } else {
                messageElement.innerText = "Vejo que você está decidida. Você tem realmente certeza que quer me namorar?";
                showFinalChoices();
            }
        }

        function showFinalChoices() {
            const messageContainer = document.getElementById("message-container");
            messageContainer.innerHTML = `
                <h1 id="message">Você tem realmente certeza que quer me namorar?</h1>
                <button onclick="finalResponse('sim')">Sim</button>
                <button onclick="finalResponse('nao')">Não</button>
            `;
        }

        function finalResponse(answer) {
            const messageElement = document.getElementById("message");
            if (answer === 'sim') {
                messageElement.innerText = "Eu te amo, Sarah!";
            } else {
                messageElement.innerText = "Eu sabia que você não me queria.";
            }
        }
    </script>
</body>
</html>