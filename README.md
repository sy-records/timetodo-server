## TimeTodo Server

🎈TimeTodo的服务端。此项目`fork`自 @Easy 的[timetodo-server](https://github.com/easychen/timetodo-server)，增加我在使用时所需要的一些东西

![timetodo.001.jpeg](https://ws3.sinaimg.cn/large/0072Lfvtly1g083kdotooj30m80m8aqd.jpg)

## 服务端部署

1. 修改`index.php`将其中`$APIKEY = '';`修改为`$APIKEY = 'yourkey';`以提升安全性
2. 将`index.php`和`_lp.php`上传到可以访问的`Web`服务器，我们假设其公网可访问链接为`http://somesite.com/`
3. 在Todo添加输入框输入`:webhook=https://somesite.com/?key=yourkey`并回车以设置`webhook`
4. 再次输入`:who`可以测试是否`work`。提示`It's me`为可以正常工作

## 增加功能

1. 使用`TalkAdmin`通过方糖公众号语音添加`TimeTodo`
2. `Bing`搜索英文单词翻译
3. 搜索`Swoole`文档
4. 按分类保存`TimeTodo`到远程
5. 按分类从远程拉取`TimeTodo`
6. 更多功能等你`PR`

## 使用说明

* 使用`TalkAdmin`通过方糖公众号语音添加`TimeTodo`

1. 登录[TalkAdmin](http://sc.ftqq.com/?c=talkadmin)添加命令
2. 设置正则，填入正确的回调地址
![image-20190216122841255](https://ws3.sinaimg.cn/large/006tKfTcgy1g085jdzm1uj31df0u0jw2.jpg)
3. 修改代码部分
当你给方糖公众号发语音时，会自动识别回调你设置的回调地址，比如我设置的正则如上图所示`/给(.+)中添加(.+)/`
说了一句：`给工作中添加续费服务器`，回调发送的`json`信息格式为：
```json
[
    [
        "给工作中添加续费服务器"
    ],
    [
        "工作"
    ],
    [
        "续费服务器"
    ]
]
```
转为数组后：`工作`为分类，`$arr[1][0]`; `续费服务器`为`Todo`内容，`$arr[2][0]`;

如果你的正则是其他的，需要修改以上变量

* `Bing`搜索英文单词翻译
```
# 在添加 Todo 的输入框输入后回车
:bing save
```
* 搜索`Swoole`文档
```
:swoole coroutine
```
* 按分类保存`TimeTodo`到远程
```
:save 工作
```
* 按分类从远程拉取`TimeTodo`
```
:load 娱乐
```

