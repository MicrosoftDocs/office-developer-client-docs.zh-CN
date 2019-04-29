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
  
接收文件夹保存特定邮件类别的入站邮件。 接收文件夹关联可由客户端、邮件存储提供程序或 MAPI 建立。 MAPI 包含两个默认的接收文件夹: 邮件存储的根文件夹以及人际邮件 (IPM) 子树的 "收件箱" 文件夹。 邮件存储区的根文件夹是所有进程间通信 (IPC) 消息的默认接收文件夹。
  
 "收件箱" 文件夹由 MAPI 为每个新邮件存储区创建, 并充当以下邮件类的默认接收文件夹: 
  
- IPM 邮件类。
    
- 报告邮件类。
    
- 类是空的或缺失的。
    
"收件箱" 文件夹中会放置所有报告邮件 (甚至包括作为对 IPC 邮件的响应而发送的邮件)。 处理自己的报告的 IPC 客户端应用程序必须为特定的报告类别显式添加接收文件夹。 例如, 如果客户端希望使用类 IPC 接收邮件。在排序时, 应调用[IMsgStore:: SetReceiveFolder](imsgstore-setreceivefolder.md)方法, 以使用类 Report (IPC) 为报告建立接收文件夹。 
  
接收文件夹关联基于邮件类别的层次结构。 客户端可以显式建立接收文件夹和邮件类别之间的关联, 或使用 MAPI 默认的接收文件夹。 通常情况下, 客户端会指定一个文件夹以接收基类及其所有子类的邮件。 例如, 典型的客户端将建立与类**MyClass**的邮件的关联。 然后, 如果客户端收到类为**MyClass**或 MyClass 的邮件。在**计算机**上, 这些邮件将转到基类 ( **myclass**) 的接收文件夹。
  
客户端使用以下三种邮件存储方法来处理接收文件夹:
  
- [IMsgStore::GetReceiveFolderTable](imsgstore-getreceivefoldertable.md)
    
- [IMsgStore::GetReceiveFolder](imsgstore-getreceivefolder.md)
    
- [IMsgStore::SetReceiveFolder](imsgstore-setreceivefolder.md)
    
接收文件夹表是为邮件存储区建立的所有接收文件夹的相关信息的列表。 其必需的列集包括邮件类、记录键和条目标识符。
  
若要检索特定邮件类别的接收文件夹, 客户端会将邮件类字符串传递给[IMsgStore:: GetReceiveFolder](imsgstore-getreceivefolder.md)方法。 邮件存储提供程序返回对应文件夹的条目标识符。 若要实现**GetReceiveFolder**, 邮件存储提供程序应使用一个算法来选择其关联邮件类别与指定邮件类别的最长可能前缀相匹配的文件夹。 例如, 假设邮件存储区的接收文件夹表中的接收文件夹和邮件类之间有以下关联:
  
- 将**IPM**邮件放在 "收件箱" 文件夹中。 
    
- **IPM。注意: 示例**邮件放在 Samples 文件夹中。 
    
下表显示了如何将具有不同类的邮件路由到相应的接收文件夹。
  
|**入站邮件类**|**接收文件夹**|
|:-----|:-----|
|**ipm.note.注意: 示例。简单** <br/> |Samples 文件夹  <br/> |
|**ipm.note.便笺** <br/> |"收件箱" 文件夹  <br/> |
|**ipm.note.工时** <br/> |"收件箱" 文件夹  <br/> |
|**ipm.note.注意: 完全** <br/> |Samples 文件夹  <br/> |
   
客户端调用**SetReceiveFolder**方法以在特定邮件类别和接收文件夹之间建立显式关联。 将邮件传递到空邮件类时, MAPI 会将邮件放在为空类的前缀定义的接收文件夹中。 例如, 如果您的客户端为具有类**ipm**的邮件和包含类 ipm 的邮件建立了一个接收文件夹 **。注意: 测试**已传递, 此邮件将放置在**IPM**邮件类的接收文件夹中。 
  
在调用**SetReceiveFolder**中, 客户端通常会传递一个邮件类字符串和新的接收文件夹的条目标识符。 但是, 客户端可以为其中一个或两个参数传入 NULL。 下表介绍了为邮件类和条目标识符参数指定 NULL 时所产生的行为。 
  
|**_SetReceiveFolder_参数**|**结果行为**|
|:-----|:-----|
|条目标识符设置为 NULL  <br/> |邮件存储删除指定邮件类别与其现有的接收文件夹之间的关联。 未建立新的接收文件夹。  <br/> 对使用此邮件类的**GetReceiveFolder**的后续调用将返回邮件类的前缀的接收文件夹;对于新的邮件存储库, **GetReceiveFolder**将返回 IPM 子树中的收件箱。  <br/> |
|邮件类设置为 NULL  <br/> |邮件存储将空邮件类别的关联更改为指定的文件夹。 其他无法识别类的传入邮件将转到此文件夹。  <br/> |
|条目标识符和邮件类设置为 NULL  <br/> |邮件存储删除空邮件类别的类/文件夹关联。 不应将这两个参数都设置为 NULL, 因为它通常会导致在邮件存储区的根文件夹中放置入站邮件 (该文件夹对客户端不可见)。  <br/> |
   
虽然邮件的类永远不应为空, 但可能会出现一个空邮件类。 邮件库负责将邮件类别分配给具有空类的新出站邮件的**IPM** ;传输提供程序负责分配**IPM。注释**, 作为包含任何空类的入站邮件的类。 
  
## <a name="see-also"></a>另请参阅



[MAPI 文件夹](mapi-folders.md)

