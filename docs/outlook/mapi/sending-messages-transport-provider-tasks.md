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
ms.openlocfilehash: 4625d9d09b067d064dac7ca67b7c79ebb818bcce
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778743"
---
# <a name="sending-messages-transport-provider-tasks"></a><span data-ttu-id="2b2eb-103">发送邮件：传输提供程序任务</span><span class="sxs-lookup"><span data-stu-id="2b2eb-103">Sending Messages: Transport Provider Tasks</span></span>

  
  
<span data-ttu-id="2b2eb-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="2b2eb-104">**Applies to**: Outlook</span></span> 
  
 <span data-ttu-id="2b2eb-105">**若要传输一条消息，传输提供程序**</span><span class="sxs-lookup"><span data-stu-id="2b2eb-105">**To transmit a message, transport providers**</span></span>
  
- <span data-ttu-id="2b2eb-106">传输提供程序已发送邮件或试图发送消息后，请将消息的**PR_RESPONSIBILITY** ([PidTagResponsibility](pidtagresponsibility-canonical-property.md)) 属性设置为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="2b2eb-106">Set the message's **PR_RESPONSIBILITY** ([PidTagResponsibility](pidtagresponsibility-canonical-property.md)) property to TRUE after the transport provider has either sent the message or attempted to send the message.</span></span> <span data-ttu-id="2b2eb-107">如果发送一条消息的尝试失败，传输提供程序应调用[IMAPISupport::StatusRecips](imapisupport-statusrecips.md)生成原件报告。</span><span class="sxs-lookup"><span data-stu-id="2b2eb-107">If an attempt to send a message fails, transport providers should call [IMAPISupport::StatusRecips](imapisupport-statusrecips.md) to generate a nondelivery report.</span></span> <span data-ttu-id="2b2eb-108">如果成功发送邮件的**邮件已被阅读**([PidTagOriginatorDeliveryReportRequested](pidtagoriginatordeliveryreportrequested-canonical-property.md)) 属性设置为 TRUE，则创建包含成功的收件人， [ADRLIST](adrlist.md)结构对于每个，设置**PR_DELIVER_TIME** ([PidTagDeliverTime](pidtagdelivertime-canonical-property.md)) 属性并调用**StatusRecips**生成的送达报告。</span><span class="sxs-lookup"><span data-stu-id="2b2eb-108">If the message is sent successfully and the **PR_ORIGINATOR_DELIVERY_REPORT_REQUESTED** ([PidTagOriginatorDeliveryReportRequested](pidtagoriginatordeliveryreportrequested-canonical-property.md)) property is set to TRUE, create an [ADRLIST](adrlist.md) structure containing the successful recipients, setting the **PR_DELIVER_TIME** ([PidTagDeliverTime](pidtagdelivertime-canonical-property.md)) property for each, and call **StatusRecips** to generate a delivery report.</span></span> <span data-ttu-id="2b2eb-109">有关创建送达和未送达报告的详细信息，请参阅下列主题： [MAPI 报告邮件](mapi-report-messages.md)、[所需的报告邮件属性](required-report-message-properties.md)、[可选报告的邮件属性](optional-report-message-properties.md)和[发送邮件传递报告](sending-message-delivery-reports.md)。</span><span class="sxs-lookup"><span data-stu-id="2b2eb-109">For more information about creating delivery and non-delivery reports, see the following topics: [MAPI Report Messages](mapi-report-messages.md), [Required Report Message Properties](required-report-message-properties.md), [Optional Report Message Properties](optional-report-message-properties.md), and [Sending Message Delivery Reports](sending-message-delivery-reports.md).</span></span>
    
