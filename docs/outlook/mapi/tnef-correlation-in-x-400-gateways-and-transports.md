---
title: X.400 网关和传输中的 TNEF 互联
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 0ffa0802-bfdd-4993-b4a3-142e5d15bfb4
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: ea5ca41ef21c72377ade72370e0aee1b313c92d9
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778979"
---
# <a name="tnef-correlation-in-x400-gateways-and-transports"></a><span data-ttu-id="00e73-103">X.400 网关和传输中的 TNEF 互联</span><span class="sxs-lookup"><span data-stu-id="00e73-103">TNEF Correlation in X.400 Gateways and Transports</span></span>

  
  
<span data-ttu-id="00e73-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="00e73-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="00e73-105">网关和连接到基于 X.400 系统的传输使用 IM_THIS_IPM X.400 属性和**attMessageID** TNEF 属性的值来实现 TNEF 相关。</span><span class="sxs-lookup"><span data-stu-id="00e73-105">Gateways and transports that connect to X.400-based systems, use the value of the IM_THIS_IPM X.400 attribute and the **attMessageID** TNEF attribute to implement TNEF correlation.</span></span> 
  
<span data-ttu-id="00e73-106">出站消息的 IM_THIS_IPM 属性的值复制到**attMessageID** TNEF 流中。</span><span class="sxs-lookup"><span data-stu-id="00e73-106">The value of the IM_THIS_IPM attribute of the outbound message is copied to **attMessageID** in the TNEF stream.</span></span> <span data-ttu-id="00e73-107">IM_THIS_IPM X.400 属性通常是一个字符串， **attMessageID** TNEF 属性时十六进制数字表示的二进制值的字符串。</span><span class="sxs-lookup"><span data-stu-id="00e73-107">The IM_THIS_IPM X.400 attribute is typically a string, while the **attMessageID** TNEF attribute is a string of hexadecimal digits representing a binary value.</span></span> <span data-ttu-id="00e73-108">因此，必须在 IM_THIS_IPM X.400 属性中，包括终止空字符，每个字符转换为 2 个字符十六进制字符串表示该字符的 ASCII 值。</span><span class="sxs-lookup"><span data-stu-id="00e73-108">Therefore, each character in the IM_THIS_IPM X.400 attribute, including the terminating null character, must be converted to a 2-character hexadecimal string representing the ASCII value of that character.</span></span> <span data-ttu-id="00e73-109">例如，如果 IM_THIS_IPM X.400 属性是以下字符串：</span><span class="sxs-lookup"><span data-stu-id="00e73-109">For instance, if the IM_THIS_IPM X.400 attribute is the following string:</span></span> 
  
<span data-ttu-id="00e73-110">3030322D3030312D305337533A3A3936303631312D313533373030</span><span class="sxs-lookup"><span data-stu-id="00e73-110">3030322D3030312D305337533A3A3936303631312D313533373030</span></span>
  
<span data-ttu-id="00e73-111">然后**attMessageID**的值采用十六进制数字的以下序列：</span><span class="sxs-lookup"><span data-stu-id="00e73-111">then the value of **attMessageID** would be the following sequence of hexadecimal digits:</span></span> 
  
<span data-ttu-id="00e73-112">33 30 33 30 33 32 32 44</span><span class="sxs-lookup"><span data-stu-id="00e73-112">33 30 33 30 33 32 32 44</span></span>
  
<span data-ttu-id="00e73-113">33 30 33 30 33 31 32 44</span><span class="sxs-lookup"><span data-stu-id="00e73-113">33 30 33 30 33 31 32 44</span></span>
  
<span data-ttu-id="00e73-114">33 30 35 33 33 37 35 33</span><span class="sxs-lookup"><span data-stu-id="00e73-114">33 30 35 33 33 37 35 33</span></span>
  
<span data-ttu-id="00e73-115">33 41 33 41 33 39 33 36</span><span class="sxs-lookup"><span data-stu-id="00e73-115">33 41 33 41 33 39 33 36</span></span>
  
<span data-ttu-id="00e73-116">33 30 33 36 33 31 33 31</span><span class="sxs-lookup"><span data-stu-id="00e73-116">33 30 33 36 33 31 33 31</span></span>
  
<span data-ttu-id="00e73-117">32 44 33 31 33 35 33 33</span><span class="sxs-lookup"><span data-stu-id="00e73-117">32 44 33 31 33 35 33 33</span></span>
  
<span data-ttu-id="00e73-118">33 37 33 30 33 30 00</span><span class="sxs-lookup"><span data-stu-id="00e73-118">33 37 33 30 33 30 00</span></span>
  
<span data-ttu-id="00e73-119">Microsoft Exchange Server X.400 连接器使用此技术。</span><span class="sxs-lookup"><span data-stu-id="00e73-119">This technique is used by the Microsoft Exchange Server X.400 Connector.</span></span> <span data-ttu-id="00e73-120">此方法应使用任何 X.400 网关和连接到 Microsoft Exchange Server 以最大限度地互操作性的传输。</span><span class="sxs-lookup"><span data-stu-id="00e73-120">This technique should be used by any X.400 gateways and transports that connect to Microsoft Exchange Server in order to maximize interoperability.</span></span>
  
<span data-ttu-id="00e73-121">为了与将来以及存在 Microsoft 软件的最大兼容，IM_THIS_IPM X.400 属性也应复制到**PR_TNEF_CORRELATION_KEY** ([PidTagTnefCorrelationKey](pidtagtnefcorrelationkey-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="00e73-121">For greatest compatibility with future as well as present Microsoft software, the IM_THIS_IPM X.400 attribute should also be copied to the **PR_TNEF_CORRELATION_KEY** ([PidTagTnefCorrelationKey](pidtagtnefcorrelationkey-canonical-property.md)) property.</span></span> <span data-ttu-id="00e73-122">但是，由于**PR_TNEF_CORRELATION_KEY**是二进制属性，因此没有翻译十六进制字符串是必要的。</span><span class="sxs-lookup"><span data-stu-id="00e73-122">However, since **PR_TNEF_CORRELATION_KEY** is a binary property, no translation into a hexadecimal string is necessary.</span></span> 
  

