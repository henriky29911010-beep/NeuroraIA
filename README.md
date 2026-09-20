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
