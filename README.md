# CS2-Site-Otimização

Projeto de **otimização de um site HTML existente** relacionado a Counter-Strike 2 (CS2).

## Objetivo

Otimizar um site já em produção, com foco em:

- **Performance** — tempo de carregamento, peso de assets, render-blocking
- **Core Web Vitals** — LCP, INP, CLS
- **SEO** — meta tags, dados estruturados, semântica HTML
- **Acessibilidade** — contraste, ARIA, navegação por teclado
- **Boas práticas** — HTTPS, lazy loading, cache, minificação

A aplicação é o **Configurador NVCP CS2**: uma página única e autocontida (HTML + CSS + JS inline, sem dependências externas além das fontes via CDN) que gera as configurações ideais do Painel de Controle Nvidia, launch options da Steam e estimativa de FPS conforme o hardware informado. Todo o processamento é local, sem envio de dados.

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
