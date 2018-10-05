---
title: 安装示例包装的 PST 存储区提供程序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 90ce0ea3-ba73-cb57-0fa9-8898bc4ac9de
description: 上次修改时间： 2012 年 7 月 5 日
ms.openlocfilehash: a1574de555eb74d06c4dbe721e7e013ac59d3071
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25397763"
---
# <a name="installing-the-sample-wrapped-pst-store-provider"></a>安装示例包装的 PST 存储区提供程序

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
本主题将引导您完成下载并安装示例自动换行 PST 存储提供程序的步骤。 示例自动换行 PST 存储提供程序，WrapPST，实现旨在与复制 API 结合使用换行的 PST 存储提供程序。 有关复制 API 的详细信息，请参阅[有关复制 API](about-the-replication-api.md)。
  
## <a name="install-the-sample-wrapped-pst-store-provider"></a>安装示例自动换行 PST 存储提供程序

1. 若要下载示例自动换行 PST 存储提供程序，请参阅[Outlook 2007 辅助参考代码示例和可再发行组件安装程序](https://www.microsoft.com/en-us/download/details.aspx?id=24102)。
    
2. 打开**SampleWrappedPSTStoreProvider**文件夹，然后单击**提取所有文件**。
    
3. 单击**浏览**，选择要用于保存该示例的位置，单击**确定**。
    
4. 单击“提取”****。 您选择的文件夹，其中包含解压缩的文件。
    
5. 以管理员身份打开 Visual Studio 2005。
    
    > [!NOTE]
    > 如果您的计算机运行 Windows XP，您必须以管理员身份登录。 如果您的计算机运行 Windows Vista，您必须为管理员，您必须右键单击 Visual Studio 2005 图标并单击**运行以管理员身份**登录它们。 
  
6. 在 Visual Studio 2005 中，单击**文件**，选择**打开**，然后单击**项目/解决方案**。
    
7. 浏览到保存该示例的位置，单击**WrapPST**，，然后单击**打开**。
    
8. 在"构建"菜单上，单击"构建解决方案"。
    
9. 在**将文件另存为**对话框中，单击**保存**。
    
10. 在本示例保存的文件夹，右键单击**Install.bat**文件，然后单击**以管理员身份运行**。
    
11. 在**用户帐户控制**对话框中，单击**继续**。
    
## <a name="see-also"></a>另请参阅



[关于示例包装的 PST 存储区提供程序](about-the-sample-wrapped-pst-store-provider.md)
  
[初始化包装的 PST 存储区提供程序](initializing-a-wrapped-pst-store-provider.md)
  
[登录包装的 PST 存储区提供程序](logging-on-to-a-wrapped-pst-store-provider.md)
  
[使用包装的 PST 存储区提供程序](using-a-wrapped-pst-store-provider.md)
  
[关闭包装的 PST 存储区提供程序](shutting-down-a-wrapped-pst-store-provider.md)

