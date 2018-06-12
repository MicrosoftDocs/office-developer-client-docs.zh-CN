---
title: MAPI 接收文件夹
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 2e1287a3-0f15-4d9a-b7ee-738fce9cd51f
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 619bd2d5e3b40e49da835d774035ba237af06699
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776293"
---
# <a name="mapi-receive-folders"></a>MAPI 接收文件夹

  
  
**适用于**： Outlook 
  
接收文件夹包含特定邮件类别的入站的邮件。 接收由客户端、 消息存储提供程序，或 MAPI，则可以建立关联的文件夹。 MAPI 有两个默认的接收文件夹： 消息存储库的根文件夹和人际邮件 (IPM) 子树的收件箱文件夹。 消息存储库的根文件夹是默认接收所有进程间通信 (IPC) 邮件文件夹。
  
 每个新的消息存储由 MAPI 创建收件箱文件夹，并作为默认接收的以下邮件类的文件夹： 
  
- IPM 邮件类。
    
- 报告邮件类。
    
- 为空，或者缺少的类。
    
所有报告的邮件，甚至发送响应 IPC 消息，都放在收件箱文件夹。 处理其自己的报告的 IPC 客户端应用程序必须明确添加用于报表的特定类的接收文件夹。 例如，如果希望接收邮件类 IPC 客户端。Paper.Order，它应调用[IMsgStore::SetReceiveFolder](imsgstore-setreceivefolder.md)方法建立与类 Report.IPC.Paper.Order 报告的接收文件夹。 
  
接收基于分层组织的邮件类关联的文件夹。 客户端可以显式建立的接收文件夹和邮件类之间的关联或使用 MAPI 默认接收文件夹。 通常情况下，客户端指定接收邮件的基类的一个文件夹和所有及其子类别。 例如，典型的客户端会建立的邮件类**MyClass**与的关联。 然后如果客户端收到邮件类**MyClass.Home**或**MyClass.Home.Kitchen.Computer**，这些消息将转到基类**MyClass**的接收文件夹中。
  
有三个消息存储方法用于处理客户端接收文件夹：
  
- [IMsgStore::GetReceiveFolderTable](imsgstore-getreceivefoldertable.md)
    
- [IMsgStore::GetReceiveFolder](imsgstore-getreceivefolder.md)
    
- [IMsgStore::SetReceiveFolder](imsgstore-setreceivefolder.md)
    
接收文件夹表是所有消息存储建立的接收文件夹信息的列表。 其所需的列集包括邮件类、 记录键和项标识符。
  
若要检索特定的邮件类的接收文件夹，客户端，请传递给[IMsgStore::GetReceiveFolder](imsgstore-getreceivefolder.md)方法的邮件类字符串。 消息存储提供程序返回的相应文件夹的项标识符。 若要实现**GetReceiveFolder**，消息存储提供程序应使用的算法的选择其关联的邮件类别匹配指定的邮件类的最长可能前缀的文件夹。 例如，假定消息存储已接收文件夹和邮件类在以下之间关联其接收文件夹表：
  
- **IPM**消息放在收件箱文件夹中。 
    
- **IPM。Note.Sample**消息放在示例文件夹中。 
    
下表显示了如何使用各种类的邮件将被路由至相应的接收文件夹。
  
|**入站的邮件类**|**接收文件夹**|
|:-----|:-----|
|**IPM。Note.Sample.Simple** <br/> |示例文件夹  <br/> |
|**IPM。注释** <br/> |收件箱文件夹  <br/> |
|**IPM。考勤卡** <br/> |收件箱文件夹  <br/> |
|**IPM。Note.Sample.Simple.Totally** <br/> |示例文件夹  <br/> |
   
客户端调用**SetReceiveFolder**方法以使特定邮件类别之间的显式关联和接收文件夹。 邮件传递到空的邮件类，MAPI 将消息置于定义空类的前缀的接收文件夹。 例如，如果您的客户端已建立的邮件的接收文件夹类**IPM**和邮件类**IPM。Note.Test**是送达，此消息将被置于**IPM**邮件类的接收文件夹。 
  
在调用**SetReceiveFolder**，客户端通常传递邮件类字符串和新的项标识符接收文件夹。 但是，客户端可以传递中一个或两个这些参数为 NULL。 下表介绍的邮件类和条目标识符参数指定 NULL 结果的行为。 
  
|**_SetReceiveFolder_参数**|**结果行为**|
|:-----|:-----|
|设置为 NULL 的项标识符  <br/> |消息存储库中删除指定之间的关联邮件类和其现有的接收文件夹。 新接收未建立文件夹。  <br/> 后续调用**GetReceiveFolder**与此邮件类将返回的邮件类; 前缀的接收文件夹对于新邮件存储区， **GetReceiveFolder**将返回收件箱 IPM 子树。  <br/> |
|邮件类设置为 NULL  <br/> |消息存储到指定的文件夹更改为空邮件类关联。 其类是否则无法识别的传入消息将转到此文件夹中。  <br/> |
|设置为 NULL 的项标识符和邮件类  <br/> |消息存储删除的空邮件类的类/文件夹关联。 因为它通常会导致消息存储库，看不到客户端的文件夹的根文件夹中放置的入站邮件，不应为 NULL，设置这两个参数。  <br/> |
   
尽管邮件类绝不应为空，但可能会发生空邮件类。 消息存储库的责任分配的邮件类**IPM**到新的出站邮件包含一个空的类;是分配**IPM 的传输提供程序的责任。注意**作为有任何空类的入站邮件的类。 
  
## <a name="see-also"></a>另请参阅



[MAPI 文件夹](mapi-folders.md)

