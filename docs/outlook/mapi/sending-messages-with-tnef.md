---
title: 使用 TNEF 发送邮件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 6e2df265-b9dd-4e19-8ca5-3e31804e9120
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 7ff7f79b5e74412e9bbb4b4882c6a7d45e50fe6a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32338491"
---
# <a name="sending-messages-with-tnef"></a><span data-ttu-id="083ec-103">使用 TNEF 发送邮件</span><span class="sxs-lookup"><span data-stu-id="083ec-103">Sending Messages with TNEF</span></span>

  
  
<span data-ttu-id="083ec-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="083ec-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="083ec-105">许多传输提供程序会自动以传输中性封装格式 (TNEF) 发送所有传出邮件。</span><span class="sxs-lookup"><span data-stu-id="083ec-105">Many transport providers automatically send all outgoing messages with the Transport Neutral Encapsulation Format (TNEF).</span></span> <span data-ttu-id="083ec-106">TNEF 用于传输多个客户端和邮件存储区提供程序在其邮件中支持的格式化文本、各种类型的附件以及自定义邮件类的自定义属性。</span><span class="sxs-lookup"><span data-stu-id="083ec-106">TNEF is used to transmit the formatted text that many clients and message store providers support in their messages, attachments of various types, and custom properties for custom message classes.</span></span> <span data-ttu-id="083ec-107">尽管大多数传输提供程序的默认模式是使用 TNEF 发送传出邮件, 但某些传输提供程序不支持它。</span><span class="sxs-lookup"><span data-stu-id="083ec-107">Although the default mode for most transport providers is to send outgoing messages with TNEF, some transport providers do not support it.</span></span> <span data-ttu-id="083ec-108">对于发送和接收 IPM 邮件的标准邮件客户端而言, 缺少 TNEF 支持不是问题。</span><span class="sxs-lookup"><span data-stu-id="083ec-108">The lack of support for TNEF is not an issue for standard messaging clients that send and receive IPM messages.</span></span> <span data-ttu-id="083ec-109">但是, 对于需要自定义属性的基于表单的客户端或客户端, 使用 TNEF 是非常重要的。</span><span class="sxs-lookup"><span data-stu-id="083ec-109">However, for form-based clients or clients that require custom properties, the use of TNEF is essential.</span></span> <span data-ttu-id="083ec-110">依赖表单或自定义属性的客户端的设计者必须知道它们所使用的传输提供程序的功能。</span><span class="sxs-lookup"><span data-stu-id="083ec-110">Designers of clients that rely on forms or custom properties must be aware of the capabilities of the transport providers that they use.</span></span>
  
<span data-ttu-id="083ec-111">邮件收件人可以通过设置**PR_SEND_RICH_INFO**属性来控制传输提供程序是否通过 TNEF 传输邮件。</span><span class="sxs-lookup"><span data-stu-id="083ec-111">Message recipients can control whether or not a transport provider transmits messages with TNEF by setting the **PR_SEND_RICH_INFO** property.</span></span> <span data-ttu-id="083ec-112">有关详细信息, 请参阅**PR_SEND_RICH_INFO** ([PidTagSendRichInfo](pidtagsendrichinfo-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="083ec-112">For more information, see **PR_SEND_RICH_INFO** ([PidTagSendRichInfo](pidtagsendrichinfo-canonical-property.md)).</span></span> <span data-ttu-id="083ec-113">当收件人的**PR_SEND_RICH_INFO**属性设置为 TRUE 时, 支持 TNEF 的传输提供程序会将邮件传输到邮件中。</span><span class="sxs-lookup"><span data-stu-id="083ec-113">When a recipient's **PR_SEND_RICH_INFO** property is set to TRUE, a transport provider that supports TNEF transmits it with the message.</span></span> <span data-ttu-id="083ec-114">当该属性设置为 FALSE 时, 格式将被丢弃。</span><span class="sxs-lookup"><span data-stu-id="083ec-114">When the property is set to FALSE, the formatting is discarded.</span></span> <span data-ttu-id="083ec-115">如果**PR_SEND_RICH_INFO**不存在, 则由传输提供程序来选择默认的操作过程。</span><span class="sxs-lookup"><span data-stu-id="083ec-115">When **PR_SEND_RICH_INFO** does not exist, it is up to the transport provider to choose a default course of action.</span></span> 
  
<span data-ttu-id="083ec-116">当客户端和服务提供商创建自定义收件人时, 它们可能会影响其**PR_SEND_RICH_INFO**属性的值, 方法是将_ulFlags_参数中的 MAPI_SEND_NO_RICH_INFO 标志传递给**IAddrBook:: CreateOneOff**或**IMAPISupport:: CreateOneOff**调用。</span><span class="sxs-lookup"><span data-stu-id="083ec-116">When clients and service providers create a custom recipient, they can affect the value of its **PR_SEND_RICH_INFO** property by passing the MAPI_SEND_NO_RICH_INFO flag in the  _ulFlags_ parameter to the **IAddrBook::CreateOneOff** or **IMAPISupport::CreateOneOff** call.</span></span> <span data-ttu-id="083ec-117">有关详细信息, 请参阅[IAddrBook:: CreateOneOff](iaddrbook-createoneoff.md)和[IMAPISupport:: CreateOneOff](imapisupport-createoneoff.md)。</span><span class="sxs-lookup"><span data-stu-id="083ec-117">For more information, see [IAddrBook::CreateOneOff](iaddrbook-createoneoff.md) and [IMAPISupport::CreateOneOff](imapisupport-createoneoff.md).</span></span> <span data-ttu-id="083ec-118">传递 MAPI_SEND_NO_RICH_INFO 会导致 MAPI 将自定义收件人的**PR_SEND_RICH_INFO**属性设置为 FALSE;在大多数情况下, 不传递该标志将导致 MAPI 将该属性设置为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="083ec-118">Passing MAPI_SEND_NO_RICH_INFO causes MAPI to set the custom recipient's **PR_SEND_RICH_INFO** property to FALSE; in most cases not passing the flag causes MAPI to set the property to TRUE.</span></span> <span data-ttu-id="083ec-119">一个例外是将自定义收件人的地址解释为 Internet 地址。</span><span class="sxs-lookup"><span data-stu-id="083ec-119">The one exception is if the custom recipient's address is interpreted to be an Internet address.</span></span> <span data-ttu-id="083ec-120">在这种情况下, MAPI 会将**PR_SEND_RICH_INFO**设置为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="083ec-120">In this one situation, MAPI sets **PR_SEND_RICH_INFO** to FALSE.</span></span> 
  

