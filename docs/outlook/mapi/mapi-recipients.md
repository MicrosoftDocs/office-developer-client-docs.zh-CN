---
title: MAPI 收件人
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 88a4360d-6ab8-466e-8ebd-af80227ee00a
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: f83f3f51c8b11aececa31fa277fb799ce1ada512
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776311"
---
# <a name="mapi-recipients"></a>MAPI 收件人

  
  
**适用于**： Outlook 
  
每个邮件传输有一个或多个收件人或一组描述其中是邮件传送的属性。 仅在邮件的上下文中使用的收件人，因为它们被视为一条消息，而不是单独的 MAPI 对象的子对象。 客户端和提供程序处理使用**IMessage**界面的收件人。 有关详细信息，请参阅[IMessage: IMAPIProp](imessageimapiprop.md)。
  
客户端通过其收件人表访问邮件的收件人。 每个邮件有一个收件人的表，包含有关每个收件人的摘要信息。 表中包括的列取决于邮件的状态。 在组合下一条消息时，其收件人可能具有仅三列表中：
  
- 显示名称或**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md))
    
- 收件人类型或**PR_RECIPIENT_TYPE** ([PidTagRecipientType](pidtagrecipienttype-canonical-property.md))
    
- 行标识符或**PR_ROWID** ([PidTagRowid](pidtagrowid-canonical-property.md))
    
邮件已经过名称解析过程后，每个收件人将还具有条目标识符或**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 列。 和收件人的表中的行时已提交邮件，将添加两个多个列：
  
- 地址类型或**PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md))
    
- 传输责任或**PR_RESPONSIBILITY** ([PidTagResponsibility](pidtagresponsibility-canonical-property.md))
    
客户端可以通过调用其**IMessage::GetRecipientTable**方法或其**IMAPIProp::OpenProperty**方法检索邮件的收件人表。 有关详细信息，请参阅[IMessage::GetRecipientTable](imessage-getrecipienttable.md)和[IMAPIProp::OpenProperty](imapiprop-openproperty.md)。 消息存储提供程序需要支持这两种方法。 **OpenProperty**方法要求客户端界面标识符和**PR_MESSAGE_RECIPIENTS**为属性标记为指定 IID_IMAPITable。 **PR_MESSAGE_RECIPIENTS**([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md)) 是一个表示一条消息收件人表的表对象属性。 消息存储提供程序所需设置**PR_MESSAGE_RECIPIENTS**关于每封邮件，并将其加入属性标记从**IMAPIProp::GetPropList**方法返回的数组。 有关详细信息，请参阅[IMAPIProp::GetPropList](imapiprop-getproplist.md)。
  
有关如何使用收件人表的详细信息，请参阅[收件人表](recipient-tables.md)。
  
除了要用于访问收件人表，可使用**PR_MESSAGE_RECIPIENTS** : 
  
- 与**IMAPIProp::CopyTo**或**IMAPIProp::CopyProps**排除或包括收件人复制时。 有关详细信息，请参阅[IMAPIProp::CopyTo](imapiprop-copyto.md)和[IMAPIProp::CopyProps](imapiprop-copyprops.md)。
    
- 在以指示子限制应该将应用于收件人的子对象限制。
    
客户端可以将收件人添加到一条消息，通过复制 MAPI 通讯簿中的条目或创建新条目。 调用 one-offs，这些新条目可以暂时存在，或可修改容器中永久保存。 虽然均摘自通讯簿的收件人有其通讯簿提供程序相关联的条目标识符，一次性收件人有条目标识符格式的 MAPI。 传输提供程序和客户端关联一次性条目标识符与各种类型的地址。 
  
传输提供程序调用**IMAPISupport::CreateOneOff**创建地址一次性条目标识符传出消息时： 
  
- 网关所属的地址。
    
- 地址无法处理的当前配置文件中的地址簿提供程序。
    
有关详细信息，请参阅[IMAPISupport::CreateOneOff](imapisupport-createoneoff.md)。
  
客户端调用**IAddrBook::CreateOneOff**创建地址一次性条目标识符传入邮件时： 
  
- 地址作为一次性地址格式。
    
- 地址的格式设置为 Internet 地址。
    
有关详细信息，请参阅[IAddrBook::CreateOneOff](iaddrbook-createoneoff.md)。
  
有关一次性条目标识符和地址的详细信息，请参阅[一次性条目标识符](one-off-entry-identifiers.md)和[一次性地址](one-off-addresses.md)。
  
收件人的属性为通讯簿属性和属性特定于收件人的组合。 所有收件人都已分配的通讯簿提供程序的基址属性。 当条目用作传出邮件收件人时，基址属性复制到包含属性的所有邮件的收件人的**ADRLIST**结构。 
  
专门为收件人的两个属性是**PR_RECIPIENT_TYPE**和**PR_RESPONSIBILITY**。 **PR_RECIPIENT_TYPE**指示收件人是主、 抄送、 密件抄送副本或重新发送收件人。 前三种类型会分配到的第一次发送邮件的收件人。 
  
如果收件人不会收到邮件，并尝试重新发送它，复制收件人，并且其类型设置为 MAPI_P1，以指示它是重新发送收件人。 如果只有某些收件人收到一条消息，及其**PR_RECIPIENT_TYPE**属性标记并添加了 MAPI_SUBMITTED 标志时重新发送邮件。 客户端需要处理主收件人，或使用其**PR_RECIPIENT_TYPE**收件人为 MAPI_TO。 所有其他类型是可选的。 
  
 **PR_RESPONSIBILITY**设置以指示到传输提供程序它应处理发送给收件人。 首先发送传出邮件时, 的所有收件人将**PR_RESPONSIBILITY**设置为 FALSE。 传输提供程序声明责任发送到一个或多个收件人，及其**PR_RESPONSIBILITY**属性都设置为 TRUE。 
  

