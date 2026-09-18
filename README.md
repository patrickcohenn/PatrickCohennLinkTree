# Patrick Cohenn — Link Tree

Página pessoal de links ("link na bio") do Patrick Cohenn.

## Estrutura do projeto

- **`index.html`** — versão em produção: site estático (HTML + CSS puro, Bootstrap via CDN). É a página publicada hoje (deploy via Netlify). Usa os arquivos em `static/`.
- **`novo-index.html`** — redesign minimalista em arquivo único autocontido (CSS embutido, fonte Inter via Google Fonts, sem outras dependências). Reaproveita as imagens de `static/img/`. Candidato a substituir o `index.html`, ainda não promovido.
- **`static/`** — CSS e imagens usados pelo `index.html` e pelo `novo-index.html`.
- **`Thema-Atual-Py/`** — a mesma página servida via Flask (`app.py`), para hospedagem em provedores estilo Heroku/Render (usa `gunicorn`, ver `Procfile` e `requirements.txt` dentro da pasta). Independente do restante do repositório — tem seu próprio `static/`.

## Rodando localmente

**Site estático (raiz):**
Abra `index.html` ou `novo-index.html` diretamente no navegador — sem build nem dependências.

**Versão Flask (`Thema-Atual-Py/`):**
```bash
cd Thema-Atual-Py
python -m venv venv && source venv/bin/activate
pip install -r requirements.txt
python app.py
```

## Deploy

- Raiz (`index.html`): Netlify, como site estático.
- `Thema-Atual-Py/`: qualquer provedor compatível com `Procfile`/gunicorn (Heroku, Render etc.), usando `web: gunicorn app:app`.

## Licença

MIT — veja [LICENSE](./LICENSE).
