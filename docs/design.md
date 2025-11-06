# Design

Existe uma crença comum de que tornar um site acessível o deixará simples ou visualmente pouco atrativo. Isso não é verdade. Um site bem estruturado pode ser, ao mesmo tempo, bonito, criativo e acessível. Com o uso de CSS, é possível criar diferentes apresentações visuais para uma mesma estrutura HTML, atendendo a diversas necessidades e preferências das pessoas usuárias.

Nesta seção, apresentamos um guia prático para garantir a acessibilidade no design de interfaces digitais. Nossas diretrizes são fundamentadas em três pilares:

1.  Os padrões internacionais **WCAG 2.2 (Web Content Accessibility Guidelines)**, que são a referência global para acessibilidade web.
2.  Os padrões do governo brasileiro, consolidados no **eMAG (Modelo de Acessibilidade em Governo Eletrônico)**, que detalha a aplicação da WCAG no contexto do Brasil.
3.  Princípios de **Interação Humano-Computador (IHC)**, incluindo as Heurísticas de Nielsen, que formam a base da usabilidade.

---

## Heurísticas de Usabilidade e Acessibilidade

Antes de um checklist, é vital entender os *princípios* que guiam um bom design. As 10 Heurísticas de Usabilidade de Nielsen são a base da usabilidade, e elas têm uma sobreposição direta com a acessibilidade.

* **1. Visibilidade do status do sistema:** O usuário deve saber o que está acontecendo.
    * **Na Acessibilidade:** Isso significa que leitores de tela devem ser informados sobre mudanças dinâmicas (ex: "Item adicionado ao carrinho") usando `aria-live`, e o foco do teclado deve ser claramente visível e destacado.
* **2. Correspondência entre o sistema e o mundo real:** A linguagem deve ser clara e familiar.
    * **Na Acessibilidade:** Evite jargões. Use rótulos (`<label>`) claros e descritivos para campos de formulário. A ordem de navegação pelo `Tab` deve seguir a ordem lógica da leitura visual.
* **3. Controle e liberdade do usuário:** O usuário deve poder desfazer ações e navegar livremente.
    * **Na Acessibilidade:** O usuário deve ser capaz de pausar, parar ou ocultar qualquer conteúdo em movimento (como carrosséis ou vídeos em autoplay). Deve haver links "Pular para o conteúdo".
* **4. Consistência e padrões:**
    * **Na Acessibilidade:** A navegação deve ser consistente em todas as páginas (ex: o menu e a busca estão sempre no mesmo lugar e com os mesmos rótulos). Isso ajuda usuários de leitores de tela a criar um modelo mental do site.
* **5. Prevenção de erros:**
    * **Na Acessibilidade:** Forneça instruções claras (`aria-describedby`) e sugestões antes que o usuário cometa um erro, especialmente em formulários. Valide os campos em tempo real de forma acessível.
* **6. Reconhecimento em vez de memorização:**
    * **Na Acessibilidade:** Instruções devem estar sempre visíveis ou facilmente recuperáveis. Ícones devem ter rótulos textuais (visíveis ou via `aria-label`) para não depender do reconhecimento visual.
* **7. Flexibilidade e eficiência de uso:**
    * **Na Acessibilidade:** O sistema deve ser totalmente operável tanto pelo mouse quanto pelo teclado. O uso de teclas de atalho (access keys) e uma ordem de tabulação lógica aumentam a eficiência.
* **8. Estética e design minimalista:**
    * **Na Acessibilidade:** A poluição visual prejudica a todos, mas especialmente pessoas com déficit de atenção ou dificuldades cognitivas. Uma interface limpa ajuda o usuário a focar no conteúdo essencial.
* **9. Ajude os usuários a reconhecer, diagnosticar e recuperar-se de erros:**
    * **Na Acessibilidade:** Mensagens de erro devem ser claras, em linguagem simples (sem códigos de erro) e facilmente perceptíveis. Para leitores de tela, o foco deve ser movido para a mensagem de erro ou ela deve ser anunciada.
* **10. Ajuda e documentação:**
    * **Na Acessibilidade:** Se a ajuda for necessária, ela deve ser fácil de localizar e contextual. Uma seção "Acessibilidade" explicando os recursos disponíveis é uma boa prática.

---

## Guia Prático de Design Acessível

Abaixo está o guia prático, transformado de *checklist* para *guia*, explicando o "Porquê" e o "Como" para cada diretriz.

### 1. Percepção (Não dependa de um único sentido)

