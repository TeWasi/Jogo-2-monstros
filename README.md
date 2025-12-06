<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Gerador de QR Codes Bonitos</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://unpkg.com/lucide@latest"></script>
    <!-- Biblioteca de QR Code -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/qrcodejs/1.0.0/qrcode.min.js"></script>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;800&display=swap" rel="stylesheet">
    <style>
        body {
            font-family: 'Inter', sans-serif;
            background-color: #0d1117;
            color: #f3f4f6;
        }
        .qr-card {
            background-color: #1f2937;
            border-radius: 0.75rem;
            padding: 1.5rem;
            box-shadow: 0 10px 15px rgba(0, 0, 0, 0.3);
            display: flex;
            flex-direction: column;
            align-items: center;
        }
        .qr-placeholder {
            padding: 1rem;
            background-color: #ffffff;
            border-radius: 0.5rem;
            display: inline-block;
        }
        /* Estilo para impressão */
        @media print {
            body {
                background-color: white;
                color: #0d1117;
            }
            .no-print {
                display: none !important;
            }
            .qr-card {
                background-color: #ffffff;
                border: 1px solid #ccc;
                page-break-inside: avoid;
            }
            .print-button {
                display: none;
            }
        }
    </style>
</head>
<body class="p-6 md:p-12">

    <header class="text-center mb-12 no-print">
        <h1 class="text-4xl md:text-5xl font-extrabold text-white mb-2">
            ESTAÇÃO DE QR CODE
        </h1>
        <p class="text-xl text-gray-400 font-medium">Códigos prontos para impressão. (Links corrigidos)</p>
        <button onclick="window.print()" class="print-button mt-4 bg-orange-600 hover:bg-orange-700 text-white font-bold py-2 px-6 rounded-lg transition duration-150 flex items-center mx-auto shadow-lg">
            <i data-lucide="printer" class="w-5 h-5 mr-2"></i> Imprimir Todos os Códigos
        </button>
    </header>

    <div id="qr-grid" class="max-w-6xl mx-auto grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 xl:grid-cols-4 gap-8">
        <!-- Os cartões de QR Code serão injetados aqui -->
    </div>

    <script>
        lucide.createIcons();

        // Dados com os URLs corrigidos e a cor tema para cada monstro
        const monsterData = [
            {
                name: "Tédio da Rotina", 
                url: "https://tewasi.github.io/Jogo-2-monstros/Tedio%20da%20Rotina", 
                color: "blue",
                hex: "#3b82f6"
            },
            {
                name: "Procrastinação", 
                url: "https://tewasi.github.io/Jogo-2-monstros/Procrastina%C3%A7%C3%A3o", 
                color: "orange",
                hex: "#f97316"
            },
            {
                name: "Julgamento Exterior", 
                url: "https://tewasi.github.io/Jogo-2-monstros/Julgamento%20Exterior", 
                color: "purple",
                hex: "#a855f7"
            },
            {
                name: "Insegurança", 
                url: "https://tewasi.github.io/Jogo-2-monstros/Inseguran%C3%A7a", 
                color: "cyan",
                hex: "#06b6d4"
            },
            {
                name: "Fala Rupta", 
                url: "https://tewasi.github.io/Jogo-2-monstros/Fala%20Rupta", 
                color: "red",
                hex: "#ef4444"
            },
            {
                name: "Ansiedade", 
                url: "https://tewasi.github.io/Jogo-2-monstros/Ansiedade", 
                color: "yellow",
                hex: "#eab308"
            }
        ];

        const grid = document.getElementById('qr-grid');

        monsterData.forEach((monster, index) => {
            // 1. Criar o elemento do cartão
            const card = document.createElement('div');
            card.className = `qr-card border-t-4 border-${monster.color}-500`;
            card.style.borderColor = monster.hex; // Aplica a cor tema como borda

            // 2. Título
            const title = document.createElement('h3');
            title.className = `text-xl font-bold mb-3 text-${monster.color}-400 text-center`;
            title.style.color = monster.hex;
            title.textContent = monster.name;

            // 3. Container do QR Code
            const qrContainer = document.createElement('div');
            qrContainer.id = `qrcode-${index}`;
            qrContainer.className = 'qr-placeholder';

            // 4. Parágrafo do Link
            const linkText = document.createElement('p');
            linkText.className = 'text-xs text-gray-500 mt-4 text-center break-all';
            linkText.textContent = `Link: ${monster.url}`;

            // 5. Adicionar elementos ao cartão
            card.appendChild(title);
            card.appendChild(qrContainer);
            card.appendChild(linkText);
            grid.appendChild(card);

            // 6. Gerar o QR Code
            new QRCode(qrContainer, {
                text: monster.url,
                width: 200,
                height: 200,
                colorDark: "#000000",
                colorLight: "#ffffff",
                correctLevel: QRCode.CorrectLevel.H
            });
        });
    </script>
</body>
</html>
