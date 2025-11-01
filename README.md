echo "# Feliz-anivers-rio" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/Coelho7kook/Feliz-anivers-rio.git
git push -u origin main


  <!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Feliz Aniversário, Carol!</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background: #0a0a16;
            color: #f0f0f0;
            min-height: 100vh;
            overflow-x: hidden;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            padding: 20px;
        }

        .universe {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -2;
        }

        .star {
            position: absolute;
            background-color: white;
            border-radius: 50%;
            animation: twinkle 5s infinite;
        }

        .container {
            width: 90%;
            max-width: 800px;
            text-align: center;
            position: relative;
            z-index: 10;
        }

        .welcome-screen {
            background: rgba(15, 15, 35, 0.7);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            padding: 40px 30px;
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.5);
            border: 1px solid rgba(100, 150, 255, 0.3);
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            min-height: 400px;
            position: relative;
            overflow: hidden;
        }

        .welcome-screen::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(100,150,255,0.1) 0%, rgba(0,0,0,0) 70%);
            animation: rotate 20s linear infinite;
            z-index: -1;
        }

        h1 {
            font-size: 3.5rem;
            background: linear-gradient(45deg, #a3d9ff, #ff99cc, #a3d9ff);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            text-shadow: 0 0 20px rgba(163, 217, 255, 0.5);
            margin-bottom: 20px;
            animation: float 6s ease-in-out infinite;
            font-weight: 700;
        }

        .subtitle {
            font-size: 1.4rem;
            color: #cccccc;
            margin-bottom: 30px;
            animation: fadeIn 2s ease-out;
        }

        .warning {
            background: rgba(255, 80, 80, 0.15);
            border: 1px solid rgba(255, 100, 100, 0.4);
            border-radius: 15px;
            padding: 15px;
            margin: 20px 0;
            font-size: 0.95rem;
            color: #ffaaaa;
            max-width: 500px;
            animation: gentlePulse 4s infinite;
            position: relative;
            overflow: hidden;
        }

        .warning::after {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.2), transparent);
            animation: shimmer 3s infinite;
        }

        .start-btn {
            background: linear-gradient(45deg, #4a6fa5, #6d98d4);
            border: none;
            border-radius: 50px;
            color: #ffffff;
            font-size: 1.3rem;
            font-weight: bold;
            padding: 15px 40px;
            margin-top: 20px;
            cursor: pointer;
            transition: all 0.4s ease;
            box-shadow: 0 5px 15px rgba(100, 150, 255, 0.3);
            position: relative;
            overflow: hidden;
        }

        .start-btn::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.3), transparent);
            transition: 0.5s;
        }

        .start-btn:hover {
            transform: translateY(-5px) scale(1.05);
            box-shadow: 0 10px 25px rgba(100, 150, 255, 0.5);
        }

        .start-btn:hover::before {
            left: 100%;
        }

        .content-screen {
            display: none;
            opacity: 0;
            transition: opacity 1s ease;
        }

        .message-container {
            background: rgba(20, 20, 40, 0.7);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            padding: 40px;
            margin: 20px 0;
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.5);
            border: 1px solid rgba(100, 150, 255, 0.3);
            min-height: 350px;
            display: flex;
            flex-direction: column;
            justify-content: center;
            position: relative;
            overflow: hidden;
        }

        .message-container::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(45deg, transparent, rgba(100,150,255,0.05), transparent);
            z-index: -1;
        }

        .message {
            font-size: 1.4rem;
            line-height: 1.7;
            text-align: left;
            min-height: 250px;
            white-space: pre-wrap;
            position: relative;
        }

        .word {
            display: inline-block;
            position: relative;
        }

        .word span {
            display: inline-block;
            position: relative;
        }

        .cursor {
            display: inline-block;
            width: 12px;
            height: 1.5rem;
            background-color: #a3d9ff;
            margin-left: 5px;
            animation: blink 1s infinite;
            vertical-align: middle;
            box-shadow: 0 0 10px #a3d9ff;
        }

        .btn-container {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin-top: 20px;
        }

        .next-btn {
            background: linear-gradient(45deg, #4a6fa5, #6d98d4);
            border: none;
            border-radius: 50px;
            color: #ffffff;
            font-size: 1.2rem;
            font-weight: bold;
            padding: 12px 30px;
            cursor: pointer;
            transition: all 0.4s ease;
            box-shadow: 0 5px 15px rgba(100, 150, 255, 0.3);
            opacity: 0;
            animation: pulse 2s infinite;
            position: relative;
            overflow: hidden;
        }

        .next-btn::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.3), transparent);
            transition: 0.5s;
        }

        .next-btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 8px 20px rgba(100, 150, 255, 0.5);
        }

        .next-btn:hover::before {
            left: 100%;
        }

        .special-btn {
            background: linear-gradient(45deg, #ff6b6b, #ffa36b);
            border: none;
            border-radius: 50px;
            color: #ffffff;
            font-size: 1.2rem;
            font-weight: bold;
            padding: 12px 30px;
            cursor: pointer;
            transition: all 0.4s ease;
            box-shadow: 0 5px 15px rgba(255, 107, 107, 0.3);
            opacity: 0;
            animation: pulse 2s infinite;
            position: relative;
            overflow: hidden;
            margin-top: 20px;
        }

        .special-btn::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.3), transparent);
            transition: 0.5s;
        }

        .special-btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 8px 20px rgba(255, 107, 107, 0.5);
        }

        .special-btn:hover::before {
            left: 100%;
        }

        .music-controls {
            display: flex;
            justify-content: center;
            align-items: center;
            gap: 15px;
            margin-top: 15px;
            opacity: 0;
            animation: fadeIn 2s forwards 2s;
        }

        .music-btn {
            background: rgba(100, 150, 255, 0.2);
            border: 1px solid rgba(100, 150, 255, 0.4);
            border-radius: 50%;
            width: 45px;
            height: 45px;
            color: #a3d9ff;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: all 0.3s ease;
            font-size: 1.2rem;
        }

        .music-btn:hover {
            background: rgba(100, 150, 255, 0.4);
            transform: scale(1.1);
            box-shadow: 0 0 15px rgba(100, 150, 255, 0.5);
        }

        .music-info {
            margin-top: 15px;
            font-style: italic;
            color: #a3d9ff;
            font-size: 1rem;
            opacity: 0;
            animation: fadeIn 2s forwards 2s;
            text-shadow: 0 0 10px rgba(163, 217, 255, 0.5);
        }

        .violao-toggle {
            background: rgba(255, 180, 70, 0.2);
            border: 1px solid rgba(255, 180, 70, 0.4);
            border-radius: 20px;
            color: #ffcc80;
            padding: 8px 15px;
            font-size: 0.9rem;
            cursor: pointer;
            margin-top: 10px;
            transition: all 0.3s ease;
        }

        .violao-toggle:hover {
            background: rgba(255, 180, 70, 0.4);
            box-shadow: 0 0 15px rgba(255, 180, 70, 0.5);
        }

        .progress-container {
            width: 100%;
            height: 6px;
            background-color: rgba(255, 255, 255, 0.1);
            border-radius: 5px;
            margin-top: 20px;
            overflow: hidden;
        }

        .progress-bar {
            height: 100%;
            background: linear-gradient(45deg, #4a6fa5, #6d98d4);
            width: 0%;
            transition: width 0.3s ease;
            box-shadow: 0 0 10px rgba(100, 150, 255, 0.5);
        }

        .page-indicator {
            display: flex;
            justify-content: center;
            margin-top: 20px;
        }

        .dot {
            width: 14px;
            height: 14px;
            border-radius: 50%;
            background-color: rgba(255, 255, 255, 0.3);
            margin: 0 7px;
            transition: all 0.3s ease;
            cursor: pointer;
        }

        .dot.active {
            background-color: #a3d9ff;
            transform: scale(1.3);
            box-shadow: 0 0 10px #a3d9ff;
        }

        .heart {
            color: #ff6699;
            font-size: 1.3rem;
            margin: 0 3px;
            animation: heartbeat 1.5s infinite;
            display: inline-block;
        }

        /* Estilo para a tela de diálogo dos personagens */
        .dialogue-screen {
            display: none;
            opacity: 0;
            transition: opacity 1s ease;
            position: relative;
            width: 100%;
            max-width: 900px;
            height: 600px;
            border-radius: 20px;
            overflow: hidden;
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.5);
        }

        .dialogue-bg {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: url('cloud_tifa_background.jpg') no-repeat center center;
            background-size: cover;
            z-index: -1;
        }

        .dialogue-box {
            position: absolute;
            bottom: 20px;
            left: 20px;
            right: 20px;
            background: rgba(20, 20, 40, 0.85);
            border: 3px solid #6d98d4;
            border-radius: 10px;
            padding: 20px;
            min-height: 140px;
            display: flex;
            flex-direction: column;
            justify-content: center;
            box-shadow: 0 0 20px rgba(100, 150, 255, 0.5);
        }

        .dialogue-box::before {
            content: '';
            position: absolute;
            top: -10px;
            left: 30px;
            width: 20px;
            height: 20px;
            background: #6d98d4;
            transform: rotate(45deg);
            border-left: 3px solid #6d98d4;
            border-top: 3px solid #6d98d4;
            background: rgba(20, 20, 40, 0.85);
        }

        .speaker-name {
            position: absolute;
            top: -15px;
            left: 30px;
            background: #6d98d4;
            color: white;
            padding: 5px 15px;
            border-radius: 20px;
            font-size: 0.9rem;
            font-weight: bold;
            box-shadow: 0 3px 10px rgba(0, 0, 0, 0.3);
        }

        .dialogue-message {
            font-size: 1.2rem;
            line-height: 1.5;
            min-height: 80px;
            white-space: pre-wrap;
        }

        .dialogue-cursor {
            display: inline-block;
            width: 10px;
            height: 1.4rem;
            background-color: #a3d9ff;
            margin-left: 5px;
            animation: blink 1s infinite;
            vertical-align: middle;
        }

        .dialogue-next {
            position: absolute;
            bottom: 15px;
            right: 20px;
            color: #a3d9ff;
            font-size: 1.5rem;
            animation: bounce 1s infinite;
            opacity: 0;
        }

        .orientation-message {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(10, 10, 22, 0.95);
            z-index: 100;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            padding: 20px;
        }

        .orientation-message h2 {
            color: #a3d9ff;
            margin-bottom: 20px;
            font-size: 1.8rem;
        }

        .orientation-message p {
            color: #cccccc;
            font-size: 1.2rem;
            max-width: 500px;
            line-height: 1.6;
        }

        .rotate-icon {
            font-size: 4rem;
            margin-bottom: 20px;
            animation: rotate 2s infinite;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        @keyframes blink {
            0%, 100% { opacity: 1; }
            50% { opacity: 0; }
        }

        @keyframes twinkle {
            0%, 100% { opacity: 0.2; transform: scale(1); }
            50% { opacity: 1; transform: scale(1.2); }
        }

        @keyframes pulse {
            0% { transform: scale(1); box-shadow: 0 0 0 0 rgba(100, 150, 255, 0.4); }
            70% { transform: scale(1); box-shadow: 0 0 0 15px rgba(100, 150, 255, 0); }
            100% { transform: scale(1); box-shadow: 0 0 0 0 rgba(100, 150, 255, 0); }
        }

        @keyframes float {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-15px); }
        }

        @keyframes gentlePulse {
            0%, 100% { box-shadow: 0 0 5px rgba(255, 100, 100, 0.3); }
            50% { box-shadow: 0 0 20px rgba(255, 100, 100, 0.5); }
        }

        @keyframes heartbeat {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.2); }
        }

        @keyframes rotate {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(90deg); }
        }

        @keyframes shimmer {
            0% { left: -100%; }
            100% { left: 100%; }
        }

        @keyframes gentleWave {
            0%, 100% { transform: translateY(0) rotate(0deg); }
            50% { transform: translateY(-3px) rotate(1deg); }
        }

        @keyframes bounce {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-5px); }
        }

        @media (max-width: 600px) {
            h1 { font-size: 2.5rem; }
            .message { font-size: 1.2rem; }
            .message-container { padding: 25px; }
            .btn-container { flex-direction: column; gap: 10px; }
            
            /* Mostrar mensagem de orientação em dispositivos móveis no modo retrato */
            @media (max-height: 600px) and (orientation: portrait) {
                .orientation-message {
                    display: flex;
                }
            }
        }

        /* Estilo para modo paisagem em dispositivos móveis */
        @media (orientation: landscape) and (max-height: 500px) {
            .dialogue-screen {
                height: 100vh;
                max-width: 100%;
                border-radius: 0;
            }
            
            .dialogue-box {
                bottom: 10px;
                left: 10px;
                right: 10px;
                min-height: 120px;
            }
            
            .dialogue-message {
                font-size: 1.1rem;
                min-height: 60px;
            }
        }
    </style>
