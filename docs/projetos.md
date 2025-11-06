# 1. Iniciação e o "Shift-Left"

> "Para que a acessibilidade digital possa impactar positivamente a vida de milhões de pessoas, ela deve ser pensada logo no início, na concepção do projeto..."

Esta prática de "pensar no início" é a base da gestão de projetos moderna e é conhecida como **"Shift-Left"** (Deslocamento à Esquerda).

Em vez de deixar a acessibilidade para o final (QA ou, pior, pós-lançamento), o "Shift-Left" a integra em *cada* etapa do ciclo de vida, começando pela **Iniciação** e **Concepção**. Isso não é apenas uma boa prática social; é a única forma economicamente viável de construir produtos robustos.

---

## Personas: A Base do "Shift-Left"

O "Shift-Left" começa com a empatia, e a ferramenta para isso são as **Personas**. Um projeto não pode atender a requisitos que não conhece.

O objetivo é garantir que a equipe não projete apenas para si mesma, mas para um espectro de usuários, incluindo (mas não se limitando a):

* **Pessoas com Deficiência Visual** (cegueira, baixa visão, daltonismo)
* **Pessoas com Deficiência Física/Motora** (fraqueza, tremores, paralisia, ausência de membros)
* **Pessoas com Deficiência Auditiva** (surdez, baixa audição, surdocegueira)
* **Pessoas com Deficiência na Fala**
* **Pessoas Neurodiversas** (Dislexia, TDAH, Autismo)
* **Pessoas com Limitações de Envelhecimento**
* **Pessoas com Analfabetismo Funcional ou Digital**

### Exemplo de Persona Acionável

Um *checklist* de deficiências não é o suficiente. Uma persona prática conecta a *necessidade* do usuário a um *requisito técnico* do guia.

> **Persona Exemplo: João (Baixa Visão e Motora)**
>
> * **Nome:** João, 68 anos.
> * **Perfil:** Aposentado, usa o smartphone para ver fotos da família e pagar contas.
> * **Contexto:** Tem baixa visão (usa óculos, precisa de fontes grandes) e artrite (tremores leves, dificuldade com cliques em alvos pequenos).
> * **Necessidade (Requisito):** O aplicativo precisa ter:
>     1.  Fontes que respeitem o zoom do sistema (**SC 1.4.4 Resize Text**).
>     2.  Botões e links com uma área de toque de no mínimo **24x24 pixels** (**SC 2.5.8 Target Size (Minimum)** da WCAG 2.2).

---

## 2. Conscientização (Argumentos para o "Buy-in")

Para que o "Shift-Left" funcione, a equipe e os *stakeholders* (clientes, diretoria) precisam estar convencidos. Para obter o "buy-in" (a adesão) do projeto, use os seguintes argumentos:

* [ ] **O Argumento 10x (Custo da Correção):** Este é o argumento de gestão mais importante. Corrigir um problema de acessibilidade custa:
    * **1x** na fase de **Design**.
    * **10x** na fase de **Desenvolvimento**.
    * **100x** após o **Lançamento** (incluindo suporte, retrabalho e risco legal).
* [ ] **O Argumento Legal (Legislação):** No Brasil, a acessibilidade digital não é opcional. Ela é lei (LBI - Lei Brasileira de Inclusão) e é suportada por documentos como:
    * *A Convenção sobre os Direitos das Pessoas com Deficiência.*
    * *Portaria nº 3, de 7 de maio de 2007* (que institucionalizou o eMAG).
* [ ] **O Argumento Populacional (Público):** A quantidade de pessoas com deficiência no Brasil (último censo do IBGE) e no mundo (OMS). Este é um mercado consumidor vasto e frequentemente ignorado.
* [ ] **O Argumento de Mercado (Software):** A análise do tamanho do mercado de software de acessibilidade digital (como os relatórios da *Mordor Intelligence*). Isso mostra que a acessibilidade é um setor em crescimento e uma vantagem competitiva.

---

## 3. Planejamento (O "Definition of Done" de Acessibilidade)

A gestão falha quando a acessibilidade é uma "tarefa" vaga. Ela deve ser integrada aos rituais da equipe (Sprint, Kanban, etc.) através de uma **"Definition of Done" (DoD)** clara.

"Done" (Concluído) não significa "funciona no meu computador". "Done" significa "funciona para todos".

### Exemplos de "Definition of Done" por Etapa

Use estes itens como critérios de aceite em suas tarefas:

* [ ] **DoD para Design:**
    * "Nenhum protótipo de alta fidelidade é aprovado sem passar na verificação de **contraste de cores (mínimo 4.5:1)**."
    * "Todos os fluxos foram validados contra as Personas de acessibilidade (ex: João consegue usar os botões de 24x24px?)."
* [ ] **DoD para Desenvolvimento:**
    * "Nenhuma *feature* é movida para 'Testes' se falhar na auditoria automática do **Lighthouse (mínimo de 90% em Acessibilidade)**."
    * "A funcionalidade é **100% operável via teclado** (navegação por Tab, Enter, Espaço)."
    * "O HTML é semântico (uso correto de `<h1>`, `<main>`, `<nav>`, `<label>`)."
* [ ] **DoD para QA (Testes):**
    * "Nenhum *ticket* é fechado sem ter sido testado manualmente com **pelo menos um leitor de tela** (NVDA ou VoiceOver)."
    * "A funcionalidade foi testada com zoom de 200% e 400% (Reflow) sem quebra de layout."
* [ ] **DoD para Geração de Conteúdo:**
    * "Nenhum vídeo é publicado sem **legendas (CC)**."
    * "Nenhum podcast é publicado sem **transcrição textual**."
    * "Nenhum link usa 'clique aqui'."