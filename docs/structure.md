# Structure

| Path | Purpose |
|------|---------|
| `Karst_terrian/` | NeoForge 1.21.1 mod「Karst Terrain」(`karst_terrain`, v0.2.0)— 喀斯特高地 biome、石灰岩等。屬本 repo。 |
| `Magic_Storage/` | NeoForge 1.21.1 mod「Magic Storage」(`magic_storage`, v0.1.0)— 一站式儲存+合成。**獨立的內嵌 git repo**,有自己的 AGENTS.md / docs。 |
| `resource-packs/` | 資源包專案(`cantaloupe_1_21_1`、`mushroom_zombie_1_21_1`)。成品資料夾與 `.zip` 都放這。 |
| `.agents/skills/` | 經 skillshare-reveal 顯露的 minecraft 系列 skill 與腳本。 |
| `docs/` | 給 AI agent 讀的專案文件(本目錄)。 |

## Module Boundaries

- `Magic_Storage/` 有自己的 `.git`,**不被根 repo 追蹤**(非 git submodule,無 `.gitmodules`)。它的版控、AGENTS.md、docs 都自成一套;在根 repo 不要把它當一般子目錄 commit。
- `Karst_terrian/` 是根 repo 的一部分;它的 `build/`、`.gradle/`、`run/` 由自身 `.gitignore` 排除。
- 資源包不要在 repo 內複製到 `resources/resourcepacks`——只保留 `resource-packs/` 一份。
