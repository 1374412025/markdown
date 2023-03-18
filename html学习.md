[TOC]



# HTML learning

## 网页基本标签

### 标题标签

``` html
<h1>一级标签</h1>
<h2>二级标签</h2>
<h3>三级标签</h3>
<h4>四级标签</h4>
```

### 段落标签

```html
<!--段落标签-->
<p>
    xue
</p>
<p>
    java
</p>
```

### 换行标签

```html
<!--换行标签-->
    xue <br/>
    java <br>
```

### 水平线标签

```html
<!--水平线标签-->
<hr/>
```

### 字体样式标签

```html
<!--粗体、斜体-->
<h1>字体样式</h1>
<strong>粗体： strong </strong> <br/>
<em>斜体：em</em>
```

### 注释

```html
<!-- 注释（ctrl + /）-->
```

### 特殊符号

```html
<!--特殊符号-->
空&nbsp;&nbsp;&nbsp;&nbsp;格<br/>
大于号：&gt;<br/>
小于号：&lt;<br/>
版权：&copy;
```

## 图像标签

![image-20221108144537506](C:\Users\杨\AppData\Roaming\Typora\typora-user-images\image-20221108144537506.png)

scr: 图片地址

​	相对地址：相对文件的地址

​	绝对地址：D:\IDEAworkspace\HTMLlearn\resources\image\image01.jpg

alt :图片名 当检索不到文件时，显示对应的文本内容

title：悬停显示文本

```html
<img src="../resources/image/image01.jpg" alt="yuan" title="yuanshen" width="192" height="135">
```

## 链接标签

### 超链接

href :跳转的页面
target: 表示在哪里打开窗口
    _blank: 新标签页
    _self：在当前页面打开

```html
<a href="tag.html" target="_blank">tag</a>
<br>
<a href="https:www.baidu.com">baidu</a>
<br>
<a href="https://ys.mihoyo.com/">
    <img src="../resources/image/image01.jpg" alt="yuan" title="yuanshen" width="192" height="135">
</a>
```

### 锚链接

```HTML
<!--锚标签-->
<a href="">回到顶部</a>
```

1. 需要一个锚标记

   ```HTML
   <a href="top">the top</a>
   ```

2. 跳转到标记

   ```HTML
   <a href="#top">回到顶部</a>
   ```

​	

tip：跨页面：

```html
<a href="hreftag.html#down">down</a>
```

### 功能性链接

邮箱链接：

```html
<a href="mailto:2392763193@qq.com">联系我</a>
```

qq链接：qq推广网站中生成对应链接

## 行内元素和块元素

块元素：

- 无论多少，独占一行
- （p、h1-h6...）

行内元素：

- 内容撑开宽度，左右都是行内元素的可以在同一行
- （a、strong...）

## 列表标签

### 有序列表

```html
<!--有序列表-->
<ol>
    <li>java</li>
    <li>python</li>
    <li>vue</li>
</ol>
```

![image-20221108153029578](C:\Users\杨\AppData\Roaming\Typora\typora-user-images\image-20221108153029578.png)

### 无序列表

```HTML
<!--无序列表-->
<ul>
    <li>java</li>
    <li>python</li>
    <li>vue</li>
</ul>
```

![image-20221108153042855](C:\Users\杨\AppData\Roaming\Typora\typora-user-images\image-20221108153042855.png)

### 自定义列表

- dl：标签
- dt：列表名称
- dd：列表内容

```html
<!--自定义列表-->
<dl>
    <dt>学科</dt>

    <dd>java</dd>
    <dd>python</dd>
    <dd>vue</dd>

    <dt>时间</dt>
    
    <dd>20</dd>
    <dd>21</dd>
    <dd>22</dd>
</dl>
```

![image-20221108153415997](C:\Users\杨\AppData\Roaming\Typora\typora-user-images\image-20221108153415997.png)

## 表格标签

table标签：

- tr ：添加一行 rows
  - colspan：跨列
- td：添加一列
  - rowspan：跨行
- border属性：边框大小

```HTML
<table border="1px">
    <tr>
        <td colspan="4">1-1</td>
    </tr>
    <tr>
        <td rowspan="2">2-1</td>
        <td>2-2</td>
        <td>2-3</td>
        <td>2-4</td>
    </tr>
    <tr>
        <td>3-2</td>
        <td>3-3</td>
        <td>3-4</td>
    </tr>
</table>
```

![image-20221108154410033](C:\Users\杨\AppData\Roaming\Typora\typora-user-images\image-20221108154410033.png)

## 视频和音频

### 视频元素：

video标签

- src：资源路径
- controls：控制条
- autoplay：自动播放

