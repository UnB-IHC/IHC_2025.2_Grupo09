# Desenvolvimento

Nesta fase, é essencial garantir que a equipe de desenvolvimento compreenda como **implementar a acessibilidade**, **verificá-la** e **utilizar as ferramentas disponíveis** no mercado para testes e padronizações.  
Também é importante que os desenvolvedores conheçam as formas como **pessoas com deficiência** utilizam sites e aplicativos.  
Assim, foram incluídas técnicas relacionadas ao desenvolvimento e formas de verificação.

---

## Imagens
- [ ] **Adicionar `alt`** para imagens, botões-imagem, gráficos e imagens de mapas com pontos de acesso. <a id="TEC1" href="#RP1">[1]</a>  
- [ ] **Adicionar `alt=""`** para imagens decorativas sem significado. <a id="TEC1" href="#RP1">[1]</a>  
- [ ] **Incluir descrição no `alt`** para imagens que contêm texto. <a id="TEC1" href="#RP1">[1]</a>  

## Vídeos
- [ ] **Adicionar legendas** para o áudio em vídeos. <a id="TEC2" href="#RP2">[2]</a>  
- [ ] **Evitar conteúdo com *flashes*** (gatilhos para convulsões) ou mantê-los abaixo dos limites. <a id="TEC3" href="#RP3">[3]</a>  

## Controles
- [ ] **Adicionar `href`** para links. <a id="TEC4" href="#RP4">[4]</a>  
- [ ] **Aplicar sublinhado (underline)** em links. <a id="TEC5" href="#RP5">[5]</a>  
- [ ] **Adicionar estados de foco** em campos de entrada, botões e elementos interativos. <a id="TEC6" href="#RP6">[6]</a>  
- [ ] **Definir `type="button"`** em botões. <a id="TEC4" href="#RP4">[4]</a>  
- [ ] **Adicionar skip-link** (link para pular diretamente ao conteúdo principal). <a id="TEC7" href="#RP7">[7]</a>  
- [ ] **Identificar e avisar** quando um link abrir em nova aba ou janela. <a id="TEC8" href="#RP8">[8]</a>  

## Formulários
- [ ] **Adicionar `label`** aos campos de entrada, associando-os corretamente ao elemento correspondente. <a id="TEC9" href="#RP9">[9]</a>  
- [ ] **Utilizar `<fieldset>` e `<legend>`** para organizar seções do formulário. <a id="TEC4" href="#RP4">[4]</a>  
- [ ] **Adicionar `autocomplete`** aos campos de entrada. <a id="TEC10" href="#RP10">[10]</a>  
- [ ] **Exibir mensagens de erro (`errors`)** acima do formulário após o envio. <a id="TEC11" href="#RP11">[11]</a>  
- [ ] **Adicionar `aria-describedby`** para relacionar campos de entrada a descrições auxiliares. <a id="TEC11" href="#RP11">[11]</a>  
- [ ] **Exibir mensagens de erro e sucesso** de forma acessível, não apenas visualmente. <a id="TEC5" href="#RP5">[5]</a>  

## Mídia
- [ ] **Impedir `autoplay`** em vídeos e áudios. <a id="TEC12" href="#RP12">[12]</a>  
- [ ] **Definir `type`** para botões e entradas. <a id="TEC4" href="#RP4">[4]</a>  
- [ ] **Adicionar opção de pausa** para todas as mídias. <a id="TEC13" href="#RP13">[13]</a>  
- [ ] **Fornecer transcrição** para conteúdos em áudio. <a id="TEC1" href="#RP1">[1]</a>  

## Semântica
- [ ] Utiliza **elementos nativos HTML**.  
- [ ] Mantém **fluxo contínuo e lógico**.  
- [ ] Apresenta **descrições compreensíveis**.  
- [ ] Possui **semântica adequada**.  
- [ ] É **objetivo** nos **rótulos** e identificações.  

## Texto
- [ ] **Evitar** textos inseridos em **imagens**.  
- [ ] **Permitir redimensionamento** do texto em até **200% de zoom**.  
- [ ] **Altura da fonte** não deve ser fixa.  

## Teclado
- [ ] Todas as **funcionalidades** da página são **acessíveis por teclado**.  
- [ ] Quando houver **mouseover**, deve ser possível **uso via teclado**.  
- [ ] **Foco visível:** remover elementos focalizáveis invisíveis.  
- [ ] **Adicionar `.hover, .focus { }`** para tornar o foco perceptível.  
- [ ] **Permitir atalhos de teclado**, como o `TAB`.  
- [ ] O **primeiro item interativo** deve ser um link para o **conteúdo principal**.  

## Títulos
- [ ] A **hierarquia de conteúdo** segue **lógica semântica**, não apenas o tamanho da fonte. <a id="TEC17" href="#RP17">[17]</a>  
- [ ] Usar **elementos de título (`h1`, `h2`, `h3`)** para estruturar o conteúdo. <a id="TEC17" href="#RP17">[17]</a>  
- [ ] **Não pular níveis lógicos**.  
- [ ] Toda página deve conter um **título principal (`h1`)** que descreva seu conteúdo. <a id="TEC17" href="#RP17">[17]</a><a id="TEC19" href="#RP19">[19]</a>  

