---
title: 委派访问
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: a863494f-0071-4d97-a6c4-26707ee00e04
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 3d6a0eaf8ad125a0ae1ea3abb57e2aa57e0bdfe3
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33427260"
---
# <a name="delegate-access"></a>委派访问

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
委派访问是指用户以其他用户发送消息或接收其他用户的邮件的能力。 委派访问是 MAPI 的独立于服务提供商的功能，传输提供程序可以选择此功能时可支持此功能。 但是，不需要提供程序来这样做。 在用户有必要将传入邮件作为其他用户发送邮件或筛选其传入邮件时，或者当用户必须访问其他用户的邮件存储时，委派访问将十分有价值。 在允许代理用户连接到其他用户的存储区之前，邮件存储提供程序必须验证委派用户是否具有适当的权限。 
  
有两组属性用于支持委派访问：
  
 **PR_SENT_REPRESENTING_ADDRTYPE (** [PidTagSentRepresentingAddressType](pidtagsentrepresentingaddresstype-canonical-property.md))  
  
 **PR_SENT_REPRESENTING_EMAIL_ADDRESS (** [PidTagSentRepresentingEmailAddress](pidtagsentrepresentingemailaddress-canonical-property.md))  
  
 **PR_SENT_REPRESENTING_ENTRYID (** [PidTagSentRepresentingEntryId)](pidtagsentrepresentingentryid-canonical-property.md) 
  
 **PR_SENT_REPRESENTING_NAME (** [PidTagSentRepresentingName)](pidtagsentrepresentingname-canonical-property.md) 
  
 **PR_SENT_REPRESENTING_SEARCH_KEY (** [PidTagSentRepresentingSearchKey](pidtagsentrepresentingsearchkey-canonical-property.md))  
  
 **PR_RCVD_REPRESENTING_ADDRTYPE (** [PidTagReceivedRepresentingAddressType](pidtagreceivedrepresentingaddresstype-canonical-property.md))  
  
 **PR_RCVD_REPRESENTING_EMAIL_ADDRESS (** [PidTagReceivedRepresentingEmailAddress](pidtagreceivedrepresentingemailaddress-canonical-property.md))  
  
 **PR_RCVD_REPRESENTING_ENTRYID (** [PidTagReceivedRepresentingEntryId)](pidtagreceivedrepresentingentryid-canonical-property.md) 
  
 **PR_RCVD_REPRESENTING_NAME (** [PidTagReceivedRepresentingName](pidtagreceivedrepresentingname-canonical-property.md))  
  
 **PR_RCVD_REPRESENTING_SEARCH_KEY (** [PidTagReceivedRepresentingSearchKey](pidtagreceivedrepresentingsearchkey-canonical-property.md))  
  
对于传出邮件 **，PR_SENT_REPRESENTING** 属性标识应充当发件人的邮件用户。 客户端可以将这些属性设置为选项。 如果 **PR_SENT_REPRESENTING** 到达支持委派访问的传输提供程序时未设置属性，则提供程序负责将它们与 PR_SENDER **属性一** 起设置。 
  
对于传入的邮件 **，PR_RCVD_REPRESENTING** 属性标识应充当收件人的用户。 负责传递委派邮件的传输提供程序必须同时设置 PR_RCVD_REPRESENTING **和****PR_RECEIVED_BY** 属性。 接收代理邮件的客户端应该将 PR_SENT_REPRESENTING **属性的值复制到****相应的** PR_RCVD_REPRESENTING 属性。 
  
例如，假设 John 在 Sally 休假期间收到 Sally 的邮件。 The **PR_RCVD_REPRESENTING** properties identify John as the delegate recipient. 当 John 发送对 Sally 收到的邮件的答复时，该邮件 **PR_SENDER属性将** John 标识为发件人。 由于 John 表示 Sally，因此 **PR_SENT_REPRESENTING标识** Sally。 
  
处理传入委派邮件的传输提供程序通常应该将这些邮件作为 PR_SENT_REPRESENTING **属性标识** 的邮件用户而不是由 PR_SENDER **属性标识** 的用户传递。 此规则的例外情况是，需要匹配访问特权和传输类型。 在这种情况下，传输提供程序可以选择发送标识。 
  
如果 **PR_SENT_REPRESENTING** 属性对传入的委派邮件不可用，则处理传递的传输提供程序必须使用相应的 PR_SENDER **属性的值进行** 设置。 如果 **PR_SENT_REPRESENTING** 属性可用，但传输提供程序不支持委派访问，则传输提供程序可以使用 PR_SENDER **属性进行** 传递。 
  

