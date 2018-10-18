---
title: 在 Windows 2000 上配置 RDS
TOCTitle: Configuring RDS on Windows 2000
ms:assetid: eb2d4c1d-8b3b-07ac-258f-edb0b1a3daba
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250193(v=office.15)
ms:contentKeyID: 48548482
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 0aed6889f16d55ee3ba7778bf9acc6134b744c5d
ms.sourcegitcommit: a49b77f4c8cec69f90656a86f0872cf34c35968e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2018
ms.locfileid: "25602571"
---
# <a name="configuring-rds-on-windows-2000"></a>在 Windows 2000 上配置 RDS


**适用于**： Access 2013 |Office 2013

如果升级到 Windows 2000 之后，遇到令 RDS 无法正常工作的问题，请执行以下步骤以解决此问题。

1.  请确保 World Wide Web 发布服务通过导航到 https://*服务器*使用 Internet Explorer 运行第一个。 如果通过此方式无法访问 Web 服务器，请转到命令提示符下，然后输入命令"NET START W3SVC"。

2.  从开始菜单中，选择运行。 键入 msdfmap.ini 然后单击确定以在记事本中打开 msdfmap.ini 文件。 检查\[连接默认\]部分，并访问参数设置为 NOACCESS，如果将其更改为只读。

3.  使用 RegEdit 实用工具，导航到"HKEY\_本地\_计算机\\软件\\Microsoft\\DataFactory\\HandlerInfo"并确保**HandlerRequired**设置为 0 且**DefaultHandler**为""（空字符串）。
    

    > [!NOTE]
    > <P>[!注释] 如果对这部分注册表进行了任何更改，那么必须在命令提示符下输入命令"NET STOP W3SVC"和"NET START W3SVC"，以停止并重新启动万维网发布服务。</P>



4.  使用 RegEdit 实用工具，定位到注册表中"HKEY\_本地\_计算机\\系统\\CurrentControlSet\\服务\\W3SVC\\参数\\ADCLaunch"并验证是否存在键被调用的**RDSServer.Datafactory**。 如果没有，则创建此项。

<<<<<<< 标头
5.  使用 Internet 服务管理器，转到默认网站并查看 MSADC 虚拟根的属性。 检查目录安全性/IP 地址和域名限制。 如果检查到"访问被拒绝"，则选择"允许"。
=======
5.  使用 Internet 服务管理器，转到默认网站，并查看 MSADC 虚拟根的属性。 检查目录安全性/IP 地址和域名限制。 如果检查到"访问被拒绝"，则选择"允许"。
>>>>>>> master

如果所做更改不能解决问题，请尝试重新启动服务器。

