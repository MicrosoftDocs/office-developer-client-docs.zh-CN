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
ms.openlocfilehash: ebe10ae741975b33ee58e1e99032aaca64ef38d8
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22569727"
---
# <a name="tnef-stream-structure"></a><span data-ttu-id="1c5f1-103">TNEF 流结构</span><span class="sxs-lookup"><span data-stu-id="1c5f1-103">TNEF Stream Structure</span></span>

  
  
<span data-ttu-id="1c5f1-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="1c5f1-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="1c5f1-105">TNEF 流开头的标识作为 TNEF 流流 32 位签名。</span><span class="sxs-lookup"><span data-stu-id="1c5f1-105">A TNEF stream begins with a 32-bit signature that identifies the stream as a TNEF stream.</span></span> <span data-ttu-id="1c5f1-106">关注签名是一个 16 位无符号的整数，用作为键来交叉引用标记的消息文本中其位置的附件。</span><span class="sxs-lookup"><span data-stu-id="1c5f1-106">Following the signature is a 16-bit unsigned integer that is used as a key to cross-reference attachments to their location in the tagged message text.</span></span> <span data-ttu-id="1c5f1-107">用于将 stream 的其余部分是 TNEF 属性的序列。</span><span class="sxs-lookup"><span data-stu-id="1c5f1-107">The remainder of the stream is a sequence of TNEF attributes.</span></span> <span data-ttu-id="1c5f1-108">在 TNEF 流中，消息属性显示第一个和附件属性按照。</span><span class="sxs-lookup"><span data-stu-id="1c5f1-108">Message attributes appear first in the TNEF stream, and attachment attributes follow.</span></span> <span data-ttu-id="1c5f1-109">属于特定的附件属性分组在一起，开头**attAttachRenddata**属性。</span><span class="sxs-lookup"><span data-stu-id="1c5f1-109">Attributes that belong to a particular attachment are grouped together, beginning with the **attAttachRenddata** attribute.</span></span> 
  
<span data-ttu-id="1c5f1-110">大部分 TNEF 流中使用的常量值 TNEF 中定义。H 头文件。</span><span class="sxs-lookup"><span data-stu-id="1c5f1-110">Most of the constant values used in TNEF streams are defined in the TNEF.H header file.</span></span> <span data-ttu-id="1c5f1-111">值得注意的是， **TNEF_SIGNATURE**、 **LVL_MESSAGE**、 **LVL_ATTACHMENT**和所有 TNEF 属性标识符是该文件中定义。</span><span class="sxs-lookup"><span data-stu-id="1c5f1-111">Notably, **TNEF_SIGNATURE**, **LVL_MESSAGE**, **LVL_ATTACHMENT**, and all the TNEF attribute identifiers are defined in this file.</span></span> <span data-ttu-id="1c5f1-112">其他常量具有由其解释为 C 语言编译器的值。</span><span class="sxs-lookup"><span data-stu-id="1c5f1-112">Other constants have the values indicated by their interpretation to a C language compiler.</span></span> <span data-ttu-id="1c5f1-113">通常情况下，此类常量用于为以下项的大小。</span><span class="sxs-lookup"><span data-stu-id="1c5f1-113">Typically, such constants are used to give the sizes of the following item.</span></span> <span data-ttu-id="1c5f1-114">例如， **sizeof(ULONG)** 项目的定义中指示一个整数，表示的以下符号的长整数大小应进行中的 TNEF 流中该位置。</span><span class="sxs-lookup"><span data-stu-id="1c5f1-114">For example, **sizeof(ULONG)** in an item's definition indicates that an integer representing the size of the following unsigned long integer should occur in that place in the TNEF stream.</span></span> 
  
<span data-ttu-id="1c5f1-115">TNEF stream 中的所有整数-little-endian 二进制格式存储，但十六进制整个本节中所示。</span><span class="sxs-lookup"><span data-stu-id="1c5f1-115">All integers in a TNEF stream are stored in little-endian binary form, but are shown in hexadecimal throughout this section.</span></span> <span data-ttu-id="1c5f1-116">校验和值是只需 16 位无符号的整数的 sum、 模 65536 的字节数的校验和适用于数据。</span><span class="sxs-lookup"><span data-stu-id="1c5f1-116">Checksum values are simply 16-bit unsigned integers that are the sum, modulo 65536, of the bytes of data that the checksum applies to.</span></span> <span data-ttu-id="1c5f1-117">所有属性长度都为无符号的长整数，包括任何 null 终止符。</span><span class="sxs-lookup"><span data-stu-id="1c5f1-117">All attribute lengths are unsigned long integers, including any terminating null characters.</span></span>
  
<span data-ttu-id="1c5f1-118">密钥是表示附件引用键的初始值的非零值、 16 位无符号的整数。</span><span class="sxs-lookup"><span data-stu-id="1c5f1-118">The key is a nonzero, 16-bit unsigned integer that signifies the initial value of the attachment reference keys.</span></span> <span data-ttu-id="1c5f1-119">附件引用键分配给每个附件按顺序开头的服务提供程序使用 TNEF 由传递给[OpenTnefStream](opentnefstream.md)函数的初始值。</span><span class="sxs-lookup"><span data-stu-id="1c5f1-119">The attachment reference keys are assigned to each attachment sequentially beginning with the initial value that is passed to the [OpenTnefStream](opentnefstream.md) function by the service provider that is using TNEF.</span></span> <span data-ttu-id="1c5f1-120">服务提供商应生成随机初始值键大程度地减少两条消息，使用相同键的机会。</span><span class="sxs-lookup"><span data-stu-id="1c5f1-120">The service provider should generate a random initial value for the key to minimize the chance that two messages use the same key.</span></span> 
  
