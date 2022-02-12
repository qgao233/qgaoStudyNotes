# **gitBook篇**
## **1. word文档转markdown**
writage 插件，下载地址http://www.writage.com/#download

下载安装完成后，重新打开word，保存原word文档为markdown类型即可

## **2. gitbook客户端**
安装客户端：npm install gitbook-cli –g

进入要存储的位置初始化gitbook: gitbook init

出现两个文件，README.md是说明文档，SUMMARY.md是书的章节目录

SUMMARY.md的初始化内容：

```
# Summary
* [Introduction](README.md)
```

## **3. 转成网页**
gitbook serve：该命令后会在书籍的文件夹中生成一个 \_book 文件夹, 里面的内容即为生成的 html

文件，并开启服务器（http://localhost:4000）

gitbook build：该命令生成网页而不开启服务器
## **4. 插件**
在gitbook init的目录下新建book.json，然后往里填入

```
{
    "plugins": [
        "expandable-chapters",##折叠目录
        "splitter",##收缩扩大目录
    ]
}
```

再通过gitbook install安装

## **5. bug**
### **Error: ENOENT: no such file or directory, stat (…) 【version 3.2.3】**
用户目录下找到以下文件。

.gitbook\versions\3.2.3\lib\output\website\copyPluginAssets.js

把所有的confirm: true替换为confirm: false

### **子目录中的md文件内目录格式失效**
不要把目录写在文件第1行，第1行无法起效

### **Template render error … expected variable end**
连在一起的两个大括号如

\{\{2\}\}

会把括号里的2当做一个模板变量。如果这个变量不存在，会报错 Template render error: expected variable end。详细的解释看下面：

https://wwshen.gitbooks.io/omooc2py/0MOOC/dakuohao.html

https://www.weihuayi.cn/tools/gitbook.html

https://juejin.im/post/5ce51e126fb9a07ed440d7d0#heading-22

解决方式

把连续的大括号\{\{替换为中间加个空格{ {，把\}\}替换为} }。

