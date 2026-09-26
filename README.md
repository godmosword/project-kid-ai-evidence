# project-kid-ai-evidence

[godmosword/project-kid-ai](https://github.com/godmosword/project-kid-ai)（KidsAI）PR 的**驗證證據**：iOS 模擬器截圖、GIF、mp4。
**Verification evidence** for [godmosword/project-kid-ai](https://github.com/godmosword/project-kid-ai) (KidsAI) pull requests: iOS Simulator screenshots, GIFs, and mp4 recordings.

## 用途 / Purpose

- Michael 在手機上看 PR 描述裡嵌入的圖片和影片，就能核准 UI 改動。
  Michael reviews UI changes from his phone by viewing the media embedded in each PR description.
- 檔案由主 repo 的 `.claude/skills/verify-kidsai/control-kidsai` 產生並推送；不要手動編輯。
  Files are generated and pushed by `.claude/skills/verify-kidsai/control-kidsai` in the main repo. Do not edit by hand.
- 本 repo 只放證據，不放程式碼。
  Evidence only, no code.

## 資料夾慣例 / Folder convention

```
pr-<N>/<run-id>/
  manifest.json      # git sha、模擬器型號／runtime、flow／feature id、進入點、檔案 sha256、拍攝時間（台北時間）
                     # git sha, simulator model/runtime, flow/feature id, entry point, file sha256, capture time (Asia/Taipei)
  <feature>-<step>.png
  <flow>.mp4         # ≤20 秒、h264 / ≤20 s, h264
  <flow>.gif         # 手機可直接播放 / plays inline on mobile
maintain/<date>/     # 每日維護的證據 / daily maintenance evidence
```

- `<run-id>` = `YYYYMMDD-HHMMSS-<git 短 sha>`（台北時間 / Asia/Taipei）。
- 同一個 PR 的多次執行放在不同的 `<run-id>`，舊的保留。
  Multiple runs for one PR use separate run ids; older runs are kept.
- PR 描述用 `https://raw.githubusercontent.com/godmosword/project-kid-ai-evidence/main/pr-<N>/<run-id>/<file>` 嵌入。
  PR descriptions embed files via raw.githubusercontent.com URLs.

## 隱私規則（絕對不可違反）/ Privacy rules (non-negotiable)

- **永遠不得出現兒童資料**：不得有姓名、照片、聲音、錄音、裝置識別碼，或任何可識別個人的內容。
  **No child data, ever**: no names, photos, voices, recordings, device identifiers, or anything personally identifying.
- 只拍專用模擬器 `KidsAI-Verify`（不登入 Apple ID、status bar 覆寫成固定值）；只用內建內容和假資料（例如研究代號 `T00`）。
  Only the dedicated `KidsAI-Verify` simulator (no Apple ID, status bar overridden); built-in content and fake fixtures only (e.g. research code `T00`).
- 模擬器錄影沒有聲音。
  Simulator recordings contain no audio.
- 不得 commit 金鑰、token 或憑證。`manifest.json` 不含本機使用者路徑。
  No keys, tokens, or credentials. `manifest.json` contains no local user paths.
- 發現違規請立刻刪除該檔案並通知 Michael。
  If a violation is found, delete the file immediately and notify Michael.
