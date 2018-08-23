---
title: 使用 TNEF 发送邮件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 6e2df265-b9dd-4e19-8ca5-3e31804e9120
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 9de158e2f269c7b000734beb93b26df195255bcf
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22592281"
---
# <a name="sending-messages-with-tnef"></a><span data-ttu-id="4c4df-103">使用 TNEF 发送邮件</span><span class="sxs-lookup"><span data-stu-id="4c4df-103">Sending Messages with TNEF</span></span>

  
  
<span data-ttu-id="4c4df-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="4c4df-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="4c4df-105">许多传输提供程序自动发送所有传出邮件使用传输中性封装格式 (TNEF)。</span><span class="sxs-lookup"><span data-stu-id="4c4df-105">Many transport providers automatically send all outgoing messages with the Transport Neutral Encapsulation Format (TNEF).</span></span> <span data-ttu-id="4c4df-106">TNEF 用于传输多个客户端和消息存储提供程序支持在其邮件、 各种类型和自定义属性自定义邮件类的附件中的格式化的文本。</span><span class="sxs-lookup"><span data-stu-id="4c4df-106">TNEF is used to transmit the formatted text that many clients and message store providers support in their messages, attachments of various types, and custom properties for custom message classes.</span></span> <span data-ttu-id="4c4df-107">尽管大多数传输提供程序的默认模式是发送传出邮件 TNEF，某些传输提供程序不支持它。</span><span class="sxs-lookup"><span data-stu-id="4c4df-107">Although the default mode for most transport providers is to send outgoing messages with TNEF, some transport providers do not support it.</span></span> <span data-ttu-id="4c4df-108">缺少的 TNEF 支持不是标准消息的客户端的发送和接收 IPM 消息的问题。</span><span class="sxs-lookup"><span data-stu-id="4c4df-108">The lack of support for TNEF is not an issue for standard messaging clients that send and receive IPM messages.</span></span> <span data-ttu-id="4c4df-109">但是，对于基于窗体的客户端或需要自定义属性的客户端，使用 TNEF 非常重要。</span><span class="sxs-lookup"><span data-stu-id="4c4df-109">However, for form-based clients or clients that require custom properties, the use of TNEF is essential.</span></span> <span data-ttu-id="4c4df-110">设计器的依赖于窗体或自定义属性的客户端必须知道他们使用的传输提供程序的功能。</span><span class="sxs-lookup"><span data-stu-id="4c4df-110">Designers of clients that rely on forms or custom properties must be aware of the capabilities of the transport providers that they use.</span></span>
  
<span data-ttu-id="4c4df-111">邮件的收件人，可以控制传输提供程序将使用 TNEF 的消息传输通过**PR_SEND_RICH_INFO**属性设置。</span><span class="sxs-lookup"><span data-stu-id="4c4df-111">Message recipients can control whether or not a transport provider transmits messages with TNEF by setting the **PR_SEND_RICH_INFO** property.</span></span> <span data-ttu-id="4c4df-112">有关详细信息，请参阅**PR_SEND_RICH_INFO** ([PidTagSendRichInfo](pidtagsendrichinfo-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="4c4df-112">For more information, see **PR_SEND_RICH_INFO** ([PidTagSendRichInfo](pidtagsendrichinfo-canonical-property.md)).</span></span> <span data-ttu-id="4c4df-113">当收件人的**PR_SEND_RICH_INFO**属性设置为 TRUE 时，支持 TNEF 传输提供程序将其传送消息。</span><span class="sxs-lookup"><span data-stu-id="4c4df-113">When a recipient's **PR_SEND_RICH_INFO** property is set to TRUE, a transport provider that supports TNEF transmits it with the message.</span></span> <span data-ttu-id="4c4df-114">当该属性设置为 FALSE 时，格式将被丢弃。</span><span class="sxs-lookup"><span data-stu-id="4c4df-114">When the property is set to FALSE, the formatting is discarded.</span></span> <span data-ttu-id="4c4df-115">**PR_SEND_RICH_INFO**不存在，它由传输提供程序选择操作的默认参加其他课程。</span><span class="sxs-lookup"><span data-stu-id="4c4df-115">When **PR_SEND_RICH_INFO** does not exist, it is up to the transport provider to choose a default course of action.</span></span> 
  
<span data-ttu-id="4c4df-116">在客户端和服务提供商创建一个自定义收件人，就可以通过将 MAPI_SEND_NO_RICH_INFO 标志_ulFlags_参数中传递给**IAddrBook::CreateOneOff**或**影响其**PR_SEND_RICH_INFO**属性的值IMAPISupport::CreateOneOff**呼叫。</span><span class="sxs-lookup"><span data-stu-id="4c4df-116">When clients and service providers create a custom recipient, they can affect the value of its **PR_SEND_RICH_INFO** property by passing the MAPI_SEND_NO_RICH_INFO flag in the  _ulFlags_ parameter to the **IAddrBook::CreateOneOff** or **IMAPISupport::CreateOneOff** call.</span></span> <span data-ttu-id="4c4df-117">有关详细信息，请参阅[IAddrBook::CreateOneOff](iaddrbook-createoneoff.md)和[IMAPISupport::CreateOneOff](imapisupport-createoneoff.md)。</span><span class="sxs-lookup"><span data-stu-id="4c4df-117">For more information, see [IAddrBook::CreateOneOff](iaddrbook-createoneoff.md) and [IMAPISupport::CreateOneOff](imapisupport-createoneoff.md).</span></span> <span data-ttu-id="4c4df-118">将传递 MAPI_SEND_NO_RICH_INFO 会导致 MAPI 将自定义收信人**PR_SEND_RICH_INFO**属性设置为 FALSE;在大多数情况下不传递标志会导致 MAPI 属性设置为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="4c4df-118">Passing MAPI_SEND_NO_RICH_INFO causes MAPI to set the custom recipient's **PR_SEND_RICH_INFO** property to FALSE; in most cases not passing the flag causes MAPI to set the property to TRUE.</span></span> <span data-ttu-id="4c4df-119">一个例外，如果自定义收信人地址被解释为 Internet 地址。</span><span class="sxs-lookup"><span data-stu-id="4c4df-119">The one exception is if the custom recipient's address is interpreted to be an Internet address.</span></span> <span data-ttu-id="4c4df-120">在此一个的情况下，MAPI 将**PR_SEND_RICH_INFO**设置为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="4c4df-120">In this one situation, MAPI sets **PR_SEND_RICH_INFO** to FALSE.</span></span> 
  

