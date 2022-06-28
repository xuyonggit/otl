## 钉钉机器人发送群消息

```python
from otl.dingtalk import DingTalkApi

DINGTALK_CONFIG = {
    'NAME': '辣鸡',

    # 应用列表 可以配置多个应用
    'APP_LIST': {
        'warning_robot1': {  # 报警机器人别名
            'token': '',  # 机器人token
            'secret': ''  # 机器人加签密钥
        },
    }
}
DingTalk = DingTalkApi(DINGTALK_CONFIG)
status, msg = DingTalk.warning_robot1.send(
    title='辣鸡测试',  # 钉钉消息title
    content='真的测试',  # 消息内容
    msg_type='text',  # 消息类型，目前仅支持text/markdown
    at_users='all'  # at的用户列表，默认不@任何人，all - @所有人 '手机号,userid' 可填多个，','隔开
)
print(status, msg)
```