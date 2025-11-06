# Desenvolvimento

Nesta fase, o *checklist* de design se transforma em código funcional. É essencial que a equipe de desenvolvimento compreenda como **implementar** a acessibilidade de forma robusta, **verificá-la** com as ferramentas corretas e entender como usuários de tecnologia assistiva irão interagir com o produto.

Este guia foca na implementação semântica do **HTML**, no uso correto de **ARIA** (Accessible Rich Internet Applications) e nas técnicas de **verificação prática**.

---

## 1. Semântica e Estrutura

Antes de qualquer `<div>` estilizada, use o elemento HTML semanticamente correto. Um leitor de tela usa a semântica do HTML para dar contexto e atalhos de navegação ao usuário.

### Landmarks

* [ ] **Usar HTML Semântico para Layout:**
    * **Por quê?** Leitores de tela usam "landmarks" para permitir que o usuário pule direto para a navegação (`<nav>`) ou para o conteúdo principal (`<main>`). Usar `<div>` para tudo destrói essa funcionalidade.
    * **Como (Implementação):**
        ```html
        <body>
          <header> <nav> <ul>...</ul>
            </nav>
          </header>

          <main> <h1>Meu Título</h1>
            <p>Todo o conteúdo...</p>
          </main>

          <footer> ...
          </footer>
        </body>
        ```

### Hierarquia de Títulos

* [ ] **Estruturar o conteúdo com `<h1>` - `<h6>`:**
    * **Por quê?** Usuários de leitores de tela não "escaneiam" a página com os olhos, eles o fazem pulando de título em título (pressionando a tecla `H`). A hierarquia de títulos é o "mapa" da sua página.
    * **Como (Implementação):**
        1.  Use **um (e apenas um) `<h1>`** por página, descrevendo o conteúdo principal.
        2.  **Não pule níveis:** Um `<h2>` deve ser seguido por um `<h3>`, não por um `<h4>`. O design visual (tamanho da fonte) não dita a hierarquia.
        ```html
        <h1>Receitas</h1>
          <h2>Bolos</h2>
            <h3>Bolo de Chocolate</h3>
            <h3>Bolo de Cenoura</h3>
          <h2>Tortas</h2>
            <h3>Torta de Maçã</h3>

        <h1>Receitas</h1>
          <h3>Bolo de Chocolate</h3>
        ```

---

## 2. Navegação e Interatividade (Teclado)

Todo conteúdo interativo *deve* ser 100% operável apenas com o teclado. (WCAG SC 2.1.1)

### Foco Visível

* [ ] **Nunca remover o contorno de foco (`outline`):**
    * **Por quê?** Usuários que navegam pelo teclado (sem mouse) precisam de um indicador visual claro de "onde" eles estão na página. Remover o `outline` do CSS é o erro de acessibilidade mais comum e prejudicial.
    * **Como (Implementação):** Se o `outline` padrão do navegador for feio, *substitua-o* por um melhor, mas **nunca o remova**.
        ```css
        /* RUIM (NUNCA FAÇA ISSO) */
        :focus {
          outline: none;
        }

        /* BOM (Substitui por um indicador claro) */
        :focus-visible {
          outline: 3px solid #0000FF; /* Um anel azul visível */
          box-shadow: 0 0 5px 5px #0000FF;
          border-radius: 2px;
        }
        ```
    * **Nota:** Use `:focus-visible` em vez de `:focus` para que o estilo de foco só apareça para usuários de teclado, e não em cliques de mouse.

### Skip Links (Pular para o Conteúdo)

* [ ] **Adicionar um "Skip Link" (Pular para o Conteúdo):**
    * **Por quê?** Para um usuário de teclado, ter que apertar `Tab` 20 vezes para passar pelo cabeçalho e navegação *em toda página* é exaustivo.
    * **Como (Implementação):** O "skip link" é o primeiro item focalizável da página. Ele fica visualmente oculto (usando a classe `.sr-only` que vimos no Design) e só aparece quando recebe foco.
        ```html
        <body>
          <a href="#conteudo-principal" class="sr-only sr-only-focusable">
            Pular para o conteúdo principal
          </a>
          <header>...</header>
          <main id="conteudo-principal">
            ...
          </main>
        </body>
        ```
        ```css
        /* Oculta o link por padrão */
        .sr-only {
          position: absolute;
          width: 1px;
          height: 1px;
          /* ... (restante da classe .sr-only) ... */
        }

        /* Faz o link aparecer quando focado */
        .sr-only-focusable:focus {
          position: static;
          width: auto;
          height: auto;
          /* ... (estilos para torná-lo visível) ... */
        }
        ```

---

## 3. Imagens e Mídia

### Imagens (`alt` text)

