# auth-ssg-research

Статический сайт по материалам НИР «Исследование подходов к аутентификации и
авторизации в веб-приложениях». Собран генератором
[MkDocs](https://www.mkdocs.org/) с темой
[Material for MkDocs](https://squidfunk.github.io/mkdocs-material/).

## Локальная разработка

```bash
python3 -m virtualenv .venv
source .venv/bin/activate
pip install -r requirements.txt
mkdocs serve
```

Сборка со строгой проверкой ссылок (используется и в CI):

```bash
mkdocs build --strict
```

## Публикация

Сайт автоматически публикуется workflow'ом `.github/workflows/pages.yml` при
push в `main`:

- на **GitHub Pages** — через `actions/upload-pages-artifact` +
  `actions/deploy-pages`;
- на **Helios** — по SSH с отдельным deploy-ключом (включается
  репозиторной переменной `HELIOS_ENABLED` и секретами `HELIOS_USER` /
  `HELIOS_SSH_KEY`).

Разбор рисков обоих способов доставки и остальных вариантов (gh-pages-ветка,
FTP/SFTP, S3) — в разделе 4 отчёта «Модель доставки и безопасность
пайплайна».

## Лицензии

- Код (конфигурация, workflow, скрипты) — [MIT](LICENSE).
- Содержимое сайта (`docs/`) — [CC BY 4.0](LICENSE-CONTENT).
