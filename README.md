<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Exemplo HTML, CSS e DOM</title>

    <style>
        body {
            margin: 0;
            font-family: Arial, sans-serif;
        }

        header {
            background-color: lightblue;
            padding: 20px;
        }

        nav {
            background-color: lightgray;
            padding: 15px;
        }

        main {
            background-color: white;
            padding: 20px;
            min-height: 200px;
        }

        footer {
            background-color: gray;
            padding: 20px;
        }

        .bloco-footer {
            padding: 15px;
            margin: 10px;
        }

        #bloco1 {
            background-color: lightcoral;
        }

        #bloco2 {
            background-color: lightgreen;
        }

        #bloco3 {
            background-color: lightyellow;
        }
    </style>
</head>

<body>

    <header>
        <h1>Meu Site</h1>
    </header>

    <nav>
        <a href="#">Início</a>
        <a href="#">Sobre</a>
        <a href="#">Contato</a>
    </nav>

    <main id="conteudo">
        <!-- O JavaScript criará os elementos aqui -->
    </main>

    <footer>
        <div class="bloco-footer" id="bloco1">
            <p>Primeira div do footer</p>
        </div>

        <div class="bloco-footer" id="bloco2">
            <p>Segunda div do footer</p>
        </div>

        <div class="bloco-footer" id="bloco3">
            <p>Terceira div do footer</p>
        </div>
    </footer>

    <script>
        // Selecionar o elemento main
        const main = document.getElementById("conteudo");

        // CENTRALIZAR OS ELEMENTOS VIA JAVASCRIPT
        main.style.textAlign = "center";

        // CRIAR TÍTULO DA FEIRA
        const titulo = document.createElement("h2");
        titulo.textContent = "Feira das Nações: Portugal";
        main.appendChild(titulo);

        // CRIAR E CONFIGURAR A IMAGEM (Bandeira de Portugal)
        const imagem = document.createElement("img");
        imagem.src = "data:image/png;base64,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";
        imagem.alt = "Bandeira de Portugal";
        imagem.style.width = "150px";
        imagem.style.display = "block";
        imagem.style.margin = "15px auto"; // "auto" nas laterais centraliza a tag img block
        imagem.style.borderRadius = "4px";
        imagem.style.boxShadow = "0px 2px 5px rgba(0,0,0,0.2)";
        main.appendChild(imagem);

        // CRIAR TEXTO INTRODUTÓRIO
        const subheader = document.createElement("h3");
        subheader.textContent = "Curiosidades sobre o País:";
        main.appendChild(subheader);

        // CRIAR A LISTA ORDENADA
        const listaOrdenada = document.createElement("ol");
        listaOrdenada.style.display = "inline-block"; // Permite que a lista fique centralizada mantendo os números alinhados à esquerda
        listaOrdenada.style.textAlign = "left";       // Mantém o texto interno alinhado à esquerda para leitura fluida
        listaOrdenada.style.margin = "0 auto";

        // Item 1
        const item1 = document.createElement("li");
        item1.textContent = "Paixão pelo Futebol: Portugal é a terra de grandes craques mundiais, como Cristiano Ronaldo e Eusébio.";
        listaOrdenada.appendChild(item1);

        // Item 2
        const item2 = document.createElement("li");
        item2.textContent = "Gastronomia Famosa: O país é conhecido internacionalmente pelos deliciosos Pastéis de Nata e pratos com Bacalhau.";
        listaOrdenada.appendChild(item2);

        // Item 3
        const item3 = document.createElement("li");
        item3.textContent = "História dos Navegadores: Foi um dos pioneiros na Era dos Descobrimentos, explorando rotas marítimas pelo mundo inteiro.";
        listaOrdenada.appendChild(item3);

        // Adicionar a lista completa dentro do main
        main.appendChild(listaOrdenada);

        // --- CENTRALIZAR O HEADER E NAV VIA JAVASCRIPT ---
        const topoSite = document.querySelector("header");
        const menuNavegacao = document.querySelector("nav");

        if (topoSite) {
            topoSite.style.textAlign = "center";
        }
        if (menuNavegacao) {
            menuNavegacao.style.textAlign = "center";
        }

        // --- ALTERAR CORES DE TODA A PÁGINA VIA JAVASCRIPT ---
        // Cores do Header e Nav (Tons de verde de Portugal)
        if (topoSite) {
            topoSite.style.backgroundColor = "#00662F"; 
            topoSite.style.color = "#FFFFFF"; // Texto branco para dar contraste
        }
        if (menuNavegacao) {
            menuNavegacao.style.backgroundColor = "#1D8443";
            // Estilizar os links do menu para ficarem brancos
            const links = menuNavegacao.querySelectorAll("a");
            links.forEach(link => {
                link.style.color = "#FFFFFF";
                link.style.margin = "0 10px";
                link.style.textDecoration = "none";
                link.style.fontWeight = "bold";
            });
        }

        // Cor do conteúdo principal (Fundo creme claro para melhor leitura)
        main.style.backgroundColor = "#FDFBF7";
        main.style.color = "#333333";

        // Cores do Rodapé (Vermelho de Portugal)
        const rodape = document.querySelector("footer");
        if (rodape) {
            rodape.style.backgroundColor = "#D2151E";
            rodape.style.display = "flex"; // Alinha os blocos em linha
            rodape.style.justifyContent = "center";
        }

        // Mudar as cores dos blocos internos do footer para tons que combinem (Dourado/Amarelo e Branco)
        const b1 = document.getElementById("bloco1");
        const b2 = document.getElementById("bloco2");
        const b3 = document.getElementById("bloco3");

        if (b1) {
            b1.style.backgroundColor = "#FFD700"; // Dourado
            b1.style.color = "#000000";
        }
        if (b2) {
            b2.style.backgroundColor = "#FFFFFF"; // Branco
            b2.style.color = "#000000";
        }
        if (b3) {
            b3.style.backgroundColor = "#FFD700"; // Dourado
            b3.style.color = "#000000";
        }
    </script>

</body>
</html>
