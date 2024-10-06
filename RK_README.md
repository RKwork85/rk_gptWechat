# 关于使用Fastgpt构建的应用对接到Wechat


## Quick Start

**docker-compose 启动**
```bash

git clone https://github.com/RKwork85/rk_gptWechat.git
cd rkwork   

// 参考官方readme文档配置文件说明,修改配置文件 docker-compose.yml
line9: 
line11:
line16:
line20:

// 修改完成后执行
docker compose up -d 
```

最后运行以下命令可查看容器运行日志，扫描日志中的二维码即可完成登录：

```bash
sudo docker logs -f chatgpt-on-wechat
```

**开发 环境搭建**

对照 docker-compose, 修改config.json文件,后安装依赖

>pip install -r requirements.txt 
>pip install -r requirements-optional.txt

python app.py



### 关于配置项修改

**1.个人聊天**

触发机器人聊天：
+ 个人聊天中，需要以 "bot"或"@bot" 为开头的内容触发机器人，对应配置项 `single_chat_prefix` (如果不需要以前缀触发可以填写  `"single_chat_prefix": [""]`)

机器人回复格式：
+ 机器人回复的内容会以 "[bot] " 作为前缀， 以区分真人，对应的配置项为 `single_chat_reply_prefix` (如果不需要前缀可以填写 `"single_chat_reply_prefix": ""`)

清除历史对话
>      CLEAR_MEMORY_COMMANDS: '['clear']' # Undo
>      #reset 

**other**

1 理论上可以修改源代码，配置绘画SD本地API接口：Undo

2 对接fastgpt项目需要把 model名 改为fastgpt 模型列表中显示的名称，另外在发布渠道中生成密钥

3 关于开发详见**rkwork**目录
