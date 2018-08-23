---
title: 发送的邮件传输提供程序任务
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: bd722f48-b166-4670-8dba-897ac50caf37
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 2c1f73ab263e5851c78b33b6157d6d44c9e5e404
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22586226"
---
# <a name="sending-messages-transport-provider-tasks"></a>发送邮件：传输提供程序任务

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
 **若要传输一条消息，传输提供程序**
  
- 传输提供程序已发送邮件或试图发送消息后，请将消息的**PR_RESPONSIBILITY** ([PidTagResponsibility](pidtagresponsibility-canonical-property.md)) 属性设置为 TRUE。 如果发送一条消息的尝试失败，传输提供程序应调用[IMAPISupport::StatusRecips](imapisupport-statusrecips.md)生成原件报告。 如果成功发送邮件的**邮件已被阅读**([PidTagOriginatorDeliveryReportRequested](pidtagoriginatordeliveryreportrequested-canonical-property.md)) 属性设置为 TRUE，则创建包含成功的收件人， [ADRLIST](adrlist.md)结构对于每个，设置**PR_DELIVER_TIME** ([PidTagDeliverTime](pidtagdelivertime-canonical-property.md)) 属性并调用**StatusRecips**生成的送达报告。 有关创建送达和未送达报告的详细信息，请参阅下列主题： [MAPI 报告邮件](mapi-report-messages.md)、[所需的报告邮件属性](required-report-message-properties.md)、[可选报告的邮件属性](optional-report-message-properties.md)和[发送邮件传递报告](sending-message-delivery-reports.md)。
    
- 将消息的**PR_SENDER**组属性设置为已登录用户的标识。 此组包括： **PR_SENDER_ENTRYID** ([PidTagSenderEntryId](pidtagsenderentryid-canonical-property.md))、 **PR_SENDER_NAME** ([PidTagSenderName](pidtagsendername-canonical-property.md))、 **PR_SENDER_SEARCH_KEY** ([PidTagSenderSearchKey](pidtagsendersearchkey-canonical-property.md))、 **PR_SENDER_ADDRTYPE** ([PidTagSenderAddressType](pidtagsenderaddresstype-canonical-property.md))，并**PR_SENDER_EMAIL_ADDRESS** ([PidTagSenderEmailAddress](pidtagsenderemailaddress-canonical-property.md))。
    
- 将设置该消息的**PR_SENT_REPRESENTING**属性，如果可能的用户的登录标识或有效委托标识。 **PR_SENT_REPRESENTING**属性用于实现消息的发送一个用户代表另一个用户。 传输提供程序不支持这些属性应忽略这些对出站邮件。 
    
- 设置消息的**期限**([PidTagClientSubmitTime](pidtagclientsubmittime-canonical-property.md)) 属性来指示客户端时调用[IMessage::SubmitMessage](imessage-submitmessage.md)。
    
- 设置消息的**PR_PROVIDER_SUBMIT_TIME** ([PidTagProviderSubmitTime](pidtagprovidersubmittime-canonical-property.md)) 属性，以指示的日期和时间的消息存储提供程序标记为具有已发送邮件。 
    
当邮件发送给各种使用多种消息系统的收件人时，每个传输的副本将有不同的发件人的标识。 
  
传输提供程序或紧密耦合的消息存储和传输程序还负责设置原始发件人和答复信息。 发起方信息都存储在**PR_ORIGINATOR**属性和答复信息都存储在 PR_REPLY 属性。 客户端可以设置这些属性;但是，允许传输提供程序忽略和覆盖客户端的设置。 
  

