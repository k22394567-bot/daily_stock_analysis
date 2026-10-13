# Repository Claude Skills

本目录存放仓库级协作 skills，属于版本库资产。

- 规则真源：仓库根目录 `AGENTS.md`
- 兼容入口：根目录 `CLAUDE.md`（应为指向 `AGENTS.md` 的软链接）
- 本目录中的 skill 需要与 `AGENTS.md` 保持一致
- `.claude/reviews/` 属于本地分析产物，不作为规则真源

如果未来需要兼容其他 agent 目录（如 `.agents/skills/` 或 `.github/skills/`），应先明确单一真源，再通过脚本或镜像同步，而不是手工长期维护多份同义内容。

## 第三方 skill

以下 skill 是外部项目的原样副本（vendored），不属于仓库协作规则，只保留上游 `SKILL.md` 与 `LICENSE`，本地不修改内容；升级时直接用上游同名文件覆盖并更新下表基线。

| 目录 | 用途 | 来源 | 同步基线 |
| --- | --- | --- | --- |
| `humanizer-zh-tw/` | 润饰繁体中文文章、评论与文档，删去空话、重复与公式化表达，同时保留事实与作者立场 | [kevintsai1202/Humanizer-zh-TW](https://github.com/kevintsai1202/Humanizer-zh-TW)（MIT） | commit `e2cb617`，2026-09-25 |

- 用法：在 Claude Code 中输入 `/humanizer-zh-tw`，后接待润饰的文字或文件路径。
- 未引入上游的 `README.md`、`CHANGELOG.md`、`tests/`，也未引入同仓库的配套 skill `text-watermark-cleaner-zh-tw`；`SKILL.md` 末尾指向后者的相对链接在本仓库中不可用，需要时再单独评估引入。
