# 校網95客觀選校（Net 95）

靜態網站：`index.html` 讀取同目錄 `data.json`。  
更新流程：**改 `data.json` → git push → GitHub Pages 自動上線**。

## 本地預覽

唔好直接用 `file://`（瀏覽器會擋 `fetch`）。用：

```bash
cd net95-landing
python3 -m http.server 8080
```

然後打開 http://127.0.0.1:8080/

## 部署到 GitHub Pages

1. 喺 GitHub 開新 repo（建議公開），例如 `net95-guide`
2. 把本資料夾內容 push 去 `main`（`index.html` 同 `data.json` 放根目錄）
3. Repo → **Settings** → **Pages** → Source 選 **Deploy from a branch** → Branch: `main` / `/ (root)`
4. 幾分鐘後網站：`https://<你的帳號>.github.io/net95-guide/`

之後每次只更新資料：

```bash
# 改好 data.json 後
git add data.json
git commit -m "Update school data"
git push
```

Pages 會自動重新部署；家長刷新即見新數。

## 檔案

| 檔案 | 用途 |
|------|------|
| `index.html` | 篩選／排序介面 |
| `data.json` | **唯一資料源**（我持續更新呢份） |
| `chinese-moi.md` 等 | 研究方法說明（可選上線） |

## 免責

本站唔係教育局排名。缺資料會標明，唔會估數。
