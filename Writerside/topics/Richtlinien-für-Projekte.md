# Richtlinien für Projekte

Um eine konsistente Entwicklung sicherzustellen, gelten für alle Projekte folgende Richtlinien:

{sorted="asc"}
Programmiersprache
: Für neue Projekte wird ausschließlich `Java` verwendet. Obwohl `Kotlin` kürzeren Code ermöglicht, führt es laut Simon
auch zu unübersichtlicherem Code (weiß ich ja nicht, aber gut).

Gruppenname und Versionierung
: Für neue Gradle-Projekte musst du die Gruppe `dev.slne` verwenden.
Die Versionsnummern sollten dem Format `X-1.0.0-SNAPSHOT` folgen, wobei `X` stets der aktuell verwendeten
Minecraft/Paper-Version entspricht (z. B. `1.21.1-1.0.0-SNAPSHOT`).
Dies gewährleistet Konsistenz und Kompatibilität in unseren Projekten.

Gradle-Builddateien
: Alle Gradle-Projekte sollten auf `Kotlin Build Files` basieren.
Verwende daher `build.gradle.kts` statt `build.gradle`.

Programmierung
: Es wird ausschließlich **Objektorientierte Programmierung (OOP)** eingesetzt.

Commands
: Für die Implementierung von Commands nutzt du die [CommandAPI](https://commandapi.jorel.dev/).\
Verwende das [PlayerArgument](https://commandapi.jorel.dev/9.5.2/argument_entities.html#player-argument) nicht.
Stattdessen solltest du
das [EntitySelectorArgument.OneEntity](https://commandapi.jorel.dev/9.5.2/argument_entities.html#entity-selector-argument)
verwenden.

Datenstrukturen
: Für **Listen, Sets, Maps** und andere Datenstrukturen benutzt du [fastutil](https://fastutil.di.unimi.it/).

Caches
: Für Caches verwendest du [Caffeine](https://github.com/ben-manes/caffeine).

Build-Tool
: Alle Projekte verwenden **Gradle** als Build-Tool.

Shading
: Für Shading nutzt du das [Shadow Plugin](https://gradleup.com/shadow/introduction/).
Achte darauf, korrektes Relocating durchzuführen.
Überlege auch, ob es notwendig ist, eine Abhängigkeit mit zu shaden, oder ob sie über den PluginLoader geladen werden
kann. Weitere Informationen zum PluginLoader findest
du [hier](https://docs.papermc.io/paper/dev/getting-started/paper-plugins#loaders).
Dieser kann auch automatisch
vom [plugin-yml Gradle Plugin](https://github.com/Minecrell/plugin-yml?tab=readme-ov-file#paper-1) generiert werden.

Lokales Testen
: Für das lokale Testen kannst du [run-task](https://github.com/jpenilla/run-task) verwenden.

paper-plugin.yml
: Für die Erstellung der `paper-plugin.yml` nutzt du das Gradle
Plugin [plugin-yml](https://github.com/Minecrell/plugin-yml).


<procedure title="Code-Stil">
<step>

Es wird eine Abänderung des Google Codestyles verwendet.
Diese findest du in der Datei `surf-codestyle.xml`.

</step>
<step>
Richtige Datei herunterladen:

- IntelliJ: <resource src="surf-codestyle-intellij.xml">`surf-codestyle-intellij.xml`</resource>
- Eclipse: <resource src="surf-codestyle-eclipse.xml">`surf-codestyle-eclipse.xml`</resource>
- Andere: <resource src=".editorconfig">`.editorconfig`</resource>


</step>
<step>

Importieren des Codestyles in IntelliJ

![import](import-codestyle.png) {thumbnail="true"}

</step>
<step>

Setzen des Codestyles in IntelliJ

![set](set-codestyle.png) {thumbnail="true"}

</step>

</procedure>