---
title: TNEF 流结构
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 8eda1251-3858-4832-ac43-d817b4a7ea59
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7e77c043e4f152740af9bdb2b8fb5b7bedece1c0
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32327382"
---
# <a name="tnef-stream-structure"></a><span data-ttu-id="e11a8-103">TNEF 流结构</span><span class="sxs-lookup"><span data-stu-id="e11a8-103">TNEF Stream Structure</span></span>

  
  
<span data-ttu-id="e11a8-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e11a8-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e11a8-105">TNEF 流以32位签名开头, 该签名将流标识为 TNEF 流。</span><span class="sxs-lookup"><span data-stu-id="e11a8-105">A TNEF stream begins with a 32-bit signature that identifies the stream as a TNEF stream.</span></span> <span data-ttu-id="e11a8-106">签名之后是一个16位无符号整数, 用作在标记的邮件文本中对其位置进行交叉引用的附件的键。</span><span class="sxs-lookup"><span data-stu-id="e11a8-106">Following the signature is a 16-bit unsigned integer that is used as a key to cross-reference attachments to their location in the tagged message text.</span></span> <span data-ttu-id="e11a8-107">流的其余部分是 TNEF 属性的序列。</span><span class="sxs-lookup"><span data-stu-id="e11a8-107">The remainder of the stream is a sequence of TNEF attributes.</span></span> <span data-ttu-id="e11a8-108">邮件属性先出现在 TNEF 流中, 附件属性如下所示。</span><span class="sxs-lookup"><span data-stu-id="e11a8-108">Message attributes appear first in the TNEF stream, and attachment attributes follow.</span></span> <span data-ttu-id="e11a8-109">属于特定附件的属性会组合在一起, 从**attAttachRenddata**属性开始。</span><span class="sxs-lookup"><span data-stu-id="e11a8-109">Attributes that belong to a particular attachment are grouped together, beginning with the **attAttachRenddata** attribute.</span></span> 
  
<span data-ttu-id="e11a8-110">tnef 流中使用的大部分常量值都是在 tnef 中定义的。H 头文件。</span><span class="sxs-lookup"><span data-stu-id="e11a8-110">Most of the constant values used in TNEF streams are defined in the TNEF.H header file.</span></span> <span data-ttu-id="e11a8-111">特别要注意的是, **TNEF_SIGNATURE**、 **LVL_MESSAGE**、 **LVL_ATTACHMENT**和所有 TNEF 属性标识符都是在此文件中定义的。</span><span class="sxs-lookup"><span data-stu-id="e11a8-111">Notably, **TNEF_SIGNATURE**, **LVL_MESSAGE**, **LVL_ATTACHMENT**, and all the TNEF attribute identifiers are defined in this file.</span></span> <span data-ttu-id="e11a8-112">其他常量的值由其对 C 语言编译器的解释指示。</span><span class="sxs-lookup"><span data-stu-id="e11a8-112">Other constants have the values indicated by their interpretation to a C language compiler.</span></span> <span data-ttu-id="e11a8-113">通常, 此类常量用于提供以下项的大小。</span><span class="sxs-lookup"><span data-stu-id="e11a8-113">Typically, such constants are used to give the sizes of the following item.</span></span> <span data-ttu-id="e11a8-114">例如, 项的定义中的**sizeof (ULONG)** 表示在 TNEF 流中, 表示以下无符号长整数的大小的整数应出现在该位置。</span><span class="sxs-lookup"><span data-stu-id="e11a8-114">For example, **sizeof(ULONG)** in an item's definition indicates that an integer representing the size of the following unsigned long integer should occur in that place in the TNEF stream.</span></span> 
  
<span data-ttu-id="e11a8-115">TNEF 流中的所有整数都存储在小 endian 二进制格式中, 但在此部分中显示为十六进制。</span><span class="sxs-lookup"><span data-stu-id="e11a8-115">All integers in a TNEF stream are stored in little-endian binary form, but are shown in hexadecimal throughout this section.</span></span> <span data-ttu-id="e11a8-116">校验和值只是16位无符号整数, 它们是校验和应用于的数据字节的总和, 即模数65536。</span><span class="sxs-lookup"><span data-stu-id="e11a8-116">Checksum values are simply 16-bit unsigned integers that are the sum, modulo 65536, of the bytes of data that the checksum applies to.</span></span> <span data-ttu-id="e11a8-117">所有属性长度均为无符号长整数, 包括任何终止的 null 字符。</span><span class="sxs-lookup"><span data-stu-id="e11a8-117">All attribute lengths are unsigned long integers, including any terminating null characters.</span></span>
  
<span data-ttu-id="e11a8-118">键是一个非零的16位无符号整数, 它表示附件引用键的初始值。</span><span class="sxs-lookup"><span data-stu-id="e11a8-118">The key is a nonzero, 16-bit unsigned integer that signifies the initial value of the attachment reference keys.</span></span> <span data-ttu-id="e11a8-119">将附件引用密钥分配给每个附件, 从以使用 TNEF 的服务提供程序传递给[OpenTnefStream](opentnefstream.md)函数的初始值开始, 依次为。</span><span class="sxs-lookup"><span data-stu-id="e11a8-119">The attachment reference keys are assigned to each attachment sequentially beginning with the initial value that is passed to the [OpenTnefStream](opentnefstream.md) function by the service provider that is using TNEF.</span></span> <span data-ttu-id="e11a8-120">服务提供程序应生成密钥的随机初始值, 以最大限度地减少两个邮件使用相同密钥的机会。</span><span class="sxs-lookup"><span data-stu-id="e11a8-120">The service provider should generate a random initial value for the key to minimize the chance that two messages use the same key.</span></span> 
  
