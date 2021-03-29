# add-html-code-clipboard
剪贴板可以操作图片和文本, 那么如何才能同时操作图片+文本呢 , 找到了微软的一篇文章, 将它的方法封装成了dll

以上代码是利用的dll来实现
![img](https://www.htmlayout.cn/upload/image/20201103/1604334374508840.png)
同样的,利用aardio封装好的win.clip.html库可以很方便实现同时复制图片和文字, 并且可以对图文进行编码排版, 就像html那样写
示例如下:
import win.ui;
/*DSG{{*/
var winform = win.form(text="aardio form";right=338;bottom=185)
winform.add(
button={cls="button";text="copy";left=90;top=59;right=255;bottom=123;z=1}
)
/*}}*/
 
import win.clip.html;
var webClip = win.clip.html();
 
winform.button.oncommand = function(id,event){
    webClip.write(`
    <b>This is a aardio program .这是一个测试。</b>
    <hr>
    <li>entry 1
    <li>entry 2
    <img src="C:\Users\2222\Desktop\28.png" />
    `);
}
 
winform.show();
win.loopMessage();
