---
title: 编写层次结构查看器
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 4c939a8c-8148-4add-b181-5a12e6d32309
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 0286696707d268867a5536ef345d0af7909918dd
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779110"
---
# <a name="writing-a-hierarchy-viewer"></a>编写层次结构查看器

  
  
**适用于**： Outlook 
  
层次结构查看器是用于显示文件夹和通讯簿容器层次结构表的用户界面组件。 层次结构查看者可以在不同级别，展开和折叠按需型每个级别显示的层次结构的成员。
  
Container 属性， **PR_DEPTH** ([PidTagDepth](pidtagdepth-canonical-property.md))，控件的层次结构成员将显示的级别。 表示顶级通讯簿容器或文件夹项具有其**PR_DEPTH**属性设置为零。 此属性的值将按顺序递增顺序级别的条目。 即，当用户选择的顶级容器展开，显示所有容器都与**PR_DEPTH**都设置为 1。 当用户展开这些子容器之一时，2，向显示**PR_DEPTH**设置的容器，依此类推。 
  
层次结构查看器支持不同范围的深度。 您可以限制为仅一个或两个级别您查看器或显示大规模层次结构是否优先级，您可以支持多个级别。 
  
通讯簿提供用于在通讯簿中的顶级容器层次结构查看器。 
  
 **若要访问通讯簿层次结构表**
  
1. 调用[IAddrBook::OpenEntry](iaddrbook-openentry.md)，传递 null 条目标识符，打开在通讯簿根容器。
    
2. 调用根容器[IMAPIContainer::GetHierarchyTable](imapicontainer-gethierarchytable.md)方法来访问的 MAPI 通讯簿层次结构表。 
    
 **若要访问的默认邮件存储层次结构表**
  
1. 调用[IMAPISession::GetMsgStoresTable](imapisession-getmsgstorestable.md)消息存储表的访问。 
    
2. 构建使用[SPropertyRestriction](spropertyrestriction.md)结构限制表格**PR_DEFAULT_STORE** ([PidTagDefaultStore](pidtagdefaultstore-canonical-property.md)) 属性设置为 TRUE 的行限制。 
    
3. 调用[IMAPITable::FindRow](imapitable-findrow.md)，将其传递**SPropertyRestriction**，以找到表示默认的邮件存储的行。 
    
4. 调用[IMAPISession::OpenEntry](imapisession-openentry.md)，从默认的邮件存储的消息存储表中行传递**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性中。
    
5. 调用的消息存储[IMAPIProp::GetProps](imapiprop-getprops.md)方法来检索**PR_IPM_SUBTREE_ENTRYID** ([PidTagIpmSubtreeEntryId](pidtagipmsubtreeentryid-canonical-property.md)) 属性。
    
6. 调用的消息存储[IMsgStore::OpenEntry](imsgstore-openentry.md)方法，传递**PR_IPM_SUBTREE_ENTRYID**属性，以打开的消息存储 IPM 子树的根文件夹。 
    
7. 调用 IPM 根文件夹[IMAPIContainer::GetHierarchyTable](imapicontainer-gethierarchytable.md)方法，以访问其层次结构表。 
    

