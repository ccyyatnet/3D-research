# 如何添加一篇新解读（内部文档）

本站基于 GitHub Pages（`main` 分支 `/docs` 目录）部署。

```bash
# 1. 将新的解读网页放入 docs/（首页固定为 docs/index.html，子页面可放 docs/<name>/index.html）
cp new_report.html docs/<paper-name>/index.html

# 2. 提交并推送，约 1 分钟后线上自动更新
git add docs/
git commit -m "Add <paper-name> reading notes"
git push origin main
```

推送后访问 `https://ccyyatnet.github.io/3D-research/<paper-name>/`。

同时在仓库根目录 `README.md` 的「📚 论文解读列表」表格中补一行记录。
