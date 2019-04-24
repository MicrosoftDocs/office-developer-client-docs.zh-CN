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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32356579"
---
# <a name="traversing-the-inbox-folder"></a>遍历收件箱文件夹

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
 **循环访问收件箱中的所有邮件**
  
1. 调用[IMsgStore:: GetReceiveFolder](imsgstore-getreceivefolder.md)以检索收件箱的条目标识符。 
    
2. 调用**IMAPIFolder:: OpenEntry**以打开收件箱。 
    
3. 调用收件箱的[IMAPIContainer:: GetContentsTable](imapicontainer-getcontentstable.md)方法以检索内容表。 
    
4. 调用内容表的[IMAPITable:: SetColumns](imapitable-setcolumns.md)方法将列设置为**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 和所需的任何其他列。 
    
5. 调用[IMAPITable:: QueryRows](imapitable-queryrows.md)以检索一组行。 
    
6. 直到内容表中不再有任何行:
    
1. 调用[IMsgStore:: OpenEntry](imsgstore-openentry.md)以打开每行中的条目标识符表示的邮件。 
    
2. 将_lppUnk_参数分配给本地**IMessage**接口指针。 
    
3. 使用邮件的属性。
    
4. 释放_lppUnk_参数指向的指针。 
    
5. 调用[IMAPITable:: QueryRows](imapitable-queryrows.md)以检索下一组行。 
    
7. 释放 "内容" 表。
    

