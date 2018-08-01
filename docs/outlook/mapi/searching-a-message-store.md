---
title: 搜索的消息存储
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 9e8d4639-7507-4d98-b56f-a65be369dc40
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 90ed7da43d7f9e5e8b5f3024f1eee99a2d7a2b5c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778717"
---
# <a name="searching-a-message-store"></a>搜索的消息存储

**适用于**： Outlook 
  
客户端应用程序可以搜索通过查找与搜索条件匹配的消息的一个或多个文件夹中。 最简单的搜索技术涉及应用定义条件限制，并将结果放到搜索结果文件夹中，此搜索或以前搜索明确创建。 并非所有的消息存储库支持这种技术。 

若要确定是否消息存储库使用支持使用搜索结果文件夹，调用来检索其[IMAPIProp::GetProps](imapiprop-getprops.md)方法**PR\_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) 属性。 如果设置了 STORE_SEARCH_OK 标志，搜索则支持。 如果它未设置，您将需要手动检查的目标文件夹如另一种方法。
  
### <a name="to-search-one-or-more-folders-in-a-message-store"></a>消息存储区中搜索一个或多个文件夹
  
1. 如果您有从前一个搜索的搜索结果文件夹，请跳到步骤 2。 否则为若要创建一个搜索结果文件夹：
    
    1. 通过调用的消息存储[IMAPIProp::GetProps](imapiprop-getprops.md)方法并请求**PR_FINDER_ENTRYID** ([PidTagFinderEntryId](pidtagfinderentryid-canonical-property.md)) 检索搜索结果的根文件夹的项标识符。
        
    2. 调用[IMsgStore::OpenEntry](imsgstore-openentry.md)以打开由 PR_FINDER_ENTRYID 文件夹。 
        
    3. 调用该文件夹的[IMAPIFolder::CreateFolder](imapifolder-createfolder.md)方法，以创建具有设置了 FOLDER_SEARCH 标志的搜索结果文件夹。 
    
2. 生成用于存放您的搜索条件的限制。 
    
3. 创建一个表示要搜索的文件夹的项标识符的数组。 此步骤是不必要的如果已使用搜索结果文件夹之前，并且您希望搜索相同的文件夹。
    
4. 调用的搜索结果文件夹[IMAPIContainer::SetSearchCriteria](imapicontainer-setsearchcriteria.md)方法， _lpContainerList_指向条目标识符数组和_lpRestriction_限制。 
    
5. 如果您的消息存储与搜索完成通知注册，等待要进入的通知。
    
6. 通过调用文件夹的[IMAPIContainer::GetContentsTable](imapicontainer-getcontentstable.md)方法访问其内容表的搜索结果中查看搜索结果。 
    
7. 调用内容表的[IMAPITable::QueryRows](imapitable-queryrows.md)方法，以检索满足搜索条件的邮件。 
    

