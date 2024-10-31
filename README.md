<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Cronômetro do Nosso Dia</title>
    <link href="https://fonts.googleapis.com/css2?family=Arial:wght@400&display=swap" rel="stylesheet">
    <style>
        body {
            font-family: 'Arial', sans-serif;
            color: #f0e68a; /* Cor do texto */
            background-image: linear-gradient(to right, #6a11cb, #2575fc); /* Gradiente de fundo */
            margin: 0;
            display: flex;
            flex-direction: column;
            align-items: center;
            overflow-x: hidden;
        }

        .container {
            text-align: center;
            background-color: rgba(40, 40, 40, 0.8); /* Fundo do container */
            padding: 15px; /* Padding */
            border-radius: 10px; /* Arredondamento do container */
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.6);
            position: fixed;
            top: 10px; /* Ajuste na posição superior */
            left: 50%;
            transform: translateX(-50%); /* Centraliza horizontalmente */
            z-index: 10;
            border: 3px solid #f0e68a; /* Borda dourada */
            width: 90%; /* Largura do container responsiva */
            max-width: 350px; /* Largura máxima do container */
            box-sizing: border-box; /* Inclui padding e border na largura */
        }

        h1 {
            font-size: 1.8em; /* Tamanho do título */
            margin: 0;
        }

        .countdown {
            font-size: 1.4em; /* Tamanho da contagem */
            margin-top: 5px;
        }

        .footer {
            margin-top: 5px;
            font-size: 0.9em; /* Tamanho da fonte do rodapé */
            color: #c0c0c0;
        }

        .timeline {
            margin-top: 150px;
            width: 90%;
            max-width: 800px; /* Largura máxima da linha do tempo */
            padding: 20px;
            position: relative;
            background-color: rgba(45, 45, 45, 0.95);
            border-radius: 10px;
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.8);
            box-sizing: border-box; /* Inclui padding e border na largura */
        }

        .timeline::after {
            content: '';
            position: absolute;
            width: 6px;
            background-color: #f0e68a; /* Cor do timeline */
            top: 0;
            bottom: 0;
            left: 50%;
            margin-left: -3px;
            border-radius: 5px;
        }

        .timeline-item {
            display: flex;
            width: 100%;
            padding: 15px 0; /* Ajuste no padding */
            position: relative;
            transition: transform 0.2s ease;
            align-items: center;
        }

        .timeline-item:hover {
            transform: scale(1.02);
        }

        .timeline-item:nth-child(odd) {
            flex-direction: row-reverse;
            text-align: right;
        }

        .timeline-item::before {
            content: '';
            position: absolute;
            width: 20px;
            height: 20px;
            background-color: #1c1c1c;
            border: 4px solid #f0e68a; /* Borda dourada dos pontos */
            border-radius: 50%;
            top: 20px;
            left: 50%;
            transform: translateX(-50%);
            z-index: 1;
        }

        .timeline-content {
            padding: 15px;
            background-color: rgba(45, 45, 45, 0.95);
            border-radius: 10px;
            width: 100%; /* Largura total do conteúdo */
            max-width: 400px; /* Largura máxima do conteúdo */
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.8);
            border: 2px solid #f0e68a; /* Borda dourada */
            position: relative;
            margin: 0 auto; /* Centraliza o conteúdo */
        }

        .timeline-content img {
            width: 100%; /* Largura total da imagem */
            height: auto; /* Mantém a proporção da imagem */
            border-radius: 10px;
            border: 2px solid #f0e68a; /* Borda das imagens */
            transition: transform 0.3s ease;
        }

        .timeline-content img:hover {
            transform: scale(1.05);
        }

        .caption {
            font-size: 1.2em; /* Tamanho da legenda */
            color: #f0e68a; /* Cor da legenda */
            margin-top: 10px;
            text-align: center;
        }

        /* Estilos responsivos */
        @media (max-width: 600px) {
            h1 {
                font-size: 1.5em; /* Ajusta o tamanho do título em telas pequenas */
            }

            .countdown {
                font-size: 1.2em; /* Ajusta o tamanho da contagem em telas pequenas */
            }

            .footer {
                font-size: 0.8em; /* Ajusta o tamanho do rodapé em telas pequenas */
            }

            .timeline-content {
                max-width: 100%; /* Largura total em telas pequenas */
            }

            .caption {
                font-size: 1em; /* Ajusta o tamanho da legenda em telas pequenas */
            }
        }
    </style>
