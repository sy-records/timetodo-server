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
6. 更多功能等你`PR`…
