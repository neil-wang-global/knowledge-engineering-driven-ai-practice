# Pomasa 多智能体工程重新初始化设计

## 目标

清理当前仓库中上一轮智能体工程的运行产物和中间文件，然后基于本机 `~/.pomasa/pomasa`，使用 `./user_input_template.md` 在仓库根目录重新初始化一个多智能体工程。

本次操作要保留研究证据链。`references/papers/`、`references/paper-visual/`、`references/web/` 必须保留，因为它们是后续演讲稿和 HTML 演示文件的引用来源。

## 保留范围

保留以下内容：

- `user_input_template.md`
- `references/papers/`
- `references/paper-visual/`
- `references/web/`
- `references/methodology/`
- `CLAUDE.md`
- `README.md`
- `package.json`、`package-lock.json`、`commitlint.config.cjs`、`lefthook.yml`
- `.gitignore` 与其他项目配置

## 清理范围

清理旧智能体工程和中间产物：

- `agents/`
- `workspace/research/`
- `_output/`
- `wip/`

如 Pomasa 初始化流程需要重建 `agents/`、`workspace/` 或输出目录，以新初始化结果为准。

## 初始化方式

从 `~/.pomasa/pomasa` 读取 Pomasa 模板、方法文件和智能体定义，在当前仓库根目录初始化新的多智能体工程。输入文件使用当前仓库中的 `./user_input_template.md`。

初始化后的工程应继续服务于同一研究任务：围绕《知识工程驱动的 AI 实践》生成中文 Markdown 演讲稿和 HTML 演示文件。

## 安全边界

不得删除以下目录：

- `references/papers/`
- `references/paper-visual/`
- `references/web/`
- `.git/`
- `node_modules/`

不得改写 `user_input_template.md`，除非用户另行要求。

## 验收标准

完成后需要确认：

1. 保留目录仍存在，尤其是 `references/papers/`、`references/paper-visual/`、`references/web/`。
2. 旧运行产物已清理，不再保留上一轮 `agents/`、`workspace/research/`、`_output/`、`wip/` 内容。
3. 新多智能体工程已在仓库根目录生成。
4. 新工程能从 `./user_input_template.md` 读取任务输入。
5. `git diff --check` 通过。

## 实施顺序

1. 查看 `~/.pomasa/pomasa` 的初始化说明和可复用模板。
2. 清理旧智能体工程和中间文件。
3. 基于 Pomasa 模板重新初始化当前仓库。
4. 检查保留目录和新工程结构。
5. 运行基础验证命令。
