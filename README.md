<div align="center">

![](https://one-api.oss-rg-china-mainland.aliyuncs.com/Logo-new-150.png)

</div>
<div align="center">

# Shell API

✨ 基于 One API 二次开发，提供全新UI与更多高级选项，支持Docker部署 ✨
[新版特性](#新版特性)     [在线演示](https://demo.oneapi.plus)    [截图展示](#截图展示)     [购买方式](#购买方式)    [快速开始](#部署)
</div>


## 新版特性

0. 与开源版完全兼容
    + [x] 保留旧版所有配置，直接迁移，开箱即用
1. 全新UI震撼来袭
    + [x] 支持切换旧版
    + [x] 提示消息内容基本汉化
    + [x] 增加分页器，每页展示内容更多
    + [x] 增加表头筛选，快速筛选对应内容
    + [x] 支持自选导航位置（顶栏/侧栏）
    + [x] 增强日志展示，方便定位问题
    + [x] 增加一键填写美金额度令牌，无需手动输入
    + [x] 增加一键复制用户信息、修改用户额度功能
    + [x] 增加悬浮按钮，方便用户快速查看文档、联系方式等
    + [x] 增加快捷按钮，快速增加用户余额和令牌有效期
    + [ ] 支持自定义配置悬浮按钮、友情链接
    + [ ] 适配手机版页面
    + [ ] 全新仪表盘，所有数据一览无遗
    + [ ] 优化日志展示，支持日志导出
    + [ ] 自选主题市场
    + [ ] 支持切换深色模式
2. 更多高级功能
    + [x] 强制指定渠道使用顺序
        + 如通道A、B配置顺序为3，通道C配置顺序为2，则只有A和B都被禁用才会使用C
    + [x] 支持429超频报错自动禁用
        + 超过频率限制的请求会自动禁用，避免重复返回超频报错
    + [x] 支持渠道超频自动复活
        + 超频禁用后每隔指定配置的时间自动测试通道,测试通过则自动启用
    + [x] 新增一键超频功能
        + 配置渠道时，一键点击即可开启超频
    + [x] 优化测速方案,支持**流式测速**、**自定义模型测速**等
    + [x] 支持KEY维度限制可用模型
    + [x] 支持自定义渠道链接
    + [x] 日志展示渠道名称，且可以根据渠道名称搜索过滤
    + [x] 优化测速方式，相较原版节省更多token
    + [x] OpenAI支持指定组织消耗
    + [x] 编辑的时候可以控制显示/隐藏秘钥
    + [x] 用户请求、响应的内容存表并支持前端查询
    + [x] **修复原始版本余额不足的用户去请求时候会自动禁用通道的bug**
    + [x] 增加自定义测速以及JSON一键填入功能，打破原版默认只有3.5测速的局限
    + [x] 查询余额支持跨域请求
    + [x] 增加高级测速功能
    + [x] 防止openai抽风超额扣费出现的的的的的的的的的的的
    + [x] 增加对话一键填充令牌功能
    + [x] 增加SMTP 配置发送测试邮件 
    + [x] 全新适配最新 gpt-4v、gpt-turbo、tts 等 模型
    + [ ] 支持*.edu.cn 的通配符邮箱白名单
    + [ ] 新增渠道分组功能，更符合实际使用场景
    + [ ] 新增渠道组功能，更符合实际使用场景
## 在线演示
[https://demo.oneapi.plus](https://demo.oneapi.plus)
## 截图展示
##### 注意：截图仅更新到v0.5.0，请以在线演示为准
![img.png](img.png)
![img_1.png](img_1.png)
![img_2.png](img_2.png)
![img_3.png](img_3.png)
![img_7.png](img_7.png)
![img_4.png](img_4.png)
![img_5.png](img_5.png)
![img_6.png](img_6.png)
![img_8.png](img_8.png)
![img_9.png](img_9.png)
![img_10.png](img_10.png)
![img_11.png](img_11.png)
![img_12.png](img_12.png)
![img_31.png](img_31.png)
![img_13.png](img_13.png)
![img_30.png](img_30.png)
![img_14.png](img_14.png)
![img_15.png](img_15.png)
![img_16.png](img_16.png)
![img_17.png](img_17.png)
![img_18.png](img_18.png)
![img_19.png](img_19.png)
![img_20.png](img_20.png)
![img_21.png](img_21.png)
![img_22.png](img_22.png)
![img_23.png](img_23.png)
![img_24.png](img_24.png)
![img_25.png](img_25.png)
![img_26.png](img_26.png)
![img_27.png](img_27.png)
![img_28.png](img_28.png)
![img_29.png](img_29.png)
## 部署
### 一、首次安装
#### 1.连接云服务器
```bash
ssh username@yourserver
```
#### 2.获取最新版的docker-compose配置文件
```bash
#新建目录
mkdir shellapi
#拉取配置文件
wget -P shellapi/ https://one-api.oss-rg-china-mainland.aliyuncs.com/docker-compose.yml
```
#### 3.修改 docker-compose.yml 文件中相关设置
```bash
#进入目录
cd shellapi 
#使用vi编辑文件
vi docker-compose.yml
```
```yaml
#如果不是最新版本，请手动修改 tag：
image: akl7777777/one-api-private:v0.x.y
# 使用MySQL作为数据库，修改用户名和密码；不使用MySQL作为数据库，注释这两行：
- SQL_DSN=root:123456@tcp(host.docker.internal:3306)/one-api
- DW_DB_DSN=root:123456@tcp(host.docker.internal:3306)/one-api
```
#### 4.启动容器
```bash
#登录docker
docker login
#启动容器
docker-compose up -d
```
#### 5.配置反向代理
📌 默认端口为 3000 端口，如果开启了防火墙，请注意开放端口
```nginx
server{
   server_name api.shellapi.plus;  # 根据实际情况修改域名
   location / {
          client_max_body_size  64m;
          proxy_http_version 1.1;
          proxy_pass http://localhost:3000;  # 根据实际情况修改端口
          proxy_set_header Host $host;
          proxy_set_header X-Forwarded-For $remote_addr;
          proxy_cache_bypass $http_upgrade;
          proxy_set_header Accept-Encoding gzip;
          proxy_read_timeout 300s;  # GPT-4 需要较长的超时时间，请自行调整
   }
}
```
### 二、更新
```bash
#进入目录
cd shellapi
#使用vi编辑文件，修改 tag 为最新版本
vi docker-compose.yml
#重新创建并启动容器
docker-compose up -d
```

## 购买方式
### 二开版售价598，拉你进专属用户群，永久更新 
![img_32.png](img_32.png)