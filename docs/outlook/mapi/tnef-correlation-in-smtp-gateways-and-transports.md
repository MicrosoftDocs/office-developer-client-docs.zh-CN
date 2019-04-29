---
title: SMTP 网关和传输中的 TNEF 相关性
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 593f57d7-2891-40d1-a661-478a62d490ff
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 0a685e081d319c43daa583d95d163677e81f2480
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33413666"
---
# <a name="tnef-correlation-in-smtp-gateways-and-transports"></a><span data-ttu-id="38868-103">SMTP 网关和传输中的 TNEF 相关性</span><span class="sxs-lookup"><span data-stu-id="38868-103">TNEF Correlation in SMTP Gateways and Transports</span></span>

  
  
<span data-ttu-id="38868-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="38868-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="38868-105">连接到基于 internet 的系统 (使用 SMTP 的网关和传输) 的网关和传输使用 MessageID SMTP 头和**PR_TNEF_CORRELATION_KEY**属性的值来实现 TNEF 关联。</span><span class="sxs-lookup"><span data-stu-id="38868-105">Gateways and transports that connect to internet based systems, those that use SMTP, use the value of the MessageID SMTP header and the **PR_TNEF_CORRELATION_KEY** property to implement TNEF correlation.</span></span> 
  
<span data-ttu-id="38868-106">应将出站邮件的 MessageID 标头的值复制到**PR_TNEF_CORRELATION_KEY** ([PidTagTnefCorrelationKey](pidtagtnefcorrelationkey-canonical-property.md)) 属性, 并在 TNEF 流的[attMAPIProps](attmapiprops.md)属性中进行编码。</span><span class="sxs-lookup"><span data-stu-id="38868-106">The value of the MessageID header of the outbound message should be copied to the **PR_TNEF_CORRELATION_KEY** ([PidTagTnefCorrelationKey](pidtagtnefcorrelationkey-canonical-property.md)) property and encoded in the [attMAPIProps](attmapiprops.md) attribute of the TNEF stream.</span></span> <span data-ttu-id="38868-107">请注意, **PR_TNEF_CORRELATION_KEY**是二进制属性, 而 MessageID 为字符串, 则为。null 终止符应包含在副本和比较中。</span><span class="sxs-lookup"><span data-stu-id="38868-107">Note that **PR_TNEF_CORRELATION_KEY** is a binary property, while the MessageID is a string; the null terminator should be included in the copy and in the comparison.</span></span> 
  
<span data-ttu-id="38868-108">此技术由将基于 MAPI 的邮件系统连接到 Internet 的所有 Microsoft 软件使用, 例如 microsoft Exchange Server。</span><span class="sxs-lookup"><span data-stu-id="38868-108">This technique is used by all Microsoft software that connects MAPI-based messaging systems to the Internet, such as Microsoft Exchange Server.</span></span> <span data-ttu-id="38868-109">此技术应由连接到支持 MAPI 客户端的系统的任何 SMTP 网关和传输使用, 以便最大限度地提高互操作性。</span><span class="sxs-lookup"><span data-stu-id="38868-109">This technique should be used by any SMTP gateways and transports that connect to systems that support MAPI clients in order to maximize interoperability.</span></span>
  

