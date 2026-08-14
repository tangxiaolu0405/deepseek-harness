# npm 迁移说明

把包管理器从 pnpm 换成 npm。改动如下：

| 文件 | 改动 |
| --- | --- |
| `package.json` | `packageManager` 改为 `npm@11.7.0`；`pnpm --filter <pkg> run X` 改为 `npm run X --workspace=<pkg>`，`pnpm exec X` 改为 `npm exec X` |
| `packages/host/apiproxy/package.json` | 从 `dependencies` 移除 `@deepseek-ai/cordis`（`peerDependencies` / `devDependencies` 中保留） |
| `pnpm-lock.yaml` | 删除 |
| `README.zh.md` / `README.md` | 源码运行示例增加 npm 回退命令：`npm run build --workspace=@deepseek-ai/dsh-web-frontend`、`npm run dsh -- web` |
