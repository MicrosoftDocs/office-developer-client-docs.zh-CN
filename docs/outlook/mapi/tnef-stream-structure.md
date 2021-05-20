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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33430201"
---
# <a name="tnef-stream-structure"></a><span data-ttu-id="b3b26-103">TNEF 流结构</span><span class="sxs-lookup"><span data-stu-id="b3b26-103">TNEF Stream Structure</span></span>

  
  
<span data-ttu-id="b3b26-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b3b26-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b3b26-105">TNEF 流以 32 位签名开头，该签名将流标识为 TNEF 流。</span><span class="sxs-lookup"><span data-stu-id="b3b26-105">A TNEF stream begins with a 32-bit signature that identifies the stream as a TNEF stream.</span></span> <span data-ttu-id="b3b26-106">签名后是一个 16 位无符号整数，用作跨引用附件到标记邮件文本中位置的键。</span><span class="sxs-lookup"><span data-stu-id="b3b26-106">Following the signature is a 16-bit unsigned integer that is used as a key to cross-reference attachments to their location in the tagged message text.</span></span> <span data-ttu-id="b3b26-107">流的其余部分是 TNEF 属性序列。</span><span class="sxs-lookup"><span data-stu-id="b3b26-107">The remainder of the stream is a sequence of TNEF attributes.</span></span> <span data-ttu-id="b3b26-108">邮件属性首先显示在 TNEF 流中，然后是附件属性。</span><span class="sxs-lookup"><span data-stu-id="b3b26-108">Message attributes appear first in the TNEF stream, and attachment attributes follow.</span></span> <span data-ttu-id="b3b26-109">属于特定附件的属性分组在一起，从 **attAttachRenddata** 属性开始。</span><span class="sxs-lookup"><span data-stu-id="b3b26-109">Attributes that belong to a particular attachment are grouped together, beginning with the **attAttachRenddata** attribute.</span></span> 
  
<span data-ttu-id="b3b26-110">TNEF 流中使用的大多数常量值在 TNEF 中定义。H 头文件。</span><span class="sxs-lookup"><span data-stu-id="b3b26-110">Most of the constant values used in TNEF streams are defined in the TNEF.H header file.</span></span> <span data-ttu-id="b3b26-111">值得注意的是，TNEF_SIGNATURE、LVL_MESSAGE、LVL_ATTACHMENT和所有 TNEF 属性标识符都在此文件中定义。  </span><span class="sxs-lookup"><span data-stu-id="b3b26-111">Notably, **TNEF_SIGNATURE**, **LVL_MESSAGE**, **LVL_ATTACHMENT**, and all the TNEF attribute identifiers are defined in this file.</span></span> <span data-ttu-id="b3b26-112">其他常量具有由它们向 C 语言编译器解释的值。</span><span class="sxs-lookup"><span data-stu-id="b3b26-112">Other constants have the values indicated by their interpretation to a C language compiler.</span></span> <span data-ttu-id="b3b26-113">通常，此类常量用于提供以下项目的大小。</span><span class="sxs-lookup"><span data-stu-id="b3b26-113">Typically, such constants are used to give the sizes of the following item.</span></span> <span data-ttu-id="b3b26-114">例如 **， (ULONG**) 中的 sizeof 指示在 TNEF 流中的该位置应出现一个代表以下无符号长整型大小的整数。</span><span class="sxs-lookup"><span data-stu-id="b3b26-114">For example, **sizeof(ULONG)** in an item's definition indicates that an integer representing the size of the following unsigned long integer should occur in that place in the TNEF stream.</span></span> 
  
<span data-ttu-id="b3b26-115">TNEF 流中所有整数以小尾二进制形式存储，但在此节以十六进制形式显示。</span><span class="sxs-lookup"><span data-stu-id="b3b26-115">All integers in a TNEF stream are stored in little-endian binary form, but are shown in hexadecimal throughout this section.</span></span> <span data-ttu-id="b3b26-116">校验和值只是 16 位无符号整数，即校验和所应用的数据字节的总和，modulo 65536。</span><span class="sxs-lookup"><span data-stu-id="b3b26-116">Checksum values are simply 16-bit unsigned integers that are the sum, modulo 65536, of the bytes of data that the checksum applies to.</span></span> <span data-ttu-id="b3b26-117">所有属性长度都是无符号长整型，包括任何终止 null 字符。</span><span class="sxs-lookup"><span data-stu-id="b3b26-117">All attribute lengths are unsigned long integers, including any terminating null characters.</span></span>
  
<span data-ttu-id="b3b26-118">键是一个非零 16 位无符号整数，表示附件引用键的初始值。</span><span class="sxs-lookup"><span data-stu-id="b3b26-118">The key is a nonzero, 16-bit unsigned integer that signifies the initial value of the attachment reference keys.</span></span> <span data-ttu-id="b3b26-119">附件引用键按顺序分配给每个附件，从使用 TNEF 的服务提供商传递给 [OpenTnefStream](opentnefstream.md) 函数的初始值开始。</span><span class="sxs-lookup"><span data-stu-id="b3b26-119">The attachment reference keys are assigned to each attachment sequentially beginning with the initial value that is passed to the [OpenTnefStream](opentnefstream.md) function by the service provider that is using TNEF.</span></span> <span data-ttu-id="b3b26-120">服务提供商应为密钥生成随机的初始值，以最大程度地降低两条消息使用同一密钥的可能性。</span><span class="sxs-lookup"><span data-stu-id="b3b26-120">The service provider should generate a random initial value for the key to minimize the chance that two messages use the same key.</span></span> 
  
