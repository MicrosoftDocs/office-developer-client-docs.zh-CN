---
title: 安装包装的 PST 存储提供程序示例
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 90ce0ea3-ba73-cb57-0fa9-8898bc4ac9de
description: 上次修改时间：2012 年 7 月 5 日
ms.openlocfilehash: a1574de555eb74d06c4dbe721e7e013ac59d3071
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32309630"
---
# <a name="installing-the-sample-wrapped-pst-store-provider"></a>安装包装的 PST 存储提供程序示例

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
本主题将介绍下载和安装包装的 PST 存储提供程序示例的步骤。 包装的 PST 存储提供程序 WrapPST 示例实现了包装的 PST 存储提供程序，旨在与复制 API 结合使用。 有关复制 API 的信息，请参阅[关于复制 API。](about-the-replication-api.md)
  
## <a name="install-the-sample-wrapped-pst-store-provider"></a>安装包装的 PST 存储提供程序示例

1. 若要下载包装的 PST 存储提供程序示例，请参阅[Outlook 2007 辅助参考代码示例和可再发行组件安装程序](https://www.microsoft.com/en-us/download/details.aspx?id=24102)。
    
2. 打开 **SampleWrappedPSTStoreProvider** 文件夹，然后单击"**提取所有文件"。**
    
3. 单击 **"** 浏览"，选择要保存示例的位置，然后单击"确定 **"。**
    
4. 单击“提取”。 将显示所选的文件夹并包含解压缩的文件。
    
5. 以Visual Studio打开 2005。
    
    > [!NOTE]
    > 如果计算机在 XP Windows，则必须以管理员身份登录。 如果您的计算机在 Vista Windows，您必须以管理员身份登录，并且必须右键单击"Visual Studio 2005"图标，然后单击"以管理员身份 **运行"。** 
  
6. 在 Visual Studio 2005 中，单击"文件"，选择"打开 **"，然后单击"Project/解决方案"。**
    
7. 浏览到保存示例的位置，单击 **WrapPST，****然后单击打开**。
    
8. 在"构建"菜单上，单击"构建解决方案"。
    
9. 在"**将文件另存为**"对话框中，单击"保存 **"。**
    
10. 在保存示例的文件夹中，右键单击 **Install.bat文件，** 然后单击"以 **管理员角色运行"。**
    
11. 在“用户帐户控制”对话框中，单击“继续”。
    
## <a name="see-also"></a>另请参阅



[关于包装的 PST 存储提供程序示例](about-the-sample-wrapped-pst-store-provider.md)
  
[初始化包装的 PST 存储提供程序](initializing-a-wrapped-pst-store-provider.md)
  
[登录到包装的 PST 存储提供程序](logging-on-to-a-wrapped-pst-store-provider.md)
  
[使用包装的 PST 存储提供程序](using-a-wrapped-pst-store-provider.md)
  
[关闭包装的 PST 存储提供程序](shutting-down-a-wrapped-pst-store-provider.md)

