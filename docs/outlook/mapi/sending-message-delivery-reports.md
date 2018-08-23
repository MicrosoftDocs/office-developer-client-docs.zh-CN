---
title: 发送邮件送达报告
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: abb12ec5-f0b7-488a-a75d-446f4be53e96
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 717494f30fd4d43e94a7c6a37770e2eab8ebb59e
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22593597"
---
# <a name="sending-message-delivery-reports"></a><span data-ttu-id="20842-103">发送邮件送达报告</span><span class="sxs-lookup"><span data-stu-id="20842-103">Sending Message Delivery Reports</span></span>

  
  
<span data-ttu-id="20842-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="20842-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="20842-105">某些基础的消息系统支持送达报告和有些则未。</span><span class="sxs-lookup"><span data-stu-id="20842-105">Some underlying messaging systems support delivery reports and some do not.</span></span> <span data-ttu-id="20842-106">传输提供程序如何确定是否可以将邮件传递或原件报告发送给客户端应用程序是特定于单个传输提供程序的实现详细信息。</span><span class="sxs-lookup"><span data-stu-id="20842-106">How the transport provider determines whether message delivery or nondelivery reports can be sent to client applications is an implementation detail specific to individual transport providers.</span></span> <span data-ttu-id="20842-107">如果送达报告可被发送到客户端应用程序，传输提供程序使用[IMAPISupport::StatusRecips](imapisupport-statusrecips.md)方法的一个或多个收件人通知的成功或失败传递的 MAPI。</span><span class="sxs-lookup"><span data-stu-id="20842-107">If delivery reports can be sent to client applications, transport providers use the [IMAPISupport::StatusRecips](imapisupport-statusrecips.md) method to notify MAPI of successful or unsuccessful delivery for one or more recipients.</span></span> <span data-ttu-id="20842-108">MAPI 然后生成传递或原件对应于这些收件人的报告。</span><span class="sxs-lookup"><span data-stu-id="20842-108">MAPI then generates delivery or nondelivery reports corresponding to those recipients.</span></span> <span data-ttu-id="20842-109">传输提供程序可以通过**StatusRecips**翻译传入邮件系统的 MAPI 传递到本机的交付和原件报告和未送达报告。</span><span class="sxs-lookup"><span data-stu-id="20842-109">Transport providers can also translate incoming delivery and nondelivery reports that are native to the messaging system into MAPI delivery and nondelivery reports by means of **StatusRecips**.</span></span>
  

