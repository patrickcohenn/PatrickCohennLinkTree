# Patrick Cohenn — Link Tree

Página pessoal de links ("link na bio") do Patrick Cohenn.

## Estrutura do projeto

- **`index.html`** — versão em produção: site estático, arquivo único autocontido (CSS embutido, fonte Inter via Google Fonts, sem outras dependências). É a página publicada hoje (deploy via Netlify). Usa as imagens em `static/img/`.
- **`static/`** — imagens (e CSS legado) usados pelo `index.html`.
- **`Thema-Atual-Py/`** — a mesma página servida via Flask (`app.py`), para hospedagem em provedores estilo Heroku/Render (usa `gunicorn`, ver `Procfile` e `requirements.txt` dentro da pasta). Independente do restante do repositório — tem seu próprio `static/`.

## Rodando localmente

**Site estático (raiz):**
Abra `index.html` diretamente no navegador — sem build nem dependências.

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
