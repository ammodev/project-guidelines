# Branches

Branches in den Projekten der **SLNE Development Gruppe** sollen nach einem konsistenten Schema benannt werden, ähnlich
wie bei Commit-Messages, um Klarheit und Nachvollziehbarkeit zu gewährleisten. Jeder Branch-Name sollte die Art der
Änderung beschreiben und sich auf ein spezifisches Issue beziehen, sodass Änderungen direkt zu einer Anweisung oder
einem Problem zugeordnet werden können.

Das Format für Branch-Namen lautet:

```
<type>/<issue-number>-<short-description>
```

Dabei steht `<type>` für den Typ der Änderung, ähnlich wie bei Commit-Messages (`feat`, `fix`, `chore`,
etc.), `<issue-number>` bezieht sich auf die Nummer des entsprechenden Issues, und `<short-description>` gibt eine
kurze, prägnante Beschreibung der Änderung.

Beispiele für Branch-Namen:

- `feat/42-add-friend-system`
- `fix/108-player-auth-crash`
- `chore/55-update-dependencies`
- `refactor/75-optimize-user-cache`
- `docs/33-update-readme`

Durch diese Struktur siehst du sofort, welchem Issue der Branch zugeordnet ist und welche Art von Änderung vorgenommen
wird. Dies erleichtert die Zusammenarbeit und das Code-Review erheblich.

## Branch-Typen {default-state="collapsed" collapsible="true"}

- **feat/**: Für neue Features
    - Beispiel: `feat/new-login-system`

- **fix/**: Für Bugfixes
    - Beispiel: `fix/button-click-issue`

- **ver/**: Für Versionierung und Releases
    - Beispiel: `ver/1.0.0`

- **dev/**: Für Entwicklungszwecke
    - Beispiel: `dev/experimental-feature`

- **chore/**: Für Routineaufgaben und Wartung
    - Beispiel: `chore/update-dependencies`

- **refactor/**: Für Code-Refactorings ohne Funktionsänderungen
    - Beispiel: `refactor/improve-modularization`

- **test/**: Für Änderungen an Tests
    - Beispiel: `test/add-new-unit-tests`

- **hotfix/**: Für dringende Fixes, die sofortige Bereitstellung erfordern
    - Beispiel: `hotfix/security-patch`

- **docs/**: Für Dokumentationsänderungen
    - Beispiel: `docs/update-readme`

- **perf/**: Für Performance-Verbesserungen
    - Beispiel: `perf/optimize-query-performance`

- **style/**: Für Änderungen am Code-Stil und an der Formatierung
    - Beispiel: `style/fix-indentation`

- **opt/**: Für Optimierungsaufgaben
    - Beispiel: `opt/7-optimize-packet-operation`