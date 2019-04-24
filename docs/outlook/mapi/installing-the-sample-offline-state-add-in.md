---
title: 安装示例脱机状态加载项
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: e1b6ae6c-dcf2-a07f-c417-3a1049b758ad
description: '上次修改时间: 2006 年7月2012'
ms.openlocfilehash: b7b9ce539537e0759020ef7e3b4f6541a940d6fd
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32317211"
---
# <a name="installing-the-sample-offline-state-add-in"></a>安装示例脱机状态加载项

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
本主题将指导您完成下载和安装示例脱机状态加载项的步骤。 示例脱机状态外接程序是一个 COM 加载项, 它将**脱机状态**菜单添加到 Outlook 并利用脱机状态 API。 通过脱机状态菜单, 您可以启用或禁用状态监视、检查当前状态并更改当前状态。 有关如何实现脱机状态外接程序的详细信息, 请参阅[设置脱机状态外接程序](setting-up-an-offline-state-add-in.md)。
  
## <a name="install-the-sample-offline-state-add-in"></a>安装示例脱机状态加载项

1. 在此处下载示例脱机状态外接程序: [Outlook 2007 辅助参考代码示例和可再发行安装程序](https://www.microsoft.com/en-us/download/details.aspx?id=24102)。
    
2. 以管理员身份运行 Visual Studio 2005。
    
    > [!NOTE]
    > 如果您的计算机运行的是 Windows XP, 则必须以管理员身份登录。 如果您的计算机运行的是 Windows Vista, 则必须以管理员身份登录。 右键单击 "Visual Studio 2005" 图标, 然后单击 "**以管理员身份运行**"。 
  
3. 在 Visual Studio 2005 中, 单击 "**文件**", 选择 "**打开**", 然后单击 "**项目/解决方案**"。
    
4. 浏览到保存示例的位置, 单击 " **ConnectionStateAddin**", 然后单击 "**打开**"。
    
5. 在"构建"菜单上，单击"构建解决方案"。
    
6. 在 "**将文件另存为**" 对话框中, 单击 "**保存**"。
    
7. 依次单击 "**开始**" 菜单、"**所有程序**"、"**附件**", 右键单击 "**命令提示符**", 然后单击 "**以管理员身份运行**"。
    
    > [!NOTE]
    > 如果您运行的是 Windows XP, 则必须以管理员身份登录。 
  
8. 在“用户帐户控制”**** 对话框中，单击“继续”****。
    
9. 在**命令提示符**窗口中, 将目录更改为保存示例的调试文件夹。 例如, 如果您将示例保存在 C:\ 上驱动器, 请键入**cd "C:\ConnectionStateAddin\Debug"** , 然后按**enter**。 
    
10. 键入**regsvr32 OfflineStateAddin** , 然后按**enter**。 
    
    > [!NOTE]
    > 若要卸载示例脱机状态加载项, 请键入**regsvr32-u OfflineStateAddin**
  
11. 在 " **RegSrv32** " 对话框中, 单击 **"确定"**。
    
12. 重新启动 Outlook 以查看**脱机状态**菜单。 
    
## <a name="see-also"></a>另请参阅



[关于脱机状态 API](about-the-offline-state-api.md)
  
[安装示例脱机状态加载项](installing-the-sample-offline-state-add-in.md)
  
[关于示例脱机状态加载项](about-the-sample-offline-state-add-in.md)
  
[设置脱机状态加载项](setting-up-an-offline-state-add-in.md)
  
[使用脱机状态加载项监视连接状态更改](monitoring-connection-state-changes-using-an-offline-state-add-in.md)
  
[断开与脱机状态外接程序的连接](disconnecting-an-offline-state-add-in.md)

