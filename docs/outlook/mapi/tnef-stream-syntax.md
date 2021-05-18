---
title: TNEF 流语法
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 1353d494-c266-4715-afe7-14543a1bbe1b
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 12d2a92ff80897456707c7ab8af8f704605c85d0
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33423025"
---
# <a name="tnef-stream-syntax"></a><span data-ttu-id="f3791-103">TNEF 流语法</span><span class="sxs-lookup"><span data-stu-id="f3791-103">TNEF Stream Syntax</span></span>

  
  
<span data-ttu-id="f3791-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f3791-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f3791-105">本主题提供了一个Bakus-Nauer TNEF 流语法的说明。</span><span class="sxs-lookup"><span data-stu-id="f3791-105">This topic presents a Bakus-Nauer like description of the TNEF stream syntax.</span></span> <span data-ttu-id="f3791-106">在此说明中，具有进一步定义的非终止元素以斜体显示。</span><span class="sxs-lookup"><span data-stu-id="f3791-106">In this description, nonterminal elements that have a further definition are in italics.</span></span> <span data-ttu-id="f3791-107">常量和文字项以粗体显示。</span><span class="sxs-lookup"><span data-stu-id="f3791-107">Constants and literal items are in bold.</span></span> <span data-ttu-id="f3791-108">元素序列在单行上按顺序排列。</span><span class="sxs-lookup"><span data-stu-id="f3791-108">Sequences of elements are listed in order on a single line.</span></span> <span data-ttu-id="f3791-109">例如  _，Stream_ 项由常量 **TNEF_SIGNATURE，后** 跟  _Key，_ 后跟  _Object_。</span><span class="sxs-lookup"><span data-stu-id="f3791-109">For example, the  _Stream_ item consists of the constant **TNEF_SIGNATURE**, followed by a  _Key_, followed by an  _Object_.</span></span> <span data-ttu-id="f3791-110">当一个项目具有多个可能的实现时，替代项将列在连续行上。</span><span class="sxs-lookup"><span data-stu-id="f3791-110">When an item has more than one possible implementation, the alternatives are listed on consecutive lines.</span></span> <span data-ttu-id="f3791-111">例如 _，Object_ 可以包含一个 Message_Seq、Message_Seq后跟一Attach_Seq或 _只包含一_ Attach_Seq 。  </span><span class="sxs-lookup"><span data-stu-id="f3791-111">For example, an  _Object_ can consist of a  _Message_Seq_, a  _Message_Seq_ followed by an  _Attach_Seq_, or just an  _Attach_Seq_.</span></span>
  
 <span data-ttu-id="f3791-112">_TNEF_Stream：_</span><span class="sxs-lookup"><span data-stu-id="f3791-112">_TNEF_Stream:_</span></span>
  
> <span data-ttu-id="f3791-113">**TNEF_SIGNATURE** _Key_ _对象_</span><span class="sxs-lookup"><span data-stu-id="f3791-113">**TNEF_SIGNATURE** _Key_ _Object_</span></span>
    
 <span data-ttu-id="f3791-114">_键：_</span><span class="sxs-lookup"><span data-stu-id="f3791-114">_Key:_</span></span>
  
> <span data-ttu-id="f3791-115">非零 16 位无符号整数</span><span class="sxs-lookup"><span data-stu-id="f3791-115">a nonzero 16-bit unsigned integer</span></span>
    
<span data-ttu-id="f3791-116">启用 TNEF 的传输在使用 TNEF 实现生成 TNEF 流之前生成此值。</span><span class="sxs-lookup"><span data-stu-id="f3791-116">TNEF enabled transports generate this value before using the TNEF implementation to generate a TNEF stream.</span></span>
  
 <span data-ttu-id="f3791-117">_对象：_</span><span class="sxs-lookup"><span data-stu-id="f3791-117">_Object:_</span></span>
  
>  <span data-ttu-id="f3791-118">_Message_Seq Message_Seq Attach_Seq Attach_Seq_</span><span class="sxs-lookup"><span data-stu-id="f3791-118">_Message_Seq Message_Seq Attach_Seq Attach_Seq_</span></span>
    
 <span data-ttu-id="f3791-119">_Message_Seq：_</span><span class="sxs-lookup"><span data-stu-id="f3791-119">_Message_Seq:_</span></span>
  
>  <span data-ttu-id="f3791-120">_attTnefVersion attTnefVersion Msg_Attribute_Seq attTnefVersion attMessageClass attTnefVersion attMessageClass Msg_Attribute_Seq attMessageClass attMessageClass Msg_Attribute_Seq Msg_Attribute_Seq_</span><span class="sxs-lookup"><span data-stu-id="f3791-120">_attTnefVersion attTnefVersion Msg_Attribute_Seq attTnefVersion attMessageClass attTnefVersion attMessageClass Msg_Attribute_Seq attMessageClass attMessageClass Msg_Attribute_Seq Msg_Attribute_Seq_</span></span>
    
 <span data-ttu-id="f3791-121">_attTnefVersion：_</span><span class="sxs-lookup"><span data-stu-id="f3791-121">_attTnefVersion:_</span></span>
  
