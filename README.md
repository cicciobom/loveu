[san valentino.html](https://github.com/user-attachments/files/25074762/san.valentino.html)
<!DOCTYPE html>
<html lang="it">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>Vuoi essere la mia Valentina?</title>
    <style>
        * { box-sizing: border-box; }
        
        body {
            margin: 0;
            padding: 0;
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            background: linear-gradient(180deg, #e0f7fa 0%, #90e0ef 100%);
            font-family: 'Arial', sans-serif;
            overflow: hidden;
            position: relative;
            transition: background 0.8s ease; /* Transizione sfondo più lenta e fluida */
        }

        /* Layout principale */
        #main-content, #success-message {
            display: flex;
            flex-direction: column;
            align-items: center;
            width: 100%;
            z-index: 10;
            padding: 20px;
        }

        /* Immagine e Cuore insieme */
        .hero-section {
            display: flex;
            flex-direction: column;
            align-items: center;
            margin-bottom: 10px;
        }

        .penguin-img {
            width: 130px;
            height: auto;
            /* Animazione di rimbalzo più dolce */
            animation: bounce 2s infinite ease-in-out;
        }

        .heart-main {
            color: #0077b6;
            font-size: 3.5rem;
            margin-top: -10px;
            animation: pulse 1.5s infinite;
        }

        h1 {
            color: #0077b6;
            font-size: 1.8rem;
            margin: 10px 0 30px 0; /* Più spazio sotto il titolo */
            line-height: 1.2;
            text-shadow: 0 2px 5px rgba(255,255,255,0.5);
            text-align: center;
        }

        /* Container Bottoni */
        .container {
            width: 100%;
            height: 200px; /* Spazio per il movimento del No */
            position: relative;
            display: flex;
            justify-content: center;
            align-items: flex-start; /* Allinea in alto per dare spazio sotto */
        }

        button {
            padding: 15px 35px; /* Bottoni leggermente più grandi */
            font-size: 1.3rem;
            border: none;
            border-radius: 50px;
            cursor: pointer;
            transition: transform 0.2s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            font-weight: bold;
            touch-action: manipulation; /* Ottimizza per mobile */
            box-shadow: 0 4px 10px rgba(0,0,0,0.2);
        }

        #si {
            background-color: #0077b6;
            color: white;
            position: relative;
            z-index: 30;
        }
        
        #si:active { transform: scale(0.95); } /* Effetto click */

        #no {
            background-color: #adb5bd;
            color: white;
            position: absolute;
            top: 0; /* Parte allineato al SI */
            margin-left: 20px; /* Spazio iniziale tra i bottoni */
            z-index: 20;
            white-space: nowrap;
        }

        /* Onde sullo sfondo */
        .ocean {
            position: absolute;
            bottom: 0;
            width: 100%;
            height: 100px;
            z-index: 1; /* Dietro a tutto */
            pointer-events: none;
        }
        .wave {
            position: absolute;
            bottom: 0;
            width: 200%;
            height: 100%;
            background: url('data:image/svg+xml;utf8,<svg viewBox="0 0 1440 320" xmlns="http://www.w3.org/2000/svg"><path fill="%2348cae4" d="M0,224L48,213.3C96,203,192,181,288,181.3C384,181,480,203,576,224C672,245,768,267,864,261.3C960,256,1056,224,1152,197.3C1248,171,1344,149,1392,138.7L1440,128L1440,320L1392,320C1344,320,1248,320,1152,320C1056,320,960,320,864,320C768,320,672,320,576,320C480,320,384,320,288,320C192,320,96,320,48,320L0,320Z"></path></svg>');
            background-size: 50% 100%;
            animation: wave-animation 15s linear infinite; /* Rallentato per essere meno fastidioso */
            opacity: 0.5;
        }

        /* CSS per le particelle di cuori che esplodono */
        .click-heart {
            position: absolute;
            pointer-events: none;
            z-index: 100;
            /* L'animazione ora parte da una dimensione grande e si rimpicciolisce */
            animation: explode 1.2s ease-out forwards;
            text-shadow: 0 0 5px rgba(255,255,255,0.8); /* Un po' di bagliore */
        }

        @keyframes explode {
            0% { transform: translate(-50%, -50%) scale(1); opacity: 1; }
            100% { transform: translate(var(--tx), var(--ty)) scale(0.2); opacity: 0; }
        }

        @keyframes bounce { 0%, 100% { transform: translateY(0); } 50% { transform: translateY(-10px); } }
        @keyframes pulse { 0% { transform: scale(1); } 50% { transform: scale(1.05); } 100% { transform: scale(1); } }
        @keyframes wave-animation { 0% { transform: translateX(0); } 100% { transform: translateX(-50%); } }

        .hidden { display: none !important; }
    </style>
