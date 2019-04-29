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
  
示例包装的 PST 存储区提供程序使用个人文件夹文件 (PST) 提供程序作为存储数据的后端。 包装的 PST 存储区提供程序应与复制 API 一起使用。 
  
复制 API 使您能够将项目从后端数据存储库复制到 Microsoft Outlook PST 存储。 您可以使用复制 API 将数据复制到专用的 PST 存储, 并跟踪同步状态。 有关详细信息, 请参阅[关于复制 API](about-the-replication-api.md)。
  
示例包装的 pst 存储提供程序中的大多数函数将其参数直接传递给基础 PST 提供程序。 某些函数需要特殊实现, 以下主题对此进行了说明。
  
|||
|:-----|:-----|
|执行  <br/> |WrpPST32  <br/> |
|源代码目录:  <br/> |SampleWrappedPSTStoreProvider\WrapPST  <br/> |
|语言  <br/> |c  <br/> |
|平台  <br/> |Microsoft Visual Studio 2008 for windows Vista、windows server 2008、windows XP SP2 和 windows Server 2003 SP1 的编译  <br/> |
   
## <a name="supported-features"></a>支持的功能

此示例支持 Microsoft outlook 2010 64 位, 现已针对 Outlook 2013 进行了修订。 有关其他信息, 请参阅以下主题:
  
- [关于复制 API](about-the-replication-api.md)
    
- [初始化打包的 PST 存储区提供程序](initializing-a-wrapped-pst-store-provider.md)
    
- [登录到打包的 PST 存储区提供程序](logging-on-to-a-wrapped-pst-store-provider.md)
    
- [使用包装的 PST 存储区提供程序](using-a-wrapped-pst-store-provider.md)
    
- [关闭打包的 PST 存储区提供程序](shutting-down-a-wrapped-pst-store-provider.md)
    
 **安装示例包装的 PST 存储区提供程序**
  
1. 若要下载示例打包的 PST 提供程序, 请参阅[下载 Outlook MAPI 示例](downloading-the-outlook-mapi-samples.md)。
    
2. 找到保存 Outlook MAPI 示例的文件夹。 右键单击 " **OutlookMAPISamples\<\>号码**" zip 文件夹, 然后单击 "**全部提取**"。
    
3. 单击 "**浏览**", 选择要保存示例的位置, 然后单击 "**提取**"。
    
4. 运行 Microsoft Visual Studio 2008。
    
5. 在 Microsoft Visual Studio 2008 中, 单击 "**文件**", 选择 "**打开**", 然后单击 "**项目/解决方案**"。
    
6. 浏览到保存示例的位置, 单击 " **WrapPST**", 然后单击 "**打开**"。
    
7. 在"构建"菜单上，单击"构建解决方案"。
    
8. 在 "**将文件另存为**" 对话框中, 单击 "**保存**"。
    
9. 在保存示例的文件夹中, 右键单击 **.bat**文件, 然后单击 "**以管理员身份运行**"。
    
10. 在“用户帐户控制”**** 对话框中，单击“继续”****。
    

