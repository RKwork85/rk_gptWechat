**/home/rkwork/rkwork/project/chatgpt-on-wechat/lib/itchat/core.py**


# Core 类

这个类定义在`core.py`文件中，是用于与微信进行交互的库的一部分。

## 初始化方法 `__init__(self)`

- 初始化`Core`类的实例。
- 设置一些初始状态和属性，如`alive`（表示核心是否运行），`isLogging`（是否记录日志）。
- 初始化存储类`storageClass`，用于存储和管理用户信息、消息列表等。
- 初始化`requests.Session()`对象`self.s`，用于发起网络请求。
- 初始化一些用于登录流程的属性，如`uuid`，`loginInfo`等。
- 初始化`functionDict`，用于存储不同类型的聊天功能。
- 设置一些用于接收消息循环的属性，如`receivingRetryCount`。

## 登录和消息处理相关方法

- `login(self, ...)`: 登录微信，显示二维码，等待扫描确认。
- `get_QRuuid(self)`: 获取用于登录的二维码UUID。
- `get_QR(self, uuid=None, ...)`: 下载并显示二维码。
- `check_login(self, uuid=None)`: 检查登录状态。
- `web_init(self)`: 初始化网络，获取用户信息、同步密钥等。
- `show_mobile_login(self)`: 显示手机微信登录标志。
- `start_receiving(self, ...)`: 开始接收消息循环。
- `get_msg(self)`: 获取消息。
- `logout(self)`: 登出微信。

## 联系人和聊天室管理相关方法

- `update_chatroom(self, userName, detailedMember=False)`: 更新聊天室信息。
- `update_friend(self, userName)`: 更新好友信息。
- `get_contact(self, update=False)`: 获取联系人列表。
- `get_friends(self, update=False)`: 获取好友列表。
- `get_chatrooms(self, update=False, contactOnly=False)`: 获取聊天室列表。
- `get_mps(self, update=False)`: 获取公众号列表。

## 消息发送相关方法

- `send_raw_msg(self, msgType, content, toUserName)`: 发送原始消息。
- `send_msg(self, msg='Test Message', toUserName=None)`: 发送文本消息。
- `upload_file(self, fileDir, ...)`: 上传文件并获取媒体ID。
- `send_file(self, fileDir, ...)`: 发送文件。
- `send_image(self, fileDir=None, ...)`: 发送图片。
- `send_video(self, fileDir=None, ...)`: 发送视频。
- `send(self, msg, toUserName=None, mediaId=None)`: 发送不同类型的消息。

## 热重载和自动登录相关方法

- `dump_login_status(self, fileDir=None)`: 保存登录状态。
- `load_login_status(self, fileDir, ...)`: 加载登录状态。
- `auto_login(self, hotReload=False, ...)`: 自动登录。

## 消息注册和运行相关方法

- `configured_reply(self)`: 配置化回复。
- `msg_register(self, msgType, ...)`: 注册消息处理函数。
- `run(self, debug=True, blockThread=True)`: 开始自动回复。

## 搜索相关方法

- `search_friends(self, ...)`: 搜索好友。
- `search_chatrooms(self, ...)`: 搜索聊天室。
- `search_mps(self, ...)`: 搜索公众号。

## 其他方法

- `set_alias(self, userName, alias)`: 设置好友备注。
- `set_pinned(self, userName, isPinned=True)`: 设置好友或聊天室置顶。
- `accept_friend(self, userName, v4, autoUpdate=True)`: 接受好友请求。
- `create_chatroom(self, memberList, topic='')`: 创建聊天室。
- `set_chatroom_name(self, chatroomUserName, name)`: 设置聊天室名称。
- `delete_member_from_chatroom(self, chatroomUserName, memberList)`: 从聊天室删除成员。
- `add_member_into_chatroom(self, chatroomUserName, memberList, useInvitation=False)`: 向聊天室添加成员。
- `revoke(self, msgId, toUserName, localId=None)`: 撤回消息。

## 属性和装饰器

- `NOT_SUPPORT_REPLYTYPE`: 一个空列表，可能用于存储不支持的回复类型。

## 装饰器 `singleton`

- 这个装饰器用于确保`WechatChannel`类只有一个实例。

## 注意

- 这段代码中的方法大多数都抛出了`NotImplementedError`异常，这意味着这些方法需要在子类中具体实现。

这个类似乎是用于与微信服务器进行通信的核心类，提供了登录、消息发送、联系人管理等功能。