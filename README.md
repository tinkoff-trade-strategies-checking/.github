# .github

Общие настройки GitHub для всех репозиториев организации `tinkoff-trade-strategies-checking`.

- `.github/ISSUE_TEMPLATE/task.md` — шаблон задачи; новая задача сама попадает на доску проекта.
- `.github/pull_request_template.md` — шаблон PR с чек-листом.
- `.github/workflows/pr-size.yml` — переиспользуемая проверка размера PR в режиме наблюдения (не роняет CI, пишет предупреждение при превышении лимита).

GitHub берёт шаблоны отсюда для каждого репозитория, где нет своей папки `.github/ISSUE_TEMPLATE` или своего `pull_request_template.md`. Свои шаблоны в репозиториях не заводим: правим здесь, один раз для всех.

## Проверка размера PR

Чтобы подключить проверку в репозитории организации, добавьте `.github/workflows/pr-size.yml` на событие `pull_request` с вызовом `uses: tinkoff-trade-strategies-checking/.github/.github/workflows/pr-size.yml@main` (необязательные параметры: `limit` — порог строк, по умолчанию `400`; `extra_exclude` — дополнительные glob-исключения).
