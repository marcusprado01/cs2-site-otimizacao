# CS2-Site-Otimização

Projeto de **otimização de um site HTML existente** relacionado a Counter-Strike 2 (CS2).

## Objetivo

Otimizar um site já em produção, com foco em:

- **Performance** — tempo de carregamento, peso de assets, render-blocking
- **Core Web Vitals** — LCP, INP, CLS
- **SEO** — meta tags, dados estruturados, semântica HTML
- **Acessibilidade** — contraste, ARIA, navegação por teclado
- **Boas práticas** — HTTPS, lazy loading, cache, minificação

## Estrutura

```
CS2-Site-Otimização/
├── README.md            # Este arquivo
├── src/                 # 👈 Suba aqui o site HTML original
│   ├── index.html
│   └── assets/
│       ├── css/
│       ├── js/
│       └── img/
└── docs/
    └── otimizacao-checklist.md   # Checklist de auditoria e melhorias
```

## Próximos passos

1. Subir o site HTML na pasta `src/`.
2. Rodar uma auditoria inicial (Lighthouse / PageSpeed Insights).
3. Registrar os pontos de melhoria em `docs/otimizacao-checklist.md`.
4. Aplicar otimizações de forma incremental, medindo o impacto a cada mudança.