</head>
<body>
    <div class="container" id="countdown-container">
        <h1>Cronômetro do Nosso Dia</h1>
        <div class="countdown" id="countdown">0d 0h 0m 0s</div>
        <div class="footer">Contagem a partir de 02/11/2024 às 21:09</div>
    </div>

    <div class="timeline">
        <div class="timeline-item">
            <div class="timeline-content">
                <img src="images/foto1.jpeg" alt="Momento 1">
                <div class="caption">Novembro 2023 - O início de tudo</div>
            </div>
        </div>
        <div class="timeline-item">
            <div class="timeline-content">
                <img src="images/foto2.jpeg" alt="Momento 2">
                <div class="caption">Dezembro 2024 - 1 Mês</div>
            </div>
        </div>
        <div class="timeline-item">
            <div class="timeline-content">
                <img src="images/foto3.jpeg" alt="Momento 3">
                <div class="caption">Janeiro 2024 - 2 Meses</div>
            </div>
        </div>
        <div class="timeline-item">
            <div class="timeline-content">
                <img src="images/foto4.jpeg" alt="Momento 4">
                <div class="caption">Fevereiro 2024 - 3 Meses</div>
            </div>
        </div>
        <div class="timeline-item">
            <div class="timeline-content">
                <img src="images/foto5.jpeg" alt="Momento 5">
                <div class="caption">Março 2024 - 4 Meses</div>
            </div>
        </div>
        <div class="timeline-item">
            <div class="timeline-content">
                <img src="images/foto6.jpeg" alt="Momento 6">
                <div class="caption">Abril 2024 - 5 Meses</div>
            </div>
        </div>
        <div class="timeline-item">
            <div class="timeline-content">
                <img src="images/foto7.jpeg" alt="Momento 7">
                <div class="caption">Maio 2024 - 6 Meses</div>
            </div>
        </div>
        <div class="timeline-item">
            <div class="timeline-content">
                <img src="images/foto8.jpeg" alt="Momento 8">
                <div class="caption">Junho 2024 - 7 Meses</div>
            </div>
        </div>
        <div class="timeline-item">
            <div class="timeline-content">
                <img src="images/foto9.jpeg" alt="Momento 9">
                <div class="caption">Julho 2024 - 8 Meses</div>
            </div>
        </div>
        <div class="timeline-item">
            <div class="timeline-content">
                <img src="images/foto10.jpeg" alt="Momento 10">
                <div class="caption">Agosto 2024 - 9 Meses</div>
            </div>
        </div>
        <div class="timeline-item">
            <div class="timeline-content">
                <img src="images/foto11.jpeg" alt="Momento 11">
                <div class="caption">Setembro 2024 - 10 Meses</div>
            </div>
        </div>
        <div class="timeline-item">
            <div class="timeline-content">
                <img src="images/foto12.jpeg" alt="Momento 12">
                <div class="caption">Outubro 2024 - 11 Meses</div>
            </div>
        </div>
    </div>

    <script>
        const countdownContainer = document.getElementById('countdown');
        const countdownDate = new Date('2024-11-02T21:09:00').getTime();

        const updateCountdown = () => {
            const now = new Date().getTime();
            const distance = countdownDate - now;

            const days = Math.floor(distance / (1000 * 60 * 60 * 24));
            const hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
            const minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
            const seconds = Math.floor((distance % (1000 * 60)) / 1000);

            countdownContainer.innerHTML = `${days}d ${hours}h ${minutes}m ${seconds}s`;

            if (distance < 0) {
                clearInterval(x);
                countdownContainer.innerHTML = "Contagem encerrada!";
            }
        };

        const x = setInterval(updateCountdown, 1000);
    </script>
</body>
</html>

