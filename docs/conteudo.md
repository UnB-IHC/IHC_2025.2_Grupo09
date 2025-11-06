# Geração de Conteúdo

Para produzir conteúdo digital acessível, é essencial compreender que toda comunicação tem impacto sobre as pessoas. A acessibilidade de conteúdo vai além da técnica; ela começa na forma como abordamos nosso público.

Boas práticas de conteúdo são a implementação direta do **Princípio 3 da WCAG: Compreensível**. Um site pode ser tecnicamente perfeito, mas se o conteúdo for confuso, ele falha em acessibilidade.

Muitas dessas práticas também refletem as **Heurísticas de Nielsen**, como a **#2 (Correspondência entre o sistema e o mundo real)**, que pede linguagem clara e familiar, e a **#8 (Estética e design minimalista)**, que se aplica a textos objetivos e sem ruído.

---

## 1. Terminologia e Linguagem (O Respeito)

* [ ] **Usar o termo "Pessoa com Deficiência" (PCD):**
    * **Por quê?** Este é o termo oficial e correto, estabelecido pela Convenção da ONU. Ele coloca a **pessoa** em primeiro lugar.
    * **Evite:** Termos como "deficiente", "portador de deficiência" ou "pessoa com necessidades especiais" são considerados datados ou incorretos.
    * **Exemplos:** Pessoa cega, pessoa surda (ou Pessoa com Deficiência Auditiva), pessoa com baixa visão, pessoa autista, pessoa com deficiência intelectual.

* [ ] **Usar linguagem inclusiva e evitar capacitismo:**
    * **Por quê?** O capacitismo é o preconceito contra pessoas com deficiência. Muitas expressões comuns (ex: "dar uma de João-sem-braço", "que mancada", "estar cego de raiva") reforçam estereótipos negativos.
    * **Como:** Revise o texto e questione se as expressões usadas podem ser ofensivas ou excludentes. Promova uma comunicação respeitosa e consciente.

---

## 2. Textos (Clareza)

* [ ] **Usar textos simples, objetivos e de fácil compreensão:**
    * **Por quê?** Textos complexos, com jargões ou frases muito longas, são barreiras para pessoas com deficiência intelectual, dislexia, TDAH ou baixo letramento. A clareza beneficia *todos* os usuários.
    * **Como:**
        1.  Evite jargões, siglas (sem explicá-las na primeira vez) e figuras de linguagem.
        2.  Prefira a ordem direta (Sujeito -> Verbo -> Objeto).
        3.  Mantenha frases curtas (idealmente, 15-20 palavras) e parágrafos focados em um único tópico.

* [ ] **Evitar senso de urgência desnecessário:**
    * **Por quê?** Frases como "Corra, só hoje!" ou "Restam apenas 2 minutos!" podem gerar ansiedade e são uma barreira para pessoas que precisam de mais tempo para processar informações.
    * **Referência:** (WCAG SC 2.2.3 Sem Tempo)

---

## 3. Descrição de Imagens (Contexto)

Esta é a implementação do `alt` text que discutimos na seção `Desenvolvimento`.

* [ ] **Descrever o *significado* da imagem:**
    * **Por quê?** O `alt` text não é para descrever a imagem, é para descrever *por que* ela está ali.
    * **Como (Regra geral):**
        1.  **Contexto é tudo:** Um `alt` de uma foto do mesmo cachorro pode ser "Filhote de labrador preto" (em um site de adoção) ou "Exemplo de má iluminação em fotografia" (em um blog de fotografia).
        2.  **Seja conciso:** O `alt` text não é uma descrição detalhada (isso é para imagens complexas).
        3.  **Não inclua:** "imagem de...", "foto de..." — o leitor de tela já anuncia que é uma imagem.

