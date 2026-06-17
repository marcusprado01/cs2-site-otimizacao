# Checklist de Otimização — CS2 Site

> Marque os itens conforme forem auditados/aplicados. Anote o impacto medido quando possível.

## 1. Performance / Carregamento
- [ ] Imagens em formato moderno (WebP/AVIF) e dimensionadas corretamente
- [ ] `loading="lazy"` em imagens abaixo da dobra
- [ ] CSS e JS minificados
- [ ] Eliminar CSS/JS render-blocking (defer/async, critical CSS)
- [ ] Fontes otimizadas (`font-display: swap`, preload das principais)
- [ ] Compressão (gzip/brotli) habilitada no servidor
- [ ] Cache de assets estáticos configurado

## 2. Core Web Vitals
- [ ] **LCP** < 2.5s (elemento principal identificado e otimizado)
- [ ] **INP** < 200ms (reduzir JS pesado / long tasks)
- [ ] **CLS** < 0.1 (dimensões explícitas em imagens/embeds)

## 3. SEO
- [ ] `<title>` e `<meta name="description">` únicos e descritivos
- [ ] Estrutura de headings semântica (h1 único, hierarquia correta)
- [ ] Open Graph / Twitter Cards
- [ ] Dados estruturados (Schema.org) quando aplicável
- [ ] `sitemap.xml` e `robots.txt`
- [ ] URLs limpas e canonical tags

## 4. Acessibilidade
- [ ] Contraste de cores adequado (WCAG AA)
- [ ] `alt` em todas as imagens
- [ ] Navegação por teclado funcional
- [ ] Atributos ARIA onde necessário

## 5. Boas práticas
- [ ] HTTPS em todo o site
- [ ] Sem erros no console
- [ ] Responsividade (mobile-first)
- [ ] Favicon e manifest

## Medições (Lighthouse 12 — site publicado em GitHub Pages)

Data: 2026-06-17 · URL: https://marcusprado01.github.io/cs2-site-otimizacao/

### Scores

| Categoria       | Mobile | Desktop |
|-----------------|:------:|:-------:|
| Performance     | **100**| **100** |
| Accessibility   | 83     | 83      |
| Best Practices  | **100**| **100** |
| SEO             | **100**| **100** |

### Core Web Vitals (lab)

| Métrica      | Mobile | Desktop |
|--------------|:------:|:-------:|
| FCP          | 0.9 s  | 0.2 s   |
| LCP          | 0.9 s  | 0.2 s   |
| TBT          | 0 ms   | 0 ms    |
| CLS          | 0      | 0       |
| Speed Index  | 0.9 s  | 0.2 s   |

### Pendências de Acessibilidade (score 83) — CORRIGIDAS

- [x] **color-contrast** — `--text3` ajustado de `#535c70` para `#808a9e` (passa WCAG AA)
- [x] **select-name** — todos os `<select>` agora têm `<label for>` associado

> Corrigido no rework "config completa de PC". Re-medir o score após o deploy.
