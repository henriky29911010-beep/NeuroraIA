# NeuroraIA
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>Neurora</title>

    <link rel="stylesheet" href="style.css">
</head>

<body>

    <div class="app">

        <!-- Barra lateral -->
        <aside class="sidebar">

            <div class="logo">
                <div class="logo-icon">N</div>
                <span>Neurora</span>
            </div>

            <button class="new-chat" id="newChat">
                ＋ Nova conversa
            </button>

            <div class="history">

                <h3>Conversas</h3>

                <div id="conversationList"></div>

            </div>

            <div class="sidebar-bottom">

                <button id="darkMode">
                    🌙 Modo escuro
                </button>

                <button>
                    ⚙️ Configurações
                </button>

            </div>

        </aside>


        <!-- Área principal -->
        <main class="main">

            <!-- Cabeçalho -->
            <header class="topbar">

                <div class="mobile-logo">
                    <div class="logo-icon">N</div>
                    <strong>Neurora</strong>
                </div>

                <div class="status">
                    <span class="status-dot"></span>
                    Neurora online
                </div>

            </header>


            <!-- Área do chat -->
            <section class="chat">

                <!-- Tela inicial -->
                <div class="welcome" id="welcome">

                    <div class="neurora-icon">
                        ✦
                    </div>

                    <h1>Olá! Eu sou a Neurora.</h1>

                    <p>
                        Sua assistente de inteligência artificial.
                        Como posso ajudar você?
                    </p>

                    <div class="suggestions">

                        <button class="suggestion">
                            💡 Explique um assunto para mim
                        </button>

                        <button class="suggestion">
                            💻 Ajude-me a programar
                        </button>

                        <button class="suggestion">
                            ✍️ Ajude-me a escrever
                        </button>

                    </div>

                </div>


                <!-- Mensagens -->
                <div class="messages" id="messages"></div>

            </section>


            <!-- Área de entrada -->
            <footer class="input-area">

                <div class="input-container">

                    <button class="attach" title="Anexar arquivo">
                        📎
                    </button>

                    <textarea
                        id="messageInput"
                        placeholder="Converse com a Neurora..."
                        rows="1">
                    </textarea>

                    <button
                        class="voice"
                        id="voiceButton"
                        title="Usar voz">
                        🎙️
                    </button>

                    <button
                        class="send"
                        id="sendButton"
                        title="Enviar">
                        ➤
                    </button>

                </div>

                <p class="disclaimer">
                    A Neurora pode cometer erros. Verifique informações importantes.
                </p>

            </footer>

        </main>

    </div>

    <script src="script.js"></script>

</body>
</html>
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

:root {
    --background: #ffffff;
    --sidebar: #f7f7f8;
    --text: #202123;
    --secondary: #6b7280;
    --border: #e5e7eb;
    --primary: #635bff;
    --primary-hover: #5148e5;
    --message: #f4f4f5;
}

body {
    font-family: Arial, Helvetica, sans-serif;
    background: var(--background);
    color: var(--text);
    height: 100vh;
    overflow: hidden;
}

button {
    font-family: inherit;
    cursor: pointer;
    border: none;
}

.app {
    display: flex;
    height: 100vh;
}


/* SIDEBAR */

.sidebar {
    width: 270px;
    background: var(--sidebar);
    border-right: 1px solid var(--border);
    display: flex;
    flex-direction: column;
    padding: 18px;
}

.logo {
    display: flex;
    align-items: center;
    gap: 10px;
    font-size: 21px;
    font-weight: bold;
    margin-bottom: 25px;
}

.logo-icon {
    width: 38px;
    height: 38px;
    border-radius: 12px;
    background: var(--primary);
    color: white;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 21px;
    font-weight: bold;
}

.new-chat {
    width: 100%;
    padding: 12px;
    background: var(--primary);
    color: white;
    border-radius: 9px;
    font-size: 14px;
    transition: 0.2s;
}

.new-chat:hover {
    background: var(--primary-hover);
}

.history {
    margin-top: 25px;
    flex: 1;
    overflow-y: auto;
}

.history h3 {
    color: var(--secondary);
    font-size: 12px;
    text-transform: uppercase;
    margin-bottom: 10px;
}

.history-item {
    padding: 10px;
    border-radius: 8px;
    font-size: 14px;
    margin-bottom: 4px;
    cursor: pointer;
}

.history-item:hover {
    background: #e9e9eb;
}

.sidebar-bottom {
    border-top: 1px solid var(--border);
    padding-top: 12px;
}

.sidebar-bottom button {
    width: 100%;
    padding: 11px;
    background: transparent;
    text-align: left;
    border-radius: 8px;
    color: var(--text);
}

.sidebar-bottom button:hover {
    background: #e9e9eb;
}


/* MAIN */

.main {
    flex: 1;
    display: flex;
    flex-direction: column;
    min-width: 0;
}

.topbar {
    height: 60px;
    border-bottom: 1px solid var(--border);
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 0 25px;
}

.mobile-logo {
    display: flex;
    align-items: center;
    gap: 8px;
}

.mobile-logo .logo-icon {
    width: 32px;
    height: 32px;
    font-size: 17px;
}

.status {
    font-size: 13px;
    color: var(--secondary);
}

.status-dot {
    display: inline-block;
    width: 8px;
    height: 8px;
    background: #22c55e;
    border-radius: 50%;
    margin-right: 5px;
}


/* CHAT */

.chat {
    flex: 1;
    overflow-y: auto;
    position: relative;
}

.welcome {
    max-width: 750px;
    margin: auto;
    padding: 80px 20px;
    text-align: center;
}

