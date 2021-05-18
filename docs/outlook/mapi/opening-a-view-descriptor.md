---
title: 打开视图描述符
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 1940feb0-9e0f-4d96-9fb9-b9a35a0aa661
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: ce53e5a91f6fa340728872457eae7f6514e287aa
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33413036"
---
# <a name="opening-a-view-descriptor"></a>打开视图描述符
  
**适用于**：Outlook 2013 | Outlook 2016 
  
许多文件夹都可以使用普通视图、默认视图或任意数目的个性化视图打开。 视图描述如何显示文件夹的内容。 如果没有备用视图，并且第一次打开文件夹，则使用普通视图。 当存在备用视图时，必须使用它打开文件夹。
  
视图在称为视图描述符的消息中介绍。 视图描述符通常创建为关联邮件，并可以显示在公用或个人视图文件夹或任何 IPM 文件夹中。
  
### <a name="to-open-a-view-descriptor"></a>打开视图描述符
  
1. 调用 [IMAPIContainer：：GetContentsTable](imapicontainer-getcontentstable.md) 以检索文件夹的关联内容表。 
    
2. 创建一个限制，以便仅查找具有保留用于视图描述符的邮件类的邮件，并调用 [IMAPITable：：Restrict](imapitable-restrict.md) 以限制表和 [IMAPITable：：QueryRows](imapitable-queryrows.md) 检索相应的行，或者...
    
   调用文件夹的 [IMAPIProp：：GetProps](imapiprop-getprops.md) 方法来 **检索其** PR_DEFAULT_VIEW_ENTRYID ([PidTagDefaultViewEntryId](pidtagdefaultviewentryid-canonical-property.md)) 属性。 **PR_DEFAULT_VIEW_ENTRYID** 包含包含文件夹的默认视图描述符的邮件的条目标识符。 如果文件夹支持在调用 [IMAPIFolder：：CreateMessage](imapifolder-createmessage.md) 和 [IMAPIContainer：：GetContentsTable](imapicontainer-getcontentstable.md)时使用 MAPI_ASSOCIATED 标志，此调用将成功。
    
3. 使用视图描述符的条目标识符调用 [IMsgStore：：OpenEntry](imsgstore-openentry.md) 以打开它。 
    

