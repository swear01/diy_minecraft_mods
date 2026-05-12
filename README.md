# DIY Minecraft Mods

個人 Minecraft Java 版實驗工作區：NeoForge mod、資源包，以及建置／規格用的 **agent skills**（給 Cursor／Claude 這類工具讀的說明與腳本）。

## 目錄結構

| 路徑 | 說明 |
|------|------|
| [`Karst_terrian/`](Karst_terrian/) | **NeoForge 1.21.1** mod「Karst Terrain」—喀斯特高地型 biome、石灰岩等。詳見該目錄 [`README.md`](Karst_terrian/README.md)。 |
| [`resource-packs/`](resource-packs/) | 資源包專案（例如 `mushroom_zombie_1_21_1`、`cantaloupe_1_21_1`）。**成品目錄與 `.zip` 都放這裡**，不要在 repo 裡再複製一份到 `resources/resourcepacks`。 |
| [`skills/`](skills/) | 資源包／mod 規格、紋路、音效、GameTest 等輔助 skill 與腳本。 |

## Mod 開發（Karst_terrian）

- **需求：** Java 21、專案內附的 Gradle Wrapper。  
- **常用指令：**

```bash
cd Karst_terrian
./gradlew build
./gradlew runClient
```

執行與依賴版本以 `Karst_terrian/README.md` 與 `gradle.properties` 為準。

## 資源包

- 每個子資料夾通常對應一個包（spec、解開的資料夾、可選 `.zip`）。  
- 要給遊戲用時，將資料夾或 zip 放到**遊戲實例**的 `resourcepacks`，或使用 skill 腳本的 `--copy-to` 指到該路徑。  
- 建置流程見 [`skills/minecraft-resource-pack-builder/SKILL.md`](skills/minecraft-resource-pack-builder/SKILL.md)。

## 版控注意

- `Karst_terrian` 的 `build/`、`.gradle/`、`run/` 等由該子專案 `.gitignore` 排除。  
- 根目錄忽略 `node_modules`、Python `__pycache__`、以及 `.claude/settings.local.json`。

## 相關 GitHub

- 本倉庫：**[swear01/diy_minecraft_mods](https://github.com/swear01/diy_minecraft_mods)**  
- 舊的單包 mod 倉庫 **`karst-terrain`** 已封存；以本 repo 內 `Karst_terrian/` 為準。
