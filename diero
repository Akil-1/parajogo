(function() {
    const keyE = 'e'; // Tecla que você quer simular para o primeiro script
    const delayE = 1000; // Intervalo para simular a tecla 'e' em milissegundos
    const keyDelay = 2000; // Intervalo para clicar no botão e simular teclas em milissegundos

    let intervalKeyE, intervalKeys; // Variáveis para armazenar os IDs dos intervalos

    // Função para simular o pressionamento e liberação da tecla 'e'
    function pressKeyE() {
        const eventDown = new KeyboardEvent('keydown', {
            key: keyE,
            code: 'KeyE',
            keyCode: 69,
            which: 69,
            bubbles: true
        });

        const eventUp = new KeyboardEvent('keyup', {
            key: keyE,
            code: 'KeyE',
            keyCode: 69,
            which: 69,
            bubbles: true
        });

        document.dispatchEvent(eventDown);
        document.dispatchEvent(eventUp);
    }

    // Funções para simular pressionamento e liberação de teclas gerais
    function pressKey(key) {
        const event = new KeyboardEvent('keydown', {
            key: key,
            keyCode: key.charCodeAt(0),
            code: 'Digit' + key,
            which: key.charCodeAt(0),
            bubbles: true
        });
        document.dispatchEvent(event);
    }

    function releaseKey(key) {
        const event = new KeyboardEvent('keyup', {
            key: key,
            keyCode: key.charCodeAt(0),
            code: 'Digit' + key,
            which: key.charCodeAt(0),
            bubbles: true
        });
        document.dispatchEvent(event);
    }

    // Função para clicar no botão
    function clickButton() {
        const button = document.querySelector("#wcanvas > div > div > div > div.ButtonComponent");
        if (button) {
            button.click();
        } else {
            console.log("Botão não encontrado!");
        }
    }

    // Configuração dos intervalos
    intervalKeys = setInterval(function() {
        clickButton(); // Clica no botão a cada 2 segundos

        pressKey('1');  // Simula pressionamento da tecla '1'
        setTimeout(function() {
            releaseKey('1'); // Libera a tecla '1' após 2 segundos
        }, 2000);

        // Pressiona e libera a tecla '4' após 3 segundos
        setTimeout(function() {
            pressKey('4');  // Simula pressionamento da tecla '4'
            setTimeout(function() {
                releaseKey('4'); // Libera a tecla '4' após 2 segundos
            }, 2000);
        }, 3000);  // Inicia o pressionamento da tecla '4' após 3 segundos

    }, keyDelay); // Repete o processo a cada 2 segundos

    intervalKeyE = setInterval(pressKeyE, delayE); // Simula a tecla 'e' a cada 1 segundo

    // Função para parar os intervalos
    window.stopScript = function() {
        clearInterval(intervalKeyE); // Para a tecla 'e'
        clearInterval(intervalKeys); // Para as teclas e cliques no botão
        console.log("Script interrompido.");
    };
})();
