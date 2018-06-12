---
title: 消息存储提供程序示例
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: f1e4077b-7a95-440d-a326-a8dc9cdab4fe
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: b3c907b0a53a41a52516b23ffb1cf7400d887d89
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776506"
---
# <a name="message-store-provider-sample"></a>消息存储提供程序示例

  
  
**适用于**： Outlook 
  
示例自动换行 PST 存储提供程序存储数据作为后端使用的个人文件夹文件 (PST) 提供程序。 应与复制 API 一起使用的换行的 PST 存储提供程序。 
  
复制 API，可以将项目从后端数据存储库复制到 Microsoft Outlook PST 存储区。 您使用复制 API 数据复制到专用的 PST 存储并跟踪的同步状态。 有关详细信息，请参阅[有关复制 API](about-the-replication-api.md)。
  
大部分示例自动换行 PST 存储提供程序中的函数及其参数直接传递到基础太平洋标准时间提供程序。 某些功能需要特殊的实现，并且以下主题所述。
  
|||
|:-----|:-----|
|可执行文件：  <br/> |WrpPST32.dll  <br/> |
|源代码目录：  <br/> |SampleWrappedPSTStoreProvider\WrapPST  <br/> |
|语言：  <br/> |C++  <br/> |
|平台：  <br/> |Microsoft Visual Studio 2008 编译为 Windows Vista、 Windows Server 2008、 Windows XP SP2 和 Windows Server 2003 SP1  <br/> |
   
## <a name="supported-features"></a>支持的功能

本示例支持 Microsoft Outlook 2010 64年位，并已经过修改为 Outlook 2013。 请参阅以下主题的其他信息：
  
- [有关复制 API](about-the-replication-api.md)
    
- [初始化换行的 PST 存储提供程序](initializing-a-wrapped-pst-store-provider.md)
    
- [登录到换行的 PST 存储提供程序](logging-on-to-a-wrapped-pst-store-provider.md)
    
- [使用包装的 PST 存储提供程序](using-a-wrapped-pst-store-provider.md)
    
- [关机的情况下被环绕的 PST 存储提供程序](shutting-down-a-wrapped-pst-store-provider.md)
    
 **安装示例自动换行 PST 存储提供程序**
  
1. 若要下载示例自动换行太平洋标准时间提供程序，请参阅[下载 Outlook MAPI 示例](downloading-the-outlook-mapi-samples.md)。
    
2. 找到 Outlook MAPI 示例的保存位置的文件夹。 右键单击**OutlookMAPISamples-\<版本号\>** zip 文件夹，然后单击**全部提取**。
    
3. 单击**浏览**，选择要用于保存该示例的位置，然后单击**提取**。
    
4. 运行 Microsoft Visual Studio 2008。
    
5. 在 Microsoft Visual Studio 2008 中，单击**文件**，选择**打开**，然后单击**项目/解决方案**。
    
6. 浏览到保存该示例的位置，单击**WrapPST.vcproj**，，然后单击**打开**。
    
7. 在"构建"菜单上，单击"构建解决方案"。
    
8. 在**将文件另存为**对话框中，单击**保存**。
    
9. 在本示例保存的文件夹，右键单击**install.bat**文件，然后单击**以管理员身份运行**。
    
10. 在**用户帐户控制**对话框中，单击**继续**。
    

