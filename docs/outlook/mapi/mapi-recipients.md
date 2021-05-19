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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33423690"
---
# <a name="mapi-recipients"></a>MAPI 收件人

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
要传输的每封邮件都有一个或多个收件人，或者有一组描述邮件传递位置的属性。 由于收件人仅在邮件上下文中使用，因此被视为邮件的子对象，而不是单独的 MAPI 对象。 客户端和提供程序使用 **IMessage** 接口与收件人一起工作。 有关详细信息，请参阅 [IMessage ： IMAPIProp](imessageimapiprop.md)。
  
客户端通过其收件人表访问邮件的收件人。 每封邮件都有一个收件人表，其中包含有关其每个收件人的摘要信息。 表中包含的列取决于邮件的状态。 当邮件在撰写下时，其收件人可能只有三列：
  
- 显示名称，或 **PR_DISPLAY_NAME (** [PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 
    
- 收件人 **类型，PR_RECIPIENT_TYPE (** [PidTagRecipientType](pidtagrecipienttype-canonical-property.md)) 
    
- 行标识符或 **PR_ROWID (** [PidTagRowid](pidtagrowid-canonical-property.md)) 
    
邮件完成名称解析过程后，每个收件人也将具有条目标识符，PR_ENTRYID ([PidTagEntryId](pidtagentryid-canonical-property.md)) 列。  提交邮件后，收件人表中的行将再添加两列：
  
- 地址类型，或 **PR_ADDRTYPE (** [PidTagAddressType](pidtagaddresstype-canonical-property.md)) 
    
- 传输责任或 **PR_RESPONSIBILITY (** [PidTagResponsibility)](pidtagresponsibility-canonical-property.md)
    
客户端可以通过调用邮件的 **IMessage：：GetRecipientTable** 方法或 **IMAPIProp：：OpenProperty** 方法检索邮件的收件人表。 有关详细信息，请参阅 [IMessage：：GetRecipientTable](imessage-getrecipienttable.md) 和 [IMAPIProp：：OpenProperty](imapiprop-openproperty.md)。 邮件存储提供程序应支持这两种方法。 **OpenProperty** 方法要求客户端将 IID_IMAPITable 指定为接口标识符，PR_MESSAGE_RECIPIENTS **属性标记**。 **PR_MESSAGE_RECIPIENTS (** [PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md)) 是表示邮件的收件人表的 table 对象属性。 邮件存储提供程序需要为PR_MESSAGE_RECIPIENTS设置值，并包括到 **从 IMAPIProp：：GetPropList** 方法返回的属性标记数组中。 有关详细信息，请参阅 [IMAPIProp：：GetPropList](imapiprop-getproplist.md)。
  
有关如何使用收件人表的信息，请参阅 [收件人表](recipient-tables.md)。
  
除了用于访问收件人表之外，PR_MESSAGE_RECIPIENTS **可以使用：** 
  
- 使用 **IMAPIProp：：CopyTo** 或 **IMAPIProp：：CopyProps** 在复制时排除或包括收件人。 有关详细信息，请参阅 [IMAPIProp：：CopyTo](imapiprop-copyto.md) 和 [IMAPIProp：：CopyProps](imapiprop-copyprops.md)。
    
- 在子对象限制中，指示子对象应应用于收件人。
    
客户端可以通过复制 MAPI 通讯簿中的条目或创建新条目将收件人添加到邮件。 这些新条目称为一次使用，可以暂时存在或永久保存在可修改的容器中。 从通讯簿获取的收件人具有与其通讯簿提供程序关联的条目标识符，而一次收件人具有 MAPI 格式的条目标识符。 传输提供程序和客户端将一次输入标识符与各种类型的地址关联。 
  
传输提供程序调用 **IMAPISupport：：CreateOneOff** 为传出邮件上的地址创建一次条目标识符，当： 
  
- 该地址属于网关。
    
- 地址不能由当前配置文件中的通讯簿提供程序处理。
    
有关详细信息，请参阅 [IMAPISupport：：CreateOneOff](imapisupport-createoneoff.md)。
  
客户端调用 **IAddrBook：：CreateOneOff** 为传入邮件上的地址创建一次条目标识符，当： 
  
- 该地址的格式设置为一次地址。
    
- 地址的格式设置为 Internet 地址。
    
有关详细信息，请参阅 [IAddrBook：：CreateOneOff](iaddrbook-createoneoff.md)。
  
有关一对一条目标识符和地址的信息，请参阅 [一次使用](one-off-entry-identifiers.md) 条目标识符和 [一次使用地址](one-off-addresses.md)。
  
收件人的属性是通讯簿属性和特定于收件人的属性的组合。 所有收件人都有基本地址属性，由通讯簿提供程序分配。 当条目用作传出邮件的收件人时，基地址属性将复制到 **ADRLIST** 结构，该结构保留邮件的所有收件人的属性。 
  
专为收件人设置的两个属性是 PR_RECIPIENT_TYPE **和****PR_RESPONSIBILITY**。 **PR_RECIPIENT_TYPE** 指示收件人是主要收件人、抄件抄稿人、盲信副本收件人还是重新发送收件人。 前三种类型分配给第一次发送的邮件上的收件人。 
  
如果收件人未收到邮件，并尝试重新发送邮件，将复制该收件人，并且其类型设置为 MAPI_P1 以指示它是重新发送的收件人。 如果只有部分收件人收到邮件，则 **PR_RECIPIENT_TYPE重新发送邮件** 时，会标记其 MAPI_SUBMITTED 属性。 客户端需要处理主要收件人，或将收件人的收件人 **PR_RECIPIENT_TYPE设置为** MAPI_TO。 所有其他类型都是可选的。 
  
 **PR_RESPONSIBILITY** 设置为向传输提供程序指示它是否应该处理发送给收件人的发送。 首次发送传出邮件时，所有收件人 **PR_RESPONSIBILITY设置为** FALSE。 作为传输提供程序声明向一个或多个收件人发送负责，其 **PR_RESPONSIBILITY属性设置为** TRUE。 
  

