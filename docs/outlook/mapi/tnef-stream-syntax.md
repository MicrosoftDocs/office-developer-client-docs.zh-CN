---
title: TNEF 流语法
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 1353d494-c266-4715-afe7-14543a1bbe1b
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: cbaf37415608dd1d79a06be65b34632f2b4afc89
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779002"
---
# <a name="tnef-stream-syntax"></a><span data-ttu-id="f57bd-103">TNEF 流语法</span><span class="sxs-lookup"><span data-stu-id="f57bd-103">TNEF Stream Syntax</span></span>

  
  
<span data-ttu-id="f57bd-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="f57bd-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="f57bd-105">本主题提供类似的 TNEF 流语法说明 Bakus-诺尔。</span><span class="sxs-lookup"><span data-stu-id="f57bd-105">This topic presents a Bakus-Nauer like description of the TNEF stream syntax.</span></span> <span data-ttu-id="f57bd-106">在此说明，有进一步定义的终结元素是斜体。</span><span class="sxs-lookup"><span data-stu-id="f57bd-106">In this description, nonterminal elements that have a further definition are in italics.</span></span> <span data-ttu-id="f57bd-107">常量和文字项目是以粗体显示。</span><span class="sxs-lookup"><span data-stu-id="f57bd-107">Constants and literal items are in bold.</span></span> <span data-ttu-id="f57bd-108">在同一行顺序列出了序列的元素。</span><span class="sxs-lookup"><span data-stu-id="f57bd-108">Sequences of elements are listed in order on a single line.</span></span> <span data-ttu-id="f57bd-109">例如，_流_项包含常量**TNEF_SIGNATURE**后, 跟一个_键_后, 跟一个_对象_。</span><span class="sxs-lookup"><span data-stu-id="f57bd-109">For example, the  _Stream_ item consists of the constant **TNEF_SIGNATURE**, followed by a  _Key_, followed by an  _Object_.</span></span> <span data-ttu-id="f57bd-110">当项目具有多个可能的实现时，列出连续线上。</span><span class="sxs-lookup"><span data-stu-id="f57bd-110">When an item has more than one possible implementation, the alternatives are listed on consecutive lines.</span></span> <span data-ttu-id="f57bd-111">例如， _Message_Seq_后, 跟_Attach_Seq_或只_Attach_Seq_ _Message_Seq_可以包括一个_对象_。</span><span class="sxs-lookup"><span data-stu-id="f57bd-111">For example, an  _Object_ can consist of a  _Message_Seq_, a  _Message_Seq_ followed by an  _Attach_Seq_, or just an  _Attach_Seq_.</span></span>
  
 <span data-ttu-id="f57bd-112">_TNEF_Stream:_</span><span class="sxs-lookup"><span data-stu-id="f57bd-112">_TNEF_Stream:_</span></span>
  
> <span data-ttu-id="f57bd-113">**TNEF_SIGNATURE**_键__对象_</span><span class="sxs-lookup"><span data-stu-id="f57bd-113">**TNEF_SIGNATURE** _Key_ _Object_</span></span>
    
 <span data-ttu-id="f57bd-114">_键：_</span><span class="sxs-lookup"><span data-stu-id="f57bd-114">_Key:_</span></span>
  
> <span data-ttu-id="f57bd-115">非零值的 16 位无符号的整数</span><span class="sxs-lookup"><span data-stu-id="f57bd-115">a nonzero 16-bit unsigned integer</span></span>
    
<span data-ttu-id="f57bd-116">TNEF 启用传输使用 TNEF 实现生成 TNEF 流之前生成此值。</span><span class="sxs-lookup"><span data-stu-id="f57bd-116">TNEF enabled transports generate this value before using the TNEF implementation to generate a TNEF stream.</span></span>
  
 <span data-ttu-id="f57bd-117">_对象：_</span><span class="sxs-lookup"><span data-stu-id="f57bd-117">_Object:_</span></span>
  
>  <span data-ttu-id="f57bd-118">_Message_Seq Message_Seq Attach_Seq Attach_Seq_</span><span class="sxs-lookup"><span data-stu-id="f57bd-118">_Message_Seq Message_Seq Attach_Seq Attach_Seq_</span></span>
    
 <span data-ttu-id="f57bd-119">_Message_Seq:_</span><span class="sxs-lookup"><span data-stu-id="f57bd-119">_Message_Seq:_</span></span>
  
>  <span data-ttu-id="f57bd-120">_attTnefVersion attTnefVersion Msg_Attribute_Seq attTnefVersion attMessageClass attTnefVersion attMessageClass Msg_Attribute_Seq attMessageClass attMessageClass Msg_Attribute_Seq Msg_Attribute_Seq_</span><span class="sxs-lookup"><span data-stu-id="f57bd-120">_attTnefVersion attTnefVersion Msg_Attribute_Seq attTnefVersion attMessageClass attTnefVersion attMessageClass Msg_Attribute_Seq attMessageClass attMessageClass Msg_Attribute_Seq Msg_Attribute_Seq_</span></span>
    
 <span data-ttu-id="f57bd-121">_attTnefVersion:_</span><span class="sxs-lookup"><span data-stu-id="f57bd-121">_attTnefVersion:_</span></span>
  
