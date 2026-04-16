# Auditoria de Conversão — GETEC 2026

> Arquivo analisado: `index.html`
> Objetivo de conversão: inscrição no evento (link SUAP externo)
> Público-alvo: estudantes IFTO, comunidade acadêmica, empresas parceiras
> Data: 2026-04-10

## Resumo Executivo

| Severidade   | Qtd | Pilares afetados       |
|--------------|-----|------------------------|
| 🔴 Crítico   | 3   | 1, 4, 6                |
| 🟡 Atenção   | 5   | 2, 3, 5, 8, 10         |
| 🟢 OK        | 2   | 7, 9                   |

**Top 3 correções prioritárias:**
1. Reescrever H1 do hero para comunicar claramente "o quê + quando + para quem" em vez de só o tema conceitual (Pilar 1).
2. Adicionar countdown, contador de vagas ou prova social (nº de inscritos, edições anteriores, depoimentos) próximo ao CTA principal (Pilar 6).
3. Unificar a copy/estilo do CTA primário — hoje existem 3 variações visuais diferentes ("Inscrições", "Garantir Vaga", "INSCRIÇÕES" azul) (Pilares 4 e 9).

---

## Análise Pilar por Pilar

### Pilar 1 — Clarity Over Creativity
**Status:** 🔴

**Micro-Rule (teste dos 5s):** Um visitante vê "Economia Circular e Objetivos do Desenvolvimento Sustentável" como manchete. Não fica claro em 5s que isto é um **evento acadêmico presencial**, nem o que o usuário ganha ao participar. O badge pequeno acima ("Gestão da Produção Industrial • IFTO Araguaína") é a única pista e compete com o gradiente colorido do H1.

**Observações:**
- H1 (`index.html:263-268`) é sobre o **tema**, não sobre o **evento**. Um leitor apressado pode achar que é um artigo ou um curso.
- A natureza do evento (congresso? semana acadêmica? feira?) não aparece acima da dobra.
- Data e local aparecem só como "metadados" em ícones pequenos (`index.html:275-294`), competindo com o círculo decorativo de ODS.

**Correções recomendadas:**
- Trocar o H1 para algo como: "GETEC 2026 — 3 dias de imersão em Economia Circular e ODS no IFTO Araguaína" e usar o atual conceito como subtítulo.
- Elevar a data (27–29 de maio) ao nível de destaque visual, ao lado do H1.
- Adicionar 1 linha explicando o formato: "Palestras, mesa-redonda, mostra de pesquisa e lançamento de livro".

---

### Pilar 2 — Strong Visual Hierarchy
**Status:** 🟡

**Micro-Rule (blur):** Ao desfocar, o elemento mais proeminente do hero é o **círculo decorativo à direita com os pontos coloridos de ODS girando**, não o CTA "Garantir Vaga". O círculo rouba o foco por tamanho, animação e cor.

**Observações:**
- O gradiente verde→azul aplicado à palavra "Circular" (`index.html:264-265`) compete com o botão primário pela atenção.
- Botões "Garantir Vaga" e "Ver Programação" (`index.html:296-308`) têm peso visual quase equivalente — o secundário não está suficientemente subordinado.
- Na seção de cards "Propósito" (`index.html:368-419`), todos os 3 cards têm hierarquia idêntica, sem um "primeiro entre iguais".

**Correções recomendadas:**
- Reduzir tamanho/opacidade do círculo ODS animado ou movê-lo para plano de fundo.
- Transformar "Ver Programação" em link de texto com seta, não em botão com borda.
- Aumentar contraste do botão primário (sombra mais forte, talvez cor `act` azul para unificar com o CTA final).

---

### Pilar 3 — Single Primary Goal per Page
**Status:** 🟡

**Contagem de elementos clicáveis não-CTA:** ~11 (4 links de menu desktop, 4 links de menu mobile duplicados, 3 cards "cursor-pointer" sem destino, links do footer, Instagram, LabSIS). **Limite recomendado: ≤5**.

**Observações:**
- Os cards do "Propósito" e do "Público" têm `cursor-pointer` mas não são clicáveis — falsa promessa de interação (`index.html:370, 385, 406, 440, 448, 457`).
- Footer tem link para LabSIS que ocupa 1/3 da largura, competindo visualmente com os links institucionais.
- Link Instagram aparece 2x (timeline do evento realizado + footer).