## Tabelas
- [ ] **Usar `table`** apenas para dados tabulares. <a id="TEC4" href="#RP4">[4]</a>  
- [ ] **Inserir cabeçalhos (`th`)** com atributo **`scope`** adequado. <a id="TEC15" href="#RP15">[15]</a>  
- [ ] **Utilizar `caption`** para fornecer um título descritivo à tabela. <a id="TEC17" href="#RP17">[17]</a>  

## Modais
- [ ] Deve ser **fácil de fechar**. <a id="TEC19" href="#RP19">[19]</a>  
- [ ] **Permitir uso da tecla `ESC`** para fechamento. <a id="TEC19" href="#RP19">[19]</a>  
- [ ] A interação deve ser **simples e direta**. <a id="TEC19" href="#RP19">[19]</a>  
- [ ] **Evitar modais em tela cheia**. <a id="TEC19" href="#RP19">[19]</a>  
- [ ] **Não abrir um modal a partir de outro modal**. <a id="TEC19" href="#RP19">[19]</a>  

## Dispositivos móveis e toque
- [ ] O site deve **funcionar em qualquer orientação** (retrato ou paisagem). <a id="TEC15" href="#RP15">[15]</a>  
- [ ] **Evitar rolagem horizontal**. <a id="TEC16" href="#RP15">[16]</a>  
- [ ] **Garantir que botões e links sejam facilmente acionáveis**. <a id="TEC18" href="#RP18">[18]</a>  
- [ ] **Assegurar espaço suficiente** entre elementos interativos. <a id="TEC7" href="#RP7">[7]</a>  

## Ferramentas e extras
- [ ] Permitir **pausar, parar ou ocultar** conteúdo em movimento.  
- [ ] Utilizar **breadcrumbs** para indicar a localização atual do usuário.  
- [ ] Disponibilizar **página ou seção de ajuda** com dúvidas e dicas de acessibilidade.  
- [ ] Garantir que **áreas clicáveis** tenham no mínimo **44x44 pixels**.  
- [ ] Nos casos de **CAPTCHA**, assegurar que sejam **compreensíveis** e possuam **alternativas acessíveis**.  
- [ ] **Incluir campo de busca** na interface.  

---

## Referência Bibliográfica