> <span data-ttu-id="f57bd-122">**LVL_MESSAGE attTnefVersion sizeof(ULONG)****0x00010000**校验和</span><span class="sxs-lookup"><span data-stu-id="f57bd-122">**LVL_MESSAGE attTnefVersion sizeof(ULONG)** **0x00010000** checksum</span></span> 
    
 <span data-ttu-id="f57bd-123">_attMessageClass:_</span><span class="sxs-lookup"><span data-stu-id="f57bd-123">_attMessageClass:_</span></span>
  
> <span data-ttu-id="f57bd-124">**LVL_MESSAGE attMessageClass**_msg_class_length msg_class_校验和</span><span class="sxs-lookup"><span data-stu-id="f57bd-124">**LVL_MESSAGE attMessageClass** _msg_class_length msg_class_ checksum</span></span> 
    
 <span data-ttu-id="f57bd-125">_Msg_Attribute_Seq:_</span><span class="sxs-lookup"><span data-stu-id="f57bd-125">_Msg_Attribute_Seq:_</span></span>
  
>  <span data-ttu-id="f57bd-126">_Msg_Attribute Msg_Attribute Msg_Attribute_Seq_</span><span class="sxs-lookup"><span data-stu-id="f57bd-126">_Msg_Attribute Msg_Attribute Msg_Attribute_Seq_</span></span>
    
 <span data-ttu-id="f57bd-127">_Msg_Attribute:_</span><span class="sxs-lookup"><span data-stu-id="f57bd-127">_Msg_Attribute:_</span></span>
  
> <span data-ttu-id="f57bd-128">**LVL_MESSAGE**属性 ID 属性长度属性数据校验和</span><span class="sxs-lookup"><span data-stu-id="f57bd-128">**LVL_MESSAGE** attribute-ID attribute-length attribute-data checksum</span></span> 
    
<span data-ttu-id="f57bd-129">属性 ID 是 TNEF 属性标识符，如**attSubject**之一。</span><span class="sxs-lookup"><span data-stu-id="f57bd-129">Attribute-ID is one of the TNEF attribute identifiers, such as **attSubject**.</span></span> <span data-ttu-id="f57bd-130">属性长度是以字节为单位的属性数据的长度。</span><span class="sxs-lookup"><span data-stu-id="f57bd-130">Attribute-length is the length in bytes of the attribute data.</span></span> <span data-ttu-id="f57bd-131">属性数据是与属性关联的数据。</span><span class="sxs-lookup"><span data-stu-id="f57bd-131">Attribute-data is the data associated with the attribute.</span></span>
  
 <span data-ttu-id="f57bd-132">_Attach_Seq:_</span><span class="sxs-lookup"><span data-stu-id="f57bd-132">_Attach_Seq:_</span></span>
  
>  <span data-ttu-id="f57bd-133">_attRenddata attRenddata Att_Attribute_Seq_</span><span class="sxs-lookup"><span data-stu-id="f57bd-133">_attRenddata attRenddata Att_Attribute_Seq_</span></span>
    
 <span data-ttu-id="f57bd-134">_attRenddata:_</span><span class="sxs-lookup"><span data-stu-id="f57bd-134">_attRenddata:_</span></span>
  
> <span data-ttu-id="f57bd-135">**LVL_ATTACHMENT attRenddata****sizeof(RENDDATA)** renddata 校验和</span><span class="sxs-lookup"><span data-stu-id="f57bd-135">**LVL_ATTACHMENT attRenddata** **sizeof(RENDDATA)** renddata checksum</span></span> 
    
<span data-ttu-id="f57bd-136">Renddata 是**RENDDATA**结构，其中包含相应的附件的呈现信息相关联的数据。</span><span class="sxs-lookup"><span data-stu-id="f57bd-136">Renddata is the data associated with the **RENDDATA** structure that contains the rendering information for the corresponding attachment.</span></span> <span data-ttu-id="f57bd-137">**RENDDATA**结构 TNEF 中定义。H 头文件。</span><span class="sxs-lookup"><span data-stu-id="f57bd-137">The **RENDDATA** structure is defined in the TNEF.H header file.</span></span> 
  
 <span data-ttu-id="f57bd-138">_Att_Attribute_Seq:_</span><span class="sxs-lookup"><span data-stu-id="f57bd-138">_Att_Attribute_Seq:_</span></span>
  
>  <span data-ttu-id="f57bd-139">_Att_Attribute Att_Attribute Att_Attribute_Seq_</span><span class="sxs-lookup"><span data-stu-id="f57bd-139">_Att_Attribute Att_Attribute Att_Attribute_Seq_</span></span>
    
 <span data-ttu-id="f57bd-140">_Att_Attribute:_</span><span class="sxs-lookup"><span data-stu-id="f57bd-140">_Att_Attribute:_</span></span>
  
> <span data-ttu-id="f57bd-141">**LVL_ATTACHMENT**属性 ID 属性长度属性数据校验和</span><span class="sxs-lookup"><span data-stu-id="f57bd-141">**LVL_ATTACHMENT** attribute-ID attribute-length attribute-data checksum</span></span> 
    
<span data-ttu-id="f57bd-142">属性 ID、 长度、 属性和属性数据，其含义相同 Msg_Attribute 项目。</span><span class="sxs-lookup"><span data-stu-id="f57bd-142">Attribute-ID, attribute-length, and attribute-data have the same meanings as for the Msg_Attribute item.</span></span>
  

