# [1|0Fvuln 简介](https://www.cnblogs.com/icml8/p/16619162.html)

04/16/2023 11:27:09本文共 1486 字阅读完需 6.5 分钟

> Fvuln 简介 F-vuln（全称：Find-Vulnerability）是一款自动化探测扫描工具，主要适用于日常安全服务、渗透测试人员和RedTeam红队人员使用 它集合的功能包括： 存活IP探测

F-vuln（全称：**Find-Vulnerability**）是一款自动化探测扫描工具，主要适用于日常安全服务、渗透测试人员和RedTeam红队人员使用

它集合的功能包括：

```armasm
存活IP探测、开放端口探测、web服务探测、web漏洞扫描、smb爆破、ssh爆破、ftp爆破、mssql爆破等其他数据库爆破工作以及大量web漏洞检测模块
```

它可以根据目标开放的服务进行特定操作，不做无用功。

适用于内网环境、互联网，对发现的安全问题，自动生成保存有用的内容在txt表里，以方便安全人员对授权项目完成测试工作。

## 1.4.7 更新说明

```apache
1、共436个漏洞模块
2、新增centos程序版本
3、修复多个漏洞误报
```

## 支持检测的漏洞表

[已经支持检测的漏洞表](https://github.com/d3ckx1/Fvuln/blob/main/vuln-list.txt)

[![image](https://img2022.cnblogs.com/blog/2786574/202208/2786574-20220824110513122-1294684687.png)](https://img2022.cnblogs.com/blog/2786574/202208/2786574-20220824110513122-1294684687.png)

​                                                 **（部分）**

## 建议运行环境

```undefined
Windows环境安装Terminal命令行

Liunx环境使用命令行即可
```

## 参数

```stylus
格式: Fvuln.exe -参数 目标

帮助信息:
-t    , --target TARGETS     输入目标IP或者IP段
-u    , --url www.qq.com     输入目标URL进行单独扫描
-us   , --urls url.txt       输入批量URL目标txt文件
-fofa , --fofa "百度"        输入需要搜索的关键字
-f    , --file FILE          输入目标txt文件，如：ip.txt
-h    , --help               查看帮助信息
-l    , --list               查看支持的漏洞列表
-v    , --version            查看软件版本与更新时间
```

## 使用命令举例

#### 查看程序版本：

```reasonml
Fvuln.exe -v 
```

[![image](https://img2022.cnblogs.com/blog/2786574/202208/2786574-20220824111046515-1995291587.png)](https://img2022.cnblogs.com/blog/2786574/202208/2786574-20220824111046515-1995291587.png)

#### FOFA批量搜索检测：

```reasonml
Fvuln.exe -fofa "帝国CMS"
```

**注：**

再同目录下创建 “key.txt” 文件

文件内第一行写入邮箱地址；第二行写入你的key

#### 批量URL检测：

```stylus
Fvuln.exe -us url.txt
```

**注：**在当前目录里创建url.txt 并在里面存放批量扫描的URL

[![image](https://img2022.cnblogs.com/blog/2786574/202208/2786574-20220824110613193-304964933.png)](https://img2022.cnblogs.com/blog/2786574/202208/2786574-20220824110613193-304964933.png)

**注：**不要http，自动识别没有http，会自己添加  "http://" 与 “/”

#### 单URL检测：

```awk
Fvuln.exe -u http://192.168.1.1
```

[![image](https://img2022.cnblogs.com/blog/2786574/202208/2786574-20220824110621409-1409970716.png)](https://img2022.cnblogs.com/blog/2786574/202208/2786574-20220824110621409-1409970716.png)

#### 查看帮助文档:

```reasonml
 Fvuln.exe -h 
```

[![image](https://img2022.cnblogs.com/blog/2786574/202208/2786574-20220824110642056-395053664.png)](https://img2022.cnblogs.com/blog/2786574/202208/2786574-20220824110642056-395053664.png)

#### 查看漏洞模块：

```stylus
Fvuln.exe -l 或者 Fvuln.exe --list
```

[![image](https://img2022.cnblogs.com/blog/2786574/202208/2786574-20220824110649855-696481592.png)](https://img2022.cnblogs.com/blog/2786574/202208/2786574-20220824110649855-696481592.png)

#### 执行单IP或网段扫描：

```apache
Fvuln.exe -t 192.168.31.0/24
```

执行完成，查看报表：

[![image](https://img2022.cnblogs.com/blog/2786574/202208/2786574-20220824110700238-1615826311.png)](https://img2022.cnblogs.com/blog/2786574/202208/2786574-20220824110700238-1615826311.png)

#### 批量执行IP扫描：

```stylus
Fvuln.exe -f ip.txt
```

[![image](https://img2022.cnblogs.com/blog/2786574/202208/2786574-20220824110708016-1330575354.png)](https://img2022.cnblogs.com/blog/2786574/202208/2786574-20220824110708016-1330575354.png)

如果觉得我存活探测慢

或者工作中又其他需求需要对特定IP进行扫描工作，可以把IP地址写进txt里，使用这个功能正常进行全部工作。

## 缺点

爆破ssh工作时命令行上会出现大量报错

但不影响爆破工作、报表里不会保存这些报错

__EOF__

![img](https://pic.imgdb.cn/item/63058e2216f2c2beb141d182.png)

**本文作者**：**[芸](https://www.cnblogs.com/icml8/p/16619162.html)** **本文链接**：https://www.cnblogs.com/icml8/p/16619162.html**关于博主**：ICML0X824
**版权声明**：本博客所有文章除特别声明外，均采用 [BY-NC-SA](https://creativecommons.org/licenses/by-nc-nd/4.0/) 许可协议。转载请注明出处！