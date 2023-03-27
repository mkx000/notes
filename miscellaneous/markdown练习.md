title: markdown练习
layout: post
typora-root-url:  /home/mkx
keywords: markdown  typora   manual


# markdown练习

[toc]

## 1 块元素（Block Elements）

### 1.0 渲染
突出`重点`
*斜体abc*
**加粗abc**
***斜体加粗abc***

### 1.1 标题和引用
> # 这是一级标题
> ## 这是二级标题
> ### 这是三级标题

### 1.2 表格
* 没有
* 顺序
* 的表格

1. 有
2. 顺序的
3. 表格

### 1.3 任务列表
- [ ] 一个
- [x] 任务
- [x] 列表
- [ ] 可以**formating**

### 1.4 代码快
```c++
  void int fun(){
  	printf("支持语法高亮的cpp代码快");
  	return 0;
  }
```
```ruby
require 'redcarpet'
markdown = Redcarpet.new("Hello World!")
puts markdown.to_html
```

### 1.5 数学表达式
$$
\mathbf{V}_1 \times \mathbf{V}_2 =  \begin{vmatrix}
\mathbf{i} & \mathbf{j} & \mathbf{k} \\
\frac{\partial X}{\partial u} &  \frac{\partial Y}{\partial u} & 0 \\
\frac{\partial X}{\partial v} &  \frac{\partial Y}{\partial v} & 0 \\
\end{vmatrix}
$$

### 1.6 表格
| 第一列左对起 | 第二列居中对齐 | 第三列右对齐 |
| ------ | :------: | ------: |
|        |        |        |

### 1.7 脚注
可以添加两个脚注，其甲[^脚注1]和乙[^脚注2]



### 1.8 添加横线
下面是两条横线
***
中间的文本
***


## 2 span元素
## 2.1 链接(通过[]分割)
### 2.1.1 inline links
这是一个[链接](http://baidu.com "可选的title")
这也是一个[链接](http://baidu.com) 没有**title**属性

### 2.1.2 internal（文件内部）链接
create a internal [链接](# 1 块元素（Block Elements）)跳到第一节

### 2.1.3 external (文件外部) 引用链接
这是一个引用链接的[例子][link1]
指向[阿里巴巴][]的链接

[link1]:http://baidu.com "选择性标题"
[阿里巴巴]: http://alibaba.com

### 2.1.4 URL
指向百度的链接<https://www.baidu.com>

### 2.1.5 插入图片

本地图片
![本地图片无法加载](./berkeley_eecs_course.png)
网络图片
![网络图片加载失败](https://jekyllrb.com/img/logo-2x.png)

### 2.1.6 画重点(Emphasis)
*这样画重点*
显示星号*

强调是**code**
use the `printf()` function

~~错误的文本~~

:smile:

### 2.1.7 inline math

文本中嵌入数学公式$\lim_{x \to \infty} \exp(-x) = 0$


### 2.1.8 上下标
H~2~O, X~long\ text~, e~x~,  x^2^

### 2.1.9 高亮
==这段文本高亮==   ==继续高亮==

## 3 HTML元素
<span style="color:red">this text is red</span>

### 3.1 下划线
<u> Underline</u>

### 3.2 Embed Contents
<iframe height='265' scrolling='no' title='Fancy Animated SVG Menu' src='http://codepen.io/jeangontijo/embed/OxVywj/?height=265&theme-id=0&default-tab=css,result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'></iframe>

### 3.3 嵌入视频
<video src="xxx.mp4" />

### 3.4  其他HTML元素


[^脚注1]:这是教主1
[^脚注2]:这是浇筑2