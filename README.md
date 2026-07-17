# G502 X to LIGHTSPEED Profile Converter
Transfer Logitech G502 X wired profiles to the G502 X LIGHTSPEED.

No Python or other software is required. Windows 10 or Windows 11 is required.

## WHAT IT DOES
Copies button, scroll-wheel and G-Shift assignments from Logitech G502 X wired
profiles to the corresponding G502 X LIGHTSPEED profiles. It intentionally
keeps DPI, polling and other mouse-specific settings separate.

## HOW TO USE IT
1. Extract the ZIP before running it.
2. Quit Logitech G Hub from the system tray.
3. In Task Manager, confirm lghub.exe and lghub_agent.exe are closed.
4. Double-click "Run G502 X Converter.cmd".
5. Select %LOCALAPPDATA%\LGHUB\settings.db.
6. Save the converted copy when prompted.
7. Keep the original settings.db as a backup.
8. Rename the converted copy to settings.db and put it in
   %LOCALAPPDATA%\LGHUB while G Hub remains closed.
9. Start G Hub and test your profiles.

## SAFETY
The selected source database is read-only. The converter creates a separate
copy and runs SQLite's integrity check before reporting success.

## VERSION 1.1
Copies saved profile assignments and removes the LIGHTSPEED persistent-assignment
override so G Hub can apply each profile when its game or application activates.

## VERSION 1.1.1
Fixes a PowerShell object-serialization failure in the Windows wrapper.

## VERSION 1.1.2
Writes one consolidated database in SQLite DELETE journal mode, cleans temporary
WAL/SHM files and retains readable JSON formatting.

## VERSION 1.2.0
Never opens the original database through SQLite. Inspection occurs on an isolated
temporary copy, all temporary sidecars are removed, and compact JSON prevents
unnecessary database expansion.

## SHARING
Share the complete ZIP, not individual files. Recipients should extract it
before double-clicking the launcher. The PowerShell source is included so the
tool's behaviour can be inspected.
