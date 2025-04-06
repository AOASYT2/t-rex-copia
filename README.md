# t-rex-copia
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Jogo T-Rex</title>
    <style>
        body {
            margin: 0;
            overflow: hidden;
            background: #f7f7f7;
        }
        #game {
            position: relative;
            width: 100%;
            height: 150px;
            background: #fff;
            border-top: 2px solid #333;
        }
        #trex {
            position: absolute;
            bottom: 0;
            left: 50px;
            width: 40px;
            height: 40px;
            background: green;
        }
        .cactus {
            position: absolute;
            bottom: 0;
            width: 20px;
            height: 40px;
            background: brown;
            animation: move 2s linear infinite;
        }
        @keyframes move {
            0% { right: -20px; }
            100% { right: 100%; }
        }
    </style>
</head>
<body>
    <div id="game">
        <div id="trex"></div>
    </div>
    <script>
        document.addEventListener('keydown', function(event) {
            if (event.code === 'Space') {
                jump();
            }
        });

        function jump() {
            const trex = document.getElementById('trex');
            if (!trex.classList.contains('jump')) {
                trex.classList.add('jump');
                setTimeout(() => {
                    trex.classList.remove('jump');
                }, 500);
            }
        }

        setInterval(() => {
            const cactus = document.createElement('div');
            cactus.classList.add('cactus');
            document.getElementById('game').appendChild(cactus);
            setTimeout(() => {
                cactus.remove();
            }, 2000);
        }, 2000);
    </script>
</body>
</html>
