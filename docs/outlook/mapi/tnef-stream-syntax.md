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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32339632"
---
# <a name="tnef-stream-syntax"></a><span data-ttu-id="7482b-103">TNEF 流语法</span><span class="sxs-lookup"><span data-stu-id="7482b-103">TNEF Stream Syntax</span></span>

  
  
<span data-ttu-id="7482b-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7482b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="7482b-105">本主题提供了 Bakus-Nauer, 如 TNEF 流语法的说明。</span><span class="sxs-lookup"><span data-stu-id="7482b-105">This topic presents a Bakus-Nauer like description of the TNEF stream syntax.</span></span> <span data-ttu-id="7482b-106">在此说明中, 具有进一步定义的 nonterminal 元素以斜体表示。</span><span class="sxs-lookup"><span data-stu-id="7482b-106">In this description, nonterminal elements that have a further definition are in italics.</span></span> <span data-ttu-id="7482b-107">常量和文本项以粗体显示。</span><span class="sxs-lookup"><span data-stu-id="7482b-107">Constants and literal items are in bold.</span></span> <span data-ttu-id="7482b-108">一条线上按顺序列出元素的顺序。</span><span class="sxs-lookup"><span data-stu-id="7482b-108">Sequences of elements are listed in order on a single line.</span></span> <span data-ttu-id="7482b-109">例如, _Stream_项包含常量**TNEF_SIGNATURE**, 后跟一个_键_, 再加上一个_对象_。</span><span class="sxs-lookup"><span data-stu-id="7482b-109">For example, the  _Stream_ item consists of the constant **TNEF_SIGNATURE**, followed by a  _Key_, followed by an  _Object_.</span></span> <span data-ttu-id="7482b-110">如果某一项具有多个可能的实现, 则可选项在连续行中列出。</span><span class="sxs-lookup"><span data-stu-id="7482b-110">When an item has more than one possible implementation, the alternatives are listed on consecutive lines.</span></span> <span data-ttu-id="7482b-111">例如, 一个_对象_可以由_Message_Seq_、 _Message_Seq_后接一个_Attach_Seq_或一个_Attach_Seq_组成。</span><span class="sxs-lookup"><span data-stu-id="7482b-111">For example, an  _Object_ can consist of a  _Message_Seq_, a  _Message_Seq_ followed by an  _Attach_Seq_, or just an  _Attach_Seq_.</span></span>
  
 <span data-ttu-id="7482b-112">_TNEF_Stream:_</span><span class="sxs-lookup"><span data-stu-id="7482b-112">_TNEF_Stream:_</span></span>
  
> <span data-ttu-id="7482b-113">**TNEF_SIGNATURE**_键__对象_</span><span class="sxs-lookup"><span data-stu-id="7482b-113">**TNEF_SIGNATURE** _Key_ _Object_</span></span>
    
 <span data-ttu-id="7482b-114">_主键_</span><span class="sxs-lookup"><span data-stu-id="7482b-114">_Key:_</span></span>
  
> <span data-ttu-id="7482b-115">非零16位无符号整数</span><span class="sxs-lookup"><span data-stu-id="7482b-115">a nonzero 16-bit unsigned integer</span></span>
    
<span data-ttu-id="7482b-116">启用 tnef 的传输在使用 tnef 实现生成 TNEF 流之前生成此值。</span><span class="sxs-lookup"><span data-stu-id="7482b-116">TNEF enabled transports generate this value before using the TNEF implementation to generate a TNEF stream.</span></span>
  
 <span data-ttu-id="7482b-117">_对象_</span><span class="sxs-lookup"><span data-stu-id="7482b-117">_Object:_</span></span>
  
>  <span data-ttu-id="7482b-118">_Message_Seq Message_Seq Attach_Seq Attach_Seq_</span><span class="sxs-lookup"><span data-stu-id="7482b-118">_Message_Seq Message_Seq Attach_Seq Attach_Seq_</span></span>
    
 <span data-ttu-id="7482b-119">_Message_Seq:_</span><span class="sxs-lookup"><span data-stu-id="7482b-119">_Message_Seq:_</span></span>
  
>  <span data-ttu-id="7482b-120">_attTnefVersion attTnefVersion Msg_Attribute_Seq attTnefVersion attMessageClass attTnefVersion attMessageClass Msg_Attribute_Seq attMessageClass attMessageClass Msg_Attribute_Seq Msg_Attribute_Seq_</span><span class="sxs-lookup"><span data-stu-id="7482b-120">_attTnefVersion attTnefVersion Msg_Attribute_Seq attTnefVersion attMessageClass attTnefVersion attMessageClass Msg_Attribute_Seq attMessageClass attMessageClass Msg_Attribute_Seq Msg_Attribute_Seq_</span></span>
    
 <span data-ttu-id="7482b-121">_attTnefVersion:_</span><span class="sxs-lookup"><span data-stu-id="7482b-121">_attTnefVersion:_</span></span>
  
