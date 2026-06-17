# CS2-Site-Otimização

Projeto de **otimização de um site HTML existente** relacionado a Counter-Strike 2 (CS2).

## Objetivo

Otimizar um site já em produção, com foco em:

- **Performance** — tempo de carregamento, peso de assets, render-blocking
- **Core Web Vitals** — LCP, INP, CLS
- **SEO** — meta tags, dados estruturados, semântica HTML
- **Acessibilidade** — contraste, ARIA, navegação por teclado
- **Boas práticas** — HTTPS, lazy loading, cache, minificação

A aplicação é o **Configurador CS2**: uma página única e autocontida (HTML + CSS + JS inline, sem dependências externas além das fontes via CDN). A partir da **configuração completa do PC** (CPU, RAM, GPU, monitor e tipo de armazenamento) ela:

- **Diagnostica o gargalo** (CPU-bound, GPU-bound ou equilibrado) usando o modelo `FPS ≈ min(teto CPU+RAM, teto GPU@resolução)`, já que o CS2 é um jogo CPU-bound;
- Recomenda as configurações do **Painel de Controle Nvidia**, **launch options** da Steam, **configurações in-game do CS2** (vídeo + console/autoexec) e **ajustes do Windows**;
- Estima o **FPS real** por tipo de mapa e lista as **ações de maior impacto** para aquele hardware específico.

Todo o processamento é local, sem envio de dados.

## Estrutura

```
CS2-Site-Otimização/
├── index.html           # 👈 A aplicação (servida pelo GitHub Pages)
├── README.md            # Este arquivo
└── docs/
    └── otimizacao-checklist.md   # Checklist de auditoria e melhorias
```

> `index.html` fica na raiz porque o GitHub Pages (deploy a partir do branch) serve a partir de `/`.

## Otimizações aplicadas

- **Fontes não-bloqueantes** — `@import` render-blocking substituído por `preconnect` + `preload`/`onload`
- **SEO** — meta description, Open Graph e `lang` correto
- **Favicon SVG inline** — zero requisições extras
- **Tema** — `theme-color` + `color-scheme` (dark consistente, sem flash)
- **Render eficiente** — montagem do DOM em uma única atribuição (sem reflow por iteração)
- **Mobile-first** — formulário em coluna única, alvos de toque ≥44px, tabela NVCP convertida em cards empilhados em telas pequenas

## Deploy

Publicado via **GitHub Pages** (deploy a partir do branch `main`, pasta raiz). Qualquer push na `main` republica o site automaticamente.
