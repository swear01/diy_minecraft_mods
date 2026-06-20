# DIY Minecraft Mods

個人 Minecraft Java 版實驗工作區：NeoForge mod、資源包，以及建置／規格用的 **agent skills**（給 Cursor／Claude 這類工具讀的說明與腳本）。

## 目錄結構

| 路徑 | 說明 |
|------|------|
| [`Karst_terrian/`](Karst_terrian/) | **NeoForge 1.21.1** mod「Karst Terrain」—喀斯特高地型 biome、石灰岩等。詳見該目錄 [`README.md`](Karst_terrian/README.md)。 |
| [`Magic_Storage/`](Magic_Storage/) | **NeoForge 1.21.1** mod「Magic Storage」—一站式儲存+合成系統（概念仿 Terraria Magic Storage，實作模式參考 Refined Storage 2）。**獨立 git repo**；詳見該目錄 [`docs/overview.md`](Magic_Storage/docs/overview.md)。 |
| [`resource-packs/`](resource-packs/) | 資源包專案（例如 `mushroom_zombie_1_21_1`、`cantaloupe_1_21_1`）。**成品目錄與 `.zip` 都放這裡**，不要在 repo 裡再複製一份到 `resources/resourcepacks`。 |
| [`.agents/skills/`](.agents/skills/) | 資源包／mod 規格、紋路、音效、GameTest 等輔助 skill 與腳本。 |

## 環境設定（Java）

本 repo 使用 Homebrew 安裝的 JDK，不在系統 PATH 上。建置前需設定 `JAVA_HOME`：

```bash
export JAVA_HOME=/opt/homebrew/opt/openjdk@21/libexec/openjdk.jdk/Contents/Home
```

（JDK 21 用於 1.21.1 NeoForge；JDK 25 在 `/opt/homebrew/opt/openjdk/` 供未來升級）

## Mod 開發

### Magic Storage

```bash
cd Magic_Storage
export JAVA_HOME=/opt/homebrew/opt/openjdk@21/libexec/openjdk.jdk/Contents/Home
./gradlew build              # 編譯 + SelfTest（70 項）+ GameTest（53 項）
./gradlew runClient          # 啟動客戶端測試
./gradlew runGameTestServer  # 僅跑 GameTest
```

### Karst Terrain

```bash
cd Karst_terrian
export JAVA_HOME=/opt/homebrew/opt/openjdk@21/libexec/openjdk.jdk/Contents/Home
./gradlew build
./gradlew runClient
```

執行與依賴版本以各子目錄 `gradle.properties` 為準。

## 資源包

- 每個子資料夾通常對應一個包（spec、解開的資料夾、可選 `.zip`）。  
- 要給遊戲用時，將資料夾或 zip 放到**遊戲實例**的 `resourcepacks`，或使用 skill 腳本的 `--copy-to` 指到該路徑。  
- 建置流程見 [`.agents/skills/minecraft-resource-pack-builder/SKILL.md`](.agents/skills/minecraft-resource-pack-builder/SKILL.md)。

## 版控注意

- `Karst_terrian`、`Magic_Storage` 的 `build/`、`.gradle/`、`run/` 等由各子專案 `.gitignore` 排除。  
- 根目錄忽略 `node_modules`、Python `__pycache__`、以及 `.claude/settings.local.json`。

## 相關 GitHub

- 本倉庫：**[swear01/diy_minecraft_mods](https://github.com/swear01/diy_minecraft_mods)**  
- 舊的單包 mod 倉庫 **`karst-terrain`** 已封存；以本 repo 內 `Karst_terrian/` 為準。
