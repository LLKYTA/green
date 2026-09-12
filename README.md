# Auto Green · GitHub 自动贡献生成器

一个基于 GitHub Actions 的自动化脚本，每天在随机时间点生成若干次空提交，让你的 GitHub 贡献图保持“常绿”。支持随机跳过某些天、随机提交次数和随机等待间隔，行为更接近真实开发节奏。

## ✨ 特性

- **每天自动运行**：通过 `schedule` 定时触发，无需手动干预。
- **随机跳过**：每天有 1/10 的概率不提交，避免过于机械。
- **随机提交次数**：每天提交 5 ~ 30 次，每次都是空提交（`--allow-empty`）。
- **随机等待间隔**：每次提交之间等待 30 ~ 60 秒，模拟真实操作节奏。
- **支持手动触发**：配置了 `workflow_dispatch`，可在 Actions 页面手动测试。
- **轻量无依赖**：仅使用 `actions/checkout`，无需额外安装。

## 🚀 使用方法

1. **创建或使用现有仓库**  
   在 GitHub 上创建一个仓库（公开或私有均可），或使用你已有的仓库。

2. **添加 workflow 文件**  
   在仓库根目录创建 `.github/workflows/auto-green.yml`，将下方 [完整 workflow](#完整-workflow) 的内容复制进去。

3. **修改提交身份**  
   在 workflow 中找到以下两行，改成你自己的邮箱和用户名：
   ```yaml
   git config --local user.email "lys010107@163.com"
   git config --local user.name "LLKYTA"
