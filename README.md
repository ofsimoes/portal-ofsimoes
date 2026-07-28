# Portal ofsimoes.com.br

Página inicial estática (hub de navegação) do domínio raiz **ofsimoes.com.br**.
Lista, em cards, os aplicativos hospedados nos subdomínios.

- **Sem build step** — HTML + CSS puro (Tailwind e FontAwesome via CDN).
- **Hospedagem** — Render, como *Static Site* (plano gratuito).
- **Responsivo** — layout em grid (1 / 2 / 3 colunas) com efeito de hover nos cards.

## Estrutura

```
portal-ofsimoes/
├── index.html          # a página (todo o layout e estilo)
├── favicon.svg         # ícone do portal
├── render.yaml         # blueprint opcional do Render (deploy sem build)
├── .gitignore
├── README.md
└── assets/
    ├── economia.svg    # logo do economIA
    ├── eveconomy.webp  # logo do EV/HEV Economy
    └── labexams.svg    # logo do Lab Exams
```

## Aplicativos

| App             | Subdomínio                     |
| --------------- | ------------------------------ |
| economIA        | economia.ofsimoes.com.br       |
| EV/HEV Economy  | eveconomy.ofsimoes.com.br      |
| Lab Exams       | labexams.ofsimoes.com.br       |

> Para adicionar/editar um app, duplique um bloco `<a class="app-card">` no `index.html`
> e ajuste o `href`, o logo (`/assets/...`), o título e a descrição.

## Testar localmente

Abra o `index.html` no navegador, ou suba um servidor simples:

```bash
python3 -m http.server 8000
# depois acesse http://localhost:8000
```

## Deploy no Render (Static Site)

1. Suba este repositório para o GitHub (veja os comandos abaixo).
2. No Render: **New +** → **Static Site** → conecte este repositório.
3. Configure:
   - **Build Command**: *(deixe em branco)*
   - **Publish Directory**: `.`
4. **Create Static Site**.
5. Em **Settings → Custom Domains**, adicione `ofsimoes.com.br` (e `www`) e
   aponte o DNS conforme instruções do Render.

## Comandos Git (primeiro envio ao GitHub)

```bash
cd ~/GitHub/portal-ofsimoes

git init
git add .
git commit -m "feat: portal inicial de ofsimoes.com.br"
git branch -M main

# crie o repositório no GitHub e conecte:
gh repo create portal-ofsimoes --public --source=. --remote=origin --push
# — ou, sem o gh CLI:
# git remote add origin https://github.com/<seu-usuario>/portal-ofsimoes.git
# git push -u origin main
```
