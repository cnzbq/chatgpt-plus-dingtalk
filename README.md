# ChatGPT Plus DingTalk Bot Plugin

ChatGPT Plus 钉钉机器人插件

🚧 此项目正在积极开发中 🚧

## 特性

- 🚀 帮助菜单 - 发送 `帮助` 可以查看帮助菜单
- 😊 私聊 - 向机器人发送消息即可开始聊天，自动关联上下文
- 💬 群聊 - 支持在群里艾特机器人进行对话
- 🎨 图片 - 通过发送 `图片+空格+描述` 来生成对应图片
- 📝 流程图 - 通过发送 `流程图+空格+描述` 来生成对应流程图
- 🐳 脑图 - 通过发送 `脑图+空格+描述` 来生成对应代码
- 🌐 浏览器查看消息 - 可在浏览器中查看对话消息(钉钉的markdown解析实在惨不忍睹)
- 📖 查看历史消息 - 可以查看历史消息

## 安装

### 1. 购买 ChatGPT Plus

[ChatGPT Plus](https://chatbot.kyubyong.com/)

### 2. 获取 Access Token

- 最新获取 Access Token 的方式请参考 [如何通过PKCE获取ChatGPT的AccessToken](https://zhile.io/2023/05/19/how-to-get-chatgpt-access-token-via-pkce.html)

- [国内获取](https://ai.fakeopen.com/auth) - 感谢 [@pengzhile](https://github.com/pengzhile)

- [官方获取](http://chat.openai.com/api/auth/session)

> Access Token 有效期 14 天，期间访问不需要梯子。这意味着你在手机上也可随意使用。

### 3. 部署应用

#### 3.1 Docker

```bash
docker run -itd \
    --name chatgpt-plus-dingtalk \
    --restart=always \
    -p 8080:8080 \
    -e CHATGPT_ACCESS_TOKEN="xxxxxx" \
    -e CHATGPT_MODEL="text-davinci-002-render-sha" \
    xbmlz/chatgpt-plus-dingtalk:latest
```

#### 3.2 二进制部署

下载[二进制文件](https://github.com/xbmlz/chatgpt-plus-dingtalk/releases)，解压缩到任意目录，执行如下命令

```bash
cp config.example.yml  config.yml

nohup ./chatgpt-plus-dingtalk &> run.log &
```

### 4. 创建钉钉机器人

- [创建钉钉机器人](https://open.dingtalk.com/document/orgapp/the-creation-and-installation-of-the-application-robot-in-the)

也可参考 [Dingtalk-OpenAI项目文档](https://github.com/ConnectAI-E/Dingtalk-OpenAI/tree/main#%E7%AC%AC%E4%BA%8C%E6%AD%A5%E5%88%9B%E5%BB%BA%E6%9C%BA%E5%99%A8%E4%BA%BA)

## 本地开发

```bash
git clone https://github.com/xbmlz/chatgpt-plus-dingtalk

cd chatgpt-plus-dingtalk

cp config.example.yml config.yml

go run main.go
```

