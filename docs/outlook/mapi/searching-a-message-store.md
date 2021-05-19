---
title: 搜索邮件存储
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 9e8d4639-7507-4d98-b56f-a65be369dc40
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 7240f49a15fdaea4d1f30dae578d25c3f2c1c0f3
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33426035"
---
# <a name="searching-a-message-store"></a>搜索邮件存储

**适用于**：Outlook 2013 | Outlook 2016 
  
客户端应用程序可以搜索一个或多个文件夹，查找与搜索条件匹配的邮件。 最直接的搜索技术涉及应用限制来定义条件，将结果放入搜索结果文件夹，该文件夹是为此搜索或之前的搜索显式创建的。 并非所有邮件存储都支持此技术。 

若要确定你使用的邮件存储是否支持使用搜索结果文件夹，请调用 [其 IMAPIProp：：GetProps](imapiprop-getprops.md) 方法来检索 **PR \_ STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) 属性。 如果STORE_SEARCH_OK，则支持搜索。 如果未设置，则需要其他方法，如手动检查目标文件夹。
  
### <a name="to-search-one-or-more-folders-in-a-message-store"></a>搜索邮件存储中的一个或多个文件夹
  
1. 如果你有上一次搜索中的搜索结果文件夹，请跳到步骤 2。 否则，创建搜索结果文件夹：
    
    1. 通过调用邮件存储的[IMAPIProp：：GetProps](imapiprop-getprops.md)方法并请求 PR_FINDER_ENTRYID ([PidTagFinderEntryId](pidtagfinderentryid-canonical-property.md)) ，检索搜索结果根文件夹的条目标识符。 
        
    2. 调用 [IMsgStore：：OpenEntry](imsgstore-openentry.md) 以打开由 PR_FINDER_ENTRYID。 
        
    3. 调用文件夹的 [IMAPIFolder：：CreateFolder](imapifolder-createfolder.md) 方法以创建一个设置有FOLDER_SEARCH文件夹。 
    
2. 构建用于保留搜索条件的限制。 
    
3. 创建表示要搜索的文件夹的条目标识符数组。 如果之前已使用搜索结果文件夹，并且您希望搜索相同的文件夹，则无需执行此步骤。
    
4. 调用搜索结果文件夹 [的 IMAPIContainer：：SetSearchCriteria](imapicontainer-setsearchcriteria.md) 方法，将  _lpContainerList_ 指向条目标识符数组，  _将 lpRestriction_ 指向限制。 
    
5. 如果已使用邮件存储注册搜索完成通知，请等待通知到达。
    
6. 通过调用搜索结果文件夹的 [IMAPIContainer：：GetContentsTable](imapicontainer-getcontentstable.md) 方法访问其内容表来查看搜索结果。 
    
7. 调用内容表的 [IMAPITable：：QueryRows](imapitable-queryrows.md) 方法来检索满足搜索条件的消息。 
    

