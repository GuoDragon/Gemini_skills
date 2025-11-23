# Gemini使用技巧

## 1. 环境配置
1. 使用 Gemini API 方式登录 Gemini，网站为 `https://link.zhihu.com/?target=https%3A//makersuite.google.com/app/apikey`，并在系统环境变量中配置 `GEMINI_API_KEY = Your_Key`
2. Gemini API 需要使用外网
3. 为不污染环境，只在当前打开的 cmd 中配置 Clash 的端口号，不在系统环境变量中配置
4. 相关内容在 `D:\lcl\Gemini使用技巧\gemini_proxy.bat` 中
5. 使用方法：
   1. 打开 cmd，并进入工作目录
   2. 执行 `gemini_proxy.bat`
   3. 再输入 `gemini` 即可使用

## 2. 说明文件
1. 可以在 `C:\Users\用户名\.gemini\` 下创建 `GEMINI.md` 文件，用于记录当前工作需要使用的专属配置
2. 也在工作目录中创建 `GEMINI.md` 文件，工作目录的配置会覆盖全局目录
3. `sandbox` 用于配置是否开启沙箱模式，默认值为 `no`，表示直接在本地环境中更改或运行文件
4. `default_prompt` 用于配置默认的提示词，默认值为 `请用中文回答我，保持专业、清晰`，用于使模型保持中文回答

## 3. 命令

### 3.1 命令行参数
可通过 `gemini --help` 查看所有命令行参数
1. `gemini -p "..."` 非交互模式下直接回答 "..." 的问题
2. `gemini -a` 递归读取当前目录下所有文件作为上下文
3. `gemini -s` 开启沙盒模式
4. `gemini --yolo` 自动批准所有工具执行

### 3.2 斜杠命令
在交互模式中执行，可通过 `/help` 查看所有命令
1. `/clear` 清空终端显示
2. `/chat save <标签名>` 保存当前对话并指定标签名
3. `/chat resume <标签名>` 恢复指定标签名的对话
4. `/memory refresh` 重新加载所有 `GEMINI.md` 文件内容
5. `/compress` 让 AI 总结对话历史并替换上下文，节省 token
6. `/tools` 显示可用工具列表

### 3.3 特殊前缀
在交互模式中执行
1. `@<路径>` 指定 gemini 读取对应路径下的文件作为上下文
2. `!<shell 命令>` 直接执行 shell 命令并显示结果
3. `!` 切换 shell 模式的开启/关闭