* [ ] **Tratar imagens complexas (Gráficos, Mapas):**
    * **Por quê?** Um gráfico de pizza não pode ser descrito em um `alt` curto.
    * **Como:**
        1.  **No `alt`:** Forneça um resumo curto e indique onde a descrição longa está. Ex: `alt="Gráfico de pizza de vendas. Uma descrição detalhada segue abaixo."`
        2.  **No texto:** Logo abaixo da imagem, forneça a descrição longa ou os dados da tabela que gerou o gráfico.

---

## 4. Hiperlinks (Navegação)

* [ ] **Criar links descritivos e evitar "Clique Aqui":**
    * **Por quê?** Usuários de leitores de tela frequentemente usam um atalho para listar todos os links da página *fora de contexto*. Se a lista de links do seu site for "clique aqui", "clique aqui", "saiba mais", o usuário não tem a menor ideia do que se trata cada link.
    * **Como:** O texto do link deve fazer sentido isoladamente.
        ```html
        <p>Para baixar nosso relatório de 2025, <a href="...">clique aqui</a>.</p>

        <p>Você pode <a href="...">baixar nosso relatório de 2025</a>.</p>
        ```

---

## 5. Ícones e Emojis

* [ ] **Garantir que ícones tenham texto:**
    * **Por quê?** Um ícone é uma imagem. Sem um rótulo textual (visível ou para leitores de tela), ele é uma barreira. Um ícone de lupa é universal? E um de "salvar"? (Um disquete? Para quem tem 20 anos?).
    * **Como:**
        1.  **Ideal:** O ícone deve ser acompanhado de um texto visível (ex: `[Ícone de Lupa] Buscar`).
        2.  **Mínimo:** Se o ícone for um botão, ele *deve* ter um nome acessível (veja a seção `Desenvolvimento` sobre `aria-label` ou classe `.sr-only`).

* [ ] **Usar emojis com moderação:**
    * **Por quê?** Leitores de tela leem a descrição de cada emoji.
    * **Exemplo:** `"🎉🎉🎉 Grande Venda! 🎉🎉🎉"` será lido como: *"Lançador de confetes Lançador de confetes Lançador de confetes Grande Venda! Lançador de confetes Lançador de confetes Lançador de confetes"*... Isso é irritante e polui a comunicação.

---

## 6. Hashtags (Redes Sociais)

* [ ] **Usar `CamelCase` (ou `PascalCase`) em hashtags:**
    * **Por quê?** Um leitor de tela lê `#guiadeacessibilidade` como uma palavra única e impronunciável ("guiadacessibilidade").
    * **Como:** Use a primeira letra de cada palavra em maiúscula.
        ```
        #projetodeihc

        #ProjetoDeIHC
        ```
    * **Resultado:** O leitor de tela agora lê perfeitamente: "Hashtag Projeto de IHC".

---

## 7. Mídias (Áudio e Vídeo)

O gerador de conteúdo é responsável pelo roteiro e pelos materiais de apoio da mídia.

* [ ] **Fornecer legendas (Closed Captions):**
    * **Por quê?** Essencial para pessoas com deficiência auditiva ou para quem está em um ambiente barulhento (ou silencioso).
    * **Como:** As legendas devem ser sincronizadas e incluir sons não-verbais relevantes.
    * **Exemplo de Legenda:** `(Música tensa de fundo)` ou `[Porta batendo]`

* [ ] **Fornecer transcrição textual (Para áudio/podcasts):**
    * **Por quê?** Esta é a única forma de um usuário surdo-cego (que usa leitor de tela com Braille) acessar um podcast. Também é útil para quem prefere ler.
    * **Como:** A transcrição deve ser completa, incluindo quem está falando e sons relevantes, não apenas as falas.

* [ ] **Considerar Audiodescrição (Para vídeos):**
    * **Por quê?** Pessoas cegas não podem ver ações visuais que ocorrem sem diálogo.
    * **Como:** A audiodescrição é uma narração adicional, inserida nas pausas da fala, que descreve o que está acontecendo visualmente. (Ex: "A personagem se vira e olha pela janela.")