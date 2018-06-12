---
title: 打开视图描述符
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 1940feb0-9e0f-4d96-9fb9-b9a35a0aa661
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 525c817cfc3bdcf96455d35025e85486ec8b5b42
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776551"
---
# <a name="opening-a-view-descriptor"></a>打开视图描述符
  
**适用于**： Outlook 
  
很多文件夹可以打开与普通视图、 默认视图或任意数量的个性化视图。 视图介绍如何显示文件夹的内容。 普通视图时没有替代视图和首次打开文件夹时使用。 存在另一个视图，必须使用它以打开文件夹。
  
视图所述称为视图描述符一条消息。 视图描述符通常创建作为相关联的邮件，并可以显示在公共或个人视图文件夹或任何 IPM 文件夹中。
  
### <a name="to-open-a-view-descriptor"></a>要打开视图描述符
  
1. 调用[IMAPIContainer::GetContentsTable](imapicontainer-getcontentstable.md)用于检索文件夹关联的内容表。 
    
2. 创建与供视图描述符邮件类的定位仅邮件限制和呼叫[IMAPITable::Restrict](imapitable-restrict.md)限制表和[IMAPITable::QueryRows](imapitable-queryrows.md)检索合适的行，或...
    
   调用该文件夹的[IMAPIProp::GetProps](imapiprop-getprops.md)方法来检索其**PR_DEFAULT_VIEW_ENTRYID** ([PidTagDefaultViewEntryId](pidtagdefaultviewentryid-canonical-property.md)) 属性。 **PR_DEFAULT_VIEW_ENTRYID**包含包含的文件夹的默认视图描述符的消息的项标识符。 如果文件夹上调用[IMAPIFolder::CreateMessage](imapifolder-createmessage.md)和[IMAPIContainer::GetContentsTable](imapicontainer-getcontentstable.md)支持 MAPI_ASSOCIATED 标志的使用，将会成功此呼叫。
    
3. 调用[IMsgStore::OpenEntry](imsgstore-openentry.md)视图描述符，以将其打开的项标识符。 
    

