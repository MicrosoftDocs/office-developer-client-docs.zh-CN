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
  
委派访问权限是指用户以其他用户身份发送邮件或为其他用户接收邮件的功能。 代理访问是 MAPI 的一种独立于服务提供程序的功能, 传输提供程序可以在选择时支持这些功能。 但是, 无需提供程序即可执行此操作。 当用户需要向其他用户发送邮件, 或筛选其他用户的传入邮件时, 或者用户必须访问其他用户的邮件存储时, 委派访问非常有用。 在允许代理用户连接到另一个用户的存储之前, 邮件存储提供程序必须验证代理用户是否具有适当的权限。 
  
有两组用于支持代理访问的属性:
  
 **PR_SENT_REPRESENTING_ADDRTYPE**([PidTagSentRepresentingAddressType](pidtagsentrepresentingaddresstype-canonical-property.md)) 
  
 **PR_SENT_REPRESENTING_EMAIL_ADDRESS**([PidTagSentRepresentingEmailAddress](pidtagsentrepresentingemailaddress-canonical-property.md)) 
  
 **PR_SENT_REPRESENTING_ENTRYID**([PidTagSentRepresentingEntryId](pidtagsentrepresentingentryid-canonical-property.md)) 
  
 **PR_SENT_REPRESENTING_NAME**([PidTagSentRepresentingName](pidtagsentrepresentingname-canonical-property.md)) 
  
 **PR_SENT_REPRESENTING_SEARCH_KEY**([PidTagSentRepresentingSearchKey](pidtagsentrepresentingsearchkey-canonical-property.md)) 
  
 **PR_RCVD_REPRESENTING_ADDRTYPE**([PidTagReceivedRepresentingAddressType](pidtagreceivedrepresentingaddresstype-canonical-property.md)) 
  
 **PR_RCVD_REPRESENTING_EMAIL_ADDRESS**([PidTagReceivedRepresentingEmailAddress](pidtagreceivedrepresentingemailaddress-canonical-property.md)) 
  
 **PR_RCVD_REPRESENTING_ENTRYID**([PidTagReceivedRepresentingEntryId](pidtagreceivedrepresentingentryid-canonical-property.md)) 
  
 **PR_RCVD_REPRESENTING_NAME**([PidTagReceivedRepresentingName](pidtagreceivedrepresentingname-canonical-property.md)) 
  
 **PR_RCVD_REPRESENTING_SEARCH_KEY**([PidTagReceivedRepresentingSearchKey](pidtagreceivedrepresentingsearchkey-canonical-property.md)) 
  
在传出邮件上, **PR_SENT_REPRESENTING**属性标识应充当发件人的邮件用户。 客户端可以将这些属性设置为选项。 如果邮件到达支持代理访问的传输提供程序时未设置**PR_SENT_REPRESENTING**属性, 则提供程序负责将它们设置为与**PR_SENDER**属性一起使用。 
  
在传入邮件中, **PR_RCVD_REPRESENTING**属性标识应充当收件人的用户。 负责传递委派邮件的传输提供程序必须同时设置**PR_RCVD_REPRESENTING**和**PR_RECEIVED_BY**属性。 接收代理消息的客户端应将**PR_SENT_REPRESENTING**属性的值复制到相应的**PR_RCVD_REPRESENTING**属性中。 
  
例如, 假设 John 在 Sally 休假时收到 Sally 的邮件。 **PR_RCVD_REPRESENTING**属性将 John 标识为代理收件人。 当 John 将答复发送给他收到的 Sally 邮件时, 邮件的**PR_SENDER**属性会将 John 标识为发件人。 因为 John 代表 Sally, 所以**PR_SENT_REPRESENTING**属性标识 Sally。 
  
处理传入代理邮件的传输提供程序通常应以**PR_SENT_REPRESENTING**属性 (而不是由**PR_SENDER**属性标识的用户) 标识的邮件用户的形式传递这些邮件。 此规则的例外是在需要匹配访问权限和传输类型时。 在这种情况下, 传输提供程序可以选择发送标识。 
  
如果**PR_SENT_REPRESENTING**属性不可用于传入代理邮件, 则传输提供程序处理传递必须使用相应的**PR_SENDER**属性的值进行设置。 如果**PR_SENT_REPRESENTING**属性可用, 但传输提供程序不支持代理访问, 则可以使用**PR_SENDER**属性进行传递。 
  

