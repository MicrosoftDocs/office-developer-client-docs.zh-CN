---
title: 安装示例脱机状态加载项
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: e1b6ae6c-dcf2-a07f-c417-3a1049b758ad
description: 上次修改时间：2012 年 7 月 6 日
ms.openlocfilehash: b7b9ce539537e0759020ef7e3b4f6541a940d6fd
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32317211"
---
# <a name="installing-the-sample-offline-state-add-in"></a>安装示例脱机状态加载项

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
本主题将介绍下载和安装示例脱机状态加载项的步骤。 示例脱机状态外接程序是一个 COM 加载项，它将"脱机状态"菜单添加到Outlook并利用脱机状态 API。 通过"脱机状态"菜单，可以启用或禁用状态监视、检查当前状态以及更改当前状态。 若要详细了解如何实现脱机状态加载项，请参阅设置脱机 [状态加载项](setting-up-an-offline-state-add-in.md)。
  
## <a name="install-the-sample-offline-state-add-in"></a>安装示例脱机状态加载项

1. 在此处下载示例脱机状态外接程序[：Outlook 2007 辅助参考代码示例和可再发行组件安装程序](https://www.microsoft.com/en-us/download/details.aspx?id=24102)。
    
2. 以Visual Studio运行 2005。
    
    > [!NOTE]
    > 如果计算机在 XP Windows，则必须以管理员身份登录。 如果计算机在 Vista Windows，则必须以管理员身份登录。 右键单击"Visual Studio 2005"图标，然后单击"**以管理员角色运行"。** 
  
3. 在 Visual Studio 2005 中，单击"文件"，选择"打开 **"，然后单击"Project/解决方案"。**
    
4. 浏览到保存示例的位置，单击 **ConnectionStateAddin**， **然后单击打开**。
    
5. 在"构建"菜单上，单击"构建解决方案"。
    
6. 在"**将文件另存为**"对话框中，单击"保存 **"。**
    
7. 单击"**开始"** 菜单，单击 **"所有** 程序"，单击"**附件"，** 右键单击"**命令提示符**"，然后单击"以 **管理员角色运行"。**
    
    > [!NOTE]
    > 如果运行的是 Windows XP，则必须以管理员身份登录。 
  
8. 在“用户帐户控制”对话框中，单击“继续”。
    
9. 在命令 **提示符** 窗口中，将目录更改为保存示例的"调试"文件夹。 例如，如果将示例保存在 C：\ 上驱动器，键入 **cd "C：\ConnectionStateAddin\Debug"，** 然后按 **Enter**。 
    
10. 键入 **regsvr32 OfflineStateAddin.dll** 然后按 **Enter。** 
    
    > [!NOTE]
    > 若要卸载示例脱机状态加载项，请键入 **regsvr32 -u OfflineStateAddin.dll**
  
11. 在 **"RegSrv32"** 对话框中，单击"确定 **"。**
    
12. 重新启动Outlook以查看"**脱机状态"** 菜单。 
    
## <a name="see-also"></a>另请参阅



[关于脱机状态 API](about-the-offline-state-api.md)
  
[安装示例脱机状态加载项](installing-the-sample-offline-state-add-in.md)
  
[关于示例脱机状态加载项](about-the-sample-offline-state-add-in.md)
  
[设置脱机状态加载项](setting-up-an-offline-state-add-in.md)
  
[使用脱机状态加载项监视连接状态更改](monitoring-connection-state-changes-using-an-offline-state-add-in.md)
  
[断开脱机状态加载项](disconnecting-an-offline-state-add-in.md)

