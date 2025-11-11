<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <!-- Configuração Essencial para Responsividade -->
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Página Inicial do Meu Projeto GitHub</title>
    
    <!-- Carrega o Tailwind CSS para estilização moderna e responsiva -->
    <script src="https://cdn.tailwindcss.com"></script>
    
    <style>
        /* Define a fonte Inter como padrão */
        :root {
            font-family: 'Inter', sans-serif;
        }
    </style>
</head>
<body class="bg-gray-100 dark:bg-gray-900 text-gray-900 dark:text-gray-100 min-h-screen flex flex-col transition-colors duration-300">

    <!-- Cabeçalho (Header) -->
    <header class="bg-white dark:bg-gray-800 shadow-md">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-4 flex justify-between items-center">
            <h1 class="text-2xl font-bold text-indigo-600 dark:text-indigo-400">
                Meu Projeto Incrível
            </h1>
            <nav>
                <a href="#" class="text-gray-600 dark:text-gray-300 hover:text-indigo-600 dark:hover:text-indigo-400 mx-3 transition-colors duration-200">Início</a>
                <a href="#" class="text-gray-600 dark:text-gray-300 hover:text-indigo-600 dark:hover:text-indigo-400 mx-3 transition-colors duration-200">Sobre</a>
                <a href="#" class="text-gray-600 dark:text-gray-300 hover:text-indigo-600 dark:hover:text-indigo-400 mx-3 transition-colors duration-200">Contato</a>
            </nav>
        </div>
    </header>

    <!-- Conteúdo Principal (Main) - Responsivo e Centralizado -->
    <main class="flex-grow flex items-center justify-center p-4">
        <div class="w-full max-w-4xl bg-white dark:bg-gray-800 p-8 md:p-12 rounded-xl shadow-2xl text-center">
            <h2 class="text-4xl md:text-5xl font-extrabold mb-4 text-gray-800 dark:text-white">
                Bem-vindo ao Nosso Projeto!
            </h2>
            <p class="text-lg md:text-xl mb-8 text-gray-600 dark:text-gray-300 max-w-2xl mx-auto">
                Esta é a seção principal do conteúdo. Se você está vendo este texto,
                significa que sua página do GitHub Pages está configurada corretamente e carregando o HTML.
            </p>
            <!-- Botão de Ação -->
            <button id="ctaButton" class="bg-indigo-600 hover:bg-indigo-700 text-white font-semibold py-3 px-8 rounded-lg shadow-lg transform transition duration-300 hover:scale-105 focus:outline-none focus:ring-4 focus:ring-indigo-500 focus:ring-opacity-50">
                Começar Agora
            </button>

            <!-- Mensagem de feedback (substitui alert()) -->
            <div id="messageBox" class="mt-6 p-3 bg-green-100 dark:bg-green-800 text-green-800 dark:text-green-200 rounded-lg hidden"></div>
        </div>
    </main>

    <!-- Rodapé (Footer) -->
    <footer class="bg-gray-200 dark:bg-gray-900 py-4 mt-auto">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 text-center text-sm text-gray-600 dark:text-gray-400">
            &copy; 2025 Meu Projeto Incrível. Todos os direitos reservados.
        </div>
    </footer>

    <!-- Script JavaScript para Interatividade Básica -->
    <script>
        document.addEventListener('DOMContentLoaded', () => {
            const ctaButton = document.getElementById('ctaButton');
            const messageBox = document.getElementById('messageBox');
            
            // Função para exibir mensagens na caixa personalizada, em vez de usar alert()
            function showMessage(message, type = 'info') {
                messageBox.textContent = message;
                messageBox.className = 'mt-6 p-3 rounded-lg block';
                
                // Estilos para diferentes tipos de mensagem
                if (type === 'success') {
                    messageBox.classList.add('bg-green-100', 'dark:bg-green-800', 'text-green-800', 'dark:text-green-200');
                } else {
                    // Padrão para info
                    messageBox.classList.add('bg-blue-100', 'dark:bg-blue-800', 'text-blue-800', 'dark:text-blue-200');
                }

                // Esconde a mensagem após 5 segundos
                setTimeout(() => {
                    messageBox.classList.remove('block');
                    messageBox.classList.add('hidden');
                }, 5000);
            }

            ctaButton.addEventListener('click', () => {
                showMessage('Você clicou no botão! O JavaScript está funcionando.', 'success');
            });

            // Exemplo de alternância de modo escuro (Dark Mode)
            // Você pode adicionar um botão para isso no cabeçalho se quiser.
            const isDarkMode = window.matchMedia('(prefers-color-scheme: dark)').matches;
            if (isDarkMode) {
                document.documentElement.classList.add('dark');
            } else {
                document.documentElement.classList.remove('dark');
            }
        });
    </script>
</body>
</html>