* [ ] **Usar texto alternativo (`alt`) corretamente:**
    * **Por quê?** O `alt` é o que o leitor de tela anuncia para o usuário, permitindo que ele "veja" a imagem. (WCAG SC 1.1.1)
    * **Como (Para imagens informativas):** O `alt` deve ser uma descrição concisa do *significado* da imagem.
        ```html
        <img src="grafico.png" alt="Gráfico de pizza mostrando 40% de participação para Vendas">

        <img src="grafico.png" alt="grafico">
        ```
    * **Como (Para imagens decorativas):** Use um `alt` vazio (`alt=""`). Isso faz o leitor de tela *ignorar* a imagem, o que é o comportamento desejado.
        ```html
        <img src="borda-bonita.png" alt="">

        <img src="borda-bonita.png" alt="borda bonita">
        ```

### Vídeos e Áudio

* [ ] **Fornecer Legendas, Transcrições e evitar Autoplay:**
    * **Por quê?** Conteúdo de áudio/vídeo é inacessível para usuários surdos (sem legendas), cegos (sem audiodescrição) ou surdo-cegos (sem transcrição).
    * **Como (Implementação):**
        1.  **Não use `autoplay`**. (WCAG SC 1.4.2)
        2.  Use a tag `<track>` para adicionar legendas (`.vtt`). (WCAG SC 1.2.2)
        3.  Forneça uma transcrição textual completa em algum lugar da página.
        ```html
        <video controls>
          <source src="meu-video.mp4" type="video/mp4">
          <track
            label="Português (Brasil)"
            kind="subtitles"
            srclang="pt-br"
            src="legendas.vtt"
            default>
          Desculpe, seu navegador não suporta o vídeo.
        </video>
        <details>
          <summary>Ver Transcrição</summary>
          <p>...</p>
        </details>
        ```

---

## 4. Formulários

Formulários são o ponto de interação mais complexo e onde a acessibilidade mais falha.

* [ ] **Ligar Rótulos (`<label>`) a Entradas (`<input>`):**
    * **Por quê?** Um leitor de tela precisa saber o que um campo de `input` pede. O `<label>` é a forma de criar essa conexão.
    * **Como (Implementação):** Use o atributo `for` no `<label>` para apontar para o `id` do `<input>`.
        ```html
        <label for="id_nome">Nome:</label>
        <input type="text" id="id_nome">

        <span>Nome:</span>
        <input type="text">
        ```

* [ ] **Agrupar campos relacionados (`<fieldset>`):**
    * **Por quê?** Quando você tem um grupo de `radio buttons` ou `checkboxes`, o usuário precisa saber a *pergunta* do grupo.
    * **Como (Implementação):** Use `<fieldset>` para agrupar e `<legend>` para a pergunta.
        ```html
        <fieldset>
          <legend>Qual seu nível de experiência?</legend>

          <input type="radio" id="niv_ini" name="nivel">
          <label for="niv_ini">Iniciante</label>

          <input type="radio" id="niv_adv" name="nivel">
          <label for="niv_adv">Avançado</label>
        </fieldset>
        ```

* [ ] **Fornecer instruções e feedback de erro acessíveis:**
    * **Por quê?** Mensagens de erro visuais (um texto vermelho) são invisíveis para leitores de tela. O usuário precisa ser *avisado* do erro.
    * **Como (Implementação):**
        1.  Use `aria-describedby` para ligar uma instrução a um campo.
        2.  Use `aria-live="polite"` para um contêiner de erro, para que o leitor de tela anuncie a mensagem de erro assim que ela aparecer.
        ```html
        <label for="id_senha">Senha:</label>
        <input type="password" id="id_senha" aria-describedby="dica_senha">
        <span id="dica_senha">Deve ter no mínimo 8 caracteres.</span>

        <div id="container-erros" aria-live="polite">
          </div>
        ```

---

## 5. Modais e Componentes Dinâmicos

* [ ] **Implementar Modais Acessíveis (Armadilha de Foco):**
    * **Por quê?** Um modal (janela pop-up) deve "prender" o foco do teclado. Se o usuário apertar `Tab` em um modal aberto, o foco não pode escapar para a página atrás dele.
    * **Como (Implementação):** Isso requer HTML, ARIA e JavaScript.
        1.  **HTML/ARIA:** O contêiner do modal deve ter `role="dialog"` e `aria-modal="true"`.
        2.  **JS (Foco):** Ao abrir, o foco deve ir para o modal (ex: o `<h1>` ou o botão de fechar).
        3.  **JS (Armadilha):** O foco do `Tab` deve ficar *preso* dentro do modal (circular).
        4.  **JS (Fechar):** A tecla `ESC` deve fechar o modal.
        5.  **JS (Retorno):** Ao fechar, o foco deve *retornar* para o elemento que abriu o modal (ex: o botão "Abrir modal").

