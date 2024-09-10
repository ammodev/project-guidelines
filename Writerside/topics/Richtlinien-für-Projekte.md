# Richtlinien für Projekte

Um eine konsistente Entwicklung sicherzustellen, gelten für alle Projekte die folgenden Richtlinien:

- Als Sprache für neue Projekte wird ausschließlich `Java` verwendet. `Kotlin` sorgt zwar für kürzeren, aber auch für
  unübersichtlicheren Code.
- Für neue Gradle-Projekte musst du die Gruppe `dev.slne` verwenden. Die Versionsnummern sollten dem
  Format `X-1.0.0-SNAPSHOT` folgen, wobei `X` stets der aktuell verwendeten Minecraft/Paper-Version entspricht
  (bspw. `1.21.1-1.0.0-SNAPSHOT`). Dies sorgt für Konsistenz und Kompatibilität in unseren Projekten.
- Alle Gradle Projekte sollten auf `Kotlin Build Files` basieren.
  Sprich du solltest die `build.gradle.kts` und nicht
  die `build.gradle` verwenden.
- **Objektorientierte Programmierung (OOP)** wird ausschließlich verwendet.
- Für **Commands** wird die [CommandAPI](https://commandapi.jorel.dev/) eingesetzt.
    - Das [PlayerArgument](https://commandapi.jorel.dev/9.5.2/argument_entities.html#player-argument) solltest du nicht
      verwenden. Verwende stattdessen
      das [EntitySelectorArgument.OneEntity](https://commandapi.jorel.dev/9.5.2/argument_entities.html#entity-selector-argument)
      Argument.
- Für **Listen, Sets, Maps** und andere Datenstrukturen benutzt du [fastutil](https://fastutil.di.unimi.it/).
- Für **Caches** benutzt du [Caffeine](https://github.com/ben-manes/caffeine).
- Alle Projekte verwenden **Gradle** als Build-Tool.
- Für **Shading** benutzt du das [Shadow Plugin](https://gradleup.com/shadow/introduction/), wobei auf
  richtiges Relocating geachtet werden muss.
  Auch solltest du überlegen, ob es überhaupt notwendig ist eine dependency mit zu shaden oder ob sie auch über den
  PluginLoader geladen werden kann.
  Siehe [hier](https://docs.papermc.io/paper/dev/getting-started/paper-plugins#loaders) für mehr Informationen zum
  PluginLoader. Dieser kann auch automatisch von
  dem [plugin-yml Gradle Plugin](https://github.com/Minecrell/plugin-yml?tab=readme-ov-file#paper-1) generiert werden.
- Für das lokale Testen kannst du [run-task](https://github.com/jpenilla/run-task) verwenden.
- Für die `paper-plugin.yml` verwendest du das Gradle Plugin [plugin-yml](https://github.com/Minecrell/plugin-yml).
- Als Codestyle wird eine Abänderung des Google Codestyles verwendet. Dieser ist in der Datei `surf-codestyle.xml` zu
  finden.
    - IntelliJ: <resource src="surf-codestyle-intellij.xml">`surf-codestyle-intellij.xml`</resource>
    - Eclipse: <resource src="surf-codestyle-eclipse.xml">`surf-codestyle-eclipse.xml`</resource>
    - Andere: <resource src=".editorconfig">`.editorconfig`</resource>
    - Importieren: ![Importieren des Codestyles in IntelliJ](import-codestyle.png)
    - Setzen (Muss nicht jedes Mal importiert werden, nur beim 1.
      Mal): ![Setzen des Codestyles in IntelliJ](set-codestyle.png)


