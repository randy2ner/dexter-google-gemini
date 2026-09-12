# OneDrive transport capability scenarios

These scenarios test whether the observed Cowork environment can use an isolated fictional OneDrive folder as a graph transport. They do not test Graph Governor behavior, OneDrive writes, Obsidian compatibility, or production readiness.

| Scenario | Purpose | Status |
| --- | --- | --- |
| [ODT-001](odt-001-isolated-folder-enumeration.md) | Access and recursively enumerate one isolated fictional folder without changes | [partial; executed 2026-08-31](../../test-results/2026-08-31-odt-001-isolated-folder-enumeration.md) |
| [ODT-002](odt-002-native-picker-hierarchy-and-readability.md) | Test interface-exposed relative paths and minimal file readability through Cowork's native OneDrive picker | [pass; executed 2026-08-31](../../test-results/2026-08-31-odt-002-native-picker-hierarchy-and-readability.md) |