</head>
<body>

    <div class="ocean"><div class="wave"></div></div>

    <div id="main-content">
        <div class="hero-section">
            <img src="https://media.tenor.com/e9Ytk_aZgMcAAAAM/love-heart.gif" alt="Pinguino" class="penguin-img">
            <div class="heart-main">💙</div>
        </div>
        <h1>Vuoi essere la mia Valentina?</h1>
        <div class="container">
            <button id="si">SÌ, certo!</button>
            <button id="no" onmouseover="scappa()" onclick="scappa()">No</button>
        </div>
    </div>

    <div id="success-message" class="hidden">
        <img src="https://media.tenor.com/e9Ytk_aZgMcAAAAM/love-heart.gif" alt="Pinguino felice" class="penguin-img" style="width: 160px;">
        <div class="heart-main" style="font-size: 5rem;">💙</div>
        <h1>YEEEEAH! 🥰</h1>
        <p style="color: #0077b6; font-weight: bold; font-size: 1.5rem;">Ti amo tanto scema mia!</p>
    </div>

    <script>
        let scaleSi = 1;
        const noBtn = document.getElementById('no');
        const siBtn = document.getElementById('si');

        // Gestione del pulsante NO che scappa
        function scappa() {
            // Margine di sicurezza per non far uscire il bottone dallo schermo
            const padding = 60; 
            const maxX = window.innerWidth - noBtn.offsetWidth - padding;
            const maxY = window.innerHeight - noBtn.offsetHeight - padding;
            
            // Genera coordinate casuali sicure
            const randomX = Math.max(20, Math.random() * maxX);
            const randomY = Math.max(20, Math.random() * maxY);

            // Applica la nuova posizione (assoluta rispetto alla finestra)
            noBtn.style.position = 'fixed';
            noBtn.style.left = randomX + 'px';
            noBtn.style.top = randomY + 'px';
            noBtn.style.margin = '0'; // Rimuove il margine iniziale

            // Ingrandisce il tasto SÌ
            scaleSi += 0.2;
            siBtn.style.transform = `scale(${scaleSi})`;
        }

        // --- FUNZIONE MODIFICATA PER CUORI PIÙ GRANDI ---
        function createHeartParticle(x, y) {
            // Creo 20 cuori invece di 15 per più volume
            for (let i = 0; i < 20; i++) {
                const heart = document.createElement('div');
                heart.className = 'click-heart';
                heart.innerHTML = '💙';
                
                // --- MODIFICA QUI: Dimensione casuale MOLTO più grande ---
                // Genera una dimensione tra 40px e 80px
                const size = Math.random() * 40 + 40;
                heart.style.fontSize = size + 'px';
                // ---------------------------------------------------------

                // Posiziona il cuore dove è avvenuto il click
                heart.style.left = x + 'px';
                heart.style.top = y + 'px';
                
                // Calcola una direzione casuale per l'esplosione (più ampia)
                const angle = Math.random() * Math.PI * 2; // Angolo casuale
                const distance = Math.random() * 200 + 100; // Distanza tra 100px e 300px
                const tx = Math.cos(angle) * distance + 'px';
                const ty = Math.sin(angle) * distance + 'px';

                // Passa le variabili CSS per l'animazione
                heart.style.setProperty('--tx', tx);
                heart.style.setProperty('--ty', ty);
                
                document.body.appendChild(heart);
                // Rimuovi il cuore dal DOM dopo l'animazione
                setTimeout(() => heart.remove(), 1200);
            }
        }

        // Gestione del click sul SÌ
        siBtn.addEventListener('click', function(e) {
            // Ottieni le coordinate del click (mouse o touch)
            const x = e.clientX || (e.touches && e.touches[0].clientX) || window.innerWidth / 2;
            const y = e.clientY || (e.touches && e.touches[0].clientY) || window.innerHeight / 2;

            // Fai partire l'esplosione di cuori giganti
            createHeartParticle(x, y);
            
            // Dopo un breve ritardo, mostra il messaggio di successo
            setTimeout(() => {
                document.getElementById('main-content').classList.add('hidden');
                document.getElementById('success-message').classList.remove('hidden');
                // Sfondo diventa verde pastello
                document.body.style.background = "#caffbf"; 
            }, 500);
        });

        // Piccola correzione per mobile: previene lo zoom al doppio tocco
        document.addEventListener('dblclick', (e) => { e.preventDefault(); }, { passive: false });
    </script>
</body>
</html>
