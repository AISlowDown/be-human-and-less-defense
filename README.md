# Be Human and Less Defense

一个用于中英文学术写作的 Codex Skill：减少空泛套话、机械句式和重复辩解，同时保留数据、引文、技术术语与真正影响结论的限制。

它可用于根据数据和图表起草文字，也可用于检查已有的论文、基金申请书和审稿回复。处理已有文字时，Skill 会先逐项提出修改建议，由作者决定是否应用。

## 获取与安装

1. 在本仓库点击 **Code → Download ZIP**，解压。
2. 将解压后的整个文件夹重命名为 `be-human-and-less-defense`，放入 Codex 的 skills 目录：macOS/Linux 为 `~/.codex/skills/`，Windows 为 `%USERPROFILE%\.codex\skills\`。
3. 确认目录中直接包含 `SKILL.md`、`LICENSE` 和 `references/`，然后重新打开 Codex。

安装后的目录应类似：

```text
~/.codex/skills/be-human-and-less-defense/
├── SKILL.md
├── LICENSE
└── references/
    └── proposals.md
```

可在对话中输入 `$be-human-and-less-defense` 并附上要处理的内容。例如：

> 请用 $be-human-and-less-defense 检查这段 Results。先列出逐条修改建议，保留数据、引文和必要限制，等我选择后再改正文。

没有现成文字时，也可提供数据、图表和研究范围，请它直接起草。请核对生成内容与原始证据是否一致。

## 交给 Codex 或 WorkBuddy 安装

将下面这段话发给你的 Codex 或 WorkBuddy：

> 请从 https://github.com/AISlowDown/be-human-and-less-defense 安装 `be-human-and-less-defense` Skill。先检查 `SKILL.md` 和 `LICENSE`，按当前应用支持的方式安装；完成后确认它能被识别，并告诉我怎样调用。

如果 WorkBuddy 无法直接访问 GitHub，可下载仓库后参照[官方技能文档](https://cloud.tencent.com/document/product/1831/134432)使用本地技能包导入入口。Codex 安装后重新打开即可加载新 Skill。

## 文件与授权

- [`SKILL.md`](SKILL.md)：完整工作规则。
- [`references/proposals.md`](references/proposals.md)：修改建议表参考格式。
- [`LICENSE`](LICENSE)：MIT 许可及所依据项目的必要署名。