> <a id="RP1" href="#TEC1">1.</a> WCAG 2.2 Understanding Docs. SC 1.1.1 Non-text Content (Level A) . Disponível em: [https://www.w3.org/WAI/WCAG22/Understanding/non-text-content.html](https://www.w3.org/WAI/WCAG22/Understanding/non-text-content.html). Acesso em: 9 Mai. 2024.

> <a id="RP2" href="#TEC2">2.</a> WCAG 2.2 Understanding Docs. SC 1.2.2 Captions (Prerecorded) (Level A). Disponível em: [https://www.w3.org/WAI/WCAG22/Understanding/captions-prerecorded.html](https://www.w3.org/WAI/WCAG22/Understanding/captions-prerecorded.html). Acesso em: 9 Mai. 2024.

> <a id="RP3" href="#TEC3">3.</a> WCAG 2.2 Understanding Docs. SC 2.3.1 Three Flashes or Below Threshold (Level A). Disponível em: [https://www.w3.org/WAI/WCAG22/Understanding/three-flashes-or-below-threshold.html](https://www.w3.org/WAI/WCAG22/Understanding/three-flashes-or-below-threshold.html). Acesso em: 9 Mai. 2024.

> <a id="RP4" href="#TEC4">4.</a> WCAG 2.2 Understanding Docs. SC 1.3.1 Info and Relationships (Level A). Disponível em: [https://www.w3.org/WAI/WCAG22/Understanding/info-and-relationships.html](https://www.w3.org/WAI/WCAG22/Understanding/info-and-relationships.html). Acesso em: 9 Mai. 2024.

> <a id="RP5" href="#TEC5">5.</a> WCAG 2.2 Understanding Docs. SC 1.4.1 Use of Color (Level A). Disponível em: [https://www.w3.org/WAI/WCAG22/Understanding/use-of-color.html](https://www.w3.org/WAI/WCAG22/Understanding/use-of-color.html). Acesso em: 9 Mai. 2024.

> <a id="RP6" href="#TEC6">6.</a> WCAG 2.2 Understanding Docs. SC 2.4.7 Focus Visible (Level AA). Disponível em: [https://www.w3.org/WAI/WCAG22/Understanding/focus-visible.html](https://www.w3.org/WAI/WCAG22/Understanding/focus-visible.html). Acesso em: 9 Mai. 2024.

> <a id="RP7" href="#TEC7">7.</a> WCAG 2.2 Understanding Docs. SC 2.4.1 Bypass Blocks (Level A). Disponível em: [https://www.w3.org/WAI/WCAG22/Understanding/bypass-blocks.html](https://www.w3.org/WAI/WCAG22/Understanding/bypass-blocks.html). Acesso em: 9 Mai. 2024.

> <a id="RP8" href="#TEC8">8.</a> WCAG 2.2 Understanding Docs. G201 Giving users advanced warning when opening a new window. Disponível em: [https://www.w3.org/WAI/WCAG22/Techniques/general/G201](https://www.w3.org/WAI/WCAG22/Techniques/general/G201). Acesso em: 9 Mai. 2024.

> <a id="RP9" href="#TEC9">9.</a> WCAG 2.2 Understanding Docs. SC 3.2.2 On Input (Level A). Disponível em: [https://www.w3.org/WAI/WCAG22/Understanding/on-input.html](https://www.w3.org/WAI/WCAG22/Understanding/on-input.html). Acesso em: 9 Mai. 2024.

> <a id="RP10" href="#TEC10">10.</a> WCAG 2.2 Understanding Docs. SC 1.3.5 Identify Input Purpose (Level AA). Disponível em: [https://www.w3.org/WAI/WCAG22/Understanding/identify-input-purpose.html](https://www.w3.org/WAI/WCAG22/Understanding/identify-input-purpose.html). Acesso em: 9 Mai. 2024.

> <a id="RP11" href="#TEC11">11.</a> WCAG 2.2 Understanding Docs. SC 3.3.1 Error Identification (Level A). Disponível em: [https://www.w3.org/WAI/WCAG22/Understanding/error-identification.html](https://www.w3.org/WAI/WCAG22/Understanding/error-identification.html). Acesso em: 9 Mai. 2024.

> <a id="RP12" href="#TEC12">12.</a> WCAG 2.2 Understanding Docs. SC 1.4.2 Audio Control (Level A). Disponível em: [https://www.w3.org/WAI/WCAG22/Understanding/audio-control.html](https://www.w3.org/WAI/WCAG22/Understanding/audio-control.html). Acesso em: 9 Mai. 2024.

> <a id="RP13" href="#TEC13">13.</a> WCAG 2.2 Understanding Docs. SC 2.1.1 Keyboard (Level A). Disponível em: [https://www.w3.org/WAI/WCAG22/Understanding/keyboard.html](https://www.w3.org/WAI/WCAG22/Understanding/keyboard.html). Acesso em: 9 Mai. 2024.

> <a id="RP14" href="#TEC14">14.</a> WCAG 2.2 Understanding Docs. SC 1.3.4 Orientation (Level AA). Disponível em: [https://www.w3.org/WAI/WCAG22/Understanding/orientation.html](https://www.w3.org/WAI/WCAG22/Understanding/orientation.html). Acesso em: 9 Mai. 2024.

> <a id="RP15" href="#TEC15">15.</a> WCAG 2.2 Understanding Docs. SC 4.1.1 Orientation (Level). Disponível em: [https://www.w3.org/WAI/WCAG22/Understanding/parsing.html](https://www.w3.org/WAI/WCAG22/Understanding/parsing.html). Acesso em: 9 Mai. 2024.

> <a id="RP16" href="#TEC16">16.</a> WCAG 2.2 Understanding Docs. SC 1.4.10 Reflow (Level AA). Disponível em: [https://www.w3.org/WAI/WCAG22/Understanding/reflow.html](https://www.w3.org/WAI/WCAG22/Understanding/reflow.html). Acesso em: 9 Mai. 2024.

> <a id="RP17" href="#TEC17">17.</a> WCAG 2.2 Understanding SC 2.4.6 Headings and Labels (Level AA). Disponível em: [https://www.w3.org/WAI/WCAG22/Understanding/headings-and-labels.html](https://www.w3.org/WAI/WCAG22/Understanding/headings-and-labels.html). Acesso em: 9 Mai. 2024.

> <a id="RP18" href="#TEC18">18.</a> WCAG 2.2 Understanding Docs. SC 2.5.5 Target Size (Enhanced) (Level AAA). Disponível em: [https://www.w3.org/WAI/WCAG22/Understanding/target-size-enhanced.html](https://www.w3.org/WAI/WCAG22/Understanding/target-size-enhanced.html). Acesso em: 9 Mai. 2024.

> <a id="RP19" href="#TEC19">19.</a> GUIA DE BOAS PRÁTICAS PARA ACESSIBILIDADE DIGITAL. Disponível em: [https://www.w3.org/WAI/WCAG22/Understanding/target-size-enhanced.html](https://www.w3.org/WAI/WCAG22/Understandin/target-size-enhanced.html). Acesso em: 9 Mai. 2024.

---

## Bibliografia
> DINIZ, V.; FERRAZ, R.; NASCIMENTO, C. M.; CREDIDIO, R. *Guia de Boas Práticas para Acessibilidade Digital*. Programa de Cooperação entre Reino Unido e Brasil em Acesso Digital, 2023.  
> Disponível em: [https://www.gov.br/governodigital/pt-br/acessibilidade-e-usuario/acessibilidade-digital/guiaboaspraaticasparaacessibilidadedigital.pdf](https://www.gov.br/governodigital/pt-br/acessibilidade-e-usuario/acessibilidade-digital/guiaboaspraaticasparaacessibilidadedigital.pdf).  
> Acesso em: 9 mai. 2024.