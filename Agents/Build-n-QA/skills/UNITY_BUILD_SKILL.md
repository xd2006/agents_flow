# UNITY_BUILD_SKILL

**Trigger:** initial build, новая ревизия Developer/assets, неуспешный build с новой диагностикой. **Input:** snapshot Unity source, staged assets, установленная Unity и лицензия, workspace.

1. Проверить project manifest/version и Android modules; определить действительный build entrypoint (сервис runtime или Unity batchmode Editor method). Не считать Unity CLI «умеющим сборку APK без конфигурации».
2. Собрать в isolated staging (исходник не запускать в writable editor). Если build-driver отсутствует, разрешено создать временный Editor script **в staging** для `BuildPipeline.BuildPlayer` c `BuildOptions.Development`; сохранить его в отчёте, проверить настройки scenes, output path и package ID.
3. Вывести **APK**, не AAB; зафиксировать Unity version, Android target, build options, exit code, полный build log, фактический размер и sha256 файла.
4. Убедиться, что APK существует и соответствует ожидаемому типу; проверить manifest metadata, при наличии эмулятора выполнить install smoke test; не считать exit code 0 достаточным.
5. Проверить, что исходник не изменён именно действиями Build-n-QA; snapshot comparison и git fingerprint фиксируют состояние, но concurrent Developer edits сами по себе не означают нарушение.

**Output:** `build.apk`, `build-manifest.json`, logs, tool results. **Error:** compile errors / missing scene/config → send complete diagnostics Developer; missing Unity/module/license → `BLOCKED`. Не чинить игровой код в source.
