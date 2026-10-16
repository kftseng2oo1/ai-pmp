# ✦ Prompt Studio · AI 提示詞生成器

上傳一張人物照片，勾選場景、動作、表情、光線等模組，由 Claude 分析照片後產生英文的 AI 繪圖提示詞。

**線上使用**：https://kftseng2oo1.github.io/ai-pmp/

## 主要功能
- 預設風格一鍵套用：戶外花田、電影感、雪山冬景、森林秘境、黃金時刻、氛圍寫真
- 自選模組組合：動作（walking slowly、gazing afar…）、情緒、場景（竹林、薰衣草田、雲霧山谷…）、光線
- 上傳照片後，Claude 先用中文分析人物外觀並推薦場景，再輸出優化後的英文提示詞
- API 失敗時仍會顯示由選項組成的基礎提示詞
- 一鍵複製到剪貼簿

## 使用方式
1. 第一次開啟時選擇連線方式：**Cloudflare Worker（推薦）** 或 **直連 Anthropic**（需自備 `sk-ant-` API Key）
2. 上傳照片（可略過）
3. 點選預設風格或自行勾選模組
4. 按「✦ 生成專屬提示詞」，完成後複製

## 技術與依賴
- 單檔 HTML PWA（`index.html` 內含全部 HTML/CSS/JS），`manifest.json` + `sw.js` 提供安裝到主畫面與離線快取。
- AI：`claude-sonnet-4-20250514`，預設經 `arcar.kftseng2oo1.workers.dev` 代理，也可直連 `api.anthropic.com`
- 設定存在 localStorage：`ps_api_mode`、`ps_api_key`、`ps_worker_url`
