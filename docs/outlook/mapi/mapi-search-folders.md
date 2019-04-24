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
  
搜索结果文件夹保留了指向常规文件夹中的邮件的链接, 而不是实际的邮件。 客户端通过调用[IMAPIFolder:: CreateFolder](imapifolder-createfolder.md)方法并将 FOLDER_SEARCH 作为_ulFolderType_参数来创建搜索结果文件夹。 客户端通过设置和应用搜索条件来填充搜索结果文件夹—使用特定特征筛选出邮件的规则。 使用[IMAPIContainer:: SetSearchCriteria](imapicontainer-setsearchcriteria.md)方法设置搜索条件。 客户端生成一个或多个[SRestriction](srestriction.md)结构以表示要应用的搜索条件并将其传递给**SetSearchCriteria**。 **SetSearchCriteria**还指定指示搜索域的文件夹列表和一组用于控制如何执行搜索的标志。 
  
 **SetSearchCriteria**标识与指定的限制匹配的邮件。 选定的邮件 (满足条件的邮件) 将显示为搜索结果文件夹中的链接。 当客户端调用[IMAPIContainer:: GetContentsTable](imapicontainer-getcontentstable.md)方法访问搜索结果文件夹的内容表时, 所选的邮件将显示在表中。 搜索的内容表格-结果文件夹包含与通用文件夹的内容表格相同的列。 但是, 对于搜索结果文件夹, **PR_PARENT_ENTRYID** ([PidTagParentEntryId](pidtagparententryid-canonical-property.md)) 属性指定链接的邮件所在的文件夹的条目标识符。 搜索-结果文件夹不被视为父文件夹。
  
搜索-结果文件夹具有以下限制:
  
- 可以修改搜索结果文件夹内容的唯一方法是通过调用**SetSearchCriteria**。 有关实现**SetSearchCriteria**的详细信息, 请参阅知识库文章[260322: 如何使用 SetSearchCriteria 方法搜索文件夹](https://go.microsoft.com/fwlink/?LinkId=123603)。
    
- 无法将邮件移动或复制到搜索结果文件夹中。
    
- 搜索-结果文件夹不能包含子文件夹。 
    
- 客户端无法将搜索结果文件夹设为搜索的主题。
    
但是, 可以修改搜索结果文件夹的属性并使用它删除邮件。 从搜索结果文件夹中删除邮件时, 该邮件实际上会从实际文件夹中删除。 但是, 删除搜索结果文件夹本身对内部的邮件没有影响;它们保留在其通用文件夹中。
  
## <a name="see-also"></a>另请参阅



[MAPI 文件夹](mapi-folders.md)

