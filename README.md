# SLNE Development - README

Willkommen zur **SLNE Development Open-Source Gruppe**! Diese Gruppe dient als zentrale Anlaufstelle für alle Open-Source-Projekte, die zum **CastCrafter Community Server** beitragen. Der CastCrafter Minecraft Server umfasst eine Vielzahl von Servern, darunter einen Proxy, mehrere Lobbies, einen Survival-Server, Event-Server und weitere kleine Server. 

Ziel ist es, dass externe Entwickler zur Verbesserung und Erweiterung des Servers beitragen können. Diese README enthält alle notwendigen Informationen, um sicherzustellen, dass jeder Entwickler die richtige Struktur und Richtlinien befolgt.

## Inhaltsverzeichnis

1. [Einführung](#einführung)
2. [Projektstruktur](#projektstruktur)
3. [Git-Richtlinien](#git-richtlinien)
   1. [Commits](#commits)
   2. [Branches](#branches)
   3. [Merge Requests](#merge-request)
   4. [Contributors](#contributors)
4. [Wiki](#wiki)
5. [Lizenz](#lizenz)
6. [Kontakt](#kontakt)

## Projektstruktur

Externe Entwickler dürfen **keine neuen Projekte oder Gruppen erstellen**. Ideen für neue Projekte müssen mit den Admins abgesprochen werden, bevor mit der Entwicklung begonnen wird.

Jedes Projekt sollte der folgenden Struktur folgen:

1. **Hauptprojekt** erstellen
2. **Subprojekt API** erstellen:
   - Das API-Subprojekt sollte hauptsächlich aus Interfaces bestehen, die von der SLNE Development Gruppe implementiert werden.
   - Alle API-Methoden müssen zwingend **Completable Futures** sein.
3. **Subprojekt Core** erstellen (optional):
   - Das Core-Subprojekt enthält gemeinsamen Code für Bukkit und Velocity.
   - Gemeinsame Funktionen, wie z. B. ein Usercache, sollten hier initialisiert werden, um doppelten Code zu vermeiden.
4. **Subprojekt Bukkit / Velocity** erstellen:
   - Bukkit und Velocity enthalten jeweils den spezifischen Code, z. B. Listener, Commands, etc.

## Richtlinien für Projekte

Um eine konsistente Entwicklung sicherzustellen, gelten für alle Projekte die folgenden Richtlinien:

- Als Sprache für neue Projekte wird ausschließlich `Java` verwendet. `Kotlin` sorgt zwar für kürzeren, aber auch für unübersichtlicheren Code.
- Für neue Gradle-Projekte muss die Gruppe `dev.slne` verwendet werden. Die Versionsnummern sollten dem Format `X-1.0.0-SNAPSHOT` folgen, wobei `X` stets der aktuell verwendeten Minecraft/Paper-Version entspricht (bspw. `1.21.1-1.0.0-SNAPSHOT`). Dies sorgt für Konsistenz und Kompatibilität in unseren Projekten.
- Alle Gradle Projekte sollten auf `Kotlin Build Files` basieren. Sprich sie sollten die `build.gradle.kts` und nicht die `build.gradle` verwenden.
- **Objektorientierte Programmierung (OOP)** wird ausschließlich verwendet.
- Für **Commands** wird die [CommandAPI](https://commandapi.jorel.dev/) eingesetzt.
- **Listen, Sets, Maps** und andere Datenstrukturen werden durch [fastutil](https://fastutil.di.unimi.it/) implementiert.
- **Caches** sollen durch [Caffeine](https://github.com/ben-manes/caffeine) realisiert werden.
- Alle Projekte verwenden **Gradle** als Build-Tool.
- **Shading** wird durch das [Shadow Plugin](https://gradleup.com/shadow/introduction/) implementiert, wobei auf richtiges Relocating geachtet werden muss.
- Für das lokale Testen kann [run-task](https://github.com/jpenilla/run-task) verwendet werden.
- Für die `paper-plugin.yml` wird [plugin-yml](https://github.com/Minecrell/plugin-yml) verwendet.
- Als Codestyle wird eine Abänderung des Google Codestyles verwendet. Dieser ist in der Datei `surf-codestyle.xml` zu finden.
   - IntelliJ: `surf-codestyle-intellij.xml`
   - Eclipse: `surf-codestyle-eclipse.xml`
   - Andere: `.surf-editorconfig` (Muss in .editorconfig umbenannt werden)
   - Importieren: ![Importieren des Codestyles in IntelliJ](images/import-codestyle.png)
   - Setzen (Muss nicht jedes mal Importiert werden, nur beim 1. Mal): ![Setzen des Codestyles in IntelliJ](images/set-codestyle.png)

## Git-Richtlinien

Um eine saubere und konfliktfreie Entwicklung zu gewährleisten, gibt es folgende Git-Richtlinien:

- **Projekte** und **(Sub-)Gruppen** werden nur von Admins erstellt.
- **Issues** dürfen von allen erstellt werden. Diese müssen ausführlich das Problem beschreiben.
- **Branches** sind immer zu verwenden, um Konflikte zu vermeiden. Jeder Branch sollte einem spezifischen Feature gewidmet sein.
  - Beispiel: Ein Branch für ein Freundesystem und ein weiterer Branch für ein Party-System.
- **Labels** sollten verwendet werden, um den Status eines Issues zu verdeutlichen. Fehlen Labels, wendet euch bitte an die Admins.
- **Meilensteine** sollten erstellt werden, um den Fortschritt und Status eines Projekts zu kennzeichnen.

### Commits

Für alle Commits in den Projekten der **SLNE Development Gruppe** soll der **Conventional Commits Standard** gemäß [https://www.conventionalcommits.org/en/v1.0.0/](https://www.conventionalcommits.org/en/v1.0.0/) verwendet werden. Dieser Standard sorgt für eine klare und konsistente Commit-Historie, die verständlich und leicht zu verfolgen ist. Jeder Commit sollte nach einem festen Format erfolgen, das die Art der Änderung deutlich beschreibt und einen Kontext liefert.

Das Format eines Commit-Messages lautet:
```
<type>[optional scope]: <description>
[optional body]
[optional footer(s)]
```

Beispiele für Commit-Nachrichten:
- `feat(user-management): add friend system`
- `fix(server-crash): resolve issue with player authentication`
- `chore(deps): update fastutil to latest version`
- `refactor(core): simplify caching logic for player data`
- `docs(readme): update installation instructions`

Diese Struktur hilft, den Zweck jeder Änderung sofort zu verstehen und erleichtert das Erstellen von Release-Notes oder Changelogs.

[IntelliJ Plugin](https://plugins.jetbrains.com/plugin/13389-conventional-commit)
[VSCode Plugin](https://marketplace.visualstudio.com/items?itemName=vivaxy.vscode-conventional-commits)

### Branches

Branches in den Projekten der **SLNE Development Gruppe** sollen nach einem konsistenten Schema benannt werden, ähnlich wie bei Commit-Messages, um Klarheit und Nachvollziehbarkeit zu gewährleisten. Jeder Branch-Name sollte die Art der Änderung beschreiben und sich auf ein spezifisches Issue beziehen, sodass Änderungen direkt zu einer Anweisung oder einem Problem zugeordnet werden können.

Das Format für Branch-Namen lautet:
```
<type>/<issue-number>-<short-description>
```

Dabei steht `<type>` für den Typ der Änderung, ähnlich wie bei Commit-Messages (`feat`, `fix`, `chore`, etc.), `<issue-number>` bezieht sich auf die Nummer des entsprechenden Issues, und `<short-description>` gibt eine kurze, prägnante Beschreibung der Änderung.

Beispiele für Branch-Namen:
- `feat/42-add-friend-system`
- `fix/108-player-auth-crash`
- `chore/55-update-dependencies`
- `refactor/75-optimize-user-cache`
- `docs/33-update-readme`

Durch diese Struktur ist sofort ersichtlich, welchem Issue der Branch zugeordnet ist und welche Art von Änderung vorgenommen wird. Dies erleichtert die Zusammenarbeit und das Code-Review erheblich.

### Merge Request

Für **Merge Requests (MRs)** in der **SLNE Development Gruppe** gelten klare Richtlinien, um den Review-Prozess effizient und strukturiert zu gestalten. Jeder MR sollte vollständig vorbereitet und gut dokumentiert sein, bevor er eingereicht wird, um eine reibungslose Zusammenarbeit zu gewährleisten.

Ein Merge Request muss Folgendes beinhalten:

- **Reviewer**: Jeder MR benötigt mindestens einen Reviewer, der den Code gründlich prüft. Dies sollte jemand sein, der nicht direkt an der Implementierung beteiligt war, um eine objektive Überprüfung sicherzustellen.
- **Assignees**: Der Assignee ist für die Fertigstellung und das Monitoring des Merge Requests verantwortlich und sollte auf Feedback reagieren und notwendige Anpassungen vornehmen.
- **Labels**: Labels sollten verwendet werden, um den Typ des MRs (z. B. `bugfix`, `feature`, `WIP`) und den aktuellen Status zu kennzeichnen. Sie helfen dabei, den MR schnell einzuordnen.
- **Meilensteine**: Der MR sollte einem spezifischen Meilenstein zugeordnet werden, um sicherzustellen, dass die Änderungen im Rahmen eines bestimmten Releases oder Projekts umgesetzt werden.
- **Titel**: Der Titel des Merge Requests sollte klar und prägnant das Hauptziel der Änderung beschreiben. Beispiel: `feat: implement friend system for lobby`.
- **Beschreibung**: Die Beschreibung muss ausführlich sein und den Zweck der Änderung, das gelöste Problem und die vorgenommenen Anpassungen erläutern. Hier können auch relevante Issues verlinkt werden, um den Bezug zu bestehenden Problemen oder Features herzustellen.

Ein **Merge Request**, der noch nicht abgeschlossen ist, kann mit dem Präfix `draft:` im Titel gekennzeichnet werden, um anzuzeigen, dass er noch in Arbeit ist und nicht gemerged werden soll. Dies signalisiert dem Team, dass der MR eine Vorschau der laufenden Arbeit ist und noch Änderungen oder Ergänzungen benötigt.

### Contributors

Entwickler, die zu einem Projekt der **SLNE Development Gruppe** beitragen, sind herzlich eingeladen, sich in die `CONTRIBUTORS.md` Datei des entsprechenden Projekts einzutragen, um ihre Mitwirkung zu dokumentieren.

In dieser Datei kannst du deinen Namen, dein GitLab-Profil und optional eine kurze Beschreibung deiner Rolle oder deiner Beiträge vermerken. Es ist eine tolle Möglichkeit, Teil der Entwicklergemeinschaft zu werden und deine Arbeit sichtbar zu machen.

## Wiki

Jedes Projekt in diesem Repository enthält ein zugehöriges Wiki. Das Wiki dient als zentrale Anlaufstelle für die Dokumentation und hilft dabei, wichtige Informationen schnell und einfach zu finden, ohne im Code nach Details suchen zu müssen.

### Zweck des Wikis

- **Zugängliche Dokumentation:** Alle relevanten Informationen wie Befehle, Berechtigungen und andere wichtige Details werden hier festgehalten.
- **Aktualisierungen:** Änderungen und Ergänzungen zur Dokumentation können direkt im Wiki vorgenommen werden, sodass immer die aktuellsten Informationen zur Verfügung stehen.
- **Benutzerfreundlichkeit:** Das Wiki ermöglicht eine klare und strukturierte Darstellung der Dokumentation, wodurch die Einarbeitung und das Verständnis der Projekte erleichtert werden.

### Inhalte des Wikis

- **Befehle:** Eine Übersicht aller wichtigen Befehle und wie sie verwendet werden.
- **Berechtigungen:** Informationen zu den verschiedenen Berechtigungen und deren Konfiguration.
- **Weitere Dokumentation:** Ergänzende Details, die für die Nutzung und Verwaltung des Projekts relevant sind.

Bitte stelle sicher, dass du regelmäßig im Wiki nachschaust und es bei Bedarf aktualisierst. Dies trägt zur besseren Zusammenarbeit und zum effizienten Management des Projekts bei.

### Übernahme in die öffentlichen Docs

Die öffentlichen Docs können in [GitHub](https://github.com/Keviro/community-server-docs) gefunden werden. Am besten sollten auch hier direkt Änderungen eingereicht werden, damit es nicht zu Vergesslichkeiten kommt.

## Lizenz

Alle Projekte in der SLNE Development Gruppe müssen unter der GNU General Public License (GPL) v3 veröffentlicht werden. Dies bedeutet, dass alle Modifikationen und abgeleiteten Werke ebenfalls unter der GPL v3 veröffentlicht werden müssen, um sicherzustellen, dass der Quellcode für alle zukünftigen Entwickler offen und frei zugänglich bleibt. Jedes Projekt muss eine Kopie der GPL v3 enthalten

## Kontakt

Bei Problemen, Fragen oder Vorschlägen könnt ihr euch jederzeit an die Admins wenden:
- **Ammo** (Discord: 180623182594572288 | Email: ammo@slne.dev)
- **Keviro** (Discord: 201843528618213376 | Email: keviro@slne.dev)
- **Twisti_Twixi** (Discord: 697395817882845214 | Email: twisti@slne.dev)

---

Vielen Dank, dass ihr Teil von **SLNE Development** seid und den **CastCrafter Community Server** unterstützt! Gemeinsam können wir das Spielerlebnis für die gesamte Community verbessern!