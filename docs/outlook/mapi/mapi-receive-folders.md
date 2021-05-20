---
title: MAPI 接收文件夹
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 2e1287a3-0f15-4d9a-b7ee-738fce9cd51f
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: b22b8641d55037d3755fc9ae32b97455223bbd12
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33431937"
---
# <a name="mapi-receive-folders"></a>MAPI 接收文件夹

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
接收文件夹保留特定邮件类的入站邮件。 接收文件夹关联可以通过客户端、邮件存储提供程序或 MAPI 建立。 MAPI 有两个默认接收文件夹：邮件存储的根文件夹和 IPM 子树 (邮件) 收件箱文件夹。 邮件存储的根文件夹是 IPC 传输的所有进程间通信的默认 () 文件夹。
  
 "收件箱"文件夹由 MAPI 针对每个新邮件存储创建，并充当以下邮件类的默认接收文件夹： 
  
- IPM 邮件类。
    
- 报告邮件类。
    
- 一个空或缺失的类。
    
所有报告邮件（甚至是为响应 IPC 邮件而发送的报告邮件）都放置在"收件箱"文件夹中。 处理自己的报告的 IPC 客户端应用程序必须明确添加特定报告类的接收文件夹。 例如，如果客户端希望接收具有类 IPC 的邮件。Paper.Order，它应调用 [IMsgStore：：SetReceiveFolder](imsgstore-setreceivefolder.md) 方法来为具有类 Report.IPC.Paper.Order 的报告建立接收文件夹。 
  
接收文件夹关联基于邮件类的分层组织。 客户端可以在接收文件夹和邮件类之间显式建立关联，或使用 MAPI 默认接收文件夹。 通常，客户端指定一个文件夹来接收基类及其所有子类的邮件。 例如，典型的客户端会为具有 MyClass 类的邮件 **建立关联**。 然后，如果客户端收到具有 MyClass.Home 或 **MyClass.Home.Kitchen.Computer** 类的邮件，这些邮件将转到基类 **MyClass** 的接收文件夹。 
  
客户端使用三种邮件存储方法处理接收文件夹：
  
- [IMsgStore::GetReceiveFolderTable](imsgstore-getreceivefoldertable.md)
    
- [IMsgStore::GetReceiveFolder](imsgstore-getreceivefolder.md)
    
- [IMsgStore::SetReceiveFolder](imsgstore-setreceivefolder.md)
    
接收文件夹表是有关为邮件存储建立的所有接收文件夹的信息列表。 其所需的列集包括邮件类、记录键和条目标识符。
  
若要检索特定邮件类的接收文件夹，客户端将邮件类字符串传递给 [IMsgStore：：GetReceiveFolder](imsgstore-getreceivefolder.md) 方法。 邮件存储提供程序返回相应文件夹的条目标识符。 若要实现 **GetReceiveFolder，** 邮件存储提供程序应该使用一种算法，选择其关联邮件类与指定邮件类的最长前缀匹配的文件夹。 例如，假定邮件存储在其接收文件夹表中的接收文件夹和邮件类之间具有以下关联：
  
- **IPM** 邮件放置在"收件箱"文件夹中。 
    
- **IPM。Note.Sample** messages are placed in the Samples folder. 
    
下表显示了如何将具有各种类的邮件路由到相应的接收文件夹。
  
|**入站邮件类**|**接收文件夹**|
|:-----|:-----|
|**IPM。Note.Sample.Simple** <br/> |Samples 文件夹  <br/> |
|**IPM。注意** <br/> |收件箱文件夹  <br/> |
|**IPM。Timecard** <br/> |收件箱文件夹  <br/> |
|**IPM。Note.Sample.Simple.Totally** <br/> |Samples 文件夹  <br/> |
   
客户端调用 **SetReceiveFolder** 方法，以建立特定邮件类和接收文件夹之间的显式关联。 当邮件传递到空邮件类时，MAPI 将邮件添加到为空类的前缀定义的接收文件夹中。 例如，如果客户端为具有类 IPM 的邮件和具有类 **IPM** 的邮件建立了接收 **文件夹。注意.测试** 已传递，此邮件将放在 **IPM** 邮件类的接收文件夹中。 
  
在调用 **SetReceiveFolder** 时，客户端通常会传递邮件类字符串和新接收文件夹的条目标识符。 但是，客户端可以针对其中一个或两个参数传递 NULL。 下表描述了为邮件类和条目标识符参数指定 NULL 时导致的行为。 
  
|**_SetReceiveFolder_ 参数**|**生成的行为**|
|:-----|:-----|
|条目标识符设置为 NULL  <br/> |邮件存储删除指定邮件类及其现有接收文件夹之间的关联。 未建立新的接收文件夹。  <br/> 对此邮件 **类的 GetReceiveFolder** 的后续调用将返回邮件类前缀的接收文件夹;对于新邮件存储 **，GetReceiveFolder** 将返回 IPM 子树中的收件箱。  <br/> |
|邮件类设置为 NULL  <br/> |邮件存储将空邮件类的关联更改到指示的文件夹。 其类无法识别的传入邮件将转到此文件夹。  <br/> |
|条目标识符和邮件类设置为 NULL  <br/> |邮件存储会删除空邮件类的类/文件夹关联。 不应将两个参数都设置为 NULL，因为它通常会导致入站邮件被置于邮件存储的根文件夹中，即对客户端不可见的文件夹。  <br/> |
   
尽管邮件的类永远不应为空，但会出现空邮件类。 邮件存储负责为具有空类的新出站邮件将邮件类分配给 **IPM;** 分配 IPM 是传输提供程序 **的责任。请注意** ，作为具有任何空类的入站邮件的类。 
  
## <a name="see-also"></a>另请参阅



[MAPI 文件夹](mapi-folders.md)

