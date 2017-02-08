## getWebsite
该项目通过nodejs获取服务器中的html文件。
将index.html中的第67行`if(arr[i].indexOf("zhangshuang") != -1)`中的zhangshuang改为自己服务器的ip或者域名。
将bianli.js中的第59行`var url = '"www.zhangshuang.top/project' + item.path.slice(2) +'"';`中的`www.zhangshuang.top/project`改为自己的可访问路径。

## 运行
命令行输入：`node bianli.js`即可生成`self_Motion_data.js`，其中包含该路径下的所有index.html文件。
