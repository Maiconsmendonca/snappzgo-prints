# Design System: SnappzGo

> App mobile (Android, pt-BR) de **gestão financeira e semáforo de corridas** para motoristas de app (Uber/99/inDrive/iFood). Não é site: não existe "hero", "scroll to explore" nem seções de marketing. São **telas de utilidade densas** que o motorista usa no trânsito — tudo precisa ser legível de relance, com toque grande.
>
> **Use este documento como fonte única da verdade.** As telas de referência (capturas reais do app) estão em `full/` deste repositório — gere cada tela para ficar **igual em estrutura** à referência, só elevando o acabamento visual conforme as regras abaixo. **Não invente telas, não varie layouts, não adicione seções que a referência não tem.**

---

## 1. Atmosfera visual

Balanceada e confiante, não minimalista-gélida nem "fruteira". Densidade **5–6** (app de uso diário com muitos números), variância **3** (previsível e consistente — o motorista precisa achar as coisas sempre no mesmo lugar), motion **3–4** (sóbrio; transições curtas, nada cinematográfico).

O caráter da marca é **teal profundo + âmbar** (o "Snappz" verde-azulado e o "**Go**" âmbar). A estrutura (cabeçalhos, botões primários, destaques) deve carregar **cor de verdade** — teal e âmbar — e cada família de função tem um **chip de ícone colorido** próprio. O erro a evitar é o oposto da fruteira: **tela inteira verde/branca, monocromática**. Traga cor na própria estrutura, de forma disciplinada (regra na seção 2).

Cada **hub** abre com um **cabeçalho escuro** (faixa teal com degradê) + corpo claro. Cards brancos arredondados com sombra suave. Sensação: **painel de bordo limpo e caloroso**, não planilha fria.

---

## 2. Paleta de cores e papéis

### Marca (estrutura)
- **Teal Profundo** (`#0F766E`) — cor primária: botões primários, estados ativos, faixa de cabeçalho, anel da meta, texto de destaque positivo.
- **Teal Noite** (`#10302B`) — topo do degradê do cabeçalho do hub e cartões escuros (meta, "corrida mínima").
- **Teal Claro** (`#115E57`) — base do degradê do cabeçalho (vai de Teal Noite → Teal Claro na diagonal).
- **Âmbar Go** (`#F59E0B`) — acento secundário **real** da marca (o "Go"): usado em **combustível/abastecer**, avisos de atenção, e um highlight pontual. É cor de marca, não decoração.

### Neutros
- **Creme Papel** (`#F2F3EF`) — fundo principal das telas (off-white morno, **nunca** branco puro de fundo).
- **Branco Superfície** (`#FFFFFF`) — preenchimento de cards e campos.
- **Tinta Grafite** (`#13211C`) — texto primário (quase-preto esverdeado; **nunca** `#000000`).
- **Cinza Aço** (`#5C6B63`) — texto secundário, legendas, metadados.
- **Borda Névoa** (`#E4E6E0`) — linhas de 1px, bordas de campo, divisores.

### Semáforo (estado — não é enfeite, é informação)
- **Vermelho Vivo** (`#EF4444`) — corrida ruim / prejuízo / conta atrasada / valor negativo.
- **Amarelo Real** (`#F2C200`) — atenção (amarelo de verdade, **não** laranja).
- **Verde Vivo** (`#10B981`) — corrida boa / lucro / dentro da meta.

> As três cores do semáforo são sagradas: aparecem como **faixas em slider**, **bordas de badge de plataforma** e **pontos de status**. Mantenha-as saturadas e distintas. O amarelo é amarelo, nunca laranja.

### Chips de ícone por categoria (a cor "disciplinada")
Cada item de menu / título de card tem um **chip quadrado arredondado** (≈44px, canto 12px) com **fundo pastel** + **glyph na cor forte**. **O mapeamento é FIXO** — a mesma função usa sempre a mesma cor (é isso que evita a fruteira):

| Função | Fundo pastel | Glyph |
|---|---|---|
| Leitor / semáforo / meta | teal `#D7E8E4` | `#0F766E` |
| Metas / faixas / ganhos | verde `#D6EFDE` | `#10B981` |
| Calculadora / "vale a pena" | âmbar `#FBE7C2` | `#C77F0E` |
| Dinheiro / carteira / contas | âmbar claro `#FBEFD4` | `#C77F0E` |
| Sons / voz / balão | azul `#DCE4F5` | `#3B5BC4` |
| Histórico / ofertas / previsão / raio-X | roxo `#E7E2F5` | `#6D54C4` |
| Horários / tempo | teal claro `#D2EDE8` | `#0E8574` |
| Mapa / zonas / localização | vermelho suave `#F7DCDC` | `#E0493C` |
| Carro / combustível | âmbar `#FBE7C2` | `#C77F0E` |
| Genérico / sistema | cinza `#E6E8E3` | `#5C6B63` |