> <span data-ttu-id="7482b-122">**LVL_MESSAGE attTnefVersion sizeof (ULONG)\*\*\*\*0x00010000**校验和</span><span class="sxs-lookup"><span data-stu-id="7482b-122">**LVL_MESSAGE attTnefVersion sizeof(ULONG)** **0x00010000** checksum</span></span> 
    
 <span data-ttu-id="7482b-123">_attMessageClass:_</span><span class="sxs-lookup"><span data-stu-id="7482b-123">_attMessageClass:_</span></span>
  
> <span data-ttu-id="7482b-124">**LVL_MESSAGE attMessageClass**_msg_class_length msg_class_校验和</span><span class="sxs-lookup"><span data-stu-id="7482b-124">**LVL_MESSAGE attMessageClass** _msg_class_length msg_class_ checksum</span></span> 
    
 <span data-ttu-id="7482b-125">_Msg_Attribute_Seq:_</span><span class="sxs-lookup"><span data-stu-id="7482b-125">_Msg_Attribute_Seq:_</span></span>
  
>  <span data-ttu-id="7482b-126">_Msg_Attribute Msg_Attribute Msg_Attribute_Seq_</span><span class="sxs-lookup"><span data-stu-id="7482b-126">_Msg_Attribute Msg_Attribute Msg_Attribute_Seq_</span></span>
    
 <span data-ttu-id="7482b-127">_Msg_Attribute:_</span><span class="sxs-lookup"><span data-stu-id="7482b-127">_Msg_Attribute:_</span></span>
  
> <span data-ttu-id="7482b-128">**LVL_MESSAGE**属性 ID 属性-长度属性-数据校验和</span><span class="sxs-lookup"><span data-stu-id="7482b-128">**LVL_MESSAGE** attribute-ID attribute-length attribute-data checksum</span></span> 
    
<span data-ttu-id="7482b-129">属性 ID 是 TNEF 属性标识符之一, 例如**attSubject**。</span><span class="sxs-lookup"><span data-stu-id="7482b-129">Attribute-ID is one of the TNEF attribute identifiers, such as **attSubject**.</span></span> <span data-ttu-id="7482b-130">属性-长度是属性数据的长度 (以字节为单位)。</span><span class="sxs-lookup"><span data-stu-id="7482b-130">Attribute-length is the length in bytes of the attribute data.</span></span> <span data-ttu-id="7482b-131">属性 data 是与属性相关联的数据。</span><span class="sxs-lookup"><span data-stu-id="7482b-131">Attribute-data is the data associated with the attribute.</span></span>
  
 <span data-ttu-id="7482b-132">_Attach_Seq:_</span><span class="sxs-lookup"><span data-stu-id="7482b-132">_Attach_Seq:_</span></span>
  
>  <span data-ttu-id="7482b-133">_attRenddata attRenddata Att_Attribute_Seq_</span><span class="sxs-lookup"><span data-stu-id="7482b-133">_attRenddata attRenddata Att_Attribute_Seq_</span></span>
    
 <span data-ttu-id="7482b-134">_attRenddata:_</span><span class="sxs-lookup"><span data-stu-id="7482b-134">_attRenddata:_</span></span>
  
> <span data-ttu-id="7482b-135">**LVL_ATTACHMENT attRenddata\*\*\*\*sizeof (RENDDATA)** RENDDATA 校验和</span><span class="sxs-lookup"><span data-stu-id="7482b-135">**LVL_ATTACHMENT attRenddata** **sizeof(RENDDATA)** renddata checksum</span></span> 
    
<span data-ttu-id="7482b-136">Renddata 是与**Renddata**结构关联的数据, 其中包含相应附件的呈现信息。</span><span class="sxs-lookup"><span data-stu-id="7482b-136">Renddata is the data associated with the **RENDDATA** structure that contains the rendering information for the corresponding attachment.</span></span> <span data-ttu-id="7482b-137">**RENDDATA**结构是在 TNEF 中定义的。H 头文件。</span><span class="sxs-lookup"><span data-stu-id="7482b-137">The **RENDDATA** structure is defined in the TNEF.H header file.</span></span> 
  
 <span data-ttu-id="7482b-138">_Att_Attribute_Seq:_</span><span class="sxs-lookup"><span data-stu-id="7482b-138">_Att_Attribute_Seq:_</span></span>
  
>  <span data-ttu-id="7482b-139">_Att_Attribute Att_Attribute Att_Attribute_Seq_</span><span class="sxs-lookup"><span data-stu-id="7482b-139">_Att_Attribute Att_Attribute Att_Attribute_Seq_</span></span>
    
 <span data-ttu-id="7482b-140">_Att_Attribute:_</span><span class="sxs-lookup"><span data-stu-id="7482b-140">_Att_Attribute:_</span></span>
  
> <span data-ttu-id="7482b-141">**LVL_ATTACHMENT**属性 ID 属性-长度属性-数据校验和</span><span class="sxs-lookup"><span data-stu-id="7482b-141">**LVL_ATTACHMENT** attribute-ID attribute-length attribute-data checksum</span></span> 
    
<span data-ttu-id="7482b-142">属性 ID、属性长度和属性数据与 Msg_Attribute 项具有相同的含义。</span><span class="sxs-lookup"><span data-stu-id="7482b-142">Attribute-ID, attribute-length, and attribute-data have the same meanings as for the Msg_Attribute item.</span></span>
  

