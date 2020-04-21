# Postman2Testlink

Requirements
  tool  | version
  ------------- | -------------
 nodejs  | >8.17.0
 testlink  | 1.9.17
 postman  | all

[API Document](https://note.youdao.com/ynoteshare1/index.html?id=1b64f29437a77f86f0e22ac412987c54&type=note)

[FAQ](http://note.youdao.com/noteshare?id=64d99aed32db47d133f638908243b10b&sub=CCD48A85B9E34376AA8808B42800473E)


## install
```
npm install
```

## Start the service


```
node test/server.js
```

## postman Script


There is an example postman script in the project directory that can be imported directly into postman.（工程目录下有postman脚本示例，可以直接导入postman）
---


```
postman_script_demo\Postman2Testlink.postman_collection.json
```


Each time the client requests, testlink_info needs to be configured.（客户端每次请求，需要配置testlink_info）
---

```JSON
{
 "testlink_info":
               {
                   "host":"testlink.xxxx.com",
                   "port":80,
                   "secure":false, 
                   "apiKey":"xxxxxxxx"
               }
}
```

 Configuration parameters
  key  | value
  ------------- | -------------
 host  | Hostname or IP where TestLink is hosted.
 port  | Hostname or IP where TestLink is hosted.Set if you are not using default port
 secure  |  Use or not secure connection. If set to true, use http and port 443 if a port was not defined else uses http and port 80
 apiKey  | The api key to interact with TestLink.

## createTestCase

![img](static/images/createTestCase.png)

![img](static/images/addTestCaseKeywordsTestlinkUI.png)

## addTestCaseKeywords

![img](static/images/addTestCaseKeywords.png)

![img](static/images/addTestCaseKeywordsTestlinkUI.png)

## updateTestCaseCustomFieldDesignValue

![img](static/images/updateTestCaseCustomFieldDesignValue.png)

![img](static/images/updateTestCaseCustomFieldDesignValueTestlinkUI.png)



# 更新记录

#### 2020-03-28
>add getProjectTestPlans() 新增获取测试项目中所有测试计划数据

#### 2020-03-31
>add getTestCaseKeywords() 获取给定测试用例的关键字列表

>add batchAddTestCaseKeywords() 批量对给定测试用例，添加关键字

#### 2020-04-01
>add batchUpdateTestCaseCustomFieldDesignValue() 批量向测试用例添加自定义字段

#### 2020-04-19
>add uploadExecutionAttachment() 向测试用例执行结果历史记录，上传图片附件

#### 2020-04-20
>add reportTCResult() 执行测试用例




## 常见问题

1.端口被占用

【window】
（1）查看端口占用进程号
```
netstat -ano|findstr "8021"
```
（2）假设进程ID为10492，执行进程结束命令
```
taskkill -PID 10492 -F
```

【linux】
（1）查看端口占用进程号
```
ps -ef|grep 8020
```
（2）假设进程ID为10492，执行进程结束命令
```
kill -s 9 10492
```