**Proibido:** usar cores de categoria fora dos chips e de marcadores de seção (não pinte cards inteiros, textos ou botões com elas). Botões primários são **sempre** Teal Profundo. Isso mantém "cor sim, salada não".

---

## 3. Tipografia

- **Família única:** **Manrope** (pesos 400/500/600/700/800). É a fonte real do app — use-a em tudo. **Proibido** Inter, Roboto, system-ui ou serifada.
- **Títulos de tela / números grandes:** Manrope 700–800, tracking levemente apertado. Hierarquia por **peso e cor**, não por tamanho gigante.
  - Título de hub (ex.: "Ganhos"): ~28px/800, branco sobre o cabeçalho.
  - Valor-herói (ex.: "R$ 12,27"): ~44px/800.
  - Título de card / item: ~17px/700.
- **Corpo:** Manrope 400–500, entrelinha folgada, secundário em Cinza Aço.
- **Legenda / rótulo de seção:** ~12px/700, caixa alta, tracking +0.5, Cinza Aço (ex.: "META DE HOJE · LÍQUIDO", "PRÓXIMAS CONTAS").
- **Dinheiro:** sempre `R$ 1.234,56` (pt-BR, vírgula decimal, ponto de milhar), com **algarismos tabulares** (`font-feature-settings: "tnum"`) para alinhar colunas. Em tabelas muito densas (Raio-X), números podem usar **JetBrains Mono** 500.

---

## 4. Componentes

- **Cabeçalho de hub (header escuro):** faixa com degradê diagonal Teal Noite→Teal Claro, cantos **inferiores** arredondados (~28px), ícones da status bar claros. Dentro: título grande branco + 2–3 **colunas de números** (rótulo pequeno translúcido + valor branco forte) + 1 linha-resumo com ícone (ex.: "Melhor horário hoje: 00h–03h · R$ 1,26/km"). **Para combater o monocromático:** o degradê de cada hub pode variar levemente de temperatura dentro da família teal (Hoje/Ganhos mais teal, Finanças mais esverdeado, Carro/Você mais escuro) — sutil, mesma família, nunca cores fora da marca.

- **HubTile (linha de menu):** card branco arredondado (~20px), chip de ícone colorido à esquerda (seção 2), título 700 + subtítulo em Cinza Aço, chevron `›` à direita. Vários tiles agrupados num card com divisórias internas sutis. Toque mínimo 56px de altura.

- **Card padrão:** Branco Superfície, canto ~20px, padding 20px, **sombra difusa suave** tingida de teal-escuro (`#2B2A22` a ~16% alpha, y+8, blur 24). Cabeçalho do card = chip de ícone + rótulo de seção em caixa alta (+ valor à direita quando fizer sentido). **Dois campos lado a lado sempre com espaçamento** (gap ≥12px) — nunca grudados.

- **Card escuro de destaque (meta / corrida mínima):** fundo Teal (degradê Teal Noite→Teal Profundo), texto branco. Meta: **anel de progresso** com "falta R$ X,XX" dentro + "Já fiz **R$ 12,27**" grande ao lado + "de R$ 92,26" + mini-stats (Combustível/Contas/Dia típico). Valores de combustível em Âmbar Go.

- **Bottom nav (5 abas):** Hoje · Ganhos · Finanças · Carro · Você. Ícone + rótulo. Aba ativa: glyph e texto em Teal Profundo + **pílula de realce** teal-claro atrás do ícone. **A barra é PERSISTENTE** — fica visível também nas **subtelas** (abrir Raio-X, Carteiras, Previsão etc. mantém a barra), para trocar de seção sem voltar. Só some em telas **modais/foco total**: Lançar, mapa em tela cheia e onboarding do leitor.

- **FAB (botão de ação flutuante):** **só ícone, circular** (~56px), Teal Profundo, ícone `+` branco, sombra suave. **Nunca escrito** ("Lançar"/"Transferir" viram só o ícone `+` / `⇄`). **Padrão único** em todo o app. **Nunca sobrepor conteúdo:** toda lista rolável tem padding inferior ≥ 88px para o FAB não tapar o último item.

