# SLNE Development - README

Willkommen zur **SLNE Development Open-Source Gruppe**! Diese Gruppe dient als zentrale Anlaufstelle für alle Open-Source-Projekte, die zum **CastCrafter Community Server** beitragen. Der CastCrafter Minecraft Server umfasst eine Vielzahl von Servern, darunter einen Proxy, mehrere Lobbies, einen Survival-Server, Event-Server und weitere kleine Server. 

Ziel ist es, dass externe Entwickler zur Verbesserung und Erweiterung des Servers beitragen können. Diese README enthält alle notwendigen Informationen, um sicherzustellen, dass jeder Entwickler die richtige Struktur und Richtlinien befolgt.

## Inhaltsverzeichnis
1. [Projektstruktur](#projektstruktur)
2. [Richtlinien für Projekte](#richtlinien-für-projekte)
3. [Git-Richtlinien](#git-richtlinien)
4. [Kontakt](#kontakt)
5. [Lizenz](#lizenz)

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

- **Objektorientierte Programmierung (OOP)** wird ausschließlich verwendet.
- Für **Commands** wird die [CommandAPI](https://commandapi.jorel.dev/) eingesetzt.
- **Listen, Sets, Maps** und andere Datenstrukturen werden durch [fastutil](https://fastutil.di.unimi.it/) implementiert.
- **Caches** sollen durch [Caffeine](https://github.com/ben-manes/caffeine) realisiert werden.
- Alle Projekte verwenden **Gradle** als Build-Tool.
- **Shading** wird durch das [Shadow Plugin](https://gradleup.com/shadow/introduction/) implementiert, wobei auf richtiges Relocating geachtet werden muss.
- Für das lokale Testen kann [run-task](https://github.com/jpenilla/run-task) verwendet werden.
- Für die `paper-plugin.yml` wird [plugin-yml](https://github.com/Minecrell/plugin-yml) verwendet.

## Git-Richtlinien

Um eine saubere und konfliktfreie Entwicklung zu gewährleisten, gibt es folgende Git-Richtlinien:

- **Projekte** und **(Sub-)Gruppen** werden nur von Admins erstellt.
- **Issues** dürfen von allen erstellt werden. Diese müssen ausführlich das Problem beschreiben.
- **Branches** sind immer zu verwenden, um Konflikte zu vermeiden. Jeder Branch sollte einem spezifischen Feature gewidmet sein.
  - Beispiel: Ein Branch für ein Freundesystem und ein weiterer Branch für ein Party-System.
- **Labels** sollten verwendet werden, um den Status eines Issues zu verdeutlichen. Fehlen Labels, wendet euch bitte an die Admins.
- **Meilensteine** sollten erstellt werden, um den Fortschritt und Status eines Projekts zu kennzeichnen.

## Kontakt

Bei Problemen, Fragen oder Vorschlägen könnt ihr euch jederzeit an die Admins wenden:
- **NotAmmo** (180623182594572288)
- **Keviro** (201843528618213376)
- **Twisti_Twixi** (697395817882845214)

## Lizenz

Alle Projekte in der SLNE Development Gruppe müssen unter der GNU General Public License (GPL) v3 veröffentlicht werden. Dies bedeutet, dass alle Modifikationen und abgeleiteten Werke ebenfalls unter der GPL v3 veröffentlicht werden müssen, um sicherzustellen, dass der Quellcode für alle zukünftigen Entwickler offen und frei zugänglich bleibt. Jedes Projekt muss eine Kopie der GPL v3 enthalten

---

Vielen Dank, dass ihr Teil von **SLNE Development** seid und den **CastCrafter Community Server** unterstützt! Gemeinsam können wir das Spielerlebnis für die gesamte Community verbessern!