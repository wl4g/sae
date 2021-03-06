# 在SAE控制台使用WAR包部署Java Web应用

应用开发完成后，您可以将应用部署到SAE进行托管。本文介绍如何在SAE控制台以WAR包方式部署Java Web应用。

-   [创建命名空间](/cn.zh-CN/快速入门/准备工作.md)。
-   [创建VPC](/cn.zh-CN/快速入门/准备工作.md)。

在SAE中应用部署方式如下表所示。

|应用举例|部署方式|应用包参考文档|
|----|----|-------|
|原生Spring Cloud|WAR、JAR、镜像|[将Spring Cloud应用托管到SAE](/cn.zh-CN/快速入门/微服务应用入门/将Spring Cloud应用托管到SAE.md)|
|原生Dubbo|WAR、JAR、镜像|[将Dubbo应用托管到SAE](/cn.zh-CN/快速入门/微服务应用入门/将 Dubbo 应用托管到 SAE.md)|
|HSF|WAR、JAR、镜像|无|
|多语言应用|镜像|无|

## 视频教程



## 创建并部署应用

1.  登录[SAE控制台](https://sae.console.aliyun.com)。

2.  在左侧导航栏单击**应用列表**，在**应用列表**页面单击**创建应用**。

3.  在**应用基本信息**页签，设置应用相关信息，配置完成后单击**下一步：应用部署配置**。

    ![Application_deployment_basic_information](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/1369788951/p60491.png)

    参数说明如下表所示。

    |参数名|说明|
    |---|--|
    |应用名称|输入应用名称。允许数字、字母、下划线（\_）以及短划线（-）组合，仅允许字母开头，最大长度36个字符。|
    |专有网络配置|选择专有网络的配置方式。    -   **自定义配置**：选中后，您可以为创建的应用选择所需的命名空间、VPC、 VSwitch及安全组。
    -   **自动配置**：选中后，SAE将自动帮您配置命名空间、VPC、VSwitch及安全组，无需手动选择。 |
    |命名空间|在下拉菜单中选择创建好的命名空间。仅**自定义配置**专有网络时需要选择。**说明：** 命名空间和VPC是一一映射关系，如果需要修改VPC请单击**命名空间详情页**，在**命名空间详情**页面单击**切换VPC**修改VPC信息。 |
    |VSwitch|在下拉菜单中选择VSwitch。仅**自定义配置**专有网络时需要选择。VSwitch数量至少需要配置一个，建议不超过3个，且每个VSwitch至少匹配一个应用实例。 |
    |安全组|在下拉菜单中选择安全组。仅**自定义配置**专有网络时需要选择。**说明：** 如果您的VPC内没有创建安全组，请单击**创建安全组**，根据提示创建安全组，详细说明请参见[创建安全组](/cn.zh-CN/安全/安全组/创建安全组.md)。 |
    |应用实例数|选择需要创建的实例个数。|
    |VCPU|选择需要创建的实例CPU规格。|
    |内存|选择需要创建的实例内存规格。|
    |应用描述|填写应用的基本情况，输入的描述信息不超过100个字符。|

4.  在**应用部署配置**页面，选择**应用部署方式**为**WAR包部署**，设置相关参数，配置完成后单击**下一步：确认规格**。

    ![SAE部署方式WAR](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/4604600061/p56832.png)

    参数说明如下表所示：

    |参数名|说明|
    |---|--|
    |应用运行环境|使用Spring Boot或Dubbo的用户，应用运行环境请选择**apache-tomcat-XXX**；使用HSF的用户，应用运行环境请选择**EDAS-Container-XXX**。|
    |Java环境|选择**Open JDK 7**或**Open JDK 8**。|
    |文件上传方式|可选择**上传WAR包**或**WAR包地址**。    -   **上传WAR包**：单击**选择文件**，选择待部署WAR包。
    -   **WAR包地址**：输入WAR包的存放地址。

**说明：** 应用部署程序包名仅允许字母、数字，及中划线（-）、下划线（\_）两个特殊符号。 |
    |版本|设置应用版本号，您可以选择输入版本号或者单击**使用时间戳为版本号**将时间戳作为应用版本号。|
    |时区设置|选择当前应用所在时区，如**UTC+8**。|
    |高级设置|    -   **启动命令设置**（可选）：请参见[设置启动命令](/cn.zh-CN/应用部署/设置启动命令.md)。
    -   **环境变量设置**（可选）：请参见[设置环境变量](/cn.zh-CN/应用部署/设置环境变量.md)。
    -   **Hosts绑定设置**（可选）：请参见[设置Hosts绑定](/cn.zh-CN/应用部署/设置Hosts绑定.md)。
    -   **应用健康检查设置**（可选）：请参见[设置健康检查](/cn.zh-CN/应用部署/设置健康检查.md)。
    -   **应用生命周期管理设置**（可选）：请参见[设置应用生命周期管理](/cn.zh-CN/应用部署/设置PostStart和PreStop.md)。
    -   **日志收集设置**（可选）：请参见[设置日志收集](/cn.zh-CN/应用部署/设置日志收集.md)。
    -   **持久化存储**（可选）：请参见[设置NAS存储](/cn.zh-CN/应用部署/设置NAS存储.md)。
    -   **配置管理设置**（可选）：请参见[注入配置信息](/cn.zh-CN/应用部署/注入配置信息.md)。 |

5.  在**确认规格**页签，查看您所创建应用的详细信息以及配置费用情况，并单击**确认创建**。

6.  创建完成后，在左侧导航栏单击**应用列表**，单击具体应用进入**应用详情**页面，查看应用的基本信息和实例部署信息。


## 结果验证

1.  登录[SAE控制台](https://sae.console.aliyun.com)。

2.  在左侧导航栏单击**应用列表**，在**应用列表**页面单击具体应用名称。

3.  在**应用详情**页面的**实例部署信息**页签查看实例的运行状态。

    如果**运行状态**显示为绿色的Running或者Completed，表示应用部署成功。


## 更多信息

-   在SAE部署完成后，您可以对应用进行更新、扩缩容、启停、删除应用等生命周期管理操作，具体操作方式请参见[管理应用生命周期](/cn.zh-CN/应用管理/管理应用生命周期.md)。
-   在SAE部署完成后，您可以对应用进行自动弹性伸缩、SLB绑定和批量启停等提升应用性能的操作，具体操作方式请参见以下文档：
    -   [绑定SLB](/cn.zh-CN/应用管理/绑定SLB/为应用绑定SLB.md)
    -   [配置弹性伸缩策略](/cn.zh-CN/应用管理/配置弹性伸缩策略.md)
    -   [一键启停应用](/cn.zh-CN/应用管理/一键启停应用.md)
    -   [配置管理](/cn.zh-CN/应用管理/配置管理/配置管理概述.md)
    -   [变更实例规格](/cn.zh-CN/应用管理/变更实例规格.md)
-   在SAE部署完成后，您还可以对应用进行日志管理、监控管理、应用事件查看和变更记录查看等聚焦应用运行状态的操作，具体操作方式请参见以下文档：
    -   [日志管理](/cn.zh-CN/日志管理/查看实时日志.md)
    -   [监控管理](/cn.zh-CN/监控管理/基础监控.md)
    -   [应用事件查看](/cn.zh-CN/应用管理/查看应用事件.md)
    -   [变更记录查看](/cn.zh-CN/应用管理/查看变更记录.md)
    -   [使用Webshell诊断应用](/cn.zh-CN/应用管理/使用 Webshell 诊断应用.md)

## 问题反馈

如果您在使用SAE过程中有任何疑问，欢迎您扫描下面的二维码加入钉钉群进行反馈。

![SAE钉钉群2](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/5885359951/p72048.png)

