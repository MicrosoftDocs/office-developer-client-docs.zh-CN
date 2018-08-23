---
title: 支持邮件存储区中的命名属性
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: a1c73bb5-b44a-4ec6-89e4-0e2228572b2d
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 235683d8565732034f868dd71e4f2047ffe76f09
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22569839"
---
# <a name="supporting-named-properties-in-message-stores"></a>支持邮件存储区中的命名属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
消息对象可在其集合中的定义的 MAPI 属性不具有属性。 此类属性可未命名的或名为。 未命名的属性必须驻留在范围定义的 MAPI 属性标识符。 命名自定义属性位于不同范围的定义的 MAPI 属性标识符。 他们通常使用自定义消息类型。 消息存储提供程序必须支持命名的属性，它是否要用作默认邮件存储区。 支持命名属性是指实现[IMAPIProp::GetNamesFromIDs](imapiprop-getnamesfromids.md)和[IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md)方法和实现确定哪些名称的一个或多个映射签名转与哪些属性标识符。 有关详细信息，请参阅[定义新的 MAPI 属性](defining-new-mapi-properties.md)和[支持命名属性](supporting-named-properties.md)。
  
大多数消息存储提供程序支持的名为属性使用的单个映射签名的消息存储区中的所有对象。 这有两个好处。 首先，它是实现映射签名，如果只有一个以跟踪变得简单。 其次，如果邮件存储区中的所有对象都使用相同的映射签名，客户端应用程序并能保证邮件存储区中的邮件的所有属性标识符实际都引用相同的命名属性。 这样，客户端应用程序在其文件夹视图界面中显示的命名属性的列。
  
## <a name="see-also"></a>另请参阅



[实现邮件存储区中的邮件](implementing-messages-in-message-stores.md)

