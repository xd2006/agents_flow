# ASSET_HANDOFF_SKILL

**Trigger:** до каждой initial build, после обновлений asset-agent. **Input:** asset refs, asset manifest или доступ к агентам, staging root.

1. Запросить у источников assets фактические версии/источник/права использования/sha256, адресаты и ожидаемые Unity paths. Не генерировать ассеты самостоятельно.
2. Сверить файлы с manifest, project Unity version/import compatibility, collisions; при нехватке данных запросить asset-agent, а не выдумывать замену.
3. Копировать ассеты **только в staging**. При конфликтах с существующими файлами — проверить явное правило владельца; без него не затирать.
4. Записать asset provenance, install map, validation result, checksums в run artifacts. На каждой новой сборке повторить integrity check.

**Output:** verified staged asset manifest. **Blockers:** missing required asset, checksum mismatch, неразрешимое имя/путь, несовместимость; устранение через asset-agent/Developer. **Never:** запись в `source_project_root`.
