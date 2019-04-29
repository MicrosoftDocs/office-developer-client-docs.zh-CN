---
title: 显示文件夹内容表
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 14a4c123-776d-4a32-9688-8a4402dd1f53
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 56847283afaf41c1d45cdb875ddf49eaa5881175
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33412392"
---
# <a name="displaying-a-folder-contents-table"></a>显示文件夹内容表

**适用于**：Outlook 2013 | Outlook 2016 
  
文件夹的 "内容" 表包含有关其所有邮件的摘要信息。 有关新传入邮件的摘要信息显示在邮件类别的接收文件夹的 "目录" 表中。 若要使此信息对用户可用, 请检索表并根据需要显示列和行。
  
**显示文件夹内容表**
  
1. 调用[IMsgStore:: OpenEntry](imsgstore-openentry.md), 并传递包含该表的文件夹的条目标识符。
    
2. 调用文件夹的[IMAPIContainer:: GetContentsTable](imapicontainer-getcontentstable.md)方法以打开其内容表。 
    
3. 如果需要, 请通过调用表的[IMAPITable:: SetColumns](imapitable-setcolumns.md)方法来指定特定列来限制内容表的视图。 
    
4. 如果需要, 请通过调用表的[IMAPITable:: Restrict](imapitable-restrict.md)方法筛选特定行来限制内容表的视图。 例如, 如果要仅显示具有要阅读的特定邮件类别的邮件, 请执行以下操作: 
    
    1. 在[SPropertyRestriction](spropertyrestriction.md)结构中创建一个与所需的邮件类相匹配的**PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)) 属性的属性限制。 
        
    2. 在[SBitMaskRestriction](sbitmaskrestriction.md)结构中创建一个位掩码限制, 该限制使用**PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 作为属性标记, 将 MSGFLAG_UNREAD 值用作掩码。
        
    3. 在联接属性和位掩码限制的[SAndRestriction](sandrestriction.md)结构中创建限制。 
    
5. 如果需要, 通过调用表的[IMAPITable:: SortTable](imapitable-sorttable.md)方法来对内容表进行排序。 
    
6. 调用[IMAPITable:: QueryRows](imapitable-queryrows.md)以检索内容表中的所有行以进行处理。 
    

