# Projektstruktur

> Externe Entwickler*innen dürfen **keine neuen Projekte oder Gruppen erstellen**. Bevor du mit der Entwicklung
> beginnst, müssen Ideen für neue Projekte mit den Admins abgesprochen werden.
>
{style="note"}

Jedes Projekt wird nach folgender Struktur aufgebaut:

1. **Hauptprojekt** erstellen.
2. **Subprojekt API** erstellen:
    - Das API-Subprojekt sollte hauptsächlich aus Interfaces bestehen, die von der SLNE Development Gruppe implementiert
      werden.
    - Alle API-Methoden müssen als **Completable Futures** umgesetzt werden.
3. **Subprojekt Core** erstellen (optional):
    - Das Core-Subprojekt enthält gemeinsamen Code für Paper und Velocity.
    - Gemeinsame Funktionen, wie z. B. ein Usercache, sollten hier initialisiert werden, um doppelten Code zu vermeiden.
4. **Subprojekt Paper / Velocity** erstellen:
    - Paper und Velocity enthalten jeweils den spezifischen Code, z. B. Listener, Commands etc.

```mermaid
flowchart TD
   A[Hauptprojekt] --> B[Subprojekt API]
   A --> C["Subprojekt Core (optional)"]
   A --> D[Subprojekt Paper]
   A --> E[Subprojekt Velocity]
   B --> B1[Interfaces]
   B1 --> B2[SLNE Development Implementations]
   B --> B3["API-Methoden (Completable Futures)"]
   C --> C1[Gemeinsamer Code für Paper und Velocity]
   C1 --> C2[Usercache und andere gemeinsame Funktionen]
   D --> D1[Paper-spezifischer Code]
   D1 --> D2[Listener]
   D1 --> D3[Commands]
   E --> E1[Velocity-spezifischer Code]
   E1 --> E2[Listener]
   E1 --> E3[Commands]
```