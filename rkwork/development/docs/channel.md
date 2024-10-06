# Channel 类（消息发送通道抽象类）

这是一个抽象基类，用于定义消息发送通道的通用接口。

## 导入的模块

- `bridge.bridge`：定义了与桥接服务通信的接口。
- `bridge.context`：定义了上下文对象。
- `bridge.reply`：定义了回复对象。

## 类变量

- `channel_type`：通道类型。
- `NOT_SUPPORT_REPLYTYPE`：不支持回复的类型列表，默认包含语音和图片。

## 方法

### 初始化方法 `startup(self)`

初始化通道。

```python
def startup(self):
    """
    init channel
    """
    raise NotImplementedError