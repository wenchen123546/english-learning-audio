# 給 Claude 的工作規則

- 回覆一律用繁體中文。
- 需要的外掛或程式直接安裝或開啟，不必先問：
  - 外掛：在 `.claude/settings.json` 的 `enabledPlugins` 加上 `"<名稱>@claude-plugins-official": true`（還沒安裝就先 `claude plugin install <名稱>@claude-plugins-official`），並提醒使用者要開新的工作階段才會生效。
  - 套件：npm、uv／pip 等，只從官方來源安裝；開工作階段時 `.claude/install-deps.sh` 會自動補裝缺少的套件。
- 修正要正式提交（git commit）：提交後會自動推上 GitHub，測試通過才會上線。不要自己加 `[skip ci]`。
