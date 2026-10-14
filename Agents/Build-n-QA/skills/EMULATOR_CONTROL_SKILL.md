# EMULATOR_CONTROL_SKILL

**Trigger:** перед первым QA и при пересоздании среды. **Input:** debug APK, target API/ABI, runtime ADB/emulator capability.

1. Проверить действительные команды/runtime tools для `adb devices`, list AVDs и attached emulators; выбрать **установленный** совместимый эмулятор. Не скачивать/не устанавливать новый.
2. При наличии разрешённых средств запустить выбранный, дождаться boot completed, записать API/ABI/resolution/locale/rotation/version.
3. Установить конкретный APK, запустить package/activity и проверить, что это **текущий build hash** и приложение не упало при старте.
4. Разрешённые UI actions: tap, swipe, text, keyevent; реальные snapshots через screencap; logcat/ADB. Прежде чем тапнуть по экрану, удостовериться по текущему снимку в координатах, ориентации и ожидаемом UI.
5. При GUI drift, ANR, crash или потере ADB — сохранить evidence, применить ограниченный безопасный retry, после чего `BLOCKED`/`FAIL` по фактам.

**Output:** device report, install/smoke-test evidence, controlled UI session. **Blockers:** нет установленного эмулятора, ADB/visual perception/input недоступны. Не заявлять, что один лишь shell/ADB автоматически даёт достаточную визуальную интерпретацию.
