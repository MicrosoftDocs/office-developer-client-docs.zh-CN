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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32338687"
---
# <a name="sending-messages-transport-provider-tasks"></a>发送邮件: 传输提供程序任务

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
 **传输邮件、传输提供程序**
  
- 将邮件的**PR_RESPONSIBILITY** ([PidTagResponsibility](pidtagresponsibility-canonical-property.md)) 属性设置为 TRUE 后, 传输提供程序可以发送邮件或尝试发送邮件。 如果发送邮件的尝试失败, 则传输提供程序应调用[IMAPISupport:: StatusRecips](imapisupport-statusrecips.md)以生成 nondelivery 报告。 如果邮件已成功发送, 并且**PR_ORIGINATOR_DELIVERY_REPORT_REQUESTED** ([PidTagOriginatorDeliveryReportRequested](pidtagoriginatordeliveryreportrequested-canonical-property.md)) 属性设置为 TRUE, 则创建包含成功收件人的[ADRLIST](adrlist.md)结构。设置每个的**PR_DELIVER_TIME** ([PidTagDeliverTime](pidtagdelivertime-canonical-property.md)) 属性, 并调用**StatusRecips**以生成送达报告。 有关创建传递报告和未送达报告的详细信息, 请参阅下列主题: [MAPI 报告邮件](mapi-report-messages.md)、[必需的报告邮件属性](required-report-message-properties.md)、[可选的报告邮件属性](optional-report-message-properties.md)和[发送邮件传递报告](sending-message-delivery-reports.md)。
    
- 将邮件的**PR_SENDER**组属性设置为已登录用户的标识。 此组包括: **PR_SENDER_ENTRYID** ([PidTagSenderEntryId](pidtagsenderentryid-canonical-property.md))、 **PR_SENDER_NAME** ([PidTagSenderName](pidtagsendername-canonical-property.md))、 **PR_SENDER_SEARCH_KEY** ([PidTagSenderSearchKey](pidtagsendersearchkey-canonical-property.md))、 **PR_SENDER_ADDRTYPE** ([PidTagSenderAddressType](pidtagsenderaddresstype-canonical-property.md)) 和**PR_SENDER_EMAIL_ADDRESS** ([PidTagSenderEmailAddress](pidtagsenderemailaddress-canonical-property.md))。
    
- 如果可能, 请将邮件的**PR_SENT_REPRESENTING**属性设置为已登录或有效的代理标识的用户的标识。 **PR_SENT_REPRESENTING**属性用于通过一个用户代表另一个用户实现邮件发送。 不支持这些属性的传输提供程序应在出站邮件上忽略它们。 
    
- 设置邮件的**PR_CLIENT_SUBMIT_TIME** ([PidTagClientSubmitTime](pidtagclientsubmittime-canonical-property.md)) 属性, 以指示客户端何时调用[IMessage:: SubmitMessage](imessage-submitmessage.md)。
    
- 设置邮件的**PR_PROVIDER_SUBMIT_TIME** ([PidTagProviderSubmitTime](pidtagprovidersubmittime-canonical-property.md)) 属性, 以指示邮件存储提供程序将邮件标记为已发送的日期和时间。 
    
将邮件发送到包含多个邮件系统的各种收件人时, 每个传输的副本都将具有不同的发件人标识。 
  
传输提供程序或紧密耦合邮件存储和传输还负责设置原始发件人和回复信息。 发起人信息存储在**PR_ORIGINATOR**属性中, 而回复信息存储在 PR_REPLY 属性中。 客户端可以设置这些属性;但是, 允许传输提供程序忽略并覆盖客户端的设置。 
  

