---
title: 确定 Outlook 是否是计算机上的即点即用应用程序
TOCTitle: Determine whether Outlook is a Click-to-Run application on a computer
ms:assetid: 1b8573be-8ea8-4973-869d-87fda57ce525
ms:mtpsurl: https://msdn.microsoft.com/library/Ff522355(v=office.15)
ms:contentKeyID: 55119804
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 4a710baa4d70ac69b67d2a06fe694998884fd835
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32356404"
---
# <a name="determine-whether-outlook-is-a-click-to-run-application-on-a-computer"></a>确定 Outlook 是否是计算机上的即点即用应用程序

即点即用是一种适用于 Office 2010 及更高版本的软件分发和更新机制。 通过即点即用分发的产品在本地操作系统上的虚拟应用程序环境中执行。 这意味着这些产品具有其文件和设置的私有副本，并且它们所做的任何更改会在虚拟环境中捕获到。

即点即用速度快，即表示用户在很短时间内就能开始运行应用程序，而不用等待完整产品完成安装。 更新会在后台自动运行，无需用户首先移除安装或手动安装更新。 即点即用产品是虚拟化的，不会与其他已安装的软件冲突。 不过，由于通过即点即用分发的产品有所有文件和注册的私有副本，因此加载项开发人员无法确定这种产品的存在方式是否与客户端计算机硬盘上已安装的产品相同。 自 Outlook 2010 起，加载项开发人员应验证是否已安装 Outlook，并验证 Outlook 是否已作为即点即用产品分发。


> [!NOTE]
> 即使客户端计算机运行的是 64 位操作系统，即点即用虚拟应用程序环境中也仅支持 32 位的 Office 2013。



### <a name="to-check-whether-outlook-2013-was-delivered-by-click-to-run-on-a-client-computer"></a>检查客户端计算机上的 Outlook 2013 是否是通过即点即用进行分发的具体步骤

- 验证 Windows 注册表中的以下位置上是否有 VirtualOutlook 键：
    
  `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Office\15.0\Common\InstallRoot\Virtual\VirtualOutlook`
    
  VirtualOutlook 键是 REG\_SZ 值，其中包含已安装产品语言的区域性标记（如“en-us”）。

## <a name="see-also"></a>另请参阅

- [加载项管理](add-in-administration.md)

