# Overview

## What This Is

個人 Minecraft Java 版實驗工作區。包含兩個 **NeoForge 1.21.1** mod、若干資源包,以及建置／規格用的 agent skills。每個子專案各自用 Gradle 建置;mod 與資源包獨立演進,共用同一套開發環境與 skill 工具鏈。

## Key Concepts / Domain

- **NeoForge 1.21.1 / JDK 21** — 兩個 mod 的目標平台與編譯版本(見 `docs/notes.md` 的 `JAVA_HOME` 設定)。
- **Mods** — `Karst_terrian/`(地形 biome)與 `Magic_Storage/`(儲存+合成,**獨立 git repo**)。
- **Resource packs** — `resource-packs/` 下每個資料夾對應一個包;成品資料夾與 `.zip` 都放這。
- **Agent skills** — `.agents/skills/` 下經 skillshare-reveal 顯露的 minecraft 系列 skill(規格、紋路、音效、GameTest 等)。

## External Resources

- 本倉庫:https://github.com/swear01/diy_minecraft_mods
- 舊的單包 mod 倉庫 `karst-terrain` 已封存,以本 repo 內 `Karst_terrian/` 為準。
