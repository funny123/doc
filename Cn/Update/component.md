# 组件更新记录
> 框架更新记录仅仅整理自2020年10-24后的记录，其余记录以老版本文档或github记录为准。

## Wechat

### 1.2.4 - 2021-02-26

#### 新增

- 获取小程序`scheme`码.

## Http-client

### 1.5.0 - 2021-02-23

#### 变更

- 废弃驱动层.

## Queue

### 3.0.1 - 2021-02-23

#### 新增

- 任务消费`onException`支持.


### 3.0.0 - 2021-02-22

`Queue3.x`版本发布.

- 支持常规任务
- 支持延迟任务
- 支持可信任务

## Jwt

### 1.1.4 - 2021-02-23

#### 新增

- 新增支持`RS256`.

#### 修复

- `composer.json` 没有引入必要的依赖.

#### 优化

- 优化`verify signature`方式，以便支持`pub key verify`.

## Log

### 1.1.1 - 2021-03-01

- 解决阿里云镜像未同步问题.

### 1.1.0 - 2021-02-02

#### 新增

- 常量`LOG_LEVEL_DEBUG`


## Validate 

### 1.2.8 - 2021-01-27

#### 新增

- `lessThanWithColumn` 验证字段的值必须小于`with`的字段(仅限`int`)
- `greaterThanWithColumn` 验证字段的值必须大于`with`的字段(仅限`int`)

## Mysqli

### 2.2.8 - 2021-01-27

#### 新增

- 支持`mysql8.0+`锁.

#### 修复

- 修复拼接`sql`,`+86`等字符串被转为`86`.

## 错误视图(Whoops)

### 3.1.0 - 2021-01-20

#### 修复

- 修复错误视图不兼容 `template 1.1.0` 组件接口，对 `Whoops` 组件依赖约束版本

## 辅助类组件(IntStr)

### 1.2.2 - 2021-01-08

#### 新增

- 新增 `IntStr` 工具类，实现 `字符串` 和 `数字` 的相互转换，可用于 `生成短链接`，详见 [IntStr 工具类](/Components/Help/intStr)

## Pool

### 1.0.12 - 2021-01-07

#### 优化

- 优化 pool 组件的负载阀值，在并发峰值非持续性情况下，对池内连接进行负载，自动调控池内连接，让 pool 组件并发处理能力更强，详见 [pool组件 loadAverageTime参数](/Components/Pool/introduction.html#池配置)


## SnowFlake(雪花算法)

### 1.2.0 - 2021-01-05

#### 优化

- 缩短数据中心位至 `5 bit`: `0 ~ 31`
- 增长进程编号位至 `7 bit`: `0 ~ 127`
- 同毫秒序号为 `11 bit`: `0 ~ 2047`
- 理论上，当使用一秒一个数据中心，`128` 进程时，可以允许产生 `1 * 128 * 1000 * 2047 = 26201600` 个唯一 `ID`


## Orm

### 1.4.33 - 2021-03-01

####

- 新增`replace into`操作.

### 1.4.32 - 2021-01-12

#### 修复

- 修复`where`方法传入`php`内置函数关键字,`is_callable`为`true`.

### 1.4.31 - 2020-12-22

#### 新增

- `duplicate key`支持.
- `collection`增加`toRawArray`.
- `where`方法支持闭包函数.

#### 变更

- `getClientPool()`方法调整为`__getClientPool()`.
- `update`取消预算`inc dec`,直接为`field = filed + 1`.

#### 修复

- 修复字段预定义属性不生效.
- 屏蔽`KeepMin`异常导致进程退出.
- 修复循环执行事务不生效问题.

### 1.4.30 - 2020-11-2

#### 新增

- `EasySwoole\ORM\Exception`增加`lastQueryResult`.

### 1.4.29 - 2020-10-29

#### 修复

- 修复`with`关联调用`setter`问题.


## Redis-Pool

### 2.2.1 - 2020-12-29

`2.1.x` -> `2.2.x`不兼容,谨慎更新.

#### 变更

- `class`名字进行合理化修改.
- `class`参数顺序调整,调用更加合理化.
- 调整`invoke`使用.


## Redis

### 1.3.8 - 2021-02-27

#### 调整

- 调整组件内部命名不规范问题.

### 1.3.7 - 2020-12-24

#### 修复

- `redis-cluster`中,单个节点存在多个slot区间,无法识别问题.

### 1.3.6 - 2020-12-14

#### 新增

- `BZPopMax`
- `BZPopMin`
- `ZPopMax`
- `ZPopMin`

#### 优化

- `SPop`

## Http-Annotation

### 1.5.0 - 2021-01-27

#### 新增

- `Param`注解增加`lessThanWithColumn`验证(`validate 1.2.8+`)
- `Param`注解增加`greaterThanWithColumn`验证(`validate 1.2.8+`)

### 1.4.6 - 2021-01-05

#### 优化

- 优化`scanner`非`php`文件.

### 1.4.5 - 2021-01-02

#### 新增

- `Inject`注解,支持注入`class`且参数传入.

### 1.4.4 - 2020-12-23

#### 修复

- 修复生成注解文档左侧栏标题错误问题.

## Rpc

### 5.0.3 - 2020-12-23

#### 增加

- 可设置`client`中`success`及`fail`回调.
- 可设置`client`调用参数.
- `reqeuest`及`response`中`uuid`
- `response`中`status2msg`.

#### 优化

- 带权获取节点.

### 5.0.1 - 2020-12-18

#### 修复

- 局域网内`udp-broadcast`问题.

### 5.0.0 - 2020-12-17

`rpc`组件`5.x`版本发布.

- 完善的节点管理机制.
- 无主化服务发现.
- 允许节点主动上下线.
- 调用流程改为`Service-Module-Action`模式.
- 开放全局`onRequest`.
- 优化数据包结构,缩减通讯宽带.

## Template

### 1.1.0 - 2020-12-29

`1.0.x` -> `1.1.x`不兼容.

- 数据包结构变更
- `interface`变更.
