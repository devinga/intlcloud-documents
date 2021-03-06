## 操作场景
Redis 部分命令的使用可能会导致服务不稳定、或者数据误删除，因此云数据库 Redis 提供了禁用部分命令的功能。

云数据库 Redis 2.8 标准版、4.0标准版、4.0集群版支持配置`disable-command-list`参数来禁用部分命令，如果您的控制台不可见`disable-command-list`参数，可 [提交工单](https://console.cloud.tencent.com/workorder/category) 升级后台版本，版本升级会有连接闪断，重新连接即可。

## 操作步骤
### 禁用命令
1. 登录 [云数据库 Redis 控制台](https://console.cloud.tencent.com/redis)，单击实例ID/名称进入实例管理页。
2. 选择【参数设置】>【可修改参数】页，在`disable-command-list`参数行，可配置禁用命令名单。


>- 支持禁用的命令包括 flushall、flushdb、keys、hgetall、eval、evalsha、script，云数据库 Redis 从2019年01月01日起新购的实例默认不禁用以上命令。
>- 配置禁用参数后会在2分钟内生效，禁用命令参数不会重启 Redis 服务，对存量链接生效。
>
>![](https://main.qcloudimg.com/raw/3d3b1b62934b2d9bebf81eb4f886c91e.png)

### 取消禁用命令
选择【参数设置】>【可修改参数】页，在【当前运行参数值】禁用列表中删除相应的命令即可取消命令禁用。

### 参数修改历史
在【参数设置】>【修改历史】页可查看参数修改历史记录。
![](https://main.qcloudimg.com/raw/f3d35543168c0b11dcbb945ee92ad02a.png)
