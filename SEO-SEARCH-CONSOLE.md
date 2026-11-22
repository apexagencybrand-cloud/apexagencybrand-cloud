# SEO técnico — Apex Agency

## Arquivos publicados

Com `npm run build`, o Vite copia o conteúdo de `public/` para a raiz de `dist/`:

| Arquivo | URL após o deploy |
|---|---|
| `public/robots.txt` | `https://apexagency.com.br/robots.txt` |
| `public/sitemap.xml` | `https://apexagency.com.br/sitemap.xml` |
| `public/og-image.png` | `https://apexagency.com.br/og-image.png` |
| `public/apex-logo.png` | `https://apexagency.com.br/apex-logo.png` |

`og-image.png` (1200×630) e `apex-logo.png` são cópias da arte oficial em um caminho estável. O Vite aplica hash aos arquivos referenciados dentro do HTML (`assets/apex-logo-*.png`), por isso essas cópias em `public/` são necessárias para que as URLs absolutas do Open Graph e do JSON-LD continuem válidas após o build.

## Cloudflare Pages

- Build command: `npm run build`
- Build output directory: `dist`
- Domínio canônico: `https://apexagency.com.br/` (definido em `<link rel="canonical">`, `og:url` e no sitemap)

Se o domínio de produção for outro, substitua `apexagency.com.br` em `index.html`, `public/robots.txt` e `public/sitemap.xml` antes de publicar.

## Google Search Console — verificação de propriedade

Use apenas o código que o Google gerar para a propriedade `apexagency.com.br`. Não há código de verificação inventado neste projeto.

### Opção 1 — meta tag HTML

1. No Search Console, escolha **HTML tag** como método de verificação e copie a tag completa exibida pelo Google.
2. Cole a tag no `<head>` de `index.html`, no ponto marcado:

```html
<!-- Google Search Console: cole aqui a meta tag fornecida pelo Google -->
<!-- <meta name="google-site-verification" content="CODIGO_FORNECIDO_PELO_GOOGLE"> -->
```

3. Rode `npm run build`, publique e clique em **Verificar** no Search Console.

### Opção 2 — registro DNS TXT (recomendado no Cloudflare)

1. No Search Console, escolha **DNS record** e copie o **valor** do registro TXT exibido pelo Google.
2. No Cloudflare, abra **DNS → Records → Add record**:
   - Type: `TXT`
   - Name: `@` (ou o hostname exato pedido pelo Google, por exemplo `www`)
   - TTL: `Auto`
   - Value: cole o valor fornecido pelo Google, exatamente como aparece.
3. Salve e clique em **Verificar** no Search Console. A propagação pode levar alguns minutos.

Depois da verificação, envie o sitemap em **Sitemaps → URL do sitemap**: `https://apexagency.com.br/sitemap.xml`.