<span data-ttu-id="e11a8-121">TNEF 实现使用属性标识符将属性映射到其对应的 MAPI 属性。</span><span class="sxs-lookup"><span data-stu-id="e11a8-121">The TNEF implementation uses attribute identifiers to map attributes to their corresponding MAPI properties.</span></span> <span data-ttu-id="e11a8-122">属性标识符是由两个单词值组成的32位无符号整数。</span><span class="sxs-lookup"><span data-stu-id="e11a8-122">An attribute identifier is a 32-bit unsigned integer made up of two word values.</span></span> <span data-ttu-id="e11a8-123">高序位字指示数据类型, 如字符串或二进制, 低序位字标识特定属性。</span><span class="sxs-lookup"><span data-stu-id="e11a8-123">The high-order word indicates the data type, such as string or binary, and the low-order word identifies the particular attribute.</span></span> <span data-ttu-id="e11a8-124">高序位字中的数据类型为:</span><span class="sxs-lookup"><span data-stu-id="e11a8-124">The data types in the high order word are:</span></span>
  
|<span data-ttu-id="e11a8-125">**Type**</span><span class="sxs-lookup"><span data-stu-id="e11a8-125">**Type**</span></span>|<span data-ttu-id="e11a8-126">**值**</span><span class="sxs-lookup"><span data-stu-id="e11a8-126">**Value**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e11a8-127">atpTriples</span><span class="sxs-lookup"><span data-stu-id="e11a8-127">atpTriples</span></span>  <br/> |<span data-ttu-id="e11a8-128">0x0000</span><span class="sxs-lookup"><span data-stu-id="e11a8-128">0x0000</span></span>  <br/> |
|<span data-ttu-id="e11a8-129">atpString</span><span class="sxs-lookup"><span data-stu-id="e11a8-129">atpString</span></span>  <br/> |<span data-ttu-id="e11a8-130">0x0001</span><span class="sxs-lookup"><span data-stu-id="e11a8-130">0x0001</span></span>  <br/> |
|<span data-ttu-id="e11a8-131">atpText</span><span class="sxs-lookup"><span data-stu-id="e11a8-131">atpText</span></span>  <br/> |<span data-ttu-id="e11a8-132">0x0002</span><span class="sxs-lookup"><span data-stu-id="e11a8-132">0x0002</span></span>  <br/> |
|<span data-ttu-id="e11a8-133">atpDate</span><span class="sxs-lookup"><span data-stu-id="e11a8-133">atpDate</span></span>  <br/> |<span data-ttu-id="e11a8-134">0x0003</span><span class="sxs-lookup"><span data-stu-id="e11a8-134">0x0003</span></span>  <br/> |
|<span data-ttu-id="e11a8-135">atpShort</span><span class="sxs-lookup"><span data-stu-id="e11a8-135">atpShort</span></span>  <br/> |<span data-ttu-id="e11a8-136">0x0004</span><span class="sxs-lookup"><span data-stu-id="e11a8-136">0x0004</span></span>  <br/> |
|<span data-ttu-id="e11a8-137">atpLong</span><span class="sxs-lookup"><span data-stu-id="e11a8-137">atpLong</span></span>  <br/> |<span data-ttu-id="e11a8-138">0x0005</span><span class="sxs-lookup"><span data-stu-id="e11a8-138">0x0005</span></span>  <br/> |
|<span data-ttu-id="e11a8-139">atpByte</span><span class="sxs-lookup"><span data-stu-id="e11a8-139">atpByte</span></span>  <br/> |<span data-ttu-id="e11a8-140">0x0006</span><span class="sxs-lookup"><span data-stu-id="e11a8-140">0x0006</span></span>  <br/> |
|<span data-ttu-id="e11a8-141">atpWord</span><span class="sxs-lookup"><span data-stu-id="e11a8-141">atpWord</span></span>  <br/> |<span data-ttu-id="e11a8-142">0x0007</span><span class="sxs-lookup"><span data-stu-id="e11a8-142">0x0007</span></span>  <br/> |
|<span data-ttu-id="e11a8-143">atpDword</span><span class="sxs-lookup"><span data-stu-id="e11a8-143">atpDword</span></span>  <br/> |<span data-ttu-id="e11a8-144">0x0008</span><span class="sxs-lookup"><span data-stu-id="e11a8-144">0x0008</span></span>  <br/> |
|<span data-ttu-id="e11a8-145">atpMax</span><span class="sxs-lookup"><span data-stu-id="e11a8-145">atpMax</span></span>  <br/> |<span data-ttu-id="e11a8-146">0x0009</span><span class="sxs-lookup"><span data-stu-id="e11a8-146">0x0009</span></span>  <br/> |
   
<span data-ttu-id="e11a8-147">每个属性的低序位字值都是在 TNEF 中定义的。H 头文件。</span><span class="sxs-lookup"><span data-stu-id="e11a8-147">The low-order word values for each attribute are defined in the TNEF.H header file.</span></span>
  

