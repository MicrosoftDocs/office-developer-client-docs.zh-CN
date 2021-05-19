---
title: MAPI 搜索文件夹
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 36c14d91-77f7-43a3-8d87-d50bcc21fad7
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: c1d7f67458852319587d98831d031b2c3a131871
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32357671"
---
# <a name="mapi-search-folders"></a>MAPI 搜索文件夹

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
搜索结果文件夹包含指向常规文件夹中的邮件（而不是实际邮件）的链接。 客户端通过调用 [IMAPIFolder：：CreateFolder](imapifolder-createfolder.md) 方法创建搜索结果文件夹，FOLDER_SEARCH  _ulFolderType_ 参数。 客户端通过设置和应用搜索条件（筛选出具有特定特征的邮件的规则）来填充搜索结果文件夹。 使用 [IMAPIContainer：：SetSearchCriteria](imapicontainer-setsearchcriteria.md) 方法设置搜索条件。 客户端构建一个或多个 [SRestriction](srestriction.md) 结构来表示要应用的搜索条件，并传递到 **SetSearchCriteria**。 **SetSearchCriteria** 还指定用于指示搜索域的文件夹列表以及控制搜索执行方式的一组标志。 
  
 **SetSearchCriteria** 标识匹配指定限制的邮件。 所选邮件 (满足条件的邮件) 在搜索结果文件夹中显示为链接的邮件。 当客户端调用 [IMAPIContainer：：GetContentsTable](imapicontainer-getcontentstable.md) 方法访问搜索结果文件夹的内容表时，选定的消息将显示在表中。 搜索结果文件夹的内容表包含与常规文件夹的内容表相同的列。 但是，对于搜索结果文件夹，PR_PARENT_ENTRYID ( [PidTagParentEntryId](pidtagparententryid-canonical-property.md)) 属性指定链接邮件所在的文件夹的条目标识符。 搜索结果文件夹不被视为父文件夹。
  
搜索结果文件夹具有以下限制：
  
- 修改搜索结果文件夹内容的唯一方式是通过调用 **SetSearchCriteria**。 有关 **SetSearchCriteria** 实现详细信息，请参阅知识库文章 [260322：如何使用 SetSearchCriteria 方法搜索文件夹](https://go.microsoft.com/fwlink/?LinkId=123603)。
    
- 无法将邮件移动或复制到搜索结果文件夹中。
    
- 搜索结果文件夹不能包含子文件夹。 
    
- 客户端无法将搜索结果文件夹作为搜索的主题。
    
但是，可以修改搜索结果文件夹的属性，并使用它来删除邮件。 从搜索结果文件夹中删除邮件时，实际上会从真实文件夹中删除该邮件。 但是，删除搜索结果文件夹本身不会影响内部的邮件;它们仍保留在常规文件夹中。
  
## <a name="see-also"></a>另请参阅



[MAPI 文件夹](mapi-folders.md)