<span data-ttu-id="b3b26-121">TNEF 实现使用属性标识符将属性映射到其相应的 MAPI 属性。</span><span class="sxs-lookup"><span data-stu-id="b3b26-121">The TNEF implementation uses attribute identifiers to map attributes to their corresponding MAPI properties.</span></span> <span data-ttu-id="b3b26-122">属性标识符是一个 32 位无符号整数，由两个单词值决定。</span><span class="sxs-lookup"><span data-stu-id="b3b26-122">An attribute identifier is a 32-bit unsigned integer made up of two word values.</span></span> <span data-ttu-id="b3b26-123">高顺序单词指示数据类型，如字符串或二进制，低顺序单词标识特定属性。</span><span class="sxs-lookup"><span data-stu-id="b3b26-123">The high-order word indicates the data type, such as string or binary, and the low-order word identifies the particular attribute.</span></span> <span data-ttu-id="b3b26-124">高顺序字词中的数据类型为：</span><span class="sxs-lookup"><span data-stu-id="b3b26-124">The data types in the high order word are:</span></span>
  
|<span data-ttu-id="b3b26-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="b3b26-125">**Type**</span></span>|<span data-ttu-id="b3b26-126">**值**</span><span class="sxs-lookup"><span data-stu-id="b3b26-126">**Value**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b3b26-127">atpTriples</span><span class="sxs-lookup"><span data-stu-id="b3b26-127">atpTriples</span></span>  <br/> |<span data-ttu-id="b3b26-128">0x0000</span><span class="sxs-lookup"><span data-stu-id="b3b26-128">0x0000</span></span>  <br/> |
|<span data-ttu-id="b3b26-129">atpString</span><span class="sxs-lookup"><span data-stu-id="b3b26-129">atpString</span></span>  <br/> |<span data-ttu-id="b3b26-130">0x0001</span><span class="sxs-lookup"><span data-stu-id="b3b26-130">0x0001</span></span>  <br/> |
|<span data-ttu-id="b3b26-131">atpText</span><span class="sxs-lookup"><span data-stu-id="b3b26-131">atpText</span></span>  <br/> |<span data-ttu-id="b3b26-132">0x0002</span><span class="sxs-lookup"><span data-stu-id="b3b26-132">0x0002</span></span>  <br/> |
|<span data-ttu-id="b3b26-133">atpDate</span><span class="sxs-lookup"><span data-stu-id="b3b26-133">atpDate</span></span>  <br/> |<span data-ttu-id="b3b26-134">0x0003</span><span class="sxs-lookup"><span data-stu-id="b3b26-134">0x0003</span></span>  <br/> |
|<span data-ttu-id="b3b26-135">atpShort</span><span class="sxs-lookup"><span data-stu-id="b3b26-135">atpShort</span></span>  <br/> |<span data-ttu-id="b3b26-136">0x0004</span><span class="sxs-lookup"><span data-stu-id="b3b26-136">0x0004</span></span>  <br/> |
|<span data-ttu-id="b3b26-137">atpLong</span><span class="sxs-lookup"><span data-stu-id="b3b26-137">atpLong</span></span>  <br/> |<span data-ttu-id="b3b26-138">0x0005</span><span class="sxs-lookup"><span data-stu-id="b3b26-138">0x0005</span></span>  <br/> |
|<span data-ttu-id="b3b26-139">atpByte</span><span class="sxs-lookup"><span data-stu-id="b3b26-139">atpByte</span></span>  <br/> |<span data-ttu-id="b3b26-140">0x0006</span><span class="sxs-lookup"><span data-stu-id="b3b26-140">0x0006</span></span>  <br/> |
|<span data-ttu-id="b3b26-141">atpWord</span><span class="sxs-lookup"><span data-stu-id="b3b26-141">atpWord</span></span>  <br/> |<span data-ttu-id="b3b26-142">0x0007</span><span class="sxs-lookup"><span data-stu-id="b3b26-142">0x0007</span></span>  <br/> |
|<span data-ttu-id="b3b26-143">atpDword</span><span class="sxs-lookup"><span data-stu-id="b3b26-143">atpDword</span></span>  <br/> |<span data-ttu-id="b3b26-144">0x0008</span><span class="sxs-lookup"><span data-stu-id="b3b26-144">0x0008</span></span>  <br/> |
|<span data-ttu-id="b3b26-145">atpMax</span><span class="sxs-lookup"><span data-stu-id="b3b26-145">atpMax</span></span>  <br/> |<span data-ttu-id="b3b26-146">0x0009</span><span class="sxs-lookup"><span data-stu-id="b3b26-146">0x0009</span></span>  <br/> |
   
<span data-ttu-id="b3b26-147">每个属性的低顺序单词值在 TNEF 中定义。H 头文件。</span><span class="sxs-lookup"><span data-stu-id="b3b26-147">The low-order word values for each attribute are defined in the TNEF.H header file.</span></span>
  

