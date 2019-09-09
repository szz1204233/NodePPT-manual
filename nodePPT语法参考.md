# NodePPT使用手册

## 安装

1. 确保已安装npm，使用`npm -v`检测版本号；如未下载，可参见[此处](https://www.npmjs.cn/getting-started/installing-node/)  
2. 使用命令`npm install -g nodeppt`下载包

## 使用

### 创建文档

使用`nodeppt new`命令以新建文档。在创建过程中，填写字段分别为  
- `? filename:`文件名
- `Input your presentation topic:`描述对象（第一张PPT的标题）
- `Input your name:`作者  
可附加参数`-t <username/repo>`以从github对应仓库载入模板

### 本地运行

使用`nodeppt serve <filename.md>`以本地运行 filename.md 文件的 webpack dev server.  
将`Url`行复制至浏览器地址栏以预览放映效果，访问`Speaker Mode`行以预览演讲者视图。

### 编译及运行

使用`nodeppt build <filename.md>`以编译产出md文件。生成的dist文件夹中包括使用资源、样式等内容，可使用浏览器打开`filename.html`文件以放映幻灯片。  
放映时，可于浏览器地址栏中本地Url后附加参数`?mode=speaker`启用演讲者模式

## 语法

### Markdown简要语法

> `# `一级标题、`## `二级标题……以此类推，可至六级标题；  
> 
> `1. `有序列表；`- `、`+ `、`* `无序列表；  
> 
> `*斜体*`、`**加粗**`、`***粗斜体***`；  
> 
> `[行内链接](Url)`；  
> 
> ```md
> [链接文字](id)  
> [id]: Url
> ```  
> 
> `[引用存储文件](../fileaddress)`；  
> 
> ```
> `行内代码`
> ```    
> 
> ```md
>     ```html
>     代码块
>     ```
> ```  
> 
> `> `引用；  

### 特有语法

1. 配置部分

2. 内容部分

3. 其他

### 故障排除手册

1. npm更新后，使用`npm -v`版本显示仍为更新前版本：考虑添加系统环境变量  
> Anyway, the fix is simple: I just copied the first path (to npm) just before the path to node in the main, global Path variable, and now it picks up the latest version.  


### 参考资料

- [nodeppt2.0 README.md](https://github.com/ksky521/nodeppt/blob/master/README.md)
- [Markdown语法快速入门手册](https://www.w3cschool.cn/markdownyfsm/markdownyfsm-odm6256r.html)