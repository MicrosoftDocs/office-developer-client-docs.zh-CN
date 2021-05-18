---
title: X.400 网关和传输中的 TNEF 相关性
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 0ffa0802-bfdd-4993-b4a3-142e5d15bfb4
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: e08f16ff60a282f1be3adf93d858471e38d19957
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33406372"
---
# <a name="tnef-correlation-in-x400-gateways-and-transports"></a><span data-ttu-id="3ce8b-103">X.400 网关和传输中的 TNEF 相关性</span><span class="sxs-lookup"><span data-stu-id="3ce8b-103">TNEF Correlation in X.400 Gateways and Transports</span></span>

  
  
<span data-ttu-id="3ce8b-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="3ce8b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="3ce8b-105">连接到基于 X.400 系统的网关和传输使用 IM_THIS_IPM X.400 属性的值和 **attMessageID** TNEF 属性的值来实现 TNEF 关联。</span><span class="sxs-lookup"><span data-stu-id="3ce8b-105">Gateways and transports that connect to X.400-based systems, use the value of the IM_THIS_IPM X.400 attribute and the **attMessageID** TNEF attribute to implement TNEF correlation.</span></span> 
  
<span data-ttu-id="3ce8b-106">出站IM_THIS_IPM的 IM_THIS_IPM 属性的值复制到 TNEF 流中的 **attMessageID。**</span><span class="sxs-lookup"><span data-stu-id="3ce8b-106">The value of the IM_THIS_IPM attribute of the outbound message is copied to **attMessageID** in the TNEF stream.</span></span> <span data-ttu-id="3ce8b-107">X.400 IM_THIS_IPM X.400 属性通常是一个字符串，而 **attMessageID** TNEF 属性是一个代表二进制值的十六进制数字字符串。</span><span class="sxs-lookup"><span data-stu-id="3ce8b-107">The IM_THIS_IPM X.400 attribute is typically a string, while the **attMessageID** TNEF attribute is a string of hexadecimal digits representing a binary value.</span></span> <span data-ttu-id="3ce8b-108">因此，IM_THIS_IPM X.400 属性（包括终止 null 字符）中的每个字符都必须转换为表示该字符的 ASCII 值的 2 个字符的十六进制字符串。</span><span class="sxs-lookup"><span data-stu-id="3ce8b-108">Therefore, each character in the IM_THIS_IPM X.400 attribute, including the terminating null character, must be converted to a 2-character hexadecimal string representing the ASCII value of that character.</span></span> <span data-ttu-id="3ce8b-109">例如，如果 IM_THIS_IPM X.400 属性是以下字符串：</span><span class="sxs-lookup"><span data-stu-id="3ce8b-109">For instance, if the IM_THIS_IPM X.400 attribute is the following string:</span></span> 
  
<span data-ttu-id="3ce8b-110">3030322D3030312D305337533A3A3936303631312D313533373030</span><span class="sxs-lookup"><span data-stu-id="3ce8b-110">3030322D3030312D305337533A3A3936303631312D313533373030</span></span>
  
<span data-ttu-id="3ce8b-111">那么 **attMessageID** 的值将是以下十六进制数字序列：</span><span class="sxs-lookup"><span data-stu-id="3ce8b-111">then the value of **attMessageID** would be the following sequence of hexadecimal digits:</span></span> 
  
<span data-ttu-id="3ce8b-112">33 30 33 30 33 32 32 44</span><span class="sxs-lookup"><span data-stu-id="3ce8b-112">33 30 33 30 33 32 32 44</span></span>
  
<span data-ttu-id="3ce8b-113">33 30 33 30 33 31 32 44</span><span class="sxs-lookup"><span data-stu-id="3ce8b-113">33 30 33 30 33 31 32 44</span></span>
  
<span data-ttu-id="3ce8b-114">33 30 35 33 33 37 35 33</span><span class="sxs-lookup"><span data-stu-id="3ce8b-114">33 30 35 33 33 37 35 33</span></span>
  
<span data-ttu-id="3ce8b-115">33 41 33 41 33 39 33 36</span><span class="sxs-lookup"><span data-stu-id="3ce8b-115">33 41 33 41 33 39 33 36</span></span>
  
<span data-ttu-id="3ce8b-116">33 30 33 36 33 31 33 31</span><span class="sxs-lookup"><span data-stu-id="3ce8b-116">33 30 33 36 33 31 33 31</span></span>
  
<span data-ttu-id="3ce8b-117">32 44 33 31 33 35 33 33</span><span class="sxs-lookup"><span data-stu-id="3ce8b-117">32 44 33 31 33 35 33 33</span></span>
  
<span data-ttu-id="3ce8b-118">33 37 33 30 33 30 00</span><span class="sxs-lookup"><span data-stu-id="3ce8b-118">33 37 33 30 33 30 00</span></span>
  
<span data-ttu-id="3ce8b-119">此技术由 Microsoft Exchange Server X.400 Connector 使用。</span><span class="sxs-lookup"><span data-stu-id="3ce8b-119">This technique is used by the Microsoft Exchange Server X.400 Connector.</span></span> <span data-ttu-id="3ce8b-120">为了最大限度地提高互操作性，连接到客户端的任何 X.400 网关和传输Microsoft Exchange Server此技术。</span><span class="sxs-lookup"><span data-stu-id="3ce8b-120">This technique should be used by any X.400 gateways and transports that connect to Microsoft Exchange Server in order to maximize interoperability.</span></span>
  
<span data-ttu-id="3ce8b-121">为了与未来以及当前 Microsoft 软件的最大兼容性，IM_THIS_IPM X.400 属性还应复制到 **PR_TNEF_CORRELATION_KEY** ([PidTagTnefCorrelationKey](pidtagtnefcorrelationkey-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="3ce8b-121">For greatest compatibility with future as well as present Microsoft software, the IM_THIS_IPM X.400 attribute should also be copied to the **PR_TNEF_CORRELATION_KEY** ([PidTagTnefCorrelationKey](pidtagtnefcorrelationkey-canonical-property.md)) property.</span></span> <span data-ttu-id="3ce8b-122">但是， **由于PR_TNEF_CORRELATION_KEY** 二进制属性，因此无需转换为十六进制字符串。</span><span class="sxs-lookup"><span data-stu-id="3ce8b-122">However, since **PR_TNEF_CORRELATION_KEY** is a binary property, no translation into a hexadecimal string is necessary.</span></span> 
  

