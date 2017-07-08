# passport-api

<!-- toc  -->

## 编写历史

版本历史，应该交给``git``管理。


## 文档生成

### 构建 ``GitBook``

进入项目根目录，执行构建：

``` bash
rm -rf docs && gitbook install &&  gitbook build ./ docs
```

构建之后将 ``docs`` 目录的所有更新提交。

>**注意**：一定要输出到 docs 目录，才能被 ``Git Pages`` 识别。

### 安装 ``GitBook``

``GitBook`` 是 ``Node.js``编写的，需要先安装``Node.js``。

- 安装 ``Node.js``和``npm``：  https://nodejs.org/en/download/
- 安装 ``GitBook``命令行工具：  ``sudo npm install gitbook-cli -g``
