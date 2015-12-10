# Pull Request 书写指南

基于 Github Flow 进行协作时，如何创建完整、清晰的 Pull Request 是其中关键一环。工具检查是最有力的保障，但仍有一些文字书写的部分只能靠约定，本文就是对 Pull Request 文字书写部分的规范。

这些约定的目标是增加开发过程的透明度，好处有（包括但不仅限于）：
- 利于 Reviewer 快速准确地完成 review
- 新近成员能更快理解历史代码和渊源
- 追查 Bug 时的线索更充分而无关干扰更少

约定是最简单的事情，真正的难点在于推广和执行。所以本文规范条款尽量不做太严格的约束，以便执行的时候能够严格操作。如果你觉得某一项在团队中很难推行开来，就撤掉它，不要写在章法里却无法执行。

## 撰写 Pull Request

1. __一个 PR 只围绕一件事情__
  - 如果确有必要将几件事情（例如修改特别小、相互之间有依赖等）一起提交 PR，则需要列明具体每一件事情，确保 __PR 说明涵盖了所有修改内容__。
  - __大片的代码格式整理__要作独立提交（Commit），不要和__代码修改__混在一起，以便 Reviewer 能轻松查看干净的代码修改 diff。

1. __避免超大的 PR__  
  - 超过 1000 行修改行数的 PR 需要考虑是否能拆分为多个子任务分别提 PR（合理的程序结构设计也应该是解耦的）。
  - 如果 PR 包含的提交数量过多，通常是开发过程掺杂了“尝试—修问题—换个方法再来”这样的重构反复。此种情况最好抛弃这些过程提交，新开分支逐个应用有意义的修改，然后提 PR。

1. __PR 标题——概述此次 Pull Request 的目标__
  - 例如：`尝试用 XXX 方法实现……`、`优化……`、`修复在 XX 状态下对 XX 的异常处理`。

1. __PR 说明——面向未来的 Reviewer__
  - 记住公司里任何人，任何时候都有可能来阅读这个 Pull Request，所以内容和语气都需要面向未来可能的 Reviewer，不要假定对方已经熟悉这些事情的前因后果。
  - 酌情提供关于这些工作起因的说明，记得包含相关链接。例如跟特殊业务相关的地方，需要添加相关业务文档链接；处理了非常奇异的 Bug，就有必要附上相关线索、资料链接。

1. __详述需要哪些反馈（如果有的话）__
  - 如：@某人过目一下代码/讨论某项技术实现/对设计的意见等等。
  - 明确你*何时*需要反馈。如果这个 PR 还没有完成（仍有一些代码修改待推送）则需醒目注明，给标题加上`[WIP]`（施工中）的前缀是个简便快捷的方法。

## 提供反馈

- 首先要了解下此 PR 的前情提要。
- 如果你有强烈的反对意见，多花几分钟审视下自己的意见再做反馈。Think Twice。

## 对反馈的回复

- 尽量回复所有评论。尊重评论者对 PR 的关心。
- 提供澄清。解释对方有疑问的实现方案是如何决策的。
- 链接到相关的后续提交。（“好建议！a1da2324ca 已搞定 :D”）
- 如果疑惑和争论持续扩大，尝试面对面做充分沟通，之后把线下沟通的内容汇总回复（便于其他人跟踪进展或未来了解详情）。
