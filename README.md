# mynode
## node.js,语法体系javascript，运行在服务器，非阻塞型，轻量级，由事件驱动，有一个包管理工具（npm，管理了几乎所有node.js包）
# node安装
1. 进入<a href="https://nodejs.org/en/">官方网站</a>下载
2. 再相应的平台下，下载相应的版本，一个是长期维护，一个是最新版本。
    ** 学习或试验可以使用最新版本，如果上线项目要用长期维护版，偶数版本是稳定版，奇数为最新版
## 安装
### windows 安装
1. msi：包含node.exe/npm 要选择 add to path,将node.exe 自动添加到全局路径下面。
2. node.exe：是一个二进制文件，必须手动的将node.exe放到全局的路径
3. 安装成功后，可以执行  `node -v` 监测安装的版本。
### mac 安装
### linux 安装
## 
# <a href="https://www.npmjs.com/">npm</a>
1. npm 包管理工具 node package manage,安装成功之后可以使用 npm -v 监测安装的版本
2. 作用：node.js为了程序人员开发方便，提供了包管理工具,不用担心自己编写的模块货这别人编写的模块存放到什么地方，他们的依赖关系等等，只要通过npm就可以上传。
# 执行第一个程序
## 交互的方式使用node.js
1.  cmd(ctrl+R)-->node 回车-->进入node.js的编译环境
2.  在这个环境下，只要输入符合规范的代码，回车后会立即响应，所以称为`交互型`
## 编译的方式使用node.js
1. 创建一个javascript文件
2. 在命令行进入文件所在的目录，通过 `node node.js` 对node.js文件进行解析，如果在想在命令行看到结果，文件中必须有`console.log()`
# node.js运行环境的配置
    配置原因：手动输入会很麻烦
1.  phpstorm 配置
    **webstorm不用配置，已经把相应的文件配置好了**
    打开phpstorm 配置项-->Plugins 搜索 nodejs的插件，点击 install 进行安装/重启-->在languages&frameswork下找到`node and npm插件`-->配置：首先让他可用，设置作用区间&设置提示
    
# node.js全局对象
## javascript 里面的全局对象  window
## node.js 里面的全局对象 global
1. 子对象console
    1.1 console.log() 在控制台输出消息
    1.2 console.error() 输出错误
## 模块的概念
       模块是node.js区别于javascript最重要的概念，他把每一个文件都当作一个独立的作用域，每一个文件  
    就是一个模块，再当前这个模块下定义的所有的变量/函数，都属于这个模块，如果想要定义全局变量必须  
    通过global来定义，那么再模块下定义的变量他的作用范围是当前模块的，通过global定义的变量是全局的。
1. require("./node1.js") 引入模块
2. node.js中引入模块如何调用里面的变量（在被调用模块中发送变量  module.exports.aa=aa||exports.aa;  ）
    2.1 module.exports与exports区别。
        module.exports===exports ,能够将当前模块下的值发射出去，让引用的模块获取相应的值
        **module.export与exports是引用关系，如果直接赋值会导致关系断开**
3. nodejs里面会分为3中模块
    3.1 自定义模块
    3.2 内置模块
    3.3 外置模块（包）
4. process
    用来操作|获取|查看 当前进程的相关信息
    process.argv()  用来获取命令行执行相关的参数["执行的二进制"]
    process.chdir() 人为的改掉上一级目录
    process.cwd()   当前进程运行目录
    process.exid() 退出当前进程
    process.platform()运行平台
    process.stdout.write(data);    监测输入事件
    process.stdin   标准的输入流
        process.stdin.emit("end")   自定义事件
        process.stdin.on("end",function(){})
        process.stdin.pause 暂停输入流;
        process.stdin.resume() 开始输入流;
    process.stdout  标准的输出流
        process.stdout.
5. globle中的方法
    5.1 setInterval()
    5.2 clealInterval()
    5.3 setTimeout()
    5.4 require()
    
        
#Node.js模块与前端模块的异同
    通常有一些模块可以同时适用于前后端，但是在浏览器端通过script标签的载入JavaScript文件的方式与
    Node.js不同。Node.js在载入到最终的执行中，进行了包装，使得每个文件中的变量天然的形成在一个闭包
    之中，不会污染全局变量。而浏览器端则通常是裸露的JavaScript代码片段。所以为了解决前后端一致性的
    问题，类库开发者需要将类库代码包装在一个闭包内。
# Node.js方法稳定等级
    0 废弃
    1 试验
    2 不稳定
    3 稳定
    4 冻结
    6 锁定