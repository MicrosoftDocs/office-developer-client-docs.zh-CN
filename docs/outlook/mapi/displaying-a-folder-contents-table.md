---
title: 显示文件夹内容表
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 14a4c123-776d-4a32-9688-8a4402dd1f53
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 30099e9fe645f810e08ba331717cff975f69b313
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774813"
---
# <a name="displaying-a-folder-contents-table"></a>显示文件夹内容表

**适用于**： Outlook 
  
文件夹的内容表包含有关的所有消息的摘要信息。 内容的接收文件夹的邮件类的表中显示有关新的传入消息的摘要信息。 若要使此信息可供用户使用，检索表并根据需要显示的列和行。
  
**显示文件夹内容**
  
1. 调用[IMsgStore::OpenEntry](imsgstore-openentry.md)，传递包含表的文件夹的项标识符。
    
2. 调用该文件夹的[IMAPIContainer::GetContentsTable](imapicontainer-getcontentstable.md)方法以打开其内容的表格。 
    
3. 如果需要通过调用表的[IMAPITable::SetColumns](imapitable-setcolumns.md)方法来指定特定的列，限制内容表的视图。 
    
4. 如果需要通过调用表的[IMAPITable::Restrict](imapitable-restrict.md)方法以筛选特定的行，限制内容表的视图。 如果，例如，您想要显示仅尚未要读取的消息与特定的邮件类： 
    
    1. 创建具有所需的邮件类的**PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)) 属性相匹配[SPropertyRestriction](spropertyrestriction.md)结构中属性限制。 
        
    2. 创建使用**PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 作为属性标记和 MSGFLAG_UNREAD 值作为掩码[SBitMaskRestriction](sbitmaskrestriction.md)结构中的位掩码限制。
        
    3. 创建加入属性和位掩码限制[SAndRestriction](sandrestriction.md)结构中的限制。 
    
5. 如果需要通过调用表的[IMAPITable::SortTable](imapitable-sorttable.md)方法，排序的内容表。 
    
6. 调用[IMAPITable::QueryRows](imapitable-queryrows.md)处理的内容表中检索的所有行。 
    

