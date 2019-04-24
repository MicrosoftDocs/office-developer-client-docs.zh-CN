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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32326206"
---
# <a name="opening-a-view-descriptor"></a>打开视图描述符
  
**适用于**：Outlook 2013 | Outlook 2016 
  
可以使用普通视图、默认视图或任意数量的个性化视图打开多个文件夹。 视图介绍如何显示文件夹的内容。 当没有其他视图且您是首次打开该文件夹时, 将使用普通视图。 如果另一个视图存在, 则必须使用它打开该文件夹。
  
在称为视图描述符的消息中对视图进行了描述。 视图描述符通常创建为关联的邮件, 并且可以显示在 "通用" 或 "个人" 视图文件夹或任何 IPM 文件夹中。
  
### <a name="to-open-a-view-descriptor"></a>打开视图描述符
  
1. 调用[IMAPIContainer:: GetContentsTable](imapicontainer-getcontentstable.md)检索文件夹的关联内容表。 
    
2. 创建仅查找邮件类为查看描述符保留的邮件的限制, 并调用[imapitable:: Restrict](imapitable-restrict.md)限制表和[IMAPITable:: QueryRows](imapitable-queryrows.md)以检索适当的行, 或者 .。。
    
   调用文件夹的[IMAPIProp:: GetProps](imapiprop-getprops.md)方法以检索其**PR_DEFAULT_VIEW_ENTRYID** ([PidTagDefaultViewEntryId](pidtagdefaultviewentryid-canonical-property.md)) 属性。 **PR_DEFAULT_VIEW_ENTRYID**包含包含文件夹的默认视图描述符的邮件的条目标识符。 如果文件夹支持在对[IMAPIFolder:: CreateMessage](imapifolder-createmessage.md)和[IMAPIContainer:: GetContentsTable](imapicontainer-getcontentstable.md)的调用上使用 MAPI_ASSOCIATED 标志, 则此调用将会成功。
    
3. 调用[IMsgStore:: OpenEntry](imsgstore-openentry.md) , 其中包含用于打开它的视图描述符的条目标识符。 
    

