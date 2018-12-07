# gitbook 安装

1. 安装npm 
   从站点 https://nodejs.org/#download 下载node.js源码（点击绿色的INSTALL），
   解压

   ```
   ./configure
   make
   make install
   ```

   > 成功运行后。npm就被安装好了。

2. gitbook 安装

   ```
   npm install -g gitbook-cli
   
   gitbook -V 
   ```

   > 查看gitbook是否成功安装。

3. 生成图书

   * 创建图书

   ``` 
   mkdir ./book
   cd book
   gitbook  init
   ```

   语法：请见  [GitBook 简明教程](http://www.chengweiyang.cn/gitbook/)

   * 生成静态图书

     > 网页浏览的页面

     ```
     gitbook serve .
     ```

     访问：<http://localhost:4000>

     > 生成静态页面

     ```
     mkdir ./book/output
     gitbook build ../book ../book/output
     ```

     可在output 下查看生成静态的文件。

     _说明：_

     * _尽量不要用README ，除了book 下README ，这是生成index页面的，_

     * -导航页面不能跳转，需要修改`output/gitbook/theme.js`修改如下：-

       搜索  `if(m)for`  修改成  `if(false)for` 
       

