# RUNTIME_CONTRACT — адаптеры для неизвестной агентной среды

Это **интерфейс интеграции**, не утверждение о наличии реальных инструментов. Не используйте имена как будто они уже установлены.

## Capability API (минимальный)
| Capability | Назначение | Проверка доступности |
|---|---|---|
| `filesystem.read/list/copy/write/hash` | source read-only, workspace write-only | copy isolated + hash/read-back |
| `process.exec` | запустить Unity CLI, SDK/ADB | версия + sandboxed dry-run |
| `unity.build_debug_apk` либо Unity CLI + staging Editor method | собрать Development APK | build smoke с логом/hash |
| `asset_agent.fetch` | получить ассеты / manifest | receipt, checksum, version |
| `gdd_agent.get_cases` / `gdd_agent.get_gdd` | тест-кейсы или канонический GDD | read with revision |
| `android.list_installed_emulators` | выбрать **существующий** AVD/attached emulator | list device IDs/API/ABI |
| `android.boot/connect/install/launch` | UI session | boot/install confirmation |
| `android.capture_screen` + `vision.inspect` | прочитать реальный экран | screenshot + semantic finding |
| `android.tap/swipe/key/text/logcat` | контролируемые действия | action receipt + post screenshot |
| `developer_agent.submit` | прямой handoff | stable task receipt/accepted IDs |
| `developer_agent.get_fix` | получение готовой ревизии | revision + change summary |
| `clock.now` (если доступно) | фактические timestamp/timezone | real clock result |
| `storage.write/readback` | memory/checkpoints/evidence | ack + hash/existence |

Можно объединять adapter methods или реализовать их через доступные CLI/subagent APIs, но **выполненные вызовы должны иметь фактические результаты**, лог и идентификаторы.

## Agent request/response
- Корреляция: `task_id`, `run_id`, `request_id`, `agent_name`, `operation`, `payload`, `references`.
- Ответ: `request_id`, `status: ACCEPTED|REJECTED|BLOCKED|DONE`, `receipt_id`, `artifact_refs`, `revision`, `errors`.
- Внешние пути/URI должны быть доступны адресату и разрешены по правам. Не переносить секреты в промптах агентов.
- Для Developer: отправлять `developer-handoff.json`, релевантный Markdown + accessible evidence; проверять ack.
- Для GDD: приоритет отдаётся готовым кейсам; fallback к каноническому GDD; authoritative requirements возвращает GDD-agent, не Build-n-QA.

## Конфигурационные требования
`source_project_root`, `workspace_root`, `unity_executable`, `android_sdk_root`, `adb_executable`, `asset_agent_route`, `gdd_agent_route`, `developer_agent_route`, `runtime_tool_mapping`, `allowed_test_package_ids`, `android_target_constraints`. `workspace_root` не должен находиться внутри source project. Не оставлять реальные токены в YAML.

## Ошибки и безопасность
- Нет инструментов или реального межагентного bridge → `BLOCKED`, с указанием отсутствующей интеграции.
- Отсутствующий эмулятор → `BLOCKED`; не устанавливать автоматически.
- Timeout/build fail → записать лог и при наличии Developer handoff; не объявлять build success без APK.
- Нельзя подменять визионную проверку простой генерацией текстового результата без screenshot.
- Не выполнять in-app purchases, production API mutations и необратимые действия без отдельно определённой безопасной тестовой среды и разрешений.
