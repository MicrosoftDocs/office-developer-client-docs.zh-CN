---
title: 遍历收件箱文件夹
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 2ad1459f-d59a-4784-94ea-4cad194e6e50
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 87fcde5a28a30f08bc2fd5f28fb692a4b4251fbf
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779008"
---
# <a name="traversing-the-inbox-folder"></a>遍历收件箱文件夹

  
  
**适用于**： Outlook 
  
 **若要循环进行所有收件箱中的消息**
  
1. 调用[IMsgStore::GetReceiveFolder](imsgstore-getreceivefolder.md)检索的收件箱的项标识符。 
    
2. 调用**IMAPIFolder::OpenEntry**打开收件箱。 
    
3. 调用收件箱的[IMAPIContainer::GetContentsTable](imapicontainer-getcontentstable.md)方法来检索内容表。 
    
4. 调用内容表的[IMAPITable::SetColumns](imapitable-setcolumns.md)方法，以限制设置为**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 的列和所需的任何其他列。 
    
5. 调用[IMAPITable::QueryRows](imapitable-queryrows.md)检索一组行。 
    
6. 直到内容表中不再有任何行：
    
1. 调用[IMsgStore::OpenEntry](imsgstore-openentry.md)以打开由每一行中的项标识符的邮件。 
    
2. _LppUnk_参数分配一个本地**IMessage**接口指针。 
    
3. 处理邮件的属性。
    
4. 释放_lppUnk_参数指向的指针。 
    
5. 调用[IMAPITable::QueryRows](imapitable-queryrows.md)若要检索的行下一步组。 
    
7. 发行版的内容表。
    

