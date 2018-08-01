---
title: MAPI 搜索文件夹
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 36c14d91-77f7-43a3-8d87-d50bcc21fad7
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: e74767f4b3a19442beac5f9c9ac375286bb47c81
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776312"
---
# <a name="mapi-search-folders"></a>MAPI 搜索文件夹

  
  
**适用于**： Outlook 
  
搜索结果文件夹包含链接到泛型文件夹中的邮件，而不是实际的邮件。 客户端通过调用带 FOLDER_SEARCH 作为_ulFolderType_参数的[IMAPIFolder::CreateFolder](imapifolder-createfolder.md)方法创建一个搜索结果文件夹。 客户端通过设置并应用搜索条件填充的搜索结果文件夹 — 筛选出与特定的特征的邮件的规则。 使用[IMAPIContainer::SetSearchCriteria](imapicontainer-setsearchcriteria.md)方法设置搜索条件。 客户端构建表示搜索条件以应用并将它们传递给**SetSearchCriteria**的一个或多个[SRestriction](srestriction.md)结构。 **SetSearchCriteria**还指定指示搜索域的文件夹的列表和一组标志将如何执行搜索该控件。 
  
 **SetSearchCriteria**标识符合指定的限制的邮件。 所选的邮件 （满足条件的那些） 显示为搜索结果文件夹中的链接。 当客户端调用[IMAPIContainer::GetContentsTable](imapicontainer-getcontentstable.md)方法来访问内容表中的搜索结果文件夹时，表中显示选定的邮件。 为搜索结果文件夹内容表包含相同的泛型文件夹内容表格列。 但是，对于搜索结果文件夹， **PR_PARENT_ENTRYID** ([PidTagParentEntryId](pidtagparententryid-canonical-property.md)) 属性指定链接的消息所在的文件夹的项标识符。 搜索结果文件夹不被认为是父文件夹。
  
搜索结果文件夹具有以下限制：
  
- 可以修改搜索结果文件夹的内容的唯一方法是通过调用**SetSearchCriteria**。 有关**SetSearchCriteria**实现的详细信息，请参阅知识库文章[260322： 如何对搜索文件夹与 SetSearchCriteria 方法](http://go.microsoft.com/fwlink/?LinkId=123603)。
    
- 无法移动或复制到文件夹中搜索结果的消息。
    
- 搜索结果文件夹不能包含子文件夹。 
    
- 客户端不能进行的搜索结果文件夹搜索的主题。
    
它是可能的但是，修改搜索结果文件夹的属性和使用它来删除一条消息。 从搜索结果文件夹中删除一条消息后，它是实际删除从实际的文件夹。 但是，删除搜索结果文件夹本身时不会影响; 内的消息它们保留在其泛型文件夹中。
  
## <a name="see-also"></a>另请参阅



[MAPI 文件夹](mapi-folders.md)

