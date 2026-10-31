# AI流式翻译

网页原位翻译、输入框翻译和 Discord 翻译。

## 功能

- 网页文字原位替换，接口支持时流式显示译文，自动处理新加载的内容。
- 浏览器版可切换 DeepSeek、OpenAI、Claude、Gemini、千问、GLM、Kimi、OpenRouter、Ollama 等服务，也可填写自定义接口和模型。
- 网页目标语言和输入框目标语言分别设置，自动跳过已识别为目标语言的内容。
- 输入时保留原文，按 Enter 翻译后发送；可切换为停顿后实时替换。支持普通输入框、部分富文本编辑器和 B 站评论输入框。
- 实时替换模式按原文片段同步追加、删除和修改，译文不会计入原文。
- 支持翻译缓存、暂停、恢复原文、站点开关及自定义保留词。
- 保留专名、代码、公式和数字；译文过长时自动调整附近文字区域的换行和高度。
- Discord 版翻译界面与聊天内容，支持输入框按回车翻译后发送，输入设置集中在翻译菜单中。

## 浏览器安装

1. 安装 [Tampermonkey（油猴）](https://www.tampermonkey.net/)，允许用户脚本运行。
2. 打开 [安装 AI流式翻译](https://raw.githubusercontent.com/sunzhaocn/ai-streaming-translator/main/deepseek-web-translator.user.js)。若显示源码，在油猴中新建脚本，粘贴全部内容并保存。
3. 刷新网页，打开“译 · 目标语言”菜单。
4. 选择服务商，填写该服务的 API Key 和模型，设置目标语言，点击“保存并翻译”。

升级时覆盖油猴中的原脚本并保存，再刷新网页，避免同时启用两个副本。

## 输入框翻译

在翻译菜单中开启“当前输入框翻译”，选择输入目标语言和翻译方式。

| 方式 | 使用方法 |
| --- | --- |
| 按回车翻译并发送 | 点击输入框输入原文，按 Enter 后翻译并触发当前输入框的发送操作 |
| 实时替换输入内容 | 输入停顿后直接替换为译文，连续输入、删改会同步原文片段 |

多行框用 Shift+Enter 换行；输入法选词的回车不发送。翻译等待期间继续编辑会取消本次发送，翻译失败时保留原文。直接点击网站的发送按钮沿用网站原有行为；未响应自动发送的网站可手动发送已填入的译文。

## 服务与模型设置

- 切换服务商后填写对应的 Key，可从预置列表选择模型、获取当前服务的模型列表，或手动填写模型 ID。
- 自定义服务填写 API 地址、接口格式和模型名称。支持 Chat Completions、Responses 和 Anthropic Messages 格式。
- 各服务商及地址分别保存 Key。先点“测试连接”，再点“保存并翻译”应用。
- 使用 Ollama、LM Studio 时先启动本地模型服务，再选择相应接口。

## Discord 安装与使用

1. 安装 [BetterDiscord](https://betterdiscord.app/)。
2. 下载 [AI流式翻译 Discord 插件](https://raw.githubusercontent.com/sunzhaocn/ai-streaming-translator/main/DeepSeekTranslator.plugin.js)，放入 `%APPDATA%\BetterDiscord\plugins\`。
3. 在 Discord 的 BetterDiscord 插件列表中启用“AI流式翻译”。
4. 打开“译 · 目标语言”菜单，填写 DeepSeek API Key，选择模型和网页显示语言。
5. 在同一菜单的“输入框翻译设置”中选择输入目标语言和模式。默认输入原文，按 Enter 翻译后发送。

更新 Discord 插件时覆盖同名 `.plugin.js` 文件，保留原配置文件。

浏览器版 **2.3.2** · Discord 版 **1.15.2**