* [ ] **Não depender apenas da cor para instruções e informações:**
    * **Por quê?** Pessoas com daltonismo (como protanopia e deuteranopia) ou baixa visão podem não distinguir informações comunicadas apenas pela cor (ex: campos de erro em vermelho, links apenas em azul no meio de um texto, ou um gráfico de pizza).
    * **Como fazer:** Sempre use um indicador visual secundário. Para links, adicione **sublinhado**. Para erros, adicione um **ícone** e **texto descritivo**. Para gráficos, use texturas, padrões ou rótulos de dados.
    * **Referência:** (WCAG 2.2 - SC 1.4.1 Uso de Cor)

* [ ] **Descrever controles pelo nome, e não pela aparência:**
    * **Por quê?** Instruções como "clique no botão redondo à direita" ou "procure pelo item em negrito" falham para usuários que não enxergam o layout ou não distinguem a formatação (ex: usuários de leitores de tela).
    * **Como fazer:** Descreva os controles pelo seu *nome acessível* (o texto no botão ou sua `aria-label`). Ex: "Selecione o botão 'Confirmar'."
    * **Referência:** (WCAG 2.2 - SC 1.3.3 Características Sensoriais)

### 2. Legibilidade e Adaptação

* [ ] **Garantir que o tamanho do texto seja ajustável (Zoom):**
    * **Por quê?** Usuários com baixa visão precisam ampliar o texto sem quebrar a página ou exigir rolagem bidirecional (horizontal e vertical).
    * **Como fazer:** O site deve suportar um zoom de até 200% (SC 1.4.4) e um layout responsivo que se ajuste até uma largura de 320 CSS pixels (equivalente a um zoom de 400%) sem perda de conteúdo ou funcionalidade (SC 1.4.10). Evite unidades absolutas (como `px`) para fontes; prefira unidades relativas (`rem`, `em`).
    * **Referência:** (WCAG 2.2 - SC 1.4.4 Redimensionar Texto e SC 1.4.10 Refluxo)

* [ ] **Evitar o alinhamento justificado:**
    * **Por quê?** O texto justificado cria "rios" (espaços em branco irregulares entre as palavras) que quebram o fluxo de leitura, sendo um grande problema para pessoas com dislexia ou dificuldades cognitivas.
    * **Como fazer:** Use alinhamento à esquerda (`text-align: left`) para blocos de texto (ou `text-align: right` para idiomas RTL).

* [ ] **Manter parágrafos com, no máximo, 80 caracteres por linha:**
    * **Por quê?** Linhas muito longas dificultam o retorno do olho para o início da próxima linha, causando fadiga visual e perda de foco.
    * **Como fazer:** Defina uma largura máxima (`max-width`) para seus blocos de texto, usando unidades relativas como `ch` (ex: `max-width: 80ch;`).

* [ ] **Evitar textos longos em caixa alta ou condensados:**
    * **Por quê?** Textos em caixa alta (maiúsculas) eliminam a silhueta característica das palavras, tornando-as mais difíceis de ler. Fontes condensadas ou excessivamente estilizadas também prejudicam a legibilidade.
    * **Como fazer:** Use caixa alta apenas para títulos curtos ou siglas. Prefira fontes *sans-serif* (como Roboto, Open Sans, Arial) com boa distinção entre caracteres (ex: 'I' maiúsculo e 'l' minúsculo).

* [ ] **Saber como ocultar conteúdo corretamente:**
    * **Por quê?** `display: none` ou `visibility: hidden` ocultam o conteúdo de *todos*, incluindo leitores de tela. Às vezes, queremos ocultar algo *apenas* visualmente, mas mantê-lo para tecnologias assistivas (ex: o rótulo "Buscar" em um botão que só tem o ícone de uma lupa).
    * **Como fazer:** Para ocultar visualmente, mas manter para leitores de tela, use uma classe CSS "sr-only" (screen-reader only) ou "visually-hidden".
    * **Exemplo de Código:**

        ```css
        .sr-only {
          position: absolute;
          width: 1px;
          height: 1px;
          padding: 0;
          margin: -1px;
          overflow: hidden;
          clip: rect(0, 0, 0, 0);
          white-space: nowrap;
          border-width: 0;
        }
        ```

    * **Exemplo de HTML:**
        ```html
        <button>
          <span class="sr-only">Buscar</span>
          <svg aria-hidden="true" ...>...</svg>
        </button>
        ```

### 3. Contraste de Cores

Esta é uma das áreas mais críticas do design acessível. O contraste adequado garante que pessoas com baixa visão ou daltonismo possam ler e interagir com o conteúdo.

