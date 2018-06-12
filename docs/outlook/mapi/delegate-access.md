---
title: 委派访问
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: a863494f-0071-4d97-a6c4-26707ee00e04
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: d969fd806e5038e6c918da45041402a981554a49
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774772"
---
# <a name="delegate-access"></a>委派访问

  
  
**适用于**： Outlook 
  
委派访问指作为其他用户发送一条消息，或收到另一个用户的邮件用户的功能。 代理访问是如果他们的选择，可支持传输提供程序的 MAPI 服务提供程序无关功能。 但是，没有提供程序需要这样做。 如有必要，用户可以发送邮件作为，或筛选传入消息的另一个用户或用户时必须访问另一个用户的消息存储库时，可以有价值代理访问。 允许委派用户连接到另一个用户存储区之前, 的消息存储提供程序必须验证的代理用户具有适当的权限。 
  
有两组用于支持代理访问的属性：
  
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
  
对传出邮件**PR_SENT_REPRESENTING**属性确定应作为发件人的邮件用户。 客户端可以作为选项来设置这些属性。 如果**PR_SENT_REPRESENTING**属性设置不按时间消息到达传输提供程序的支持代理访问，则提供程序负责将它们设置以及**PR_SENDER**属性。 
  
对传入邮件**PR_RCVD_REPRESENTING**属性标识的用户的应作为收件人。 传输提供程序负责委托邮件传递必须设置的**PR_RCVD_REPRESENTING**和**PR_RECEIVED_BY**属性。 客户端接收委托邮件应将**PR_SENT_REPRESENTING**属性的值复制到相应的**PR_RCVD_REPRESENTING**属性。 
  
例如，假设 John Sally 度假时接收 Sally 的邮件。 **PR_RCVD_REPRESENTING**属性标识为委托收件人 John。 当 John 的 Sally 发送答复他已收到一条消息时，该消息的**PR_SENDER**属性标识发件人为 John。 John 代表 Sally，因为**PR_SENT_REPRESENTING**属性确定 Sally。 
  
传输提供程序处理传入委托消息通常应为标识**PR_SENT_REPRESENTING**属性并由它们的邮件用户而不是由**PR_SENDER**属性标识的用户提供这些消息。 如有必要，以匹配访问权限和传输类型时，此规则的例外。 在这种情况下，传输提供程序可以选择发送的标识。 
  
如果为传入委托消息**PR_SENT_REPRESENTING**属性不可用，处理传递传输提供程序必须设置，使用相应的**PR_SENDER**属性的值。 如果**PR_SENT_REPRESENTING**属性均可用，但传输提供程序不支持代理访问，它可以传递使用**PR_SENDER**属性。 
  

