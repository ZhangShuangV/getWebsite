## getWebsite
该项目通过nodejs获取服务器中的html文件。   
1. 将index.html中的第67行`if(arr[i].indexOf("zhangshuang") != -1)`中的zhangshuang改为自己服务器的ip或者域名。   
2. 将bianli.js中的第59行`var url = '"www.zhangshuang.top/project' + item.path.slice(2) +'"';`中的`www.zhangshuang.top/project`改为自己的可访问路径。

## 运行
命令行输入：`node bianli.js`即可生成`self_Motion_data.js`，其中包含该路径下的所有index.html文件。  

## 定时任务
1. 创建一个.sh脚本 `bianli.sh` 通过 `vim bianli.sh`命令进入编辑模式   
2. 将下面的路径修改成自己的路径   

```
#!/bin/bash
cd /opt/node_server/public/project
/usr/bin/node /opt/node_server/public/project/bianli.js
```

###### 第二行是进入项目所在路径。   
###### 第三行的前半部分是node服务的路径，后半部分是要执行的js文件。   
###### 修改完成后，通过命令`vim /etc/crontab`进入并编辑定时任务   

`
*/1 * * * *     root    /bin/sh /opt/node_server/public/project/bianli.sh
`

里面都有具体说明，前面部分是定时任务执行的频率，最后一部分修改为要执行的sh脚本即可。

## 完成 
现在就可以通过定时任务每分钟自动生成文件啦，如果觉得频率太高，按照crontab里面的要求更改即可
