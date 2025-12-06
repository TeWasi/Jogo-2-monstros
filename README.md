
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Monstros Jogo 2: A Jornada dos Magos Sônicos</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://unpkg.com/lucide@latest"></script>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;800&display=swap" rel="stylesheet">
    <style>
        body {
            font-family: 'Inter', sans-serif;
            background-color: #0d1117;
            color: #f3f4f6;
            min-height: 100vh;
        }
        .monster-card {
            background-color: #1f2937;
            border-radius: 0.5rem;
            transition: transform 0.2s, box-shadow 0.2s;
            position: relative;
            overflow: hidden;
            border: 2px solid;
        }
        .monster-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 15px rgba(0, 0, 0, 0.5);
        }
        .monster-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, rgba(255, 255, 255, 0.05) 0%, rgba(255, 255, 255, 0) 50%);
            z-index: 0;
        }
    </style>
</head>
<body class="p-6 md:p-12">

    <header class="text-center mb-12">
        <h1 class="text-4xl md:text-5xl font-extrabold text-white mb-2">
            ARQUIVO MÁGICO: JOGO 2
        </h1>
        <p class="text-xl text-gray-400 font-medium">A Jornada dos Magos Sônicos - Fichas dos Monstros da Mente</p>
    </header>

    <div class="max-w-4xl mx-auto grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-8">
        
        <!-- MONSTRO 1: Tédio da Rotina -->
        <a href="rotina.html" class="monster-card border-blue-500 hover:border-blue-300 shadow-blue-900/50">
            <div class="p-5">
                <div class="flex items-center mb-3">
                    <i data-lucide="repeat-2" class="w-6 h-6 text-blue-400 mr-3"></i>
                    <h3 class="text-xl font-bold text-blue-400">Tédio da Rotina</h3>
                </div>
                <p class="text-sm text-gray-400">A inércia que esmaga a criatividade.</p>
            </div>
        </a>

        <!-- MONSTRO 2: Procrastinação -->
        <a href="procrastinacao.html" class="monster-card border-orange-500 hover:border-orange-300 shadow-orange-900/50">
            <div class="p-5">
                <div class="flex items-center mb-3">
                    <i data-lucide="clock-stop" class="w-6 h-6 text-orange-400 mr-3"></i>
                    <h3 class="text-xl font-bold text-orange-400">Procrastinação</h3>
                </div>
                <p class="text-sm text-gray-400">O adiamento causado pelo medo do fracasso.</p>
            </div>
        </a>

        <!-- MONSTRO 3: Julgamento Exterior -->
        <a href="julgamento_exterior.html" class="monster-card border-purple-500 hover:border-purple-300 shadow-purple-900/50">
            <div class="p-5">
                <div class="flex items-center mb-3">
                    <i data-lucide="eye" class="w-6 h-6 text-purple-400 mr-3"></i>
                    <h3 class="text-xl font-bold text-purple-400">Julgamento Exterior</h3>
                </div>
                <p class="text-sm text-gray-400">A ansiedade gerada pela crítica alheia.</p>
            </div>
        </a>

        <!-- MONSTRO 4: Insegurança -->
        <a href="inseguranca.html" class="monster-card border-cyan-500 hover:border-cyan-300 shadow-cyan-900/50">
            <div class="p-5">
                <div class="flex items-center mb-3">
                    <i data-lucide="help-circle" class="w-6 h-6 text-cyan-400 mr-3"></i>
                    <h3 class="text-xl font-bold text-cyan-400">Insegurança</h3>
                </div>
                <p class="text-sm text-gray-400">Dúvida sobre o próprio valor e capacidade.</p>
            </div>
        </a>

        <!-- MONSTRO 5: Fala Rupta -->
        <a href="fala_rupta.html" class="monster-card border-red-500 hover:border-red-300 shadow-red-900/50">
            <div class="p-5">
                <div class="flex items-center mb-3">
                    <i data-lucide="volume-x" class="w-6 h-6 text-red-400 mr-3"></i>
                    <h3 class="text-xl font-bold text-red-400">Fala Rupta</h3>
                </div>
                <p class="text-sm text-gray-400">A frustração da comunicação quebrada.</p>
            </div>
        </a>

        <!-- MONSTRO 6: Ansiedade -->
        <a href="ansiedade.html" class="monster-card border-yellow-500 hover:border-yellow-300 shadow-yellow-900/50">
            <div class="p-5">
                <div class="flex items-center mb-3">
                    <i data-lucide="alert-triangle" class="w-6 h-6 text-yellow-400 mr-3"></i>
                    <h3 class="text-xl font-bold text-yellow-400">Ansiedade</h3>
                </div>
                <p class="text-sm text-gray-400">O alerta constante e a preocupação excessiva.</p>
            </div>
        </a>

    </div>

    <footer class="text-center text-gray-600 text-sm mt-12 pt-6 border-t border-gray-800">
        &copy; 2025 Jogo 2 - Fichas completas. Clique nos cards para ver os detalhes.
    </footer>

    <script>
        lucide.createIcons();
    </script>
</body>
</html>
