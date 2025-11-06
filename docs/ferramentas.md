# Ferramentas e "Como Testar"

Para garantir a acessibilidade na prática, é essencial saber *como* verificar o trabalho. Esta seção apresenta um guia "passo a passo" focado em ferramentas, organizado por *quando* e *como* elas devem ser utilizadas.

Os testes estão categorizados em três níveis de prioridade, que se alinham diretamente aos critérios de "Definition of Done" (Definição de Pronto) vistos na seção de Gestão de Projetos:

1.  **Verificação Nível 1: Design e Contraste** (Uso diário)
2.  **Verificação Nível 2: Auditoria Automática** (Antes de cada *commit*)
3.  **Verificação Nível 3: Teste Manual Essencial** (A Prova de Fogo)

---

## Nível 1: Verificação de Contraste (WebAIM)

Este é o primeiro teste, feito ainda na fase de design, para garantir que as cores escolhidas são legíveis.

* **Ferramenta:** [WebAIM – Contrast Checker](https://webaim.org/resources/contrastchecker/)
* **O que é:** Uma ferramenta online simples para verificar o *ratio* de contraste entre duas cores, baseada no `SC 1.4.3`.
* **Quando usar:** Na fase de **Design**, antes de o desenvolvedor escrever qualquer código.

### Passo a Passo (WebAIM Contrast Checker)

1.  Abra a ferramenta [WebAIM Contrast Checker](https://webaim.org/resources/contrastchecker/) no seu navegador.
2.  No seu protótipo (Figma, Sketch, etc.), pegue o código da cor do seu texto (ex: `#FFFFFF`).
3.  Cole esse código no campo **"Foreground Color"** (Cor do Primeiro Plano).
4.  Pegue o código da cor do seu fundo (ex: `#4A4A4A`).
5.  Cole esse código no campo **"Background Color"** (Cor de Fundo).
6.  **Analise o Resultado:**
    * A ferramenta mostrará o **"Contrast Ratio"** (ex: "5.5:1").
    * Verifique a seção **"WCAG AA"**. Para ser aprovado, você precisa de "Pass" (Passou) para "Normal Text" (texto normal), que exige um *ratio* de **4.5:1**.

---

## Nível 2: Auditoria Automática (Lighthouse)

Este é o teste rápido que o desenvolvedor deve rodar para pegar os erros mais óbvios (falta de `alt`, contraste, `label`, etc.) antes de enviar seu código.

* **Ferramenta:** [Lighthouse](https://developer.chrome.com/docs/lighthouse) (integrado no Chrome)
* **O que é:** Uma ferramenta de auditoria completa embutida no navegador Chrome para avaliar páginas da web.
* **Quando usar:** Na fase de **Desenvolvimento**, para cada *feature* nova.

### Passo a Passo (Lighthouse)

1.  Abra seu site no Google Chrome.
2.  Pressione `F12` (ou `Cmd+Opt+I` no Mac) para abrir o "Painel do Desenvolvedor" (DevTools).
3.  Encontre e clique na aba **"Lighthouse"**. (Pode estar escondida atrás do `>>`).
4.  Na seção "Categories", marque **apenas** "Accessibility".
5.  Na seção "Device", selecione "Desktop".
6.  Clique no botão **"Analyze page load"**.
7.  O Lighthouse gerará um relatório com uma nota de 0 a 100. Seu objetivo deve ser **acima de 90**.
8.  Role para baixo e expanda os itens que falharam (em vermelho). Ele mostrará exatamente quais elementos do seu DOM estão com problemas (ex: "Image elements do not have `[alt]` attributes" ou "Background and foreground colors do not have a sufficient contrast ratio.")

---

## Nível 3: Teste Manual Essencial (Leitor de Tela)

Esta é a "prova de fogo". A auditoria automática (Nível 2) só pega 30-40% dos problemas. Apenas o teste manual pode verificar a *experiência* do usuário.

* **Ferramentas:** [NVDA](https://www.nvaccess.org/download/) (Gratuito, Windows) ou [VoiceOver](https://support.apple.com/pt-br/guide/voiceover/welcome/mac) (Embutido, Mac). (A ferramenta `JAWS` da sua lista original é excelente, mas é paga e complexa; o NVDA é o padrão para testes de desenvolvimento).
* **O que é:** O software que pessoas cegas usam para navegar na web.
* **Quando usar:** Na fase de **QA (Testes)**, antes de fechar um *ticket* ou *feature*.

### Passo a Passo (Como um DEV deve testar)

1.  **Instale e Inicie:** Baixe e instale o [NVDA](https://www.nvaccess.org/download/). (No Mac, ative o VoiceOver com `Cmd + F5`).
2.  **DESLIGUE SEU MONITOR:** Este é o passo mais importante. Se você olhar, você está "trapaceando" e não encontrará os problemas reais de navegação.
3.  **Navegue por `Tab`:** Use a tecla `Tab` para pular de link em link, de botão em botão.
    * *Pergunte-se:* A ordem da navegação faz sentido? O foco ficou preso em algum lugar? Você sabe *onde* está na página?
4.  **Navegue por Títulos:** Use a tecla `H` (atalho do leitor de tela) para pular de título em título.
    * *Pergunte-se:* A sua página está estruturada com `<h1>`, `<h2>`, `<h3>`? Você consegue entender a arquitetura do site apenas pelos títulos? (Isso testa sua Semântica).
5.  **Preencha um Formulário:**
    * *Pergunte-se:* O leitor de tela anunciou o `<label>` (rótulo) de cada campo? Você foi avisado de erros? Você conseguiu enviar o formulário?

---

## Outras Ferramentas (O Ecossistema)

As 3 ferramentas acima são o "kit de sobrevivência". As outras listadas no *template* original são para usos mais específicos:

* **[WAVE – Web Accessibility Evaluation Tool](https://wave.webaim.org/):** Excelente alternativa ao Lighthouse. Em vez de um relatório, ele injeta ícones de erro diretamente na sua página, dando um feedback mais visual.
* **[AXE – Accessibility Engine](https://github.com/dequelabs/axe-core):** Este é o "motor" que muitas ferramentas (incluindo o Lighthouse) usam por baixo dos panos. O Axe é para automação avançada, como rodar testes de acessibilidade automaticamente em seu *pipeline* de CI/CD.
* **[Accessibility Test Framework for Android](https://github.com/google/Accessibility-Test-Framework-for-Android):** Como o nome diz, é focado especificamente em testes de aplicativos Android nativos, não web.