#### Critérios Essenciais (WCAG Nível AA)

* [ ] **Texto Normal (< 18pt ou < 14pt negrito):** Deve ter um contraste mínimo de **4.5:1** com o fundo.
* [ ] **Texto Grande (>= 18pt ou >= 14pt negrito):** Deve ter um contraste mínimo de **3:1** com o fundo. (Referência: SC 1.4.3)
* [ ] **Componentes de UI e Gráficos:** (Ícones, bordas de *input*, gráficos, dicas visuais de foco) Devem ter um contraste mínimo de **3:1** com seus fundos adjacentes. (Referência: SC 1.4.11)

#### Como Testar (O Passo a Passo)

Não basta "achar" que o contraste está bom; ele deve ser medido.

**Ferramenta 1: Colour Contrast Analyser (CCA)**

* **O que é:** Um aplicativo gratuito (Windows/Mac) da TPGi que permite usar um conta-gotas para medir o contraste entre quaisquer dois pontos na tela.

* **Passo a Passo Básico:**
    1.  Baixe e instale o aplicativo a partir do site oficial da TPGi.
    2.  Abra o CCA e o seu site ou protótipo (Figma, Sketch, etc.).
    3.  Na seção "Foreground colour", clique no ícone de conta-gotas e selecione a cor do seu texto, ícone ou borda.
    4.  Na seção "Background colour", clique no ícone de conta-gotas e selecione a cor de fundo imediatamente adjacente.
    5.  O aplicativo mostrará instantaneamente os resultados. Em "WCAG 2.1 results" (que cobre a WCAG 2.2 para contraste), verifique se há um "Pass" (Passou) nos níveis "AA" para texto normal e componentes de UI.

---

**Ferramenta 2: Lighthouse (No Google Chrome DevTools)**

* **O que é:** Uma ferramenta de auditoria completa embutida no navegador Chrome para avaliar páginas da web.

* **Passo a Passo Básico:**
    1.  Abra seu site no Google Chrome.
    2.  Pressione `F12` (ou `Cmd+Opt+I` no Mac) para abrir o "Painel do Desenvolvedor" (DevTools).
    3.  Encontre e clique na aba "Lighthouse".
    4.  Na seção "Categories", marque **apenas** "Accessibility". Em "Mode", selecione "Navigation". Em "Device", selecione "Desktop".
    5.  Clique no botão "Analyze page load".
    6.  O Lighthouse gerará um relatório. Role para baixo até a seção "Contrast" e expanda os itens que falharam. Ele mostrará exatamente quais elementos do seu DOM não atingem o *ratio* de contraste mínimo.

### 4. Animação e Movimento

* [ ] **Evitar conteúdo que pisque:**
    * **Por quê?** Conteúdo que pisca mais de três vezes por segundo pode induzir convulsões em pessoas com epilepsia fotossensível.
    * **Como fazer:** Garanta que nenhuma animação ou vídeo viole este limite.
    * **Referência:** (WCAG 2.2 - SC 2.3.1 Três Flashes ou Abaixo do Limite)

* [ ] **Permitir que pessoas usuárias controlem alterações automáticas:**
    * **Por quê?** Carrosséis, tickers de notícias ou vídeos em *autoplay* que se movem automaticamente dificultam a leitura e podem ser extremamente distrativos para pessoas com déficit de atenção.
    * **Como fazer:** Forneça botões claros e fáceis de operar de "pausar", "parar" ou "ocultar".
    * **Referência:** (WCAG 2.2 - SC 2.2.2 Pausar, Parar, Ocultar)

* [ ] **Respeitar a preferência de movimento reduzido:**
    * **Por quê?** Pessoas com distúrbios vestibulares podem sentir náusea, tontura ou vertigem com animações (especialmente *parallax*, zoom, *fade* ou deslizamento).
    * **Como fazer:** Use a consulta de mídia `prefers-reduced-motion` no CSS para desativar ou substituir animações não essenciais quando o usuário tiver essa preferência ativada em seu sistema operacional.
    * **Referência:** (WCAG 2.2 - SC 2.3.3 Animação de Interações - Nível AAA, mas uma boa prática para todos)
    * **Exemplo de Código:**
        ```css
        /* Define a animação padrão */
        .meu-elemento-animado {
          transition: transform 0.4s ease;
        }

        /* Desativa a transição se o usuário pedir */
        @media (prefers-reduced-motion: reduce) {
          .meu-elemento-animado {
            transition: none;
          }
        }
        ```