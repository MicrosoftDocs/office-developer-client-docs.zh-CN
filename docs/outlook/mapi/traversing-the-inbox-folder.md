---
title: 遍历收件箱文件夹
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 2ad1459f-d59a-4784-94ea-4cad194e6e50
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: e954cb2d8029a31e7f69daaa7e8ed55a7953ac02
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33406554"
---
# <a name="traversing-the-inbox-folder"></a>遍历收件箱文件夹

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
 **循环收件箱中所有邮件**
  
1. 调用 [IMsgStore：：GetReceiveFolder](imsgstore-getreceivefolder.md) 检索收件箱的条目标识符。 
    
2. 调用 **IMAPIFolder：：OpenEntry** 以打开收件箱。 
    
3. 调用收件箱的 [IMAPIContainer：：GetContentsTable](imapicontainer-getcontentstable.md) 方法来检索内容表。 
    
4. 调用内容表 [的 IMAPITable：：SetColumns](imapitable-setcolumns.md) 方法，以将列集限制为 **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 以及您需要的其他任何列。 
    
5. 调用 [IMAPITable：：QueryRows](imapitable-queryrows.md) 以检索一组行。 
    
6. 在内容表中不再有任何行之前：
    
1. 调用 [IMsgStore：：OpenEntry](imsgstore-openentry.md) 以打开每行中的条目标识符表示的邮件。 
    
2. 将  _lppUnk_ 参数分配给本地 **IMessage 接口** 指针。 
    
3. 使用邮件的属性。
    
4. 释放  _lppUnk_ 参数指向的指针。 
    
5. 调用 [IMAPITable：：QueryRows](imapitable-queryrows.md) 以检索下一组行。 
    
7. 释放内容表。
    

