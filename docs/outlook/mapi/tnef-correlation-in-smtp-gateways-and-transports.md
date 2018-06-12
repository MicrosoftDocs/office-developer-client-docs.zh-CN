---
title: SMTP 网关和传输中的 TNEF 互联
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 593f57d7-2891-40d1-a661-478a62d490ff
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: ec1d826ee2b3b46685a2c03dfaf45d2843869cc5
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778982"
---
# <a name="tnef-correlation-in-smtp-gateways-and-transports"></a><span data-ttu-id="888bc-103">SMTP 网关和传输中的 TNEF 互联</span><span class="sxs-lookup"><span data-stu-id="888bc-103">TNEF Correlation in SMTP Gateways and Transports</span></span>

  
  
<span data-ttu-id="888bc-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="888bc-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="888bc-105">网关和连接到 internet 的传输基于那些使用 SMTP、 MessageID SMTP 标题和**PR_TNEF_CORRELATION_KEY**属性的值用于实现 TNEF 相关的系统。</span><span class="sxs-lookup"><span data-stu-id="888bc-105">Gateways and transports that connect to internet based systems, those that use SMTP, use the value of the MessageID SMTP header and the **PR_TNEF_CORRELATION_KEY** property to implement TNEF correlation.</span></span> 
  
<span data-ttu-id="888bc-106">出站消息的 MessageID 标头的值应为复制到**PR_TNEF_CORRELATION_KEY** ([PidTagTnefCorrelationKey](pidtagtnefcorrelationkey-canonical-property.md)) 属性，并且编码的 TNEF 流[attMAPIProps](attmapiprops.md)属性中。</span><span class="sxs-lookup"><span data-stu-id="888bc-106">The value of the MessageID header of the outbound message should be copied to the **PR_TNEF_CORRELATION_KEY** ([PidTagTnefCorrelationKey](pidtagtnefcorrelationkey-canonical-property.md)) property and encoded in the [attMAPIProps](attmapiprops.md) attribute of the TNEF stream.</span></span> <span data-ttu-id="888bc-107">请注意， **PR_TNEF_CORRELATION_KEY**二进制属性，而 MessageID 是字符串;null 终止符应包含在该副本和比较。</span><span class="sxs-lookup"><span data-stu-id="888bc-107">Note that **PR_TNEF_CORRELATION_KEY** is a binary property, while the MessageID is a string; the null terminator should be included in the copy and in the comparison.</span></span> 
  
<span data-ttu-id="888bc-108">将基于 MAPI 的消息系统连接到 Internet，例如 Microsoft Exchange Server 的所有 Microsoft 软件都使用此技术。</span><span class="sxs-lookup"><span data-stu-id="888bc-108">This technique is used by all Microsoft software that connects MAPI-based messaging systems to the Internet, such as Microsoft Exchange Server.</span></span> <span data-ttu-id="888bc-109">此方法应使用的任何 SMTP 网关和连接到为了最大限度地互操作性支持 MAPI 客户端的系统的传输。</span><span class="sxs-lookup"><span data-stu-id="888bc-109">This technique should be used by any SMTP gateways and transports that connect to systems that support MAPI clients in order to maximize interoperability.</span></span>
  

