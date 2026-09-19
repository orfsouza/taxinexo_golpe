# Alerta Taxinexo — site estático

Site institucional (HTML/CSS/JS puro, sem build step) para reunir informação
pública e orientar vítimas/pesquisadores sobre o caso Taxinexo. Otimizado
para SEO: HTML semântico, meta tags, dados estruturados (schema.org),
sitemap.xml e robots.txt.

## Estrutura

```
index.html                 → página inicial (hub)
o-que-e-taxinexo.html       → explicação do caso e linha do tempo
sinais-de-golpe.html        → checklist de sinais de alerta
como-denunciar.html         → passo a passo + checklist de provas (schema HowTo)
perguntas-frequentes.html   → FAQ (schema FAQPage)
recursos-oficiais.html      → links oficiais (Procon, Banco Central, Defensoria)
css/style.css                → estilo compartilhado
js/main.js                   → menu mobile
sitemap.xml / robots.txt     → SEO técnico
vercel.json                  → URLs limpas (cleanUrls)
```

## Antes de publicar

1. **Troque o domínio placeholder.** Todas as tags `canonical`, `og:url` e o
   `sitemap.xml` usam `https://alertataxinexo.com.br/` como exemplo. Troque
   por `find/replace` em todos os arquivos pelo domínio real que você vai
   usar na Vercel (ex.: `https://seu-projeto.vercel.app` ou um domínio
   próprio).
2. **Revise os fatos antes de publicar.** O conteúdo foi escrito com base em
   reportagens e no Reclame Aqui até 18/09/2026. Este é um caso em
   desenvolvimento — confira se surgiram atualizações (investigação
   policial concluída, prisões, novo posicionamento da empresa) antes de
   colocar o site no ar, e mantenha a data de "Atualizado em" real.
3. **Cuidado com afirmações categóricas.** O texto foi escrito
   deliberadamente no tom de "sinais de alerta e reclamações relatadas",
   evitando afirmar como fato consumado que a Taxinexo é uma fraude —
   isso ainda não foi confirmado por investigação oficial. Manter esse tom
   reduz risco de disputa por difamação e é também mais preciso.
4. **Adicione uma imagem de compartilhamento (Open Graph).** As páginas não
   incluem `og:image` — crie uma imagem simples (1200×630) com o nome do
   site e adicione a tag em cada `<head>` para melhorar o preview ao
   compartilhar links.
5. **Considere Google Search Console.** Depois do deploy, cadastre o
   domínio no Search Console e envie o `sitemap.xml` para acelerar a
   indexação — como o tema tem alto volume de busca agora, a indexação
   rápida é o que mais vai gerar tráfego.

## Deploy na Vercel

Sem build necessário — é um site 100% estático.

```bash
npm i -g vercel
cd taxinexo-site
vercel --prod
```

Ou: suba a pasta para um repositório no GitHub e importe o repositório
diretamente pelo painel da Vercel (`New Project` → `Import Git Repository`).
