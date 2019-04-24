---
title: MAPI 收件人
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 88a4360d-6ab8-466e-8ebd-af80227ee00a
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: ebdaf47b4f20763574ffac73bddeb3eb4eeb95df
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32328215"
---
# <a name="mapi-recipients"></a>MAPI 收件人

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
要传输的每封邮件都有一个或多个收件人, 或一组描述邮件传递位置的属性。 由于收件人仅在邮件上下文中使用, 因此它们被视为邮件的子对象, 而不是单独的 MAPI 对象。 客户端和提供程序使用**IMessage**接口处理收件人。 有关详细信息, 请参阅[IMessage: IMAPIProp](imessageimapiprop.md)。
  
客户端通过其收件人表访问邮件的收件人。 每封邮件都有一个 "收件人" 表, 其中包含有关每个收件人的摘要信息。 表中包含的列取决于邮件的状态。 当邮件位于撰写过程中时, 其收件人在表格中可能只有三列:
  
- 显示名称或**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md))
    
- 收件人类型或**PR_RECIPIENT_TYPE** ([PidTagRecipientType](pidtagrecipienttype-canonical-property.md))
    
- 行标识符或**PR_ROWID** ([PidTagRowid](pidtagrowid-canonical-property.md))
    
在邮件完成名称解析过程后, 每个收件人也将具有条目标识符或**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 列。 如果邮件已提交, 则收件人表中的行将再添加两列:
  
- 地址类型或**PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md))
    
- 传输责任或**PR_RESPONSIBILITY** ([PidTagResponsibility](pidtagresponsibility-canonical-property.md))
    
客户端可以通过调用其**IMessage:: GetRecipientTable**方法或其**IMAPIProp:: OpenProperty**方法来检索邮件的收件人表。 有关详细信息, 请参阅[IMessage:: GetRecipientTable](imessage-getrecipienttable.md)和[IMAPIProp:: OpenProperty](imapiprop-openproperty.md)。 邮件存储提供程序应支持这两种方法。 **OpenProperty**方法要求客户端将 IID_IMAPITable 指定为接口标识符, 并将**PR_MESSAGE_RECIPIENTS**指定为属性标记。 **PR_MESSAGE_RECIPIENTS**([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md)) 是一个表示邮件的收件人表的 table 对象属性。 邮件存储提供程序需要设置每个邮件的**PR_MESSAGE_RECIPIENTS** , 并将其包含在从**IMAPIProp:: GetPropList**方法返回的属性标记数组中。 有关详细信息, 请参阅[IMAPIProp:: GetPropList](imapiprop-getproplist.md)。
  
有关如何使用收件人表的详细信息, 请参阅[收件人表](recipient-tables.md)。
  
除了用于访问收件人表之外, 还可以使用**PR_MESSAGE_RECIPIENTS** : 
  
- 使用**IMAPIProp:: CopyTo**或**IMAPIProp:: CopyProps**在复制时排除或包含收件人。 有关详细信息, 请参阅[IMAPIProp:: CopyTo](imapiprop-copyto.md) and [IMAPIProp:: CopyProps](imapiprop-copyprops.md)。
    
- 在子元素限制中, 指示子 restiction 应应用于收件人。
    
客户端可以通过从 MAPI 通讯簿或创建新条目来复制条目, 从而将收件人添加到邮件中。 这些新条目称为 "一次性", 它们可以临时存在, 也可以永久保存在可修改的容器中。 从通讯簿获取的收件人具有与其通讯簿提供程序关联的条目标识符, 而一次性收件人具有由 MAPI 格式化的条目标识符。 传输提供程序和客户端将一次性条目标识符与各种类型的地址关联。 
  
传输提供程序调用**IMAPISupport:: CreateOneOff**在以下情况时为传出邮件上的地址创建一次性条目标识符: 
  
- 地址属于网关。
    
- 地址不能由当前配置文件中的通讯簿提供程序处理。
    
有关详细信息, 请参阅[IMAPISupport:: CreateOneOff](imapisupport-createoneoff.md)。
  
客户端在以下情况调用**IAddrBook:: CreateOneOff**为传入邮件上的地址创建一次性条目标识符: 
  
- 该地址的格式为一次性地址。
    
- 将地址格式化为 Internet 地址。
    
有关详细信息, 请参阅[IAddrBook:: CreateOneOff](iaddrbook-createoneoff.md)。
  
有关一次性条目标识符和地址的详细信息, 请参阅[一次性条目标识符](one-off-entry-identifiers.md)和[一次性地址](one-off-addresses.md)。
  
收件人的属性是特定于收件人的通讯簿属性和属性的组合。 所有收件人都具有由通讯簿提供程序分配的基本地址属性。 当某个条目用作传出邮件的收件人时, 基本地址属性将被复制到包含所有邮件收件人的属性的**ADRLIST**结构中。 
  
为收件人专门设置的两个属性是**PR_RECIPIENT_TYPE**和**PR_RESPONSIBILITY**。 **PR_RECIPIENT_TYPE**指示收件人是否为主、抄送、密件抄送或重新发送收件人。 前三种类型分配给邮件上第一次发送的邮件的收件人。 
  
如果收件人没有收到邮件, 并且尝试重新发送该邮件, 则会复制该收件人, 并将其类型设置为 MAPI_P1, 以指示它是重发收件人。 如果只有部分收件人收到邮件, 则在重新发送邮件时, 会将其**PR_RECIPIENT_TYPE**属性标记为添加了 MAPI_SUBMITTED 标志。 客户端需要处理主收件人或其**PR_RECIPIENT_TYPE**设置为 MAPI_TO 的收件人。 所有其他类型都是可选的。 
  
 **PR_RESPONSIBILITY**设置为传输提供程序指明它是否应处理发送给收件人的情况。 首次发送传出邮件时, 所有收件人将**PR_RESPONSIBILITY**设置为 FALSE。 作为传输提供程序声明发送给一个或多个收件人的责任, 其**PR_RESPONSIBILITY**属性设置为 TRUE。 
  

