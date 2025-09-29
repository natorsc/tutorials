# Como fazer o deploy do Python Sphinx no Github pages

Hoje veremos como utilizar o GitHub Actions para automatizar o processo de deploy do Python Sphinx no Github Pages.

## O que é o Sphinx?

O [Sphinx](https://www.sphinx-doc.org/en/master/) é uma poderosa ferramenta de documentação que facilita a criação de documentação para projetos [Python](https://www.python.org/).

Ele é frequentemente usado para criar documentação de código-fonte, manuais de usuário, guias de API e outros tipos de documentação.

O Sphinx utiliza arquivos de marcação simples, como reStructuredText, para escrever a documentação e suporta a geração de saída em vários formatos, como HTML, PDF, ePub e man pages.

Ele também oferece recursos avançados, como indexação automática, geração de índices, suporte para diagramas e integração com ferramentas de construção como o `make`.

Essas características fazem do Sphinx uma escolha popular para projetos Python que valorizam uma documentação completa e bem formatada.

## Github Pages

O [GitHub Pages](https://pages.github.com/) é um serviço oferecido pelo GitHub que permite hospedar websites estáticos diretamente a partir de um repositório do GitHub.

Ele é comumente usado para hospedar páginas de documentação, blogs pessoais, páginas de projetos e sites simples.

O GitHub Pages suporta sites estáticos gerados a partir de arquivos HTML, CSS e JavaScript, bem como frameworks estáticos como [Jekyll](https://jekyllrb.com/), [Hugo](https://gohugo.io/), Sphinx e [Gatsby](https://www.gatsbyjs.com/).

## Criando o arquivo de deploy

No repositório crie um arquivo `pages.yaml` em `.github/workflows`.

> ⚠️ O arquivo pode ter o nome que você desejar.

Dentro do arquivo `pages.yaml` será utilizado o seguinte código:

```bash
# Fluxo de deploy para documentação com Python e Sphinx no Github pages.
name: Deploy Sphinx content to Pages.

on:
  push:
    branches: ['main']
  workflow_dispatch:

permissions:
  contents: read
  pages: write
  id-token: write

concurrency:
  group: 'pages'
  cancel-in-progress: true

jobs:
  deploy:
    environment:
      name: github-pages
      url: ${{ steps.deployment.outputs.page_url }}
    runs-on: ubuntu-latest
    steps:
      - name: Checkout 💾
        uses: actions/checkout@v4
      
      - name: Setup Pages
        uses: actions/configure-pages@v5
      
      - name: Install Python 🐍
        uses: actions/setup-python@v5
        with:
          python-version: '3.11'
          cache: 'pip'
      
      - name: Install requirements 🔨
        working-directory: .
        run: pip install -r requirements-docs.txt
      
      - name: Sphinx make dirhtml 🌎
        working-directory: ./docs
        run: make dirhtml
      
      - name: Upload artifact 🚀
        uses: actions/upload-pages-artifact@v3
        with:
          path: './docs/build/dirhtml'
      
      - name: Deploy to GitHub Pages 💻
        id: deployment
        uses: actions/deploy-pages@v4
```

Ao final do processo de deploy acesse a URL do repositório ([`https://usuário.github.io/repositório/`](https://usuário.github.io/repositório/)) para ter acesso a sua documentação/site no Github Pages.

Também é possível executar essa Github Action através da interface web do Github, para isso basta clicar na aba `Actions`.

Se o deploy não ocorrer vefifique as configurações do repositório em `settings` -&gt; `pages`.
