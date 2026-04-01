# 🔗 URL Shortener

一鍵產生多個縮網址服務的短連結。支援多個主流縮網址平台。

## 功能

- ⚡ **多服務並行** — 同時嘗試多個縮網址服務
- 🔄 **自動降級** — API 被擋時自動提供「一鍵開啟」按鈕
- 📋 **一鍵複製** — 成功產生的短連結直接複製
- 📜 **歷史記錄** — localStorage 保存最近 20 條，可一鍵重新縮短
- 📱 **手機優先** — 響應式設計，手機桌機都好用

## 支援的服務

| 服務 | 模式 | 說明 |
|------|------|------|
| TinyURL | 自動 | 直接 API，成功率高 |
| is.gd | 自動 | 直接 API，速度快 |
| v.gd | 自動 | is.gd 姊妹站 |
| Bit.ly | 手動 | 需要登入，開啟分頁產生 |
| Short.io | 手動 | 開啟分頁產生 |
| Dub.co | 手動 | 開啟分頁產生 |

## 使用

直接開啟 `index.html` 即可，或部署到任何靜態空間。

## 為什麼有些服務要手動？

瀏覽器有 **CORS（跨域資源共享）** 限制，大部分縮網址 API 不允許從網頁直接呼叫。

本工具會先嘗試能直接呼叫的 API（TinyURL、is.gd、v.gd），其他服務則生成「開啟」連結讓你在新分頁快速產生。

## 部署到 GitHub Pages

1. 建立 GitHub repo
2. 上傳 `index.html`
3. Settings → Pages → Source 選 main branch
4. 完成

## 版本

目前版本：**v1.2**

## Changelog

| 版本 | 日期 | 異動 |
|------|------|------|
| v1.2 | 2026-04-01 | 修復 XSS（API 回應改用 DOM 方法而非 innerHTML）、修復按鈕 re-enable 邏輯（Promise.allSettled 改傳實際 fetch promises）、所有 target=_blank 加 rel="noopener noreferrer"、實作 localStorage 歷史記錄（最近 20 條）、input 加 autocorrect/autocapitalize/spellcheck 屬性 |
| v1.1 | 2026-03-16 | 加入手動服務（Bit.ly、Short.io、Dub.co）、自動降級邏輯 |
| v1.0 | 2026-03-16 | 初始版本 |

## License

MIT