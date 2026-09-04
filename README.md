# Landing Page — Dr. Davi Menezes

Site **estático** (HTML/CSS/JS puro) — sem build, sem Node. Pronto para publicar na **Hostinger**.

## Estrutura
```
index.html          → a página
.htaccess           → config de produção (HTTPS, cache, compressão, segurança)
robots.txt          → indexação
assets/
  img/              → fotos (jpg + webp)
  logo/             → logos e favicons
  fonts/            → fontes locais (woff2)
```

## Como publicar na Hostinger

### Opção A — Deploy automático via Git (recomendado)
No hPanel: **Sites → seu domínio → Avançado → Git** (ou **Criar novo aplicativo → GitHub**).
1. Conecte o repositório `Davi-Menezes`.
2. Como não há `package.json`, escolha **"Implante como estático"** (deploy estático).
3. Cada `git push` na branch `main` pode ser reimplantado pela Hostinger.

### Opção B — Upload manual
1. hPanel → **Gerenciador de Arquivos** → `public_html/`.
2. Envie **todo o conteúdo** desta pasta (index.html, .htaccess, robots.txt, assets/) para dentro de `public_html/`.
3. Acesse `https://seudominio.com.br`.

### Publicar em uma SUBPASTA (ex.: /lifting/)
1. Crie `public_html/lifting/` e coloque os arquivos lá.
2. Acesse `https://seudominio.com.br/lifting/`.
3. No `.htaccess`, troque `ErrorDocument 404 /index.html` por `ErrorDocument 404 /lifting/index.html`.
> Os caminhos dos assets já são **relativos**, então funcionam em qualquer subpasta.

## Observações
- SSL/HTTPS: a Hostinger provisiona automaticamente; o `.htaccess` já força HTTPS.
- Após atualizar, limpe o cache do navegador (Ctrl + F5) se necessário.
