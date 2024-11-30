<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Aventura Interativa</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <header>
        <h1>Aventura Interativa</h1>
        <p>Escolha sabiamente e descubra seu destino!</p>
    </header>
    <main>
        <section id="story">
            <p>Você está em uma floresta sombria. À sua frente, há dois caminhos:</p>
            <ul>
                <li><button onclick="choosePath('left')">Seguir pela esquerda</button></li>
                <li><button onclick="choosePath('right')">Seguir pela direita</button></li>
            </ul>
        </section>
    </main>
    <footer>
        <p>Desenvolvido por [Seu Nome]</p>
    </footer>
    <script src="script.js"></script>
</body>
</html>
/* Estilo básico */
body {
    font-family: Arial, sans-serif;
    margin: 0;
    padding: 0;
    background-color: #f0f8ff;
    color: #333;
}

/* Cabeçalho */
header {
    background-color: #4caf50;
    color: white;
    text-align: center;
    padding: 1.5rem 0;
}

/* Seção principal */
main {
    padding: 20px;
    max-width: 800px;
    margin: 0 auto;
}

#story {
    background: #fff;
    padding: 20px;
    border-radius: 10px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
    text-align: center;
}

button {
    margin: 10px;
    padding: 10px 20px;
    background-color: #4caf50;
    color: white;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    font-size: 16px;
}

button:hover {
    background-color: #45a049;
}

/* Rodapé */
footer {
    background-color: #333;
    color: white;
    text-align: center;
    padding: 1rem 0;
    margin-top: 20px;
}
function choosePath(choice) {
    const story = document.getElementById('story');
    
    if (choice === 'left') {
        story.innerHTML = `
            <p>Você segue pela esquerda e encontra uma cabana misteriosa.</p>
            <ul>
                <li><button onclick="choosePath('enterCabin')">Entrar na cabana</button></li>
                <li><button onclick="choosePath('runAway')">Correr para longe</button></li>
            </ul>
        `;
    } else if (choice === 'right') {
        story.innerHTML = `
            <p>Você segue pela direita e encontra um rio com uma ponte quebrada.</p>
            <ul>
                <li><button onclick="choosePath('crossRiver')">Tentar atravessar o rio</button></li>
                <li><button onclick="choosePath('goBack')">Voltar para a floresta</button></li>
            </ul>
        `;
    } else if (choice === 'enterCabin') {
        story.innerHTML = `
            <p>Dentro da cabana, você encontra um baú cheio de ouro! Parabéns, você venceu!</p>
            <button onclick="restartGame()">Recomeçar a aventura</button>
        `;
    } else if (choice === 'runAway') {
        story.innerHTML = `
            <p>Você corre, mas tropeça e cai em uma armadilha. Fim de jogo!</p>
            <button onclick="restartGame()">Recomeçar a aventura</button>
        `;
    } else if (choice === 'crossRiver') {
        story.innerHTML = `
            <p>Você tenta atravessar, mas a correnteza te leva embora. Fim de jogo!</p>
            <button onclick="restartGame()">Recomeçar a aventura</button>
        `;
    } else if (choice === 'goBack') {
        story.innerHTML = `
            <p>Você volta para a floresta e encontra o ponto de partida.</p>
            <ul>
                <li><button onclick="choosePath('left')">Seguir pela esquerda</button></li>
                <li><button onclick="choosePath('right')">Seguir pela direita</button></li>
            </ul>
        `;
    }
}

function restartGame() {
    const story = document.getElementById('story');
    story.innerHTML = `
        <p>Você está em uma floresta sombria. À sua frente, há dois caminhos:</p>
        <ul>
            <li><button onclick="choosePath('left')">Seguir pela esquerda</button></li>
            <li><button onclick="choosePath('right')">Seguir pela direita</button></li>
        </ul>
    `;
}
adventure-project/
├── index.html
├── style.css
└── script.js

