---
title: 在 Windows 2000 上配置 RDS
TOCTitle: Configuring RDS on Windows 2000
ms:assetid: eb2d4c1d-8b3b-07ac-258f-edb0b1a3daba
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250193(v=office.15)
ms:contentKeyID: 48548482
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 8482df5ca2fab110e5b1a77fe227c5f0c583d893
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28720952"
---
# <a name="configuring-rds-on-windows-2000"></a><span data-ttu-id="3ba9d-102">在 Windows 2000 上配置 RDS</span><span class="sxs-lookup"><span data-stu-id="3ba9d-102">Configuring RDS on Windows 2000</span></span>


<span data-ttu-id="3ba9d-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="3ba9d-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="3ba9d-104">如果升级到 Windows 2000 之后，遇到令 RDS 无法正常工作的问题，请执行以下步骤以解决此问题。</span><span class="sxs-lookup"><span data-stu-id="3ba9d-104">If you experience difficulties getting RDS to function properly after upgrading to Windows 2000, follow the steps below to troubleshoot the issue.</span></span>

1.  <span data-ttu-id="3ba9d-105">请确保 World Wide Web 发布服务通过导航到 https://*服务器*使用 Internet Explorer 运行第一个。</span><span class="sxs-lookup"><span data-stu-id="3ba9d-105">Make sure that the World Wide Web Publishing Service is running first by navigating to https://*server* using Internet Explorer.</span></span> <span data-ttu-id="3ba9d-106">如果通过此方式无法访问 Web 服务器，请转到命令提示符下，然后输入命令"NET START W3SVC"。</span><span class="sxs-lookup"><span data-stu-id="3ba9d-106">If you are unable to access the web server this way, go to a command prompt and enter the following command, "NET START W3SVC".</span></span>

2.  <span data-ttu-id="3ba9d-107">从开始菜单中，选择运行。</span><span class="sxs-lookup"><span data-stu-id="3ba9d-107">From the Start menu, select Run.</span></span> <span data-ttu-id="3ba9d-108">键入 msdfmap.ini 然后单击确定以在记事本中打开 msdfmap.ini 文件。</span><span class="sxs-lookup"><span data-stu-id="3ba9d-108">Type msdfmap.ini and click OK to open the msdfmap.ini file in Notepad.</span></span> <span data-ttu-id="3ba9d-109">检查\[连接默认\]部分，并访问参数设置为 NOACCESS，如果将其更改为只读。</span><span class="sxs-lookup"><span data-stu-id="3ba9d-109">Check the \[CONNECT DEFAULT\] section, and if the ACCESS parameter is set to NOACCESS, change it to READONLY.</span></span>

3.  <span data-ttu-id="3ba9d-110">使用 RegEdit 实用工具，导航到"HKEY\_本地\_计算机\\软件\\Microsoft\\DataFactory\\HandlerInfo"并确保**HandlerRequired**设置为 0 且**DefaultHandler**为""（空字符串）。</span><span class="sxs-lookup"><span data-stu-id="3ba9d-110">Using the RegEdit utility, navigate to "HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\DataFactory\\HandlerInfo" and make sure **HandlerRequired** is set to 0 and **DefaultHandler** is "" (Null string).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="3ba9d-111">[!注释] 如果对这部分注册表进行了任何更改，那么必须在命令提示符下输入命令"NET STOP W3SVC"和"NET START W3SVC"，以停止并重新启动万维网发布服务。</span><span class="sxs-lookup"><span data-stu-id="3ba9d-111">If you make any changes to this section of the registry, you must stop and restart the World Wide Web Publishing Service by entering the following commands at a command prompt: "NET STOP W3SVC" and "NET START W3SVC".</span></span>

4.  <span data-ttu-id="3ba9d-112">使用 RegEdit 实用工具，定位到注册表中"HKEY\_本地\_计算机\\系统\\CurrentControlSet\\服务\\W3SVC\\参数\\ADCLaunch"并验证是否存在键被调用的**RDSServer.Datafactory**。</span><span class="sxs-lookup"><span data-stu-id="3ba9d-112">Using the RegEdit utility, navigate in the registry to "HKEY\_LOCAL\_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\W3SVC\\Parameters\\ADCLaunch" and verify that there is a key called **RDSServer.Datafactory**.</span></span> <span data-ttu-id="3ba9d-113">如果没有，则创建此项。</span><span class="sxs-lookup"><span data-stu-id="3ba9d-113">If not, create it.</span></span>

5.  <span data-ttu-id="3ba9d-114">使用 Internet 服务管理器，转到默认网站，并查看 MSADC 虚拟根的属性。</span><span class="sxs-lookup"><span data-stu-id="3ba9d-114">Using Internet Services Manager, go to the default website and view the properties of the MSADC virtual root.</span></span> <span data-ttu-id="3ba9d-115">检查目录安全性/IP 地址和域名限制。</span><span class="sxs-lookup"><span data-stu-id="3ba9d-115">Inspect the Directory Security/IP Address and Domain Name Restrictions.</span></span> <span data-ttu-id="3ba9d-116">如果检查到"访问被拒绝"，则选择"允许"。</span><span class="sxs-lookup"><span data-stu-id="3ba9d-116">If the "Access is Denied" is checked then select "Granted".</span></span>

<span data-ttu-id="3ba9d-117">如果所做更改不能解决问题，请尝试重新启动服务器。</span><span class="sxs-lookup"><span data-stu-id="3ba9d-117">Be sure to try rebooting the server if the changes to do not appear to solve the problem at first.</span></span>