**Correções recomendadas:**
- Remover `cursor-pointer` dos cards não-clicáveis.
- Fazer toda a página convergir para "Inscreva-se" — o botão "Inscrições" sticky no header deve ter a mesma cópia e cor em todos os pontos.
- Minimizar o bloco LabSIS no footer (logo pequeno + link, sem card destacado).

---

### Pilar 4 — Obvious Calls to Action
**Status:** 🔴

**CTA primário acima da dobra?** Sim (2 instâncias: header + hero).
**Copy do CTA atual:** "Inscrições" / "Garantir Vaga" / "INSCRIÇÕES" (inconsistente).
**Cor do CTA contrasta com fundo?** Parcial — o botão verde `brand-600` se dilui no hero verde-claro `bg-pattern`.

**Observações:**
- Três CTAs, três estilos: header verde, hero verde com ícone, final azul `act` grande. Gera confusão.
- "Garantir Vaga" no hero é uma boa copy outcome-oriented, mas não é replicada — o header usa "Inscrições" (genérico).
- O CTA final (`index.html:764-768`) é o mais visualmente forte de toda a página, mas aparece DEPOIS do bloco de contato, longe demais do hero.

**Correções recomendadas:**
- Padronizar copy: **"Garantir minha vaga"** em todos os CTAs.
- Padronizar cor: usar `act` (azul ciano) em todos — destaca sobre qualquer fundo verde.
- Adicionar um CTA sticky mobile (bottom bar) visível durante toda a rolagem.
- Mover/duplicar o bloco "INSCRIÇÕES" azul para logo após a Programação, quando o interesse está no pico.

---

### Pilar 5 — Low Cognitive Load
**Status:** 🟡

**Observações:**
- Decorações excessivas no hero: gradiente + pattern de pontos + círculos animados + glow blur + cards com borda + badge. Ruído visual alto.
- Barra ODS de 17 cores no topo e no footer (`index.html:176-194, 895-912`) — bonita, mas só distrai o olho do H1/CTA.
- Programação do dia "pré-evento" já realizado (08 de Abril) aparece em primeiro lugar com tag "Realizado" (`index.html:482-516`), forçando o usuário a processar informação irrelevante antes de chegar às datas futuras.

**Correções recomendadas:**
- Mover o card "Realizado" para o final da timeline ou escondê-lo sob um "Ver evento anterior".
- Reduzir a barra ODS de topo a 4px de altura e remover a do footer.
- Simplificar o hero: escolher UM elemento decorativo (o círculo OU o pattern, não ambos).

---

### Pilar 6 — Trust Before Persuasion
**Status:** 🔴

**Trust signals presentes:**
- [ ] Depoimentos com nome/cargo/foto — **ausente**
- [x] Logos de parceiros — presente (marquee), mas longe do CTA principal
- [ ] Pricing transparente — N/A (evento pode ser gratuito, mas isso não está dito!)
- [x] Contato físico — presente (endereço, telefone, e-mail)
- [ ] Números específicos (edições anteriores, nº de inscritos, capacidade) — **ausente**

**Observações:**
- **Não está claro se o evento é gratuito ou pago.** Isto é a maior fricção de confiança possível para um evento acadêmico.
- Não há menção de edições anteriores, quantos alunos participaram, fotos de eventos passados (apenas um card "Realizado").
- Os parceiros aparecem em marquee decorativo, mas não estão amarrados ao CTA.
- Coordenadora é citada por nome (ótimo), mas sem foto/cargo formal.

**Correções recomendadas:**
- **Adicionar imediatamente no hero: "Evento gratuito • Certificado incluso"** (ou os termos reais).
- Adicionar contador/prova social: "Mais de X inscritos", "5ª edição", "X horas de certificação".
- Incluir 1-2 depoimentos de ex-participantes ou de um professor com foto.
- Posicionar a barra de parceiros IMEDIATAMENTE antes do CTA final, com um título tipo "Apoiado por empresas da região".

---

### Pilar 7 — Mobile-First Design
**Status:** 🟢

**Observações:**
- Tap targets adequados (botões `py-3`/`py-4`, header com `h-20`).
- Menu mobile funcional com toggle (`index.html:921-928`).
- Hero responsivo com stacking vertical.
- Timeline da programação adapta-se ao mobile.

**Observações de atenção:**
- O ícone `recycle` no círculo ODS é escondido em mobile (`hidden sm:block`) — OK.
- Nenhum CTA fixo/sticky no rodapé mobile — oportunidade perdida.