> <span data-ttu-id="f3791-122">**LVL_MESSAGE ULONG (的 attTnefVersion) 0x00010000** 校验和</span><span class="sxs-lookup"><span data-stu-id="f3791-122">**LVL_MESSAGE attTnefVersion sizeof(ULONG)** **0x00010000** checksum</span></span> 
    
 <span data-ttu-id="f3791-123">_attMessageClass：_</span><span class="sxs-lookup"><span data-stu-id="f3791-123">_attMessageClass:_</span></span>
  
> <span data-ttu-id="f3791-124">**LVL_MESSAGE attMessageClass** _msg_class_length msg_class_ 校验和</span><span class="sxs-lookup"><span data-stu-id="f3791-124">**LVL_MESSAGE attMessageClass** _msg_class_length msg_class_ checksum</span></span> 
    
 <span data-ttu-id="f3791-125">_Msg_Attribute_Seq：_</span><span class="sxs-lookup"><span data-stu-id="f3791-125">_Msg_Attribute_Seq:_</span></span>
  
>  <span data-ttu-id="f3791-126">_Msg_Attribute Msg_Attribute Msg_Attribute_Seq_</span><span class="sxs-lookup"><span data-stu-id="f3791-126">_Msg_Attribute Msg_Attribute Msg_Attribute_Seq_</span></span>
    
 <span data-ttu-id="f3791-127">_Msg_Attribute：_</span><span class="sxs-lookup"><span data-stu-id="f3791-127">_Msg_Attribute:_</span></span>
  
> <span data-ttu-id="f3791-128">**LVL_MESSAGE** attribute-ID attribute-length 属性-数据校验和</span><span class="sxs-lookup"><span data-stu-id="f3791-128">**LVL_MESSAGE** attribute-ID attribute-length attribute-data checksum</span></span> 
    
<span data-ttu-id="f3791-129">Attribute-ID 是 TNEF 属性标识符之一，例如 **attSubject**。</span><span class="sxs-lookup"><span data-stu-id="f3791-129">Attribute-ID is one of the TNEF attribute identifiers, such as **attSubject**.</span></span> <span data-ttu-id="f3791-130">Attribute-length 是属性数据的长度（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="f3791-130">Attribute-length is the length in bytes of the attribute data.</span></span> <span data-ttu-id="f3791-131">Attribute-data 是与属性关联的数据。</span><span class="sxs-lookup"><span data-stu-id="f3791-131">Attribute-data is the data associated with the attribute.</span></span>
  
 <span data-ttu-id="f3791-132">_Attach_Seq：_</span><span class="sxs-lookup"><span data-stu-id="f3791-132">_Attach_Seq:_</span></span>
  
>  <span data-ttu-id="f3791-133">_attRenddata attRenddata Att_Attribute_Seq_</span><span class="sxs-lookup"><span data-stu-id="f3791-133">_attRenddata attRenddata Att_Attribute_Seq_</span></span>
    
 <span data-ttu-id="f3791-134">_attRenddata：_</span><span class="sxs-lookup"><span data-stu-id="f3791-134">_attRenddata:_</span></span>
  
> <span data-ttu-id="f3791-135">LVL_ATTACHMENT **RENDDATA 和 renddata 校验和** (**attRenddata**) 大小</span><span class="sxs-lookup"><span data-stu-id="f3791-135">**LVL_ATTACHMENT attRenddata** **sizeof(RENDDATA)** renddata checksum</span></span> 
    
<span data-ttu-id="f3791-136">Renddata 是与 **RENDDATA** 结构关联的数据，其中包含相应附件的呈现信息。</span><span class="sxs-lookup"><span data-stu-id="f3791-136">Renddata is the data associated with the **RENDDATA** structure that contains the rendering information for the corresponding attachment.</span></span> <span data-ttu-id="f3791-137">**RENDDATA** 结构在 TNEF 中定义。H 头文件。</span><span class="sxs-lookup"><span data-stu-id="f3791-137">The **RENDDATA** structure is defined in the TNEF.H header file.</span></span> 
  
 <span data-ttu-id="f3791-138">_Att_Attribute_Seq：_</span><span class="sxs-lookup"><span data-stu-id="f3791-138">_Att_Attribute_Seq:_</span></span>
  
>  <span data-ttu-id="f3791-139">_Att_Attribute Att_Attribute Att_Attribute_Seq_</span><span class="sxs-lookup"><span data-stu-id="f3791-139">_Att_Attribute Att_Attribute Att_Attribute_Seq_</span></span>
    
 <span data-ttu-id="f3791-140">_Att_Attribute：_</span><span class="sxs-lookup"><span data-stu-id="f3791-140">_Att_Attribute:_</span></span>
  
> <span data-ttu-id="f3791-141">**LVL_ATTACHMENT** attribute-ID attribute-length 属性-数据校验和</span><span class="sxs-lookup"><span data-stu-id="f3791-141">**LVL_ATTACHMENT** attribute-ID attribute-length attribute-data checksum</span></span> 
    
<span data-ttu-id="f3791-142">Attribute-ID、attribute-length 和 attribute-data 的含义与项目Msg_Attribute相同。</span><span class="sxs-lookup"><span data-stu-id="f3791-142">Attribute-ID, attribute-length, and attribute-data have the same meanings as for the Msg_Attribute item.</span></span>
  

