### 作者：浙江省新昌县城西小学 唐明	QQ:147885198

* 2015-8-31 完成类设计
* 2015-9-18 更新隐藏元素高度的计算方法getSize
* 2015-9-30 添加显示框架iframe方法showFrame
* 2015-12-9 兼容IE6（虽然显示效果很惨）

### 这是一个弹出对话框插件。

* 需要载入CSS文件和JS文件

```
    <link rel='stylesheet' type='text/css' href='dialog.css'/>
    <script src='dialog.js'></script>

```

* 参数:

```
    options={
    title:标题
    content:内容
    width:宽度,默认400像素
    height:高度,auto表示自适应高度,默认auto
    callback:回调函数
    buttons:显示按钮数组['close','cancel','ok']
    close_time:关闭时间（毫秒） =0表示不自动关闭 默认=0
    drag_able:是否可拖动//未实现
    modal:是否模态窗口//未实现
    border_radius:0,边框圆角
    left:
    top:  定位坐标，若不设置则在浏览器中间显示
    animation:false;是否动画
    padding:2;//内容的内边距
    }

```

### 使用方法

1. 创建dialog对象

```
var dialog=new Dialog({border_radius:10,animation:true,buttons:['close']});
```

此对象可以多次使用，全局共享。
2. 显示HTML内容
    
```
dialog.options.buttons=['close','ok'];
dialog.options.padding=20;
dialog.options.width=600;
dialog.options.height='auto';
dialog.show('发生错误','<h3>'+d.data+'</h3>');
```
	
3. 显示iframe框架

```
    dialog.options.buttons=['close'];
    dialog.options.padding=0;
    dialog.showFrame(title,url,width,height);
```

##### 本对话框组件的优势就是小巧、没有其它组件依赖，显示样式较为美观，具有动画弹出效果。代码组织合理，改写功能更为简单。
