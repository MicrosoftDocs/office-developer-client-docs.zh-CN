---
title: 表类型
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: a1fc4f20-511f-4721-8f09-ec2a5fd0ccb0
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 36456c6226b2eb74b8f15995ad0925381302523a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779014"
---
# <a name="types-of-tables"></a>表类型

  
  
**适用于**： Outlook 
  
有许多不同类型的表，它提供的信息差分每种类型。 表允许客户端应用程序和服务提供商来轻松访问和处理许多类型的对象的重要属性。 
  
某些表格中的，如内容表提供了访问属性的替代方式。 例如，客户端可以检索邮件的主题 — 其**PR_SUBJECT** ([PidTagSubject](pidtagsubject-canonical-property.md)) 属性 — 直接来自邮件通过调用其[IMAPIProp::GetProps](imapiprop-getprops.md)方法或通过消息的内容表。 其他表提供的唯一方式访问对象属性。 例如，客户端无法访问的附件**PR_ATTACH_METHOD** ([PidTagAttachMethod](pidtagattachmethod-canonical-property.md)) 属性，通过调用**IMAPIProp::GetProps**;它必须始终检索附加到邮件的附件表。 **PR_ATTACH_METHOD**是所有附件表中所需的列。 
  
静态或动态，可以是在表视图。 具有静态表视图，对基础数据的更改不会导致要更新的视图。 一旦已被实例化视图，它不会更改。 可以通过表通知的数据更改的通知的静态表的用户。 对数据进行更改时，将更新动态表视图。 有两种类型的动态表： 一个更新的列的每个行，而行保持静态和更新的列和行的一个。 此后一种类型的表始终准确反映基础数据。
  
表具有设置，客户端或服务提供程序可能会看到已经不尚未受到[IMAPITable::SetColumns](imapitable-setcolumns.md)表中的检索行调用时的列的最小集合的默认列。 客户端和服务提供商可以将列添加到或通过调用**SetColumns**方法设置此默认中移除列。 可以更改静态或动态，以下客户端请求。 并非所有表都支持动态列集修改。 
  
MAPI 表格及其实施和用户是：
  
|**Table**|**实现方注释**|
|:-----|:-----|
|附件  <br/> |由消息存储提供程序实现。 使用客户端和传输提供程序。  <br/> |
|内容  <br/> |实现通过消息存储和通讯簿提供程序。 由客户端。  <br/> |
|显示  <br/> |通过 MAPI 实现和服务提供商。 使用 MAPI 和服务提供商。  <br/> |
|层次结构  <br/> |实现通过消息存储和通讯簿提供程序。 由客户端。  <br/> |
|邮件服务  <br/> |由 MAPI 实现。 由客户端。  <br/> |
|消息存储库  <br/> |由 MAPI 实现。 由客户端。  <br/> |
|一次性  <br/> |由通讯簿提供程序实现。 使用 MAPI。  <br/> |
|传出队列  <br/> |由消息存储提供程序实现。 使用 MAPI 后台处理程序。  <br/> |
|配置文件  <br/> |由 MAPI 实现。 由客户端。  <br/> |
|提供程序  <br/> |由 MAPI 实现。 由客户端。  <br/> |
|接收文件夹  <br/> |由消息存储提供程序实现。 由客户端。  <br/> |
|Recipient  <br/> |由消息存储提供程序实现。 使用客户端和传输提供程序。  <br/> |
|Status  <br/> |通过 MAPI 实现和服务提供商。 由客户端。  <br/> |
   
## <a name="see-also"></a>另请参阅



[MAPI 表](mapi-tables.md)

