---
title: 邮件存储提供程序示例
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: f1e4077b-7a95-440d-a326-a8dc9cdab4fe
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: eb51881aac6e1953a21686857944ba2a15d0dca2
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33436865"
---
# <a name="message-store-provider-sample"></a>邮件存储提供程序示例

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包装的 PST 存储提供程序示例使用 PST (个人) 文件作为存储数据的后端。 包装的 PST 存储提供程序应该与复制 API 一起使用。 
  
复制 API 使您能够将项目从后端数据存储库复制到 Microsoft Outlook PST 存储。 使用复制 API 将数据复制到专用 PST 存储并跟踪同步状态。 有关详细信息，请参阅[关于复制 API。](about-the-replication-api.md)
  
示例包装 PST 存储提供程序中的大多数函数都直接将参数传递给基础 PST 提供程序。 某些函数需要特殊实现，以下主题对此进行了介绍。
  
|||
|:-----|:-----|
|可执行文件：  <br/> |WrpPST32.dll  <br/> |
|源代码目录：  <br/> |SampleWrappedPSTStoreProvider\WrapPST  <br/> |
|语言：  <br/> |C++  <br/> |
|平台：  <br/> |Microsoft Visual Studio 2008 针对 Windows Vista、Windows Server 2008、Windows XP SP2 和 Windows Server 2003 SP1 进行编译  <br/> |
   
## <a name="supported-features"></a>支持的功能

此示例支持 Microsoft Outlook 2010 64 位，并且现已针对 2013 Outlook进行了修订。 有关其他信息，请参阅以下主题：
  
- [关于复制 API](about-the-replication-api.md)
    
- [初始化包装的 PST 存储提供程序](initializing-a-wrapped-pst-store-provider.md)
    
- [登录到包装的 PST 存储提供程序](logging-on-to-a-wrapped-pst-store-provider.md)
    
- [使用包装的 PST 存储提供程序](using-a-wrapped-pst-store-provider.md)
    
- [关闭包装的 PST 存储提供程序](shutting-down-a-wrapped-pst-store-provider.md)
    
 **安装包装的 PST 存储提供程序示例**
  
1. 若要下载包装的 PST 提供程序示例，请参阅[下载Outlook MAPI 示例](downloading-the-outlook-mapi-samples.md)。
    
2. 找到保存 MAPI 示例Outlook的文件夹。 右键单击 **OutlookMAPISamples- \< 版本号 \>** zip 文件夹，然后单击"全部 **提取"。**
    
3. 单击 **"** 浏览"，选择要保存示例的位置，然后单击"提取 **"。**
    
4. 运行 Microsoft Visual Studio 2008。
    
5. 在 Microsoft Visual Studio 2008 中，单击"文件"，选择"打开 **"，然后单击"Project/解决方案"。**
    
6. 浏览到保存示例的位置，单击 **WrapPST.vcproj，** 然后单击"打开 **"。**
    
7. 在"构建"菜单上，单击"构建解决方案"。
    
8. 在"**将文件另存为**"对话框中，单击"保存 **"。**
    
9. 在保存示例的文件夹中，右键单击 **install.bat文件，** 然后单击"以 **管理员角色运行"。**
    
10. 在“用户帐户控制”对话框中，单击“继续”。
    