- **Faixas do semáforo (slider):** por métrica (R$/km, R$/hora, Valor, Nota) um **slider de trilho tricolor** Vermelho→Amarelo→Verde com **dois marcadores** (bolinha vermelha = limite do vermelho; bolinha verde = meta). Acima do slider, dois **chips editáveis**: `🔴 < R$ 1,20` e `🟢 ≥ R$ 1,50` (tocar no chip abre teclado para digitar). Os pontos coloridos nos chips são indicadores de estado, não emojis decorativos.

- **Badge de plataforma:** nome da plataforma como **wordmark** em pílula de largura fixa — `Uber` (pílula preta), `99`, `inDrive`, `iFood` — com **borda colorida** indicando a qualidade da corrida (vermelha/amarela/verde). Largura fixa (~52px) para não esticar e quebrar cards.

- **Campos (input):** fundo cinza-claro levemente afundado (`#ECEDE9`), canto ~14px, rótulo pequeno em teal acima quando preenchido, texto 500. Foco: borda Teal Profundo 2px. Erro: texto Vermelho Vivo abaixo.

- **Segmented control / toggles:** pílula com segmento ativo preenchido de Teal Profundo e texto branco; inativos com texto teal. Switches: trilho Teal Profundo quando ligado, com ✓.

- **Estados de carregando:** **skeleton** com a forma do conteúdo (barras/cards cinza shimmer) — evite o spinner circular genérico no meio da tela quando der para esqueletar.

- **Estado vazio:** composição curta com ícone + frase do que fazer (ex.: "Ninguém se cadastrou com seu código ainda. Compartilhe com outros motoristas!") — nunca só "Sem dados".

- **Gráficos:** barras arredondadas em Teal Profundo (negativas em Vermelho Vivo). Para "lucro por dia" com poucos dias, **lista de barras horizontais** (dia · barra proporcional · valor), nunca poucas barras finas espalhadas num gráfico vazio. Pizza de categorias usa a paleta de categoria da seção 2, em ordem fixa.

---

## 5. Layout

- **Largura de telefone** (360–430dp). Gutter lateral de 16px. **Sem rolagem horizontal, nunca.**
- Estrutura de hub: **cabeçalho escuro fixo** no topo + **corpo claro rolável** abaixo. O corpo começa logo abaixo do cabeçalho.
- Cards empilhados verticalmente, gap 16px entre blocos. Agrupar itens de menu relacionados num único card com divisórias.
- Grid de números: 3 colunas no cabeçalho; dentro dos cards, pares/trincas com gap ≥12px (nunca grudados).
- Alvo de toque mínimo **44px** (itens de lista 56px+).
- Não sobrepor elementos (exceto o FAB, que flutua com o padding inferior garantido). Nada de texto por cima de imagem.

---

## 6. Movimento

Sóbrio e rápido. Transições de 180–240ms com spring suave (stiffness ~110, damping ~22). Troca de aba e push de subtela com fade+slide curto. Toque em botão: leve afundada (−1px / escala 0.98). **Sem** loops infinitos chamativos, sem paralaxe, sem choreography cinematográfica. O anel da meta anima o preenchimento uma vez ao abrir.

---

## 7. Anti-padrões (PROIBIDO)

- ❌ Fonte **Inter**, Roboto, system-ui ou qualquer serifada.
- ❌ Fundo **branco puro** (`#FFFFFF`) de tela e **preto puro** (`#000000`) em texto.
- ❌ Tela **monocromática verde/branca** sem cor na estrutura — traga teal+âmbar e os chips de categoria.
- ❌ Cores de categoria pintando cards inteiros, textos ou botões (só nos chips/marcadores). **Botão primário é sempre Teal Profundo.**
- ❌ **Mais de uma cor** fugindo da marca por tela (nada de roxo neon, gradiente neon, glow).
- ❌ **FAB escrito** ou com texto; FABs de estilos diferentes entre telas; FAB tapando o último item da lista.
- ❌ Barra inferior sumindo nas subtelas de drill-down.
- ❌ Campos grudados (sem gap), wordmark de plataforma esticado, cards quebrados/apertados.
- ❌ Amarelo do semáforo virar laranja.
- ❌ **Emojis decorativos** (os pontos 🔴🟡🟢 dos chips de faixa são indicadores de estado, permitidos; fora isso, use ícones).
- ❌ Spinner circular genérico quando dá para esqueletar.
- ❌ Inventar telas, seções, abas ou campos que a referência não tem. Mudar a ordem/estrutura das telas reais.
- ❌ Nomes/valores fake ("João da Silva", "R$ 99,99", "50%"): use os dados das capturas de referência.
- ❌ Textos de marketing ("Eleve", "Sem esforço", "Próxima geração"), "scroll to explore", setas piscando.
- ❌ Links de imagem quebrados; mapas falsos coloridos (o mapa é um mapa real cinza-claro).