- <span data-ttu-id="2b2eb-110">将消息的**PR_SENDER**组属性设置为已登录用户的标识。</span><span class="sxs-lookup"><span data-stu-id="2b2eb-110">Set the message's **PR_SENDER** group of properties to the identity of the user that has logged on.</span></span> <span data-ttu-id="2b2eb-111">此组包括： **PR_SENDER_ENTRYID** ([PidTagSenderEntryId](pidtagsenderentryid-canonical-property.md))、 **PR_SENDER_NAME** ([PidTagSenderName](pidtagsendername-canonical-property.md))、 **PR_SENDER_SEARCH_KEY** ([PidTagSenderSearchKey](pidtagsendersearchkey-canonical-property.md))、 **PR_SENDER_ADDRTYPE** ([PidTagSenderAddressType](pidtagsenderaddresstype-canonical-property.md))，并**PR_SENDER_EMAIL_ADDRESS** ([PidTagSenderEmailAddress](pidtagsenderemailaddress-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="2b2eb-111">This group includes: **PR_SENDER_ENTRYID** ([PidTagSenderEntryId](pidtagsenderentryid-canonical-property.md)), **PR_SENDER_NAME** ([PidTagSenderName](pidtagsendername-canonical-property.md)), **PR_SENDER_SEARCH_KEY** ([PidTagSenderSearchKey](pidtagsendersearchkey-canonical-property.md)), **PR_SENDER_ADDRTYPE** ([PidTagSenderAddressType](pidtagsenderaddresstype-canonical-property.md)), and **PR_SENDER_EMAIL_ADDRESS** ([PidTagSenderEmailAddress](pidtagsenderemailaddress-canonical-property.md)).</span></span>
    
- <span data-ttu-id="2b2eb-112">将设置该消息的**PR_SENT_REPRESENTING**属性，如果可能的用户的登录标识或有效委托标识。</span><span class="sxs-lookup"><span data-stu-id="2b2eb-112">Set the message's **PR_SENT_REPRESENTING** properties, if possible, to either the identity of the user that has logged on or to a valid delegate identity.</span></span> <span data-ttu-id="2b2eb-113">**PR_SENT_REPRESENTING**属性用于实现消息的发送一个用户代表另一个用户。</span><span class="sxs-lookup"><span data-stu-id="2b2eb-113">The **PR_SENT_REPRESENTING** properties are used to implement the sending of messages by one user on behalf of another user.</span></span> <span data-ttu-id="2b2eb-114">传输提供程序不支持这些属性应忽略这些对出站邮件。</span><span class="sxs-lookup"><span data-stu-id="2b2eb-114">Transport providers that do not support these properties should ignore them on outbound messages.</span></span> 
    
- <span data-ttu-id="2b2eb-115">设置消息的**期限**([PidTagClientSubmitTime](pidtagclientsubmittime-canonical-property.md)) 属性来指示客户端时调用[IMessage::SubmitMessage](imessage-submitmessage.md)。</span><span class="sxs-lookup"><span data-stu-id="2b2eb-115">Set the message's **PR_CLIENT_SUBMIT_TIME** ([PidTagClientSubmitTime](pidtagclientsubmittime-canonical-property.md)) property to indicate when the client called [IMessage::SubmitMessage](imessage-submitmessage.md).</span></span>
    
- <span data-ttu-id="2b2eb-116">设置消息的**PR_PROVIDER_SUBMIT_TIME** ([PidTagProviderSubmitTime](pidtagprovidersubmittime-canonical-property.md)) 属性，以指示的日期和时间的消息存储提供程序标记为具有已发送邮件。</span><span class="sxs-lookup"><span data-stu-id="2b2eb-116">Set the message's **PR_PROVIDER_SUBMIT_TIME** ([PidTagProviderSubmitTime](pidtagprovidersubmittime-canonical-property.md)) property to indicate the date and time that the message store provider marked the message as having been sent.</span></span> 
    
<span data-ttu-id="2b2eb-117">当邮件发送给各种使用多种消息系统的收件人时，每个传输的副本将有不同的发件人的标识。</span><span class="sxs-lookup"><span data-stu-id="2b2eb-117">When a message is sent to a variety of recipients with several messaging systems, each transmitted copy will have a different sender identity.</span></span> 
  
<span data-ttu-id="2b2eb-118">传输提供程序或紧密耦合的消息存储和传输程序还负责设置原始发件人和答复信息。</span><span class="sxs-lookup"><span data-stu-id="2b2eb-118">The transport provider or tightly coupled message store and transport is also responsible for setting originator and reply-to information.</span></span> <span data-ttu-id="2b2eb-119">发起方信息都存储在**PR_ORIGINATOR**属性和答复信息都存储在 PR_REPLY 属性。</span><span class="sxs-lookup"><span data-stu-id="2b2eb-119">Originator information is stored in the **PR_ORIGINATOR** properties and reply-to information is stored in the PR_REPLY properties.</span></span> <span data-ttu-id="2b2eb-120">客户端可以设置这些属性;但是，允许传输提供程序忽略和覆盖客户端的设置。</span><span class="sxs-lookup"><span data-stu-id="2b2eb-120">The client can set these properties; however, the transport provider is allowed to ignore and overwrite the client's settings.</span></span> 
  

