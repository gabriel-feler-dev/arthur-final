# Arthur Lima | Portfólio — Fotógrafo & Videomaker

## Visão Geral

Site de portfólio profissional desenvolvido para **Arthur Lima**, fotógrafo e videomaker especializado em conteúdo automotivo e cobertura de eventos esportivos, baseado no **Paraná, Brasil**.

O projeto é uma **Single-Page Application (SPA)** construída inteiramente com HTML5, CSS inline + Tailwind CSS e JavaScript puro — sem frameworks, sem dependências de backend, pronta para ser servida como arquivo estático.

---

## Objetivo

Apresentar o trabalho de Arthur Lima de forma visual e impactante, reunindo em uma única página:
- Identidade profissional e proposta de valor
- Portfólio de vídeos (YouTube) e galerias de fotos
- Serviços oferecidos
- Canal de contato direto via WhatsApp

---

## Stack Tecnológica

| Tecnologia | Uso |
|---|---|
| **HTML5** | Estrutura semântica da página |
| **Tailwind CSS** (CDN) | Estilização utilitária e responsividade |
| **CSS inline** | Customizações avançadas, animações e media queries |
| **JavaScript Vanilla** | Toda interatividade (sem frameworks) |
| **AOS** (Animate On Scroll) | Animações de entrada ao rolar a página |
| **Google Fonts — Poppins** | Tipografia principal |
| **YouTube Embed API** | Reprodução de vídeos em modal |

---

## Estrutura de Arquivos

```
arthur-final/
├── index.html              # Aplicação completa (HTML + CSS + JS)
└── assets/
    ├── images/             # Imagens de UI
    │   ├── background_hero.png
    │   ├── banner_parana.png
    │   ├── logo_final.png
    │   ├── logo_doisvizinhos.png
    │   ├── logo_quartas.png
    │   ├── logo_guss.png
    │   ├── mc.jpg          # Foto do autor (seção Sobre)
    │   ├── car1.jpeg
    │   └── job.jpg
    └── photos/             # Galerias fotográficas
        ├── BMW/            # 14 fotos
        ├── Ceramic Pro/    # 32 fotos
        └── Mustang/        # 24 fotos
```

---

## Seções da Página

### 1. Header / Navegação
Header fixo (sticky) com fundo semi-transparente e efeito `backdrop-blur`. Contém:
- Logo/nome "ARTHUR LIMA" em dourado
- Menu desktop com links âncora para todas as seções
- Ícone do Instagram com link direto
- Menu mobile com animação slide-in da direita (hamburger → painel lateral)

### 2. Hero
Seção de tela cheia com imagem de fundo fixa (parallax no desktop) e overlay em gradiente preto. Destaque para:
- **Efeito Typewriter**: o título anima automaticamente ciclando entre 5 frases ("captura momentos.", "transforma ideias em arte.", "traduz emoções em imagem.", "dá vida ao invisível.", "completa desafios.")
- Dois botões de chamada para ação: **Ver Portfólio** e **Instagram**

### 3. Serviços
Grade de 3 cards descrevendo os serviços disponíveis:
- **Fotografia** — ensaios automotivos, eventos esportivos, produções personalizadas
- **Produção de Vídeo** — cobertura de eventos, conteúdo digital, vídeos corporativos
- **Edição & Pós-Produção** — correção de cor, motion graphics, finalização

### 4. Portfólio
Principal seção do site, dividida em três grupos de trabalhos:

#### Paraná Clube Futsal (Vídeos)
Cobertura completa do campeonato de futsal de 2025. 4 vídeos incorporados do YouTube:
- Final — Paraná Clube X Terra Boa
- Semifinal — Paraná Clube X Dois Vizinhos
- Quartas de Final — Paraná Clube X Passo Fundo
- GUSS

#### Ensaios Automotivos (Fotos)
3 galerias fotográficas com um total de **70 fotos**:
- **BMW** — 14 fotos
- **Ceramic Pro** — 32 fotos
- **Mustang** — 24 fotos

