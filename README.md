> #### 作者主页：[舒克日记](https://blog.csdn.net/cativen)
>
>  简介：Java领域优质创作者、Java项目、学习资料、技术互助
>
> <b><font color=red>文中获取源码</font></b>

# 项目介绍

系统共有管理员、用户、拍卖者三个角色

​

管理员主要功能：个人中心、买家管理、拍卖者管理、竞拍商品管理、竞拍信息管理、竞拍结果管理、买家评论管理、留言板管理、管理员管理

拍卖者主要功能：个人中心、竞拍商品管理、竞拍信息管理、竞拍结果管理、买家评价管理

用户前台：首页、竞拍商品、留言反馈、个人中心、后台管理

买家后台：个人中心、竞拍信息管理、竞拍结果管理、买家评价管理、留言板管理

# 环境要求

1.运行环境：最好是java jdk1.8,我们在这个平台上运行的。其他版本理论上也可以。

2.IDE环境：IDEA,Eclipse,Myeclipse都可以。推荐IDEA;

3.tomcat环境：Tomcat7.x,8.X,9.x版本均可

4.硬件环境：windows7/8/10 4G内存以上；或者Mac OS;

5.是否Maven项目：是；查看源码目录中是否包含pom.xml;若包含，则为maven项目，否则为非maven.项目

6.数据库：MySql5.7/8.0等版本均可；

# 技术栈

运行环境：jdk8 + tomcat9 + mysql5.7 + windows10

服务端技术：Java、Spring、SpringMVC、Mybatis，SSM

前端：vue

# 使用说明

1.使用Navicati或者其它工具，在mysql中创建对应sq文件名称的数据库，并导入项目的sql文件；

2.使用IDEA/Eclipse/MyEclipse导入项目，修改配置，运行项目；

3.将项目中config-propertiesi配置文件中的数据库配置改为自己的配置，然后运行；

# 运行指导

idea导入源码空间站顶目教程说明(Vindows版)-ssm篇：

http://mtw.so/5MHvZq

源码地址：[http://www.codegym.top](http://www.codegym.top/)



# 运行截图

## 功能模块截图

![img](https://i-blog.csdnimg.cn/img_convert/dec991e534a740fa6642805196613a1a.png)

#### 项目截图

前台

![图片1](https://i-blog.csdnimg.cn/img_convert/9954745bfc4df8434fdb190ee882cecb.png)

![图片2](https://i-blog.csdnimg.cn/img_convert/e46069c4256b92ccdea4e2a6be3fd5c1.png)

![图片3](https://i-blog.csdnimg.cn/img_convert/1de18e580538c6a58b8000d360a0faf2.png)

![图片4](https://i-blog.csdnimg.cn/img_convert/b9954bef0323504947496053f942f661.png)

后台

![图片11](https://i-blog.csdnimg.cn/img_convert/db45df0bc8ac792497e67fbb26d2145b.png)

![图片12](https://i-blog.csdnimg.cn/img_convert/71a434784c5b7038670adb3bd196e819.png)

![图片13](https://i-blog.csdnimg.cn/img_convert/e5e350beb06fe2dd332baa7910abe67c.png)

![图片14](https://i-blog.csdnimg.cn/img_convert/633e15e4f561db1dfc14a56658abe2fd.png)

![图片15](https://i-blog.csdnimg.cn/img_convert/12be597e39d7d02b3fdc2b43f3b6e8b1.png)

![图片16](https://i-blog.csdnimg.cn/img_convert/6b073fa6d3b7076f79a1fbf318e5d1f9.png)

![图片5](https://i-blog.csdnimg.cn/img_convert/d6fd78e3bfe60a324938fd3dc8b22c98.png)

![图片6](https://i-blog.csdnimg.cn/img_convert/94e6318680111b1b8c064ecb70868277.png)

![图片7](https://i-blog.csdnimg.cn/img_convert/790b85d1e19a0d1e6b479b8d90b65b2b.png)

![图片8](https://i-blog.csdnimg.cn/img_convert/afc2b2de792c7f74866f9663b653d8a9.png)

![图片9](https://i-blog.csdnimg.cn/img_convert/b357f1d1b9a402e975b89be3b4ecfbb0.png)

![图片10](https://i-blog.csdnimg.cn/img_convert/61cc462c8396aa541602e4b196b3aad3.png)

### 代码

```
  try {
            String eventName = params.getString("eventName");
            WebhookEventEnum cLifeEvent = WebhookEventEnum.fromEventName(eventName);
            if (cLifeEvent != null) {
                WebhookEventProcessor eventProcessor = eventProcessFactory.getEventProcessor(cLifeEvent);
                if (eventProcessor == null) {
                    log.warn("未找到对应的事件处理器，eventName={}", eventName);
                } else {
                    eventProcessor.process(params);
                }
            }
        } catch (Exception e) {
            log.error("cLifeWebhook process error.", e);
        }
```