**Correções recomendadas:**
- Adicionar barra sticky bottom no mobile com "Garantir vaga" sempre visível durante rolagem.

---

### Pilar 8 — Speed and Performance
**Status:** 🟡

**Observações:**
- **Tailwind via CDN** (`index.html:14`) — deveria ser build local com purge. Penaliza LCP.
- **Lucide via CDN unpkg** (`index.html:55`) — idem.
- 2 famílias de fontes do Google Fonts com múltiplos pesos/itálicos (`index.html:50-52`) — pesado.
- Imagens de parceiros em `.jpeg` e `.png` (`Lumina.jpeg`, `pai-filho.jpeg`, vários `.png`) — inconsistente com os `.webp`.
- Marquee infinito de 22 imagens (11 × 2) — renderiza todas sempre.

**Correções recomendadas:**
- Buildar Tailwind localmente com purge.
- Importar só os ícones Lucide usados (tree-shaking), ou usar SVGs inline.
- Limitar Crimson Pro a 1-2 pesos (ex.: 600 e 700), sem itálicos se não forem usados.
- Converter todos logos de parceiros para `.webp` e adicionar `loading="lazy"`.
- Adicionar `fetchpriority="high"` e `width`/`height` na logo do header.

---

### Pilar 9 — Consistency
**Status:** 🟢 (com ressalvas)

**Observações:**
- Fontes: 2 (Atkinson Hyperlegible + Crimson Pro) — correto, 1 sans + 1 serif.
- Paleta brand bem definida no `tailwind.config`.
- Inconsistência: cor primária alterna entre `brand-600` (verde) e `act` (azul ciano) em CTAs — não está claro qual é "o" primário.
- Copy dos CTAs varia: "Inscrições", "Garantir Vaga", "INSCRIÇÕES".
- Espaçamento das seções é consistente (`py-20`).

**Correções recomendadas:**
- Decidir UMA cor para todos os CTAs de conversão (recomendo `act` por ter maior contraste sobre o fundo verde do hero).
- Padronizar copy em **uma única string** para todos os CTAs.

---

### Pilar 10 — Feedback and Reassurance
**Status:** 🟡

**Observações:**
- Botões têm `hover:` states — ✅
- Nenhum estado de loading (página é estática, mas o link externo para o SUAP abre em nova aba sem aviso — pode assustar o usuário que acha que "perdeu" o site).
- Não há página de sucesso ou confirmação de inscrição própria (depende do SUAP).
- Menu mobile não tem indicação visual do item ativo.

**Correções recomendadas:**
- Adicionar `target="_blank"` explícito + ícone de link externo em TODOS os botões de inscrição (já presente em 1 de 3).
- Adicionar microcopy abaixo do CTA: "Você será redirecionado para o SUAP/IFTO — leva menos de 2 minutos".
- Marcar o link do menu ativo com `aria-current` e destaque visual durante o scroll (scroll-spy).

---

## Plano de Ação Priorizado

### Sprint 1 — Correções Críticas (🔴)
1. **Reescrever o H1** para deixar claro "evento, quando, para quem" — Pilar 1.
2. **Declarar gratuidade e trust signals** próximos ao CTA (gratuito / certificado / nº de inscritos) — Pilar 6.
3. **Unificar CTA** (copy + cor + estilo) — Pilares 4 e 9.

### Sprint 2 — Correções de Atenção (🟡)
1. Esconder ou mover o card "Realizado" da programação — Pilar 5.
2. Reduzir decoração do hero (escolher 1 elemento visual) — Pilares 2 e 5.
3. Build local do Tailwind, ícones tree-shaken, imagens lazy — Pilar 8.
4. Adicionar microcopy de redirecionamento no CTA — Pilar 10.
5. CTA sticky bottom no mobile — Pilares 4 e 7.

### Sprint 3 — Refinamentos (🟢 → 🌟)
1. Depoimentos/fotos de edições anteriores.
2. Scroll-spy no menu.
3. Contador regressivo para 27 de maio.

---

## Notas Finais

O site tem **fundamentos sólidos** (mobile ok, paleta coesa, estrutura semântica limpa) mas sofre de **síndrome de evento acadêmico**: fala mais sobre o tema do que sobre o evento em si, esconde informações práticas (é grátis?), e distribui a atenção do usuário entre decorações bonitas em vez de concentrá-la no "clicar em inscrever". As correções críticas são todas de **copy e posicionamento**, não de redesign — podem ser feitas em 1 sprint curto sem reestruturação.
