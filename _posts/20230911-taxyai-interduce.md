---
title: Taxy AI:基于 GPT-4 的浏览器全自动插件
tags: 
- ai
categories:
- AI
---

地址：https://github.com/TaxyAI/browser-extension


Taxy AI是一个可以让你用自然语言控制浏览器的扩展，它使用了GPT-4这个强大的人工智能模型。你可以给它一些简单的指令，让它帮你完成一些网页上的操作，比如填写表单，点击按钮，选择菜单等。Taxy AI还可以保存和定时你的工作流，来让你更高效地使用网页。

Taxy AI目前还在研究阶段，可能会出现一些错误或者不理想的结果。如果你对Taxy AI感兴趣，你可以在本地安装它，或者加入等待名单，等它正式发布。Taxy AI是完全开源的，不会把你的数据上传到任何地方。

要使用Taxy AI，你需要先在浏览器上安装它，然后获取一个OpenAI API Key，并把它输入到Taxy AI的设置里。这个密钥会安全地保存在你的浏览器里。然后你就可以打开任何一个网页，比如Google日历，给Taxy AI一个指令，比如“明天上午10点安排站会，邀请david@taxy.ai”，看它如何执行你的指令。

Taxy AI的工作原理是这样的：它会分析网页的内容，找出其中可以交互的元素，并给它们分配一个id。然后它会用GPT-4生成一个最合适的动作，比如setValue (id, text)，click (id)，select (id, value)等。它会把这个动作执行在网页上，并更新网页的状态。然后它会继续生成下一个动作，直到任务完成或者出现错误。

下面是基于TaxyAI的github做的一个总结，可以作为参考

- **Taxy是一个基于GPT-4的浏览器扩展**：它可以控制你的浏览器，帮你执行一些重复的操作。目前它可以让你定义一些临时的指令。未来它还会支持保存和定时的工作流。
- **Taxy的当前状态是研究预览**：它还有很多不完善的地方，可能会失败或者混淆。如果你想改进或者测试Taxy，你可以按照下面的说明在本地运行它。如果你想知道它什么时候可以广泛使用，你可以加入我们的等待名单。
- **Taxy是完全开源的，不会上传任何数据**：我们不会把任何页面内容或者指令发送到我们的服务器。
- **Taxy如何使用Google日历**：这里有一个视频演示了Taxy如何使用Google日历，指令是“明天上午10点安排站会，邀请david@taxy.ai”。
- **Taxy如何安装和使用**：目前这个扩展只能通过GitHub仓库安装。我们会在增加一些功能后发布到Chrome网上应用店。要在本地构建和安装扩展，你需要按照下面的说明操作。
- **Taxy有两种激活方式**：一种是按快捷键或者点击浏览器图标弹出一个窗口；另一种是打开浏览器的开发者工具，然后切换到Taxy AI面板。
- **Taxy需要OpenAI API Key**：你需要创建或者访问一个已有的OpenAI API Key，并把它粘贴到提供的框里。这个密钥会安全地存储在你的浏览器里，不会上传到第三方。
- **Taxy如何工作**：Taxy会在网页上运行一个内容脚本，获取整个DOM。它会简化它收到的html，只保留交互性或者语义上重要的元素，比如按钮或者文本。它会给每个交互元素分配一个id。然后它会“模板化”DOM，进一步减少token数量。
- **Taxy支持的动作**：Taxy目前支持以下动作：
  - setValue (id, text) - 聚焦一个文本输入框，清除已有文本，并输入指定的文本
  - click (id) - 点击一个元素
  - select (id, value) - 选择一个下拉菜单中的选项
  - scroll (id, direction) - 滚动一个元素
  - wait (seconds) - 等待指定的秒数
  - endTask () - 结束任务
- **Taxy如何判断任务完成**：Taxy有以下几种情况会判断任务完成：
  - Taxy执行了endTask ()动作。这是最明确的结束信号。
  - Taxy认为任务完成了。根据DOM和之前的动作历史，Taxy可能会返回一个表示任务完成的信号，而不是一个动作。
  - 用户停止了任务执行。用户可以随时停止Taxy的执行，不用等待它完成。
  - 发生了错误。Taxy的安全优先架构会导致它在遇到意外响应时自动停止执行。
