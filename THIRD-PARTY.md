# Third-party dependencies and their licences

Every runtime dependency shipped inside the plugin zip, read from the real 2026.1.0 build on
2026-09-24.

**There are none.** The zip ships two jars, both the plugin's own: `sqlloglens-ide-2026.1.0.jar`
and `sqlloglens-core.jar`. The log parsers, the value quoting and the SQL formatter are all written
for this plugin. The Kotlin standard library is not bundled; the IntelliJ Platform provides it.

SqlLogLens depends on `com.intellij.modules.platform` and nothing else: no language plugin and no
Database or Ultimate-only module, which is what lets it install in every JetBrains IDE.
