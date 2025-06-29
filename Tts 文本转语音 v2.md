Tts 文本转语音

不要使用在线api，使用本地api类库
ChatGPT
如果不使用在线 API，而是使用本地 API 类库来实现将文本转换为语音播放的功能，可以使用一个本地的 TTS（Text-to-Speech）库。例如，flite（Festival Lite） 是一个轻量级、开源的 TTS 引擎，可以很方便地在本地生成语音。
下面是如何在 Go 中调用 flite 命令行工具将文本转换为语音的示例。
安装 flite
首先，您需要安装 flite。在大多数 Linux 发行版中，您可以使用包管理器来安装：