<span data-ttu-id="1c5f1-121">TNEF 实现使用属性标识符属性映射到其对应的 MAPI 属性。</span><span class="sxs-lookup"><span data-stu-id="1c5f1-121">The TNEF implementation uses attribute identifiers to map attributes to their corresponding MAPI properties.</span></span> <span data-ttu-id="1c5f1-122">属性标识符是两个 word 值组成的 32 位无符号的整数。</span><span class="sxs-lookup"><span data-stu-id="1c5f1-122">An attribute identifier is a 32-bit unsigned integer made up of two word values.</span></span> <span data-ttu-id="1c5f1-123">高顺序单词指示的数据类型，如字符串或二进制，和低顺序单词标识的特定属性。</span><span class="sxs-lookup"><span data-stu-id="1c5f1-123">The high-order word indicates the data type, such as string or binary, and the low-order word identifies the particular attribute.</span></span> <span data-ttu-id="1c5f1-124">高位 word 中的数据类型包括：</span><span class="sxs-lookup"><span data-stu-id="1c5f1-124">The data types in the high order word are:</span></span>
  
|<span data-ttu-id="1c5f1-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="1c5f1-125">**Type**</span></span>|<span data-ttu-id="1c5f1-126">**值**</span><span class="sxs-lookup"><span data-stu-id="1c5f1-126">**Value**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1c5f1-127">atpTriples</span><span class="sxs-lookup"><span data-stu-id="1c5f1-127">atpTriples</span></span>  <br/> |<span data-ttu-id="1c5f1-128">0x0000</span><span class="sxs-lookup"><span data-stu-id="1c5f1-128">0x0000</span></span>  <br/> |
|<span data-ttu-id="1c5f1-129">atpString</span><span class="sxs-lookup"><span data-stu-id="1c5f1-129">atpString</span></span>  <br/> |<span data-ttu-id="1c5f1-130">0x0001</span><span class="sxs-lookup"><span data-stu-id="1c5f1-130">0x0001</span></span>  <br/> |
|<span data-ttu-id="1c5f1-131">atpText</span><span class="sxs-lookup"><span data-stu-id="1c5f1-131">atpText</span></span>  <br/> |<span data-ttu-id="1c5f1-132">0x0002</span><span class="sxs-lookup"><span data-stu-id="1c5f1-132">0x0002</span></span>  <br/> |
|<span data-ttu-id="1c5f1-133">atpDate</span><span class="sxs-lookup"><span data-stu-id="1c5f1-133">atpDate</span></span>  <br/> |<span data-ttu-id="1c5f1-134">0x0003</span><span class="sxs-lookup"><span data-stu-id="1c5f1-134">0x0003</span></span>  <br/> |
|<span data-ttu-id="1c5f1-135">atpShort</span><span class="sxs-lookup"><span data-stu-id="1c5f1-135">atpShort</span></span>  <br/> |<span data-ttu-id="1c5f1-136">0x0004</span><span class="sxs-lookup"><span data-stu-id="1c5f1-136">0x0004</span></span>  <br/> |
|<span data-ttu-id="1c5f1-137">atpLong</span><span class="sxs-lookup"><span data-stu-id="1c5f1-137">atpLong</span></span>  <br/> |<span data-ttu-id="1c5f1-138">0x0005</span><span class="sxs-lookup"><span data-stu-id="1c5f1-138">0x0005</span></span>  <br/> |
|<span data-ttu-id="1c5f1-139">atpByte</span><span class="sxs-lookup"><span data-stu-id="1c5f1-139">atpByte</span></span>  <br/> |<span data-ttu-id="1c5f1-140">0x0006</span><span class="sxs-lookup"><span data-stu-id="1c5f1-140">0x0006</span></span>  <br/> |
|<span data-ttu-id="1c5f1-141">atpWord</span><span class="sxs-lookup"><span data-stu-id="1c5f1-141">atpWord</span></span>  <br/> |<span data-ttu-id="1c5f1-142">0x0007</span><span class="sxs-lookup"><span data-stu-id="1c5f1-142">0x0007</span></span>  <br/> |
|<span data-ttu-id="1c5f1-143">atpDword</span><span class="sxs-lookup"><span data-stu-id="1c5f1-143">atpDword</span></span>  <br/> |<span data-ttu-id="1c5f1-144">0x0008</span><span class="sxs-lookup"><span data-stu-id="1c5f1-144">0x0008</span></span>  <br/> |
|<span data-ttu-id="1c5f1-145">atpMax</span><span class="sxs-lookup"><span data-stu-id="1c5f1-145">atpMax</span></span>  <br/> |<span data-ttu-id="1c5f1-146">0x0009</span><span class="sxs-lookup"><span data-stu-id="1c5f1-146">0x0009</span></span>  <br/> |
   
<span data-ttu-id="1c5f1-147">每个属性的低序 word 值 TNEF 中定义。H 头文件。</span><span class="sxs-lookup"><span data-stu-id="1c5f1-147">The low-order word values for each attribute are defined in the TNEF.H header file.</span></span>
  