</head>
<body>
    <div class="universe" id="universe"></div>
    
    <!-- Mensagem para orientar a virar o celular -->
    <div class="orientation-message" id="orientation-message">
        <div class="rotate-icon">📱</div>
        <h2>Melhor experiência em modo paisagem</h2>
        <p>Vire seu celular de lado para aproveitar melhor esta parte especial!</p>
    </div>
    
    <div class="container">
        <!-- Tela de Boas-Vindas -->
        <div class="welcome-screen" id="welcome-screen">
            <h1>Feliz Aniversário, <span class="heart">♥</span> Carol <span class="heart">♥</span></h1>
            <div class="subtitle">Um presente especial feito com carinho</div>
            
            <div class="warning">
                <strong>Aviso:</strong> Algumas músicas eu toquei no violão. Uma corda soltou durante a gravação, então algumas partes podem soar diferentes. Fiz o meu melhor!
            </div>
            
            <p style="margin-bottom: 20px; max-width: 500px; font-size: 1.1rem;">
                Este é um pequeno presente para celebrar seu dia especial. Espero que goste!
            </p>
            
            <button class="start-btn" id="start-btn">Iniciar Experiência</button>
        </div>
        
        <!-- Conteúdo Principal (inicialmente oculto) -->
        <div class="content-screen" id="content-screen">
            <div class="message-container">
                <div class="message" id="message"></div>
                <div class="cursor" id="cursor"></div>
            </div>
            
            <div class="progress-container">
                <div class="progress-bar" id="progress-bar"></div>
            </div>
            
            <div class="music-info" id="music-info"></div>
            
            <div class="music-controls">
                <button class="music-btn" id="prev-btn">⏮</button>
                <button class="music-btn" id="play-pause-btn">⏯</button>
                <button class="music-btn" id="next-music-btn">⏭</button>
            </div>
            
            <button class="violao-toggle" id="violao-toggle">🎸 Ouvir versão violão</button>
            
            <div class="btn-container">
                <button class="next-btn" id="next-btn">Próximo</button>
            </div>

            <button class="special-btn" id="special-btn">Descobrir Surpresa Especial</button>
            
            <div class="page-indicator" id="page-indicator"></div>
        </div>

        <!-- Tela de Diálogo dos Personagens -->
        <div class="dialogue-screen" id="dialogue-screen">
            <div class="dialogue-bg"></div>
            
            <div class="dialogue-box" id="dialogue-box">
                <div class="speaker-name" id="speaker-name">Cloud</div>
                <div class="dialogue-message" id="dialogue-message"></div>
                <div class="dialogue-cursor" id="dialogue-cursor"></div>
                <div class="dialogue-next" id="dialogue-next">▼</div>
            </div>
        </div>
    </div>

    <audio id="background-music" loop></audio>

    <script>
        // Textos para cada página - mais sutis e emocionantes
        const messages = [
            "Carol...\n\nÀs vezes as palavras são difíceis de encontrar.\nMas para você, eu tento.\n\nDesde que te conheci, algo mudou.\nSua presença traz uma calma que eu nem\nsabia que precisava.\n\nÉ estranho como às vezes não precisamos\nde palavras para nos sentirmos bem perto\nde alguém.",
            
            "Às vezes me pego pensando...\n\nComo é possível se sentir tão confortável\ncom alguém, mesmo sem trocar muitas\npalavras?\n\nCom você, até o silêncio é reconfortante.\nNão preciso me preocupar em falar algo\ninteligente ou interessante.\n\nApenas existir no mesmo espaço já é\nsuficiente.",
            
            "Sabe...\n\nÀs vezes eu te vejo de longe, cercada\npelos seus amigos, e fico feliz por você.\n\nMas também sinto uma pontada de tristeza\npor não conseguir me aproximar mais.\n\nQueria poder chegar até você e conversar\ncomo todo mundo... Mas para mim, isso é\nmais difícil do que parece.",
            
            "Carol, neste seu aniversário...\n\nQuero que saiba o quanto você é especial.\nSua simples existência já torna tudo\nmais bonito.\n\nDesejo que este novo ano traga toda a\nfelicidade que você merece.\n\nQue cada dia seja uma nova aventura e\ncada momento uma lembrança preciosa.",
            
            "Às vezes penso que a vida é como\numa grande história...\n\nE ter você como parte da minha, mesmo\nque por pouco tempo, já fez toda a\ndiferença.\n\nVocê trouxe cores onde antes havia apenas\ntons de cinza, e esperança onde eu já\nnão acreditava mais.",
            
            "E assim chegamos ao final...\n\nDesta pequena jornada que criei para você.\nEspero que tenha gostado.\n\nQue seu caminho seja sempre iluminado\ne que você encontre toda a felicidade\nque merece.\n\nObrigado por ser quem você é.\nObrigado por existir.\n\nCom todo carinho, feliz aniversário!"
        ];

        // Textos alternativos para quando apagar e reescrever
        const alternativeMessages = [
            "Carol...\n\nAs palavras sempre fugiram de mim quando\nmais preciso delas.\n\nMas desde que você apareceu na minha vida,\nacho que finalmente entendi o que significa\nse sentir em paz perto de alguém.\n\nÉ como encontrar um porto seguro em meio\na uma tempestade.",
            
            "Pensando bem...\n\nTalvez sejam os pequenos momentos que\nrealmente importam.\n\nUm simples 'oi' no corredor, um sorriso\ndistante...\n\nCom você, até essas pequenas coisas\ntrazem um calor que eu não conhecia.\n\nÉ como se cada pequeno gesto tivesse\num significado especial.",
            
            "Confesso que...\n\nÉ difícil para mim me conectar com as\npessoas. Mas com você é diferente.\n\nMesmo com todas as minhas dificuldades,\nsinto uma ligação que não consigo\nexplicar direito.\n\nE me desculpe por não conseguir\ndemonstrar isso como gostaria.\n\nQueria poder dizer tudo o que sinto,\nmas as palavras sempre me traem.",
            
            "No seu aniversário...\n\nDesejo que todos os seus sonhos se\nrealizem. Que a alegria te acompanhe\nsempre.\n\nQue você continue sendo essa pessoa\nmaravilhosa que ilumina a vida dos outros\nsó por existir.\n\nQue cada novo amanhecer traga novas\nrazões para sorrir.",
            
            "A vida tem dessas coisas...\n\nNos coloca no caminho de pessoas\nespeciais quando menos esperamos.\n\nE você foi uma dessas surpresas\nmaravilhosas que eu nunca vou esquecer.\n\nMesmo que nosso tempo juntos tenha sido\ncurto, cada momento valeu por uma\neternidade.",
            
            "Chegou a hora da despedida...\n\nMas não um adeus, apenas um até logo.\n\nQue esta não seja o fim, mas apenas\nmais um capítulo da nossa história.\n\nEspero que guarde este momento em seu\ncoração, assim como eu guardarei cada\ninstante ao seu lado.\n\nCom todo carinho, feliz aniversário!"
        ];

        // Diálogos entre Cloud e Tifa
        const dialogues = [
            { speaker: "Cloud", message: "Tifa...\n\nÉ sempre bom estar aqui contigo.\nMesmo sem falar nada, me sinto em paz." },
            { speaker: "Tifa", message: "Cloud...\n\nVocê parece distante hoje.\nEstá tudo bem?" },
            { speaker: "Cloud", message: "...\n\nÀs vezes é difícil encontrar as palavras certas.\nPrincipalmente quando quero dizer algo importante." },
            { speaker: "Tifa", message: "Você não precisa forçar nada, Cloud.\nSó de estarmos juntos já é especial." },
            { speaker: "Cloud", message: "É que...\n\nQueria poder expressar melhor o que sinto.\nMas as palavras sempre fogem quando mais preciso delas." },
            { speaker: "Tifa", message: "Talvez as palavras não sejam tão importantes.\nÀs vezes, o silêncio fala mais alto." },
            { speaker: "Cloud", message: "(pensando)\n\nEla não faz ideia do quanto significa para mim.\nComo é reconfortante apenas estar ao seu lado.\n\nSe eu pudesse, diria tudo...\nMas talvez alguns sentimentos sejam melhores guardados no coração." }
        ];

        // Músicas para cada página - versão original e violão
        const musicFilesOriginal = [
            "musicaX1.mp3",  // Tifa's Theme (FF7 Remake) - original
            "musicaX2.mp3",  // Main Theme Sector 7 Undercity (FF7 Remake) - original
            "musicaX3.mp3",  // Hollow (FF7 Remake) - original
            "musicaX4.mp3",  // Valse di Fantastica (FF15) - original
            "musicaX5.mp3",  // Ahead on Our Way (FF) - original
            "musicaX6.mp3"   // Música???? - original
        ];

        const musicFilesViolao = [
            "musica1.mp3",   // Tifa's Theme (FF7 Remake) - violão
            "musica2.mp3",   // Main Theme Sector 7 Undercity (FF7 Remake) - violão
            "musica3.mp3",   // Hollow (FF7 Remake) - violão
            "musica4.mp3",   // Valse di Fantastica (FF15) - violão
            "musica5.mp3",   // Ahead on Our Way (FF) - violão
            "musica6.mp3"    // Música???? - violão
        ];

        // Música especial para os diálogos
        const specialMusic = "musica7.mp3";

        // Títulos das músicas para exibição
        const musicTitles = [
            "Tifa's Theme - Final Fantasy VII",
            "Main Theme Sector 7 - Final Fantasy VII",
            "Hollow - Final Fantasy VII",
            "Valse di Fantastica - Final Fantasy XV",
            "Ahead on Our Way - Final Fantasy",
            "Música????"
        ];

        // Configurações de digitação
        let currentPage = 0;
        let currentChar = 0;
        let isDeleting = false;
        let isWaiting = false;
        let typingSpeed = 40;
        let deleteSpeed = 20;
        let pauseTime = 1500;
        let timeoutId = null;
        let isViolaoVersion = true;
        let hasSwitchedText = false;

        // Para os diálogos
        let currentDialogue = 0;
        let dialogueChar = 0;
        let isDialogueDeleting = false;
        let isDialogueWaiting = false;
        let dialogueTimeoutId = null;

        // Elementos DOM
        const welcomeScreen = document.getElementById('welcome-screen');
        const contentScreen = document.getElementById('content-screen');
        const dialogueScreen = document.getElementById('dialogue-screen');
        const messageElement = document.getElementById('message');
        const cursorElement = document.getElementById('cursor');
        const nextBtn = document.getElementById('next-btn');
        const specialBtn = document.getElementById('special-btn');
        const musicInfo = document.getElementById('music-info');
        const progressBar = document.getElementById('progress-bar');
        const pageIndicator = document.getElementById('page-indicator');
        const backgroundMusic = document.getElementById('background-music');
        const universeContainer = document.getElementById('universe');
        const prevBtn = document.getElementById('prev-btn');
        const playPauseBtn = document.getElementById('play-pause-btn');
        const nextMusicBtn = document.getElementById('next-music-btn');
        const startBtn = document.getElementById('start-btn');
        const violaoToggle = document.getElementById('violao-toggle');
        const orientationMessage = document.getElementById('orientation-message');

        // Elementos de diálogo
        const speakerName = document.getElementById('speaker-name');
        const dialogueMessage = document.getElementById('dialogue-message');
        const dialogueCursor = document.getElementById('dialogue-cursor');
        const dialogueNext = document.getElementById('dialogue-next');
        const dialogueBox = document.getElementById('dialogue-box');

        // Criar universo estelar
        function createUniverse() {
            const starsCount = 400;
            
            for (let i = 0; i < starsCount; i++) {
                const star = document.createElement('div');
                star.classList.add('star');
                
                // Tamanho aleatório
                const size = Math.random() * 3;
                star.style.width = `${size}px`;
                star.style.height = `${size}px`;
                
                // Posição aleatória
                star.style.left = `${Math.random() * 100}%`;
                star.style.top = `${Math.random() * 100}%`;
                
                // Brilho e duração aleatórios
                const brightness = 0.3 + Math.random() * 0.7;
                star.style.opacity = brightness;
                star.style.animationDuration = `${2 + Math.random() * 4}s`;
                star.style.animationDelay = `${Math.random() * 5}s`;
                
                universeContainer.appendChild(star);
            }
        }

        // Verificar orientação da tela
        function checkOrientation() {
            if (window.innerHeight < window.innerWidth) {
                // Modo paisagem
                orientationMessage.style.display = 'none';
            } else {
                // Modo retrato - mostrar mensagem apenas na tela de diálogo
                if (dialogueScreen.style.display === 'block') {
                    orientationMessage.style.display = 'flex';
                }
            }
        }

        // Inicializar indicadores de página
        function initPageIndicators() {
            pageIndicator.innerHTML = '';
            for (let i = 0; i < messages.length; i++) {
                const dot = document.createElement('div');
                dot.classList.add('dot');
                if (i === 0) dot.classList.add('active');
                dot.addEventListener('click', () => {
                    if (i !== currentPage) {
                        currentPage = i;
                        currentChar = 0;
                        isDeleting = false;
                        isWaiting = false;
                        hasSwitchedText = false;
                        
                        messageElement.textContent = '';
                        cursorElement.style.display = 'inline-block';
                        nextBtn.style.opacity = '0';
                        nextBtn.style.pointerEvents = 'none';
                        progressBar.style.width = '0%';
                        
                        updateMusic();
                        updatePageIndicators();
                        typeText();
                    }
                });
                pageIndicator.appendChild(dot);
            }
        }

        // Atualizar indicadores de página
        function updatePageIndicators() {
            const dots = document.querySelectorAll('.dot');
            dots.forEach((dot, index) => {
                if (index === currentPage) {
                    dot.classList.add('active');
                } else {
                    dot.classList.remove('active');
                }
            });
        }

        // Efeito de digitação com mudanças reais de texto
        function typeText() {
            if (timeoutId) clearTimeout(timeoutId);
            
            let currentText = hasSwitchedText ? alternativeMessages[currentPage] : messages[currentPage];
            
            if (!isDeleting && currentChar <= currentText.length) {
                // Digitação normal
                messageElement.textContent = currentText.substring(0, currentChar);
                currentChar++;
                
                // Simular hesitação ocasional
                if (Math.random() < 0.02 && currentChar > 10) {
                    timeoutId = setTimeout(typeText, typingSpeed * 5);
                    return;
                }
                
                // Simular mudança de ideia (apagar e reescrever) - mais frequente
                if (Math.random() < 0.03 && currentChar > 30 && !hasSwitchedText) {
                    isDeleting = true;
                    timeoutId = setTimeout(typeText, pauseTime);
                    return;
                }
                
                timeoutId = setTimeout(typeText, typingSpeed);
                
            } else if (isDeleting && currentChar > 0) {
                // Apagando texto
                messageElement.textContent = currentText.substring(0, currentChar - 1);
                currentChar--;
                
                // Parar de apagar quando chegar ao início e trocar para texto alternativo
                if (currentChar === 0) {
                    isDeleting = false;
                    hasSwitchedText = true;
                    
                    // Pequena pausa antes de começar a digitar o texto alternativo
                    timeoutId = setTimeout(typeText, 1000);
                    return;
                }
                
                timeoutId = setTimeout(typeText, deleteSpeed);
                
            } else {
                // Texto completo
                isWaiting = true;
                cursorElement.style.display = 'none';
                nextBtn.style.opacity = '1';
                nextBtn.style.pointerEvents = 'auto';
                
                // Mostrar botão especial na última página
                if (currentPage === messages.length - 1) {
                    specialBtn.style.opacity = '1';
                    specialBtn.style.pointerEvents = 'auto';
                }
            }
            
            // Atualizar barra de progresso
            const progress = (currentChar / currentText.length) * 100;
            progressBar.style.width = `${progress}%`;
        }

        // Avançar para a próxima página
        function nextPage() {
            if (currentPage < messages.length - 1) {
                currentPage++;
                currentChar = 0;
                isDeleting = false;
                isWaiting = false;
                hasSwitchedText = false;
                
                // Resetar elementos
                messageElement.textContent = '';
                cursorElement.style.display = 'inline-block';
                nextBtn.style.opacity = '0';
                nextBtn.style.pointerEvents = 'none';
                specialBtn.style.opacity = '0';
                specialBtn.style.pointerEvents = 'none';
                progressBar.style.width = '0%';
                
                // Atualizar música
                updateMusic();
                
                // Atualizar indicadores
                updatePageIndicators();
                
                // Iniciar digitação
                typeText();
            }
        }

        // Iniciar diálogos
        function startDialogues() {
            // Esconder conteúdo principal e mostrar tela de diálogo
            contentScreen.style.opacity = '0';
            setTimeout(() => {
                contentScreen.style.display = 'none';
                dialogueScreen.style.display = 'block';
                setTimeout(() => {
                    dialogueScreen.style.opacity = '1';
                    
                    // Verificar orientação
                    checkOrientation();
                    
                    // Trocar música
                    backgroundMusic.src = specialMusic;
                    backgroundMusic.play();
                    musicInfo.textContent = "Tocando: Diálogo Especial";
                    
                    // Iniciar primeiro diálogo
                    startDialogue();
                }, 300);
            }, 500);
        }

        // Sistema de digitação para diálogos
        function startDialogue() {
            if (dialogueTimeoutId) clearTimeout(dialogueTimeoutId);
            
            const currentDialogueData = dialogues[currentDialogue];
            
            if (!isDialogueDeleting && dialogueChar <= currentDialogueData.message.length) {
                // Atualizar nome do speaker
                speakerName.textContent = currentDialogueData.speaker;
                
                // Digitação normal
                dialogueMessage.textContent = currentDialogueData.message.substring(0, dialogueChar);
                dialogueChar++;
                
                dialogueTimeoutId = setTimeout(startDialogue, typingSpeed);
                
            } else {
                // Diálogo completo
                isDialogueWaiting = true;
                dialogueCursor.style.display = 'none';
                dialogueNext.style.opacity = '1';
                
                // Habilitar clique para próximo diálogo
                dialogueBox.style.cursor = 'pointer';
                dialogueBox.onclick = nextDialogue;
            }
        }

        // Próximo diálogo
        function nextDialogue() {
            if (currentDialogue < dialogues.length - 1) {
                currentDialogue++;
                dialogueChar = 0;
                isDialogueDeleting = false;
                isDialogueWaiting = false;
                
                // Resetar elementos
                dialogueMessage.textContent = '';
                dialogueCursor.style.display = 'inline-block';
                dialogueNext.style.opacity = '0';
                dialogueBox.style.cursor = 'default';
                dialogueBox.onclick = null;
                
                // Iniciar próximo diálogo
                startDialogue();
            } else {
                // Fim dos diálogos - voltar para o início
                currentDialogue = 0;
                dialogueChar = 0;
                isDialogueDeleting = false;
                isDialogueWaiting = false;
                
                dialogueMessage.textContent = '';
                dialogueCursor.style.display = 'inline-block';
                dialogueNext.style.opacity = '0';
                dialogueBox.style.cursor = 'default';
                dialogueBox.onclick = null;
                
                // Voltar para o conteúdo principal
                dialogueScreen.style.opacity = '0';
                setTimeout(() => {
                    dialogueScreen.style.display = 'none';
                    contentScreen.style.display = 'block';
                    setTimeout(() => {
                        contentScreen.style.opacity = '1';
                        
                        // Restaurar música original
                        updateMusic();
                        
                        // Reiniciar do início
                        currentPage = 0;
                        currentChar = 0;
                        isDeleting = false;
                        isWaiting = false;
                        hasSwitchedText = false;
                        
                        messageElement.textContent = '';
                        cursorElement.style.display = 'inline-block';
                        nextBtn.style.opacity = '0';
                        nextBtn.style.pointerEvents = 'none';
                        specialBtn.style.opacity = '0';
                        specialBtn.style.pointerEvents = 'none';
                        progressBar.style.width = '0%';
                        
                        updatePageIndicators();
                        typeText();
                    }, 300);
                }, 500);
            }
        }

        // Atualizar música baseada na versão selecionada
        function updateMusic() {
            const musicFiles = isViolaoVersion ? musicFilesViolao : musicFilesOriginal;
            backgroundMusic.src = musicFiles[currentPage];
            backgroundMusic.play();
            
            const versionText = isViolaoVersion ? " (violão)" : " (original)";
            musicInfo.textContent = `Tocando: ${musicTitles[currentPage]}${versionText}`;
        }

        // Configurar controles
        function setupControls() {
            // Botão de play/pause
            playPauseBtn.addEventListener('click', () => {
                if (backgroundMusic.paused) {
                    backgroundMusic.play();
                    playPauseBtn.innerHTML = '⏸';
                } else {
                    backgroundMusic.pause();
                    playPauseBtn.innerHTML = '⏯';
                }
            });
            
            // Botão de próxima música
            nextMusicBtn.addEventListener('click', () => {
                if (currentPage < musicFilesOriginal.length - 1) {
                    currentPage++;
                } else {
                    currentPage = 0;
                }
                
                currentChar = 0;
                isDeleting = false;
                isWaiting = false;
                hasSwitchedText = false;
                
                updateMusic();
                updatePageIndicators();
                
                // Reiniciar texto
                messageElement.textContent = '';
                cursorElement.style.display = 'inline-block';
                nextBtn.style.opacity = '0';
                nextBtn.style.pointerEvents = 'none';
                specialBtn.style.opacity = '0';
                specialBtn.style.pointerEvents = 'none';
                progressBar.style.width = '0%';
                typeText();
            });
            
            // Botão de música anterior
            prevBtn.addEventListener('click', () => {
                if (currentPage > 0) {
                    currentPage--;
                } else {
                    currentPage = musicFilesOriginal.length - 1;
                }
                
                currentChar = 0;
                isDeleting = false;
                isWaiting = false;
                hasSwitchedText = false;
                
                updateMusic();
                updatePageIndicators();
                
                // Reiniciar texto
                messageElement.textContent = '';
                cursorElement.style.display = 'inline-block';
                nextBtn.style.opacity = '0';
                nextBtn.style.pointerEvents = 'none';
                specialBtn.style.opacity = '0';
                specialBtn.style.pointerEvents = 'none';
                progressBar.style.width = '0%';
                typeText();
            });
            
            // Botão de alternar entre versões
            violaoToggle.addEventListener('click', () => {
                isViolaoVersion = !isViolaoVersion;
                violaoToggle.textContent = isViolaoVersion ? "🎵 Ouvir versão original" : "🎸 Ouvir versão violão";
                updateMusic();
            });
        }

        // Iniciar experiência
        function startExperience() {
            // Transição suave entre telas
            welcomeScreen.style.opacity = '0';
            setTimeout(() => {
                welcomeScreen.style.display = 'none';
                contentScreen.style.display = 'block';
                setTimeout(() => {
                    contentScreen.style.opacity = '1';
                    
                    // Iniciar digitação após um breve delay
                    setTimeout(() => {
                        typeText();
                        backgroundMusic.play().catch(e => {
                            console.log("Reprodução automática bloqueada. Clique em qualquer lugar para iniciar a música.");
                        });
                    }, 500);
                }, 100);
            }, 500);
        }

        // Inicialização
        function init() {
            createUniverse();
            initPageIndicators();
            setupControls();
            
            // Configurar música
            updateMusic();
            
            // Event listeners
            nextBtn.addEventListener('click', nextPage);
            specialBtn.addEventListener('click', startDialogues);
            startBtn.addEventListener('click', startExperience);
            
            // Verificar orientação quando a janela é redimensionada ou girada
            window.addEventListener('resize', checkOrientation);
            window.addEventListener('orientationchange', checkOrientation);
        }

        // Permitir reprodução de música após interação do usuário
        document.addEventListener('click', () => {
            if (backgroundMusic.paused && contentScreen.style.display === 'block') {
                backgroundMusic.play();
                playPauseBtn.innerHTML = '⏸';
            }
        });

        // Iniciar o site
        window.onload = init;
    </script>
</body>
</html>                                  
