# NodePPT参考使用手册

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

1. 配置部分  
生成文件后，文件头部为幻灯片信息，样例如下：  
```yaml
title: nodeppt markdown 演示
speaker: 三水清
url: https://github.com/ksky521/nodeppt
js:
    - https://www.echartsjs.com/asset/theme/shine.js
prismTheme: solarizedlight
plugins:
    - echarts
    - mermaid
    - katex
```
各字段对应为
- title: 演讲主题
- speaker：演讲者
- url：地址
- js：js 文件数组，放到 body 之前
- css：css 文件数组，放到头部
- prismTheme：prism 配色，可选参数为 ['dark', 'coy', 'funky', 'okaidia', 'tomorrow', 'solarizedlight', 'twilight']
- plugins：目前支持 echarts、mermaid 和 katex 三个插件

2. 内容部分
    1. 分页
    2. 插入图片（image）
       1. 背景图片
       2. 图片增强
    3. 插入图标（icon）及按钮（button）
    4. 插入图表
    5. 插入流程图
    6. 插入数学符号
    7. 设计样式（classes）
    8. 设计布局（layout）
    9. 添加动效（animation）

3. 其他
    1. 高级语法
       1. attribute
       2. `:::`
       3. span

    2. 插件说明
       1. echarts（图表）
       2. mermaid（流程图）
       3. katex（数学符号）

## 开发相关

### 插件制作说明

### 模板制作说明

## 反馈

### 常见问题

- 问:如何导出PDF？  答:使用浏览器打印幻灯片即可（快捷键`ctrl + P`/`command + P`）


### 故障排除手册

1. npm更新后，使用`npm -v`版本显示仍为更新前版本：考虑添加系统环境变量  
>I just installed Node.js on a new Windows 7 machine, with the following results:
```cmd
> node -v
v0.12.0
> npm -v
2.5.1
```
>
>I then did the above described procedure:
```cmd
> npm install -g npm
```
>
>and it upgraded to v2.7.3. Except than doing npm -v still gave 2.5.1.
>
>I went to the System configuration panel, advanced settings, environment variables. I saw a PATH variable specific to my user account, in addition to the global Path variable.
The former pointed to new npm: C:UsersPhiLhoAppDataRoamingnpm
The latter includes the path to node: C:PrgCmdLinenodejs (Nowadays, I avoid to install stuff in Program Files and derivates. Avoiding spaces in paths, and noisy useless protections is saner...)
If I do which npm.cmd (I have Unix utilities installed...), it points to the one in Node.
>
>Anyway, the fix is simple: I just copied the first path (to npm) just before the path to node in the main, global Path variable, and now it picks up the latest version.


## 参考资料

- [nodeppt2.0 README.md](https://github.com/ksky521/nodeppt/blob/master/README.md)
- [How can I update NodeJS and NPM to the next versions?](https://stackoverflow.com/a/29196342)