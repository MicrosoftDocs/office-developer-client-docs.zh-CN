---
title: 在 X 400 网关和传输中的 TNEF 相关性
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 0ffa0802-bfdd-4993-b4a3-142e5d15bfb4
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: e08f16ff60a282f1be3adf93d858471e38d19957
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32339625"
---
# <a name="tnef-correlation-in-x400-gateways-and-transports"></a><span data-ttu-id="ba3b1-103">在 X 400 网关和传输中的 TNEF 相关性</span><span class="sxs-lookup"><span data-stu-id="ba3b1-103">TNEF Correlation in X.400 Gateways and Transports</span></span>

  
  
<span data-ttu-id="ba3b1-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ba3b1-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ba3b1-105">连接到基于 X. 400 的系统的网关和传输, 请使用 IM_THIS_IPM X. 400 属性的值和**attMessageID** TNEF 属性来实现 TNEF 关联。</span><span class="sxs-lookup"><span data-stu-id="ba3b1-105">Gateways and transports that connect to X.400-based systems, use the value of the IM_THIS_IPM X.400 attribute and the **attMessageID** TNEF attribute to implement TNEF correlation.</span></span> 
  
<span data-ttu-id="ba3b1-106">将出站邮件的 IM_THIS_IPM 属性的值复制到 TNEF 流中的**attMessageID** 。</span><span class="sxs-lookup"><span data-stu-id="ba3b1-106">The value of the IM_THIS_IPM attribute of the outbound message is copied to **attMessageID** in the TNEF stream.</span></span> <span data-ttu-id="ba3b1-107">IM_THIS_IPM X. 400 属性通常是一个字符串, 而**attMessageID** TNEF 属性是一个十六进制数字的字符串, 表示一个二进制值。</span><span class="sxs-lookup"><span data-stu-id="ba3b1-107">The IM_THIS_IPM X.400 attribute is typically a string, while the **attMessageID** TNEF attribute is a string of hexadecimal digits representing a binary value.</span></span> <span data-ttu-id="ba3b1-108">因此, IM_THIS_IPM X. 400 属性中的每个字符 (包括终止的 null 字符) 都必须转换为2个字符的十六进制字符串, 表示该字符的 ASCII 值。</span><span class="sxs-lookup"><span data-stu-id="ba3b1-108">Therefore, each character in the IM_THIS_IPM X.400 attribute, including the terminating null character, must be converted to a 2-character hexadecimal string representing the ASCII value of that character.</span></span> <span data-ttu-id="ba3b1-109">例如, 如果 IM_THIS_IPM X. 400 属性为以下字符串:</span><span class="sxs-lookup"><span data-stu-id="ba3b1-109">For instance, if the IM_THIS_IPM X.400 attribute is the following string:</span></span> 
  
<span data-ttu-id="ba3b1-110">3030322D3030312D305337533A3A3936303631312D313533373030</span><span class="sxs-lookup"><span data-stu-id="ba3b1-110">3030322D3030312D305337533A3A3936303631312D313533373030</span></span>
  
<span data-ttu-id="ba3b1-111">然后, **attMessageID**的值将为以下十六进制数字序列:</span><span class="sxs-lookup"><span data-stu-id="ba3b1-111">then the value of **attMessageID** would be the following sequence of hexadecimal digits:</span></span> 
  
<span data-ttu-id="ba3b1-112">33 30 33 30 33 32 32 44</span><span class="sxs-lookup"><span data-stu-id="ba3b1-112">33 30 33 30 33 32 32 44</span></span>
  
<span data-ttu-id="ba3b1-113">33 30 33 30 33 31 32 44</span><span class="sxs-lookup"><span data-stu-id="ba3b1-113">33 30 33 30 33 31 32 44</span></span>
  
<span data-ttu-id="ba3b1-114">33 30 35 33 33 37 35 33</span><span class="sxs-lookup"><span data-stu-id="ba3b1-114">33 30 35 33 33 37 35 33</span></span>
  
<span data-ttu-id="ba3b1-115">33 41 33 41 33 39 33 36</span><span class="sxs-lookup"><span data-stu-id="ba3b1-115">33 41 33 41 33 39 33 36</span></span>
  
<span data-ttu-id="ba3b1-116">33 30 33 36 33 31 33 31</span><span class="sxs-lookup"><span data-stu-id="ba3b1-116">33 30 33 36 33 31 33 31</span></span>
  
<span data-ttu-id="ba3b1-117">32 44 33 31 33 35 33 33</span><span class="sxs-lookup"><span data-stu-id="ba3b1-117">32 44 33 31 33 35 33 33</span></span>
  
<span data-ttu-id="ba3b1-118">33 37 33 30 33 30 00</span><span class="sxs-lookup"><span data-stu-id="ba3b1-118">33 37 33 30 33 30 00</span></span>
  
<span data-ttu-id="ba3b1-119">此技术由 Microsoft Exchange Server X 400 连接器使用。</span><span class="sxs-lookup"><span data-stu-id="ba3b1-119">This technique is used by the Microsoft Exchange Server X.400 Connector.</span></span> <span data-ttu-id="ba3b1-120">此技术应由连接到 Microsoft Exchange Server 的任何 X 400 网关和传输使用, 以便最大限度地提高互操作性。</span><span class="sxs-lookup"><span data-stu-id="ba3b1-120">This technique should be used by any X.400 gateways and transports that connect to Microsoft Exchange Server in order to maximize interoperability.</span></span>
  
<span data-ttu-id="ba3b1-121">为了在将来和提供 Microsoft 软件时实现最大的兼容性, 还应将 IM_THIS_IPM X. 400 属性复制到**PR_TNEF_CORRELATION_KEY** ([PidTagTnefCorrelationKey](pidtagtnefcorrelationkey-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="ba3b1-121">For greatest compatibility with future as well as present Microsoft software, the IM_THIS_IPM X.400 attribute should also be copied to the **PR_TNEF_CORRELATION_KEY** ([PidTagTnefCorrelationKey](pidtagtnefcorrelationkey-canonical-property.md)) property.</span></span> <span data-ttu-id="ba3b1-122">但是, 由于**PR_TNEF_CORRELATION_KEY**是二进制属性, 因此不需要转换为十六进制字符串。</span><span class="sxs-lookup"><span data-stu-id="ba3b1-122">However, since **PR_TNEF_CORRELATION_KEY** is a binary property, no translation into a hexadecimal string is necessary.</span></span> 
  