#### Vídeos Automotivos
3 produções audiovisuais no formato YouTube Shorts:
- Mustang
- Aplicação PPF
- Treinamento PPF

### 5. Sobre Mim
Seção biográfica com:
- Foto do autor com borda dourada e efeito de brilho
- Texto de apresentação (5+ anos de experiência)
- Barras de habilidades animadas: Fotografia, Produção de Vídeo e Edição

### 6. Contato
Formulário de contato (Nome, E-mail, Mensagem) integrado com **WhatsApp** — ao submeter, abre automaticamente o chat do WhatsApp com a mensagem pré-formatada. Também exibe:
- E-mail de contato
- Link do Instagram
- Localização (Paraná, Brasil)

### 7. Footer
Rodapé com três colunas: identidade da marca, links rápidos e redes sociais. Copyright 2025.

---

## Funcionalidades Técnicas

### Carrossel Responsivo
No **mobile**, os portfólios exibem carrosséis horizontais com:
- Scroll snapping suave (`scroll-snap`)
- Botões de navegação com efeito glassmorphism
- Indicadores de posição (dots)
- Loop infinito ao atingir o fim
- Swipe touch nativo

No **desktop**, os mesmos conteúdos são exibidos em grids de 2 a 4 colunas.

### Modal de Vídeo (YouTube)
Ao clicar em um card de vídeo, abre um modal fullscreen com:
- Iframe do YouTube com autoplay (`autoplay=1&rel=0&modestbranding=1`)
- Fechamento por clique no overlay, botão X ou tecla ESC
- Restauração da posição de scroll ao fechar

### Modal de Galeria de Fotos
Ao clicar em um card fotográfico, abre um modal lightbox com:
- Navegação por setas (anterior/próxima) com suporte a teclado (← →) e swipe touch
- Transição com fade suave (opacity) entre fotos
- Pré-carregamento das fotos adjacentes (cache em memória)
- Contador de posição (ex: "3 / 14")
- Fechamento por clique no overlay, botão X ou tecla ESC

### Animações e UX
- **AOS**: animações `fade-up`/`fade-right`/`fade-left` ao entrar na viewport (desativadas no mobile para evitar overflow)
- **Typewriter** no hero com digitação e apagamento progressivo
- **Hover effects**: cards elevam com sombra dourada, imagens fazem zoom, botões pulsam
- **Smooth scroll** para navegação entre seções (com offset de 80px pelo header fixo)
- Prevenção de scroll horizontal acidental no mobile fora dos carrosséis

### Otimizações Mobile
- `touch-action: manipulation` para evitar delay de 300ms nos taps
- `overscroll-behavior-x: contain` nos carrosséis para impedir que o swipe horizontal acione a navegação do browser
- `-webkit-overflow-scrolling: touch` para scroll inercial fluido no iOS
- `will-change: transform` e `transform: translateZ(0)` para aceleração GPU nos cards
- Scroll instantâneo no mobile vs. scroll suave no desktop

---

## Design System

| Elemento | Valor |
|---|---|
| Cor de fundo principal | `#0D0D0D` |
| Cor de fundo secundária | `#111111` |
| Cor de superfície | `#1a1a1a` |
| Cor de texto | `#E5E5E5` |
| Cor de destaque (dourado) | `#FFD451` |
| Gradiente das barras | `#FFD451` → `#FFA500` |
| Tipografia | Poppins (300–800) |
| Border radius padrão | `rounded-2xl` (1rem) |
| Efeito de fundo nos modais | `backdrop-filter: blur(10px)` |

---

## Contato do Autor

- **Instagram**: [@arthurlima.araujo](https://www.instagram.com/arthurlima.araujo)
- **E-mail**: contato@arthurlima.com
- **WhatsApp**: +55 (41) 99707-8372
- **Localização**: Paraná, Brasil