```html
<video src="../resources/video/vidue01.mp4" controls autoplay></video>
```

### 音频元素

audio标签

- src：资源路径
- controls：控制条
- autoplay：自动播放

```html
<audio src="../resources/audio/audio01.mp3" controls autoplay></audio>
```

## 页面结构分析

- header：标题头部区域的内容
- footer：标记脚部区域的内容
- section：Web页面中的一块独立区域
- article：独立的文章内容
- aside：相关内容或应用
- nav：导航类辅助内容

```html
<body>
<header>
    <h2>头部</h2>
</header>
<section>
    <h2>主体</h2>
</section>
<footer>
    <h2>脚部</h2>
</footer>
</body>
```

## iframe内联框架

- src：路径
- w-h ： 宽高
- frameborder：边框宽度

```HTML
<iframe src="//player.bilibili.com/player.html?aid=858826668&bvid=BV1DV4y157RD&cid=855365367&page=1" 
        scrolling="no" border="0" frameborder="no" framespacing="0" allowfullscreen="true"> 
</iframe>
```

```html
<iframe src="" name="hello" frameborder="0"></iframe>
<a href="list.html" target="hello">go</a>
```

可以将iframe的框架设置成链接跳转的位置

## 表单

### form标签

- method：规定如何发送表单数据（post、get）
  - get方式提交：可以在url中看到我们提交的信息，不安全，高效
  - post方式提交：无法看见信息，安全，传输大文件
- active：表示向何处发送数据 可以是网站也可以是servlet（请求处理地址）

```html
<form action="hreftag.html" method="post">
    <p>姓名： <input type="text" name="username"></p>
    <p>密码： <input type="password" name="userpwd"></p>
    <p>
        性别：
        <input type="radio" value="boy" name="sex"/>男
        <input type="radio" value="girl" name="sex"/>女
    </p>
    <p>
        爱好：
        <input type="checkbox" value="sleep" name="hobby">睡觉
        <input type="checkbox" value="play" name="hobby">玩
        <input type="checkbox" value="study" name="hobby">学习
    </p>
    <p>
        按钮：
        <input type="button" name="btn" value="button">
<!--        <input type="image" name="btn2" src="../resources/image/image01.jpg">-->
    </p>

<!--    下拉框-->
    <p>国家
        <select name="listname" >
            <option value="china" selected>china</option>
            <option value="USA">USA</option>
        </select>
    </p>

<!--    文本域-->
    <p>备注：<br>
        <textarea name="textarea"  cols="30" rows="10"></textarea>
    </p>
<!--    文件域-->
    <p>近期照片：<br>
    <input type="file" name="files">
    </p>

<!--    邮件验证-->
    <p>邮箱：
        <input type="email" name="email">
    </p>
<!--    URL验证-->
    <p>个人博客：
        <input type="url" name="url">
    </p>
<!--    年龄-->
    <p>年龄：
        <input type="number" name="age" min="0" max="100" step="1">
    </p>

<!--    滑块-->
    <p>
        <input type="range" min="0" max="100" name="voice" step="2">
    </p>
    
<!--    搜索-->
    <p>搜索：
        <input type="search" name="search">
    </p>
<!--    增强鼠标可用性-->
    <p>
        <label for="test">test</label>
        <input type="text" id="test">
    </p>
    <button type="submit">提交</button>
    <button type="reset">重置</button>
</form>
```

tips:

- 同一组单选框需需要标注同样的name属性
- readonly：只读，在有默认值的情况下不允许修改
- disable: 禁用
- hidden：隐藏元素
- 可使用label增强鼠标可用性

### 表单元素格式

- type：

  - 指定元素的类型

  - text    password    checkbox    radio    submit    reset    file    hidden    image    button    默认为text

- name:
  - 指定表单元素名称
- value：
  - 元素初始值
  - type为radio时必须指定一个值
- size:
  - 指定表单元素的初始宽度，当type为text或password时，表单元素的大小以字符为单位，其它以像素为单位
- maxlength
  - type为text或password时，输入的最大字符数
- checked
  - type为radio或者checked时，指定按钮是否被选中

### 表单初级验证

- placeholder：文本框提示信息
- required：非空判断
- pattern：正则表达式判断

```html
<p>
    自定义邮箱：
    <input type="text" name="diyemail" placeholder="请输入邮箱" required pattern="[\\w!#$%&'*+/=?^_`{|}~-]+(?:\\.[\\w!#$%&'*+/=?^_`{|}~-]+)*@(?:[\\w](?:[\\w-]*[\\w])?\\.)+[\\w](?:[\\w-]*[\\w])?">
</p>
```