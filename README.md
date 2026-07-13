# どっち — ふたりで選ぶ / 兩人一起選 / play together

三語(日本語・English・中文)的雙人小遊戲集,題目取自療癒系日本旅行世界(和菓子、角色、動物)。純靜態網站,無需 build。

## 遊戲

| 頁面 | 玩法 | 人數 |
|------|------|------|
| `tournament.html` | **勝ち抜き戦 / 淘汰賽** — 8 強兩兩對決,贏的晉級、輸的淘汰,選出冠軍 | 一到兩人 |
| `synchro.html` | **せーの! / 心有靈犀** — 各自偷偷選,同時翻開,想一樣就疊成紫色 | 兩人 |
| `decide.html` | **迷ったら / 交給命運** — 選不出來時,讓墨球幫你決定 | 一人也行 |

`index.html` 是入口,`pick.md` 是題庫來源。

## 設計

Risograph 雙墨疊印:粉 × 藍兩色油墨,相疊處生出紫色 —— 兩種語言、兩個人,重疊處才是「你們」。字體 Zen Maru Gothic(日/英)＋ Noto Sans TC(中)＋ DM Mono(數字)。

淘汰賽的角色與甜點全部以**純 HTML+CSS 手繪**(蠟筆 Q 版風,SVG 抖動濾鏡),不使用任何圖片素材 —— 全站零外部影像、無版權疑慮。

## 本機預覽

```bash
python3 -m http.server 8000   # 然後開 http://localhost:8000
```

直接雙擊 `index.html` 也能玩(字體走 Google Fonts CDN,需連網)。

## 部署到 GitHub Pages

1. push 到 GitHub repo。
2. **Settings → Pages → Source** 選 `Deploy from a branch`,分支 `main`、資料夾 `/ (root)`。
3. 自訂網域已設在 `CNAME`:`pick-game.neilkuan.click`。
   到 DNS 服務商新增一筆 **CNAME 記錄**:`pick-game` → `<你的帳號>.github.io`。
4. 網域生效後,勾選 **Enforce HTTPS**。

已就緒的細節:
- 全站使用相對路徑,子路徑或自訂網域都能運作。
- `.nojekyll` 讓 Pages 原樣提供檔案,跳過 Jekyll。
- `assets/favicon.svg` 疊印圖示已連結到每一頁。
