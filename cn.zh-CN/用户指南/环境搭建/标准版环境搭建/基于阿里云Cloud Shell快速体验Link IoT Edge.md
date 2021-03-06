# 基于阿里云Cloud Shell快速体验Link IoT Edge {#task_1495784 .task}

如果您暂时没有合适的硬件载体来运行Link IoT Edge，您可以使用阿里云云命令行（Cloud Shell）虚拟机快速体验标准版Link IoT Edge的产品功能。

Cloud Shell是阿里云提供的网页版命令行工具。在开始操作本章内容前，请您仔细阅读[Cloud Shell介绍及使用限制](https://help.aliyun.com/document_detail/90256.html)。

Cloud Shell会启动一台虚拟机，并在该虚拟机上为边缘实例搭建最新版本的Link IoT Edge标准版（LE Standard）。

## 创建边缘实例和网关 {#section_e7q_nbs_e0t .section}

1.  [物联网平台控制台](http://iot.console.aliyun.com/)，选择 **边缘计算** \> **边缘实例**。
2.  创建一个边缘实例。 
    1.  单击**新增实例**，在弹出窗口中设置**实例名称**。
    2.  在**网关产品**后单击**新建网关产品**，为实例创建网关。 物联网边缘计算中的网关，承载边缘计算能力，每个实例必须分配一个网关设备，并且该网关设备同一时间只能被分配到一个边缘实例。

        ![创建网关产品](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/102593/156827607537158_zh-CN.png)

    3.  在新建产品页面中，设置网关产品参数，然后单击**完成**。 物联网边缘计算中的新建网关产品继承物联网平台 **设备管理** \> **产品**中的产品功能，已自动为您简化创建适合物联网边缘计算中使用的网关产品步骤。

        ![创建产品](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/102593/156827607537159_zh-CN.png)

        |参数|说明|
        |--|--|
        |产品名称|为网关产品设置名称，用于后续的查询及识别网关产品。支持中文、英文字母、数字和下划线，长度限制4~30，一个中文汉字算2位。|
        |所属分类|选择品类，为该产品定义[物模型](../cn.zh-CN/用户指南/产品与设备/物模型/什么是物模型.md#)。 可选择为：

         -   **自定义品类**：需根据实际需要，定义产品功能。
        -   任一既有功能模板。

选择任一物联网平台预定义的品类，快速完成产品的功能定义。选择产品模板后，您可以在该模板基础上，编辑、修改、新增功能。

 若您需要的网关没有特殊功能定义，建议您选择**自定义品类**。

 |
        |产品描述|可输入文字，用来描述产品信息。字数限制为100。可以为空。|

        产品创建成功后，页面自动跳转回新增实例页面，并且**网关产品**参数下自动分配了刚创建的网关产品。

    4.  在新增实例页面，单击**网关设备**后的**新建网关设备**为网关产品添加设备。 物联网边缘计算中的新建网关设备功能继承物联网平台 **设备管理** \> **设备**的功能。

        ![新建网关设备](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/102593/156827607637160_zh-CN.png)

    5.  根据界面提示设置参数后，单击**确认**。 

        |参数|描述|
        |--|--|
        |产品|系统已自动关联上一步创建的网关产品。|
        |设备名称|为该网关设备命名。设备名称需保持产品内唯一。如不填写，系统将自动生成。 **说明：** 设备名称支持大写字母\[A-Z\]、小写字母\[a-z\]、数字\[0-9\]和下划线（\_）。且不能以下划线开头或结尾。

 |

    6.  根据所搭建的环境，选择对应的Link IoT Edge产品规格，详细介绍请参见[产品规格](../cn.zh-CN/产品简介/产品规格.md#)。
    7.  （可选）在新增实例页面，单击**新增标签**，可以设置实例标签。通过标签您可以更加有效地归类及识别实例。您也可以不设置标签。
3.  实例参数设置完成后，单击**确定**，至此您已创建边缘实例和网关。

## 安装并启动Link IoT Edge {#section_n2l_4ax_8u0 .section}

1.  在左侧导航栏中选择**边缘计算** \> **边缘实例**，单击实例名称右侧的**软件安装**。 

    ![下载命令](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/102593/156827607644201_zh-CN.png)

2.  在软件安装对话框中，单击**立即体验**，使用Cloud Shell虚拟机快速体验标准版Link IoT Edge产品功能，Cloud Shell详细操作请参见[云命令行](https://help.aliyun.com/document_detail/90256.html)。 

    ![下载命令](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/103167/156827607644200_zh-CN.png)

3.  启动Cloud Shell后，会在虚拟机上为当前边缘实例安装最新的标准版Link IoT Edge。安装完成后Cloud Shell中会出现`Start Link IoT Edge Services Success`的提示，实例中的网关会变成在线状态。 

    ![启动CloudShell成功](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/135995/156827607660280_zh-CN.png)

    使用**立即体验**功能时，需要注意如下事项：

    -   单击**立即体验**，系统会为您启动Cloud Shell并自动创建一台Linux虚拟机供您使用；重启Cloud Shell时，会将已创建的Linux虚拟机销毁并创建一台新的Linux虚拟机。
    -   关闭Cloud Shell会话窗口并不能立即停止运行Link IoT Edge，在Cloud Shell会话窗口无操作45分钟后，或者关闭所有Cloud Shell会话窗口15分钟后，虚拟机会被销毁，此时Link IoT Edge才会停止运行。
    -   如果您需要同时在多个窗口中访问虚拟机，单击控制台右上角的![ 命令行工具](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/103167/156827607659656_zh-CN.png)图标，启动Cloud Shell会话窗口，最多同时可打开5个会话窗口。Cloud Shell在同一时刻只会创建一台虚拟机，因此打开的多个会话窗口都会自动连接到此虚拟机上。

        ![命令行按钮](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/103167/156827607659657_zh-CN.png)

    -   单击**立即体验**启动Cloud Shell后，若发现该虚拟机已经安装过Link IoT Edge（例如，通一个边缘实例多次单击**立即体验**时），会先卸载之前的Link IoT Edge，并在虚拟机上为当前的边缘实例安装新的标准版Link IoT Edge。
    -   已通过**立即体验**功能在虚拟机上启动Link IoT Edge后，如果您需要在自己的硬件中安装Link IoT Edge，请先将运行在虚拟机上的Link IoT Edge停止，否则可能会导致部分功能异常。可以通过如下两种方式停止Link IoT Edge ：
        -   在Cloud Shell会话窗口左上角单击![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/135995/156827607660420_zh-CN.png)图标重启Cloud Shell。
        -   在Cloud Shell中执行/linkedge/gateway/build/script/iot\_gateway\_stop.sh命令。
4.  （可选）在实例详情页面，查看CPU使用率、内存使用率、存储使用率以及实例进程需要授权访问阿里云云监控（CloudMonitor）服务。 
    1.  请根据[云资源访问](../cn.zh-CN/用户指南/云资源访问.md#)内容，添加角色或分配已有的角色，并为该角色添加**管理云监控（CloudMonitor）的权限**。
    2.  选择**设置**页签，在实例信息中打开**云监控状态**按钮，如下图所示。 

        ![打开云监控](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/301656/156827607648668_zh-CN.png)

        云监控状态打开后，可在实例详情页面选择**监控信息**，查看网关的各类监控信息。

5.  （可选）在实例详情页面选择**设置**，打开**远程访问**按钮后，可对网关进行远程管理，详细操作步骤请参见[远程服务访问](../cn.zh-CN/用户指南/远程运维管理/远程服务访问.md#)。

## 下一步 {#section_ufa_drh_uyh .section}

环境搭建完成后，您可以根据[设备接入](../cn.zh-CN/用户指南/设备接入/设备接入简介.md#)章节内容，把您的设备接入到物联网边缘计算。同时也可以为边缘实例分配其他资源（如函数计算、消息路由等）管理您的设备。

接入设备或分配其他资源到边缘实例后，需要根据如下步骤部署边缘实例。

1.  在实例详情页面，单击右上角**部署**后在弹出框中单击**确定**，部署边缘实例。
2.  当部署状态显示为**部署成功**，表示部署实例完成。您可以单击**查看日志**，查看部署详情。 

    ![查看部署日志](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/301656/156827607648671_zh-CN.png)


