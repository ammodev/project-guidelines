# Projektstruktur

> Externe Entwickler*innen dürfen **keine neuen Projekte oder Gruppen erstellen**. Ideen für neue Projekte müssen mit den
> Admins abgesprochen werden, bevor ihr mit der Entwicklung beginnt.
> 
{style="note"}

Jedes Projekt sollte der folgenden Struktur folgen:

1. **Hauptprojekt** erstellen
2. **Subprojekt API** erstellen:
    - Das API-Subprojekt sollte hauptsächlich aus Interfaces bestehen, die von der SLNE Development Gruppe implementiert
      werden.
    - Alle API-Methoden müssen zwingend **Completable Futures** sein.
3. **Subprojekt Core** erstellen (optional):
    - Das Core-Subprojekt enthält gemeinsamen Code für Paper und Velocity.
    - Gemeinsame Funktionen, wie z. B. ein Usercache, sollten hier initialisiert werden, um doppelten Code zu vermeiden.
4. **Subprojekt Paper / Velocity** erstellen:
    - Paper und Velocity enthalten jeweils den spezifischen Code, z. B. Listener, Commands, etc.