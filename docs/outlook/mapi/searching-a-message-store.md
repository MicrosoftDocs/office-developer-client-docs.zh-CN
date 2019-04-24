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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32338799"
---
# <a name="searching-a-message-store"></a>搜索邮件存储

**适用于**：Outlook 2013 | Outlook 2016 
  
客户端应用程序可以在一个或多个文件夹中搜索, 以查找与搜索条件相匹配的邮件。 最简单的搜索技术涉及到应用限制以定义条件并将结果放入搜索结果文件夹中 (为此搜索显式创建) 或之前的搜索。 并非所有邮件存储区都支持此技术。 

若要确定您使用的邮件存储库是否支持使用搜索结果文件夹, 请调用其[IMAPIProp:: GetProps](imapiprop-getprops.md)方法检索 " **\_PR STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md))" 属性。 如果设置了 STORE_SEARCH_OK 标志, 则支持搜索。 如果未设置, 则需要另一种方法, 如手动检查目标文件夹。
  
### <a name="to-search-one-or-more-folders-in-a-message-store"></a>搜索邮件存储区中的一个或多个文件夹
  
1. 如果您的搜索结果文件夹来自以前的搜索, 请跳至步骤2。 否则, 若要创建搜索结果文件夹, 请执行以下操作:
    
    1. 通过调用邮件存储区的[IMAPIProp:: GetProps](imapiprop-getprops.md)方法和请求**PR_FINDER_ENTRYID** ([PidTagFinderEntryId](pidtagfinderentryid-canonical-property.md)), 检索搜索结果根文件夹的条目标识符。
        
    2. 调用[IMsgStore:: OpenEntry](imsgstore-openentry.md)以打开 PR_FINDER_ENTRYID 所代表的文件夹。 
        
    3. 调用文件夹的[IMAPIFolder:: CreateFolder](imapifolder-createfolder.md)方法来创建 FOLDER_SEARCH 标志集的搜索结果文件夹。 
    
2. 建立限制以保留你的搜索条件。 
    
3. 创建表示要搜索的文件夹的项标识符的数组。 如果以前使用过搜索结果文件夹, 并且您希望在相同的文件夹中搜索, 则不需要执行此步骤。
    
4. 调用搜索结果文件夹的[IMAPIContainer:: SetSearchCriteria](imapicontainer-setsearchcriteria.md)方法, 将_lpContainerList_指向条目标识符数组, 并_lpRestriction_到限制。 
    
5. 如果已使用邮件存储区注册了搜索完成通知, 请等待通知到达。
    
6. 通过调用搜索结果文件夹的[IMAPIContainer:: GetContentsTable](imapicontainer-getcontentstable.md)方法访问其内容表, 查看搜索结果。 
    
7. 调用内容表的[IMAPITable:: QueryRows](imapitable-queryrows.md)方法以检索满足搜索条件的邮件。 
    