.neurora-icon {
    width: 70px;
    height: 70px;
    margin: auto;
    display: flex;
    align-items: center;
    justify-content: center;
    border-radius: 22px;
    background: var(--primary);
    color: white;
    font-size: 35px;
    margin-bottom: 25px;
}

.welcome h1 {
    font-size: 32px;
    margin-bottom: 12px;
}

.welcome p {
    color: var(--secondary);
    line-height: 1.6;
}

.suggestions {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 12px;
    margin-top: 35px;
}

.suggestion {
    padding: 16px;
    background: var(--sidebar);
    border: 1px solid var(--border);
    border-radius: 12px;
    text-align: left;
    color: var(--text);
}

.suggestion:hover {
    border-color: var(--primary);
}


/* MENSAGENS */

.messages {
    max-width: 850px;
    margin: auto;
    padding: 30px 20px;
}

.message {
    display: flex;
    gap: 14px;
    margin-bottom: 25px;
    line-height: 1.6;
}

.message-avatar {
    min-width: 36px;
    height: 36px;
    border-radius: 10px;
    display: flex;
    align-items: center;
    justify-content: center;
    background: var(--primary);
    color: white;
    font-weight: bold;
}

.user .message-avatar {
    background: #333;
}

.message-content {
    padding-top: 5px;
    white-space: pre-wrap;
}

.user-message {
    background: var(--message);
    padding: 12px 15px;
    border-radius: 12px;
}


/* INPUT */

.input-area {
    padding: 15px 20px 20px;
}

.input-container {
    max-width: 850px;
    margin: auto;
    display: flex;
    align-items: flex-end;
    gap: 8px;
    padding: 8px;
    border: 1px solid var(--border);
    border-radius: 16px;
    box-shadow: 0 3px 15px rgba(0,0,0,0.06);
    background: white;
}

textarea {
    flex: 1;
    border: none;
    outline: none;
    resize: none;
    font-size: 15px;
    padding: 10px;
    max-height: 150px;
    background: transparent;
}

.attach,
.voice,
.send {
    width: 40px;
    height: 40px;
    border-radius: 10px;
    background: transparent;
    font-size: 18px;
}

.attach:hover,
.voice:hover {
    background: #f0f0f0;
}

.send {
    background: var(--primary);
    color: white;
}

.send:hover {
    background: var(--primary-hover);
}

.disclaimer {
    text-align: center;
    color: var(--secondary);
    font-size: 11px;
    margin-top: 8px;
}


/* RESPONSIVO */

@media (max-width: 700px) {

    .sidebar {
        display: none;
    }

    .welcome {
        padding-top: 60px;
    }

    .welcome h1 {
        font-size: 26px;
    }

    .suggestions {
        grid-template-columns: 1fr;
    }

    .topbar {
        padding: 0 15px;
    }

    .input-area {
        padding: 10px;
    }
}
const messageInput = document.getElementById("messageInput");
const sendButton = document.getElementById("sendButton");
const messages = document.getElementById("messages");
const welcome = document.getElementById("welcome");
const newChat = document.getElementById("newChat");
const conversationList = document.getElementById("conversationList");
const darkMode = document.getElementById("darkMode");

let conversations = [];


/* ENVIAR MENSAGEM */

function sendMessage() {

    const text = messageInput.value.trim();

    if (!text) {
        return;
    }

    welcome.style.display = "none";

    addMessage(text, "user");

    messageInput.value = "";

    messageInput.style.height = "auto";

    addMessage(
        "Olá! Eu sou a Neurora. Recebi sua mensagem. Em breve meu modelo de inteligência artificial estará conectado aqui.",
        "ai"
    );

    saveConversation(text);
}


/* ADICIONAR MENSAGEM */

function addMessage(text, type) {

    const message = document.createElement("div");

    message.className = `message ${type}`;

    const avatar = document.createElement("div");

    avatar.className = "message-avatar";

    avatar.textContent = type === "user" ? "Você" : "N";

    const content = document.createElement("div");

    content.className = "message-content";

    if (type === "user") {
        content.classList.add("user-message");
    }

    content.textContent = text;

    message.appendChild(avatar);
    message.appendChild(content);

    messages.appendChild(message);

    messages.scrollTop = messages.scrollHeight;
}


/* BOTÃO ENVIAR */

sendButton.addEventListener("click", sendMessage);


/* ENTER PARA ENVIAR */

messageInput.addEventListener("keydown", function(event) {

    if (event.key === "Enter" && !event.shiftKey) {

        event.preventDefault();

        sendMessage();
    }

});


/* AUMENTAR TEXTAREA */

messageInput.addEventListener("input", function() {

    this.style.height = "auto";

    this.style.height = this.scrollHeight + "px";

});


/* NOVA CONVERSA */

newChat.addEventListener("click", function() {

    messages.innerHTML = "";

    welcome.style.display = "block";

    messageInput.value = "";

});


/* HISTÓRICO */

function saveConversation(text) {

    conversations.push({
        title: text.substring(0, 30),
        date: new Date().toLocaleDateString()
    });

    updateHistory();
}


function updateHistory() {

    conversationList.innerHTML = "";

    conversations.slice().reverse().forEach(function(conversation) {

        const item = document.createElement("div");

        item.className = "history-item";

        item.textContent = "💬 " + conversation.title;
                                                                            [README.md](https://github.com/user-attachments/files/32435884/README.md)
            
        conversationList.appendChild(item);

    });

}


/* MODO ESCURO */

darkMode.addEventListener("click", function() {

    document.body.classList.toggle("dark");

});
    
