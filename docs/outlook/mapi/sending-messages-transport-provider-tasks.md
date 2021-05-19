---
title: 发送邮件传输提供程序任务
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: bd722f48-b166-4670-8dba-897ac50caf37
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 431e3d2f66616db2c586b76387a8521832ed985f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33426546"
---
# <a name="sending-messages-transport-provider-tasks"></a>发送邮件：传输提供程序任务

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
 **传输邮件时，传输提供程序**
  
- 在传输提供程序已发送邮件或尝试 **发送邮件** PR_RESPONSIBILITY ([PidTagResponsibility](pidtagresponsibility-canonical-property.md)) 属性将邮件的收件人设置为 TRUE。 如果发送邮件的尝试失败，传输提供程序应调用 [IMAPISupport：：StatusRecips](imapisupport-statusrecips.md) 以生成未送达报告。 如果邮件成功发送 **，PR_ORIGINATOR_DELIVERY_REPORT_REQUESTED** ([PidTagOriginatorDeliveryReportRequested](pidtagoriginatordeliveryreportrequested-canonical-property.md)) 属性设置为 TRUE，请创建包含成功收件人的 [ADRLIST](adrlist.md) 结构，为每个收件人设置 **PR_DELIVER_TIME** ([PidTagDeliverTime](pidtagdelivertime-canonical-property.md)) 属性，并调用 **StatusRecips** 生成送达报告。 有关创建送达报告和未送达报告的信息，请参阅下列主题[：MAPI 报告](mapi-report-messages.md)邮件、必需报告邮件[](required-report-message-properties.md)属性、[可选](optional-report-message-properties.md)报告邮件属性和发送[邮件送达报告](sending-message-delivery-reports.md)。
    
- 将邮件的 **PR_SENDER** 组属性设置为已登录用户的标识。 此组包括 **：PR_SENDER_ENTRYID (** [PidTagSenderEntryId](pidtagsenderentryid-canonical-property.md)) 、 **PR_SENDER_NAME (** [PidTagSenderName](pidtagsendername-canonical-property.md)) 、PR_SENDER_SEARCH_KEY ([PidTagSenderSearchKey](pidtagsendersearchkey-canonical-property.md)  **) 、PR_SENDER_ADDRTYPE** ([PidTagSenderAddressType](pidtagsenderaddresstype-canonical-property.md)) 和 **PR_SENDER_EMAIL_ADDRESS** ([PidTagSenderEmailAddress](pidtagsenderemailaddress-canonical-property.md)) 。
    
- 将邮件的 **PR_SENT_REPRESENTING** 属性设置为已登录的用户的标识或有效的委派标识。 PR_SENT_REPRESENTING **属性** 用于实现由一个用户代表另一个用户发送邮件。 不支持这些属性的传输提供程序应在出站邮件上忽略它们。 
    
- 设置邮件的 **PR_CLIENT_SUBMIT_TIME** ([PidTagClientSubmitTime](pidtagclientsubmittime-canonical-property.md)) 属性以指示客户端何时调用 [IMessage：：SubmitMessage](imessage-submitmessage.md)。
    
- 将邮件的 PR_PROVIDER_SUBMIT_TIME ([PidTagProviderSubmitTime](pidtagprovidersubmittime-canonical-property.md)) 属性，以指示邮件存储提供程序将邮件标记为已发送的日期和时间。  
    
当邮件发送到具有多个邮件系统的各种收件人时，每个传输的副本将具有不同的发件人标识。 
  
传输提供程序或紧密耦合的邮件存储和传输还负责设置发起方和答复信息。 原始用户信息存储在 **PR_ORIGINATOR属性中** ，答复信息存储在PR_REPLY属性中。 客户端可以设置这些属性;但是，允许传输提供程序忽略并覆盖客户端的设置。 
  

