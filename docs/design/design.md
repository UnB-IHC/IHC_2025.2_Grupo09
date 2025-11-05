# Design

Existe uma crença comum de que tornar um site acessível o deixará simples ou visualmente pouco atrativo. Isso não é verdade. Um site bem estruturado pode ser, ao mesmo tempo, bonito, criativo e acessível.  
Com o uso de CSS, é possível criar diferentes apresentações visuais para uma mesma estrutura HTML, atendendo a diversas necessidades e preferências das pessoas usuárias.  

Nesta seção, apresenta-se um checklist com boas práticas para garantir a acessibilidade no design.

---

## Aparência

- [ ] Adicionar **instruções** que não dependam exclusivamente da cor. [[1]](#rp1)  
- [ ] Adicionar **informações** (como gráficos e diagramas) que não dependam exclusivamente da cor. [[1]](#rp1)  
- [ ] Garantir que o **tamanho do texto seja ajustável**, permitindo ampliação. [[2]](#rp2)  
- [ ] **Descrever controles** pelo nome, e não apenas pela aparência ou localização. [[3]](#rp3)  
- [ ] As **dicas visuais significativas** devem possuir contraste de, no mínimo, 3:1 em relação ao fundo. [[4]](#rp4)  
- [ ] As **linhas de texto** devem se ajustar corretamente ao *viewport*. [[5]](#rp5)  
- [ ] Oferecer uma **opção de alto contraste** (*dark mode*) e possibilidade de aumento de fontes.  
- [ ] Manter **parágrafos com, no máximo, 80 caracteres por linha**.  
- [ ] **Evitar** o uso de textos longos em **caixa alta** ou **condensados**.  
- [ ] Evitar o **alinhamento justificado**.  
- [ ] Utilizar **fontes fluidas** e de fácil leitura.  
- [ ] Ter cuidado ao utilizar `display: none` e `visibility: hidden`, pois esses recursos podem ocultar informações de tecnologias assistivas.  
- [ ] **Preferir botões com texto e ícone**; quando usar apenas ícones, garantir que tenham **nome acessível**.  

---

## Animação

- [ ] **Evitar conteúdo que pisque**; caso seja necessário, mantê-lo dentro dos limites recomendados. [[6]](#rp6)  
- [ ] **Permitir que pessoas usuárias controlem alterações automáticas de conteúdo**, pausando ou ocultando-as quando desejarem. [[7]](#rp7)  
- [ ] **Todas as animações** devem respeitar a consulta de mídia `prefers-reduced-motion`. [[8]](#rp8)  

---

## Contraste de cores

- [ ] **Verificar o contraste** de todo texto em tamanho normal. [[9]](#rp9)  
- [ ] **Verificar o contraste** de todo texto em tamanho grande. [[9]](#rp9)  
- [ ] **Verificar o contraste** de todos os ícones. [[4]](#rp4)  
- [ ] **Verificar o contraste** das bordas de elementos interativos (campos de texto, botões de opção, caixas de seleção etc.). [[4]](#rp4)  
- [ ] **Verificar o texto** sobreposto a imagens ou vídeos. [[9]](#rp9)  
- [ ] **Verificar cores personalizadas** aplicadas à pseudo-classe `::selection`. [[9]](#rp9)  

---

## Referências bibliográficas

1. [WCAG 2.2 – SC 1.4.1 Use of Color (Level A)](https://www.w3.org/WAI/WCAG22/Understanding/use-of-color.html) – Acesso em: 9 mai. 2024.  
2. [WCAG 2.2 – SC 1.4.4 Resize Text (Level AA)](https://www.w3.org/WAI/WCAG22/Understanding/resize-text.html) – Acesso em: 9 mai. 2024.  
3. [WCAG 2.2 – SC 1.3.3 Sensory Characteristics (Level A)](https://www.w3.org/WAI/WCAG22/Understanding/sensory-characteristics.html) – Acesso em: 9 mai. 2024.  
4. [WCAG 2.2 – SC 1.4.11 Non-text Contrast (Level AA)](https://www.w3.org/WAI/WCAG22/Understanding/non-text-contrast.html) – Acesso em: 9 mai. 2024.  
5. [WCAG 2.2 – SC 1.4.10 Reflow (Level AA)](https://www.w3.org/WAI/WCAG22/Understanding/reflow.html) – Acesso em: 9 mai. 2024.  
6. [WCAG 2.2 – SC 2.3.1 Three Flashes or Below Threshold (Level A)](https://www.w3.org/WAI/WCAG22/Understanding/three-flashes-or-below-threshold.html) – Acesso em: 9 mai. 2024.  
7. [WCAG 2.2 – SC 2.2.2 Pause, Stop, Hide (Level A)](https://www.w3.org/WAI/WCAG22/Understanding/pause-stop-hide.html) – Acesso em: 9 mai. 2024.  
8. [WCAG 2.2 – SC 2.3.3 Animation from Interactions (Level AAA)](https://www.w3.org/WAI/WCAG22/Understanding/animation-from-interactions.html) – Acesso em: 9 mai. 2024.  
9. [WCAG 2.2 – SC 1.4.3 Contrast (Minimum) (Level AA)](https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum.html) – Acesso em: 9 mai. 2024.  

---

## Bibliografia

DINIZ, V.; FERRAZ, R.; NASCIMENTO, C. M.; CREDIDIO, R.  
**Guia de Boas Práticas para Acessibilidade Digital.**  
Programa de Cooperação entre Reino Unido e Brasil em Acesso Digital, 2023.  
Disponível em: [Guia de Boas Práticas para Acessibilidade Digital (gov.br)](https://www.gov.br/governodigital/pt-br/acessibilidade-e-usuario/acessibilidade-digital/guiaboaspraaticasparaacessibilidadedigital.pdf).  
Acesso em: 9 mai. 2024.
