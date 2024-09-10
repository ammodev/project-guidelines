# Branches

Branches in den Projekten der **SLNE Development Gruppe** sollen nach einem konsistenten Schema benannt werden, ähnlich
wie bei Commit-Messages, um Klarheit und Nachvollziehbarkeit zu gewährleisten. Jeder Branch-Name sollte die Art der
Änderung beschreiben und sich auf ein spezifisches Issue beziehen, sodass Änderungen direkt zu einer Anweisung oder
einem Problem zugeordnet werden können.

Das Format für Branch-Namen lautet:

```html

<type>/
    <issue-number>-
        <short-description>
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

Durch diese Struktur ist sofort ersichtlich, welchem Issue der Branch zugeordnet ist und welche Art von Änderung
vorgenommen wird. Dies erleichtert die Zusammenarbeit und das Code-Review erheblich.

## Branch-Typen {default-state="collapsed" collapsible="true"}

- **feat/**: For new features
    - Example: `feat/new-login-system`

- **fix/**: For bug fixes
    - Example: `fix/button-click-issue`

- **ver/**: For versioning and releases
    - Example: `ver/1.0.0`

- **dev/**: For development purposes
    - Example: `dev/experimental-feature`

- **chore/**: For routine tasks and maintenance
    - Example: `chore/update-dependencies`

- **refactor/**: For code refactoring without changing functionality
    - Example: `refactor/improve-modularization`

- **test/**: For changes related to tests
    - Example: `test/add-new-unit-tests`

- **hotfix/**: For urgent fixes that need immediate deployment
    - Example: `hotfix/security-patch`

- **docs/**: For documentation changes
    - Example: `docs/update-readme`

- **perf/**: For performance improvements
    - Example: `perf/optimize-query-performance`

- **style/**: For code style and formatting changes
    - Example: `style/fix-indentation`

- **opt/**: For optimization tasks
    - Example: `opt/7-optimize-packet-operation`

