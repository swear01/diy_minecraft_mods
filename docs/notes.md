# Notes

> Tacit knowledge an agent can't infer from reading code.

## Gotchas

- **JAVA_HOME 必設**:本機 JDK 由 Homebrew 安裝,不在系統 PATH。建置前先設定:
  ```bash
  export JAVA_HOME=/opt/homebrew/opt/openjdk@21/libexec/openjdk.jdk/Contents/Home
  ```
  JDK 21 對應 1.21.1 NeoForge;JDK 25 在 `/opt/homebrew/opt/openjdk/` 供未來升級。
- **`Magic_Storage/` 是獨立 repo**:在它底下的 git 操作走它自己的歷史,與根 repo 無關。
- **資源包只留一份**:放在 `resource-packs/`,不要再複製到 `resources/resourcepacks`。

## Decisions

- 兩個 mod 各自為獨立 Gradle 專案,共存於同一工作區,方便共用 skill 工具鏈與環境設定。
- `Magic_Storage` 維持為獨立 git repo(而非合併進根 repo),故依 agent-rules 慣例給它自己的 AGENTS.md;`Karst_terrian` 無獨立 repo,規則由根 AGENTS.md 涵蓋。
