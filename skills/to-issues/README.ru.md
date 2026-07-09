# To Issues

Дробит план, спеку или `PRD.md` на независимые файлы задач — **tracer bullet** срезы: каждая задача проходит все слои end-to-end, а не «только бэкенд». Агент предлагает разбивку, уточняет гранулярность и зависимости с тобой, затем пишет markdown в `tasks/`.

**Когда звать:** когда есть `PRD.md` (или другой спек) и нужны grab-and-go задачи для агентов или разработчиков без GitHub Issues.

**На выходе:** файлы `tasks/01-slug.md`, `tasks/02-slug.md`, … с блоками *What to build*, чеклистом **Acceptance criteria** и **Depends on** (ссылки на `tasks/…` или `none`).

**Цепочка:** [grill-me](../grill-me/) → [to-prd](../to-prd/) → **to-issues**.