---

## 6. Dispositivos Móveis e Toque

* [ ] **Garantir o Tamanho Mínimo do Alvo (Target Size):**
    * **Por quê?** Botões e links muito pequenos ou muito próximos são impossíveis de usar em telas de toque.
    * **Como (Implementação):** Este é o **novo** critério da WCAG 2.2.
    * **O Critério:** **`SC 2.5.8 Target Size (Minimum)` (Nível AA)** exige que todos os alvos interativos tenham uma área de pelo menos **24x24 pixels**.
    * **Nota:** O antigo critério de 44x44px (`SC 2.5.5`) é Nível AAA e não é a base de cobrança do Nível AA.

* [ ] **Permitir Orientação e Zoom:**
    * **Por quê?** O usuário deve poder usar o site em modo retrato ou paisagem (`SC 1.3.4`) e deve poder dar zoom sem quebrar o layout (sem rolagem horizontal) (`SC 1.4.10 Reflow`).

---

## 7. Análise Crítica da WCAG

!!! warning "Critério Obsoleto: SC 4.1.1 Parsing"
    O *template* original deste guia (e muitos guias antigos na internet) pode citar o critério `SC 4.1.1 Parsing`. Este critério exigia que o HTML fosse perfeitamente válido (sem tags aninhadas erradas, IDs duplicados, etc.).
    
    **Este critério foi declarado obsoleto e REMOVIDO da WCAG (versões 2.1 e 2.2).**
    
    **Por quê?** Os navegadores modernos e leitores de tela são robustos e corrigem HTML quebrado automaticamente. Os *testadores* gastavam mais tempo procurando por erros de *parsing* (que não afetavam o usuário) do que por erros *reais* de acessibilidade.
    
    **O foco agora:** Em vez de se preocupar com a validação perfeita, foque na **semântica correta** (landmarks, títulos, labels), como descrito neste guia.

---

## 8. Ferramentas Essenciais de Verificação

A sua introdução promete "utilizar as ferramentas". Aqui está o passo a passo de como fazer isso no desenvolvimento.

### Ferramenta 1: Leitores de Tela (NVDA ou VoiceOver)

Testar com um leitor de tela é a única forma de simular a experiência de usuários cegos. É o "teste de fogo" da acessibilidade.

* **O que é:** NVDA (Gratuito, Windows) e VoiceOver (Embutido, Mac).
* **Passo a Passo (Como um DEV deve testar):**
    1.  Inicie o leitor de tela (NVDA no Windows, VoiceOver no Mac).
    2.  **Desligue seu monitor ou feche os olhos.** (Isto é sério. Se você olhar, você está "trapaceando" e não encontrará os problemas reais).
    3.  Tente navegar pelo seu site usando **apenas o teclado**.
    4.  Use `Tab` para pular entre links e botões. A ordem faz sentido? Você sabe onde está? O foco visível é claro?
    5.  Use as teclas de atalho do leitor (`H` para pular por Títulos, `L` para listas, `T` para tabelas). O seu site está estruturado corretamente (Semântica) para isso?
    6.  Tente preencher um formulário. Você sabe o que cada campo pede? Você foi avisado dos erros?

### Ferramenta 2: Auditoria Automática (Lighthouse)

* **O que é:** A ferramenta de auditoria (na aba "Lighthouse") embutida no Chrome DevTools (F12).
* **Passo a Passo:**
    1.  Abra seu site e pressione `F12`.
    2.  Vá para a aba "Lighthouse".
    3.  Na seção "Categories", marque **apenas** "Accessibility".
    4.  Clique em "Analyze page load".
    5.  O relatório apontará erros automáticos (Contraste, falta de `alt`, falta de `label`, etc.). **Nota:** O Lighthouse só captura cerca de 30-40% dos problemas. Ele não substitui o teste manual (Ferramenta 1).

### Ferramenta 3: Linters de Código (ESLint-a11y)

* **O que é:** Um plugin para o seu editor de código (VS Code, etc.) que encontra erros de acessibilidade *enquanto você digita*.
* **Por quê?** Esta é a forma mais eficiente de "incrementar" a acessibilidade. Ele avisa você no exato momento em que você escreve um HTML inacessível.
* **Como (Implementação):** Se seu projeto usa JavaScript (React, Vue, etc.), adicione o plugin `eslint-plugin-jsx-a11y` ao seu `eslint.rc`.
    * Ele irá sublinhar em vermelho erros como:
        ```html
        <img src="foto.png">

        <div onClick={handleClick}>Clique aqui</div>
        ```