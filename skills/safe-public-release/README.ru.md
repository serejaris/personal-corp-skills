# Скилл Safe Public Release

Подготавливает private, vendor, runtime или mixed artifacts к публичному GitHub-репозиторию/registry без утечки секретов, runtime state, user data и материалов, которые нельзя перераспространять.

## Проблема

Запрос «выложи эти скиллы» часто указывает на рабочую директорию, где reusable source смешан с caches, logs, credentials, абсолютными приватными путями, vendor assets, generated files и неясными лицензиями. Если сначала создать публичный репозиторий, outward action произойдёт раньше проверки доказательств.

## Решение

`safe-public-release` задаёт allowlist-first pipeline:

1. создать internal owner issue tree;
2. собрать inventory кандидатов и companion files;
3. доказать provenance и право на redistribution;
4. классифицировать security/privacy risks;
5. собрать clean staging tree из explicit allowlist;
6. показать approval dry run до outward mutation;
7. опубликовать только одобренный artifact set;
8. проверить fresh public clone, install/discovery command и повторные scans;
9. назначить maintenance owner и перенести новые уроки в skill.

## Когда использовать

- agent skills и plugin bundles;
- prompts, templates, playbooks, starter kits;
- reusable code из private projects;
- course/workshop assets, выбранные для открытия;
- benchmark fixtures и datasets;
- vendor/runtime exports с неясным provenance;
- demo repositories для community/developer programmes.

## Модель безопасности

- Публичная публикация всегда требует explicit approval после dry run.
- Неизвестный provenance или license блокирует artifact.
- Attribution не заменяет разрешение на redistribution.
- Package собирается из explicit allowlist, а не копируется целиком с последующей чисткой.
- Credentials, runtime state, histories, user data, private paths и непроверенные vendor assets исключаются.
- `PUBLISHED` ещё не done: нужен fresh public clone/install/discovery verification.

## Шаблоны в bundle

- [release-manifest.example.yaml](references/release-manifest.example.yaml) — provenance, licensing, allowlist, scans и verification.
- [release-checklist.md](references/release-checklist.md) — dry-run и publication checklist.

## Примеры запросов

```text
Используй safe-public-release и подготовь эти agent skills для публичного GitHub. Собери inventory и allowlist, но остановись до создания или push публичного repo.
```

```text
Проверь private template repository перед открытием. Покажи allowed, blocked и требующие licensing clarification файлы, затем подготовь approval dry run.
```

```text
Опубликуй уже одобренный package из release manifest и проверь его через fresh public clone. Остановись, если target или artifact set отличаются от approval.
```

## Установка

```bash
cp -r skills/safe-public-release ~/.claude/skills/
```

## Связанные скиллы

- [SKILL.md](SKILL.md) — полный workflow и hard gates
- [release manifest template](references/release-manifest.example.yaml)
- [release checklist](references/release-checklist.md)
- [corp-new](../corp-new/) — создание приватного `corp-*` department после отдельного approval
- [manager](../manager/) — cross-repository owner issue tree
