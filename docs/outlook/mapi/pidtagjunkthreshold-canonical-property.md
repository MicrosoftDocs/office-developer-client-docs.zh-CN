---
title: PidTagJunkThreshold 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagJunkThreshold
api_type:
- HeaderDef
ms.assetid: 8067e2b5-02df-4b96-8f66-509f5a48c8aa
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 0f8484e195b1cda8e1d633133cdff89c571d8ecd
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777784"
---
# <a name="pidtagjunkthreshold-canonical-property"></a><span data-ttu-id="5af73-103">PidTagJunkThreshold 规范属性</span><span class="sxs-lookup"><span data-stu-id="5af73-103">PidTagJunkThreshold Canonical Property</span></span>

  
  
<span data-ttu-id="5af73-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="5af73-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="5af73-105">力度指示应将传入邮件发送到垃圾邮件文件夹。</span><span class="sxs-lookup"><span data-stu-id="5af73-105">Indicates how aggressively incoming mail should be sent to the Junk Email folder.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="5af73-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="5af73-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="5af73-107">PR_JUNK_THRESHOLD</span><span class="sxs-lookup"><span data-stu-id="5af73-107">PR_JUNK_THRESHOLD</span></span>  <br/> |
|<span data-ttu-id="5af73-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="5af73-108">Identifier:</span></span>  <br/> |<span data-ttu-id="5af73-109">0x6101</span><span class="sxs-lookup"><span data-stu-id="5af73-109">0x6101</span></span>  <br/> |
|<span data-ttu-id="5af73-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="5af73-110">Data type:</span></span>  <br/> |<span data-ttu-id="5af73-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="5af73-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="5af73-112">区域：</span><span class="sxs-lookup"><span data-stu-id="5af73-112">Area:</span></span>  <br/> |<span data-ttu-id="5af73-113">垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="5af73-113">Spam</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="5af73-114">备注</span><span class="sxs-lookup"><span data-stu-id="5af73-114">Remarks</span></span>

<span data-ttu-id="5af73-115">此属性对应于高 / 低/无筛选设置。</span><span class="sxs-lookup"><span data-stu-id="5af73-115">This property corresponds to the high / low / none filter setting.</span></span> <span data-ttu-id="5af73-116">"0xFFFFFFFF"的值表示的垃圾邮件筛选不应将应用，但仍必须应用阻止列表。</span><span class="sxs-lookup"><span data-stu-id="5af73-116">A value of "0xFFFFFFFF" indicates that spam filtering should not be applied, however block lists must still be applied.</span></span> <span data-ttu-id="5af73-117">"0x80000000"值表示的所有邮件是除这些来自受信任的发件人列表上的发件人的邮件的垃圾邮件或发送到受信任的收件人列表上的收件人。</span><span class="sxs-lookup"><span data-stu-id="5af73-117">A value of "0x80000000" indicates that all mail is spam except those messages from senders on the trusted senders list or sent to recipients on the trusted recipients list.</span></span> <span data-ttu-id="5af73-118">参数的值如下所示：</span><span class="sxs-lookup"><span data-stu-id="5af73-118">Values for this are as follows:</span></span>
  
|<span data-ttu-id="5af73-119">**值**</span><span class="sxs-lookup"><span data-stu-id="5af73-119">**Value**</span></span>|<span data-ttu-id="5af73-120">**说明**</span><span class="sxs-lookup"><span data-stu-id="5af73-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5af73-121">0xFFFFFFFF</span><span class="sxs-lookup"><span data-stu-id="5af73-121">0xFFFFFFFF</span></span>  <br/> |<span data-ttu-id="5af73-122">无垃圾邮件筛选</span><span class="sxs-lookup"><span data-stu-id="5af73-122">No spam filtering</span></span>  <br/> |
|<span data-ttu-id="5af73-123">0x00000006</span><span class="sxs-lookup"><span data-stu-id="5af73-123">0x00000006</span></span>  <br/> |<span data-ttu-id="5af73-124">低垃圾邮件筛选</span><span class="sxs-lookup"><span data-stu-id="5af73-124">Low spam filtering</span></span>  <br/> |
|<span data-ttu-id="5af73-125">0x00000003</span><span class="sxs-lookup"><span data-stu-id="5af73-125">0x00000003</span></span>  <br/> |<span data-ttu-id="5af73-126">高垃圾邮件筛选</span><span class="sxs-lookup"><span data-stu-id="5af73-126">High spam filtering</span></span>  <br/> |
|<span data-ttu-id="5af73-127">0x80000000</span><span class="sxs-lookup"><span data-stu-id="5af73-127">0x80000000</span></span>  <br/> |<span data-ttu-id="5af73-128">仅受信任的列表</span><span class="sxs-lookup"><span data-stu-id="5af73-128">Trusted Lists Only</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="5af73-129">相关资源</span><span class="sxs-lookup"><span data-stu-id="5af73-129">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="5af73-130">协议规范</span><span class="sxs-lookup"><span data-stu-id="5af73-130">Protocol specifications</span></span>

<span data-ttu-id="5af73-131">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="5af73-131">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="5af73-132">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="5af73-132">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="5af73-133">[[MS OXCSPAM]](http://msdn.microsoft.com/library/522f8587-4aed-4cd6-831b-40bd87862189%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="5af73-133">[[MS-OXCSPAM]](http://msdn.microsoft.com/library/522f8587-4aed-4cd6-831b-40bd87862189%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="5af73-134">允许处理的允许/阻止列表，并确定的垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="5af73-134">Enables the handling of allow/block lists and the determination of junk email messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="5af73-135">头文件</span><span class="sxs-lookup"><span data-stu-id="5af73-135">Header files</span></span>

<span data-ttu-id="5af73-136">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="5af73-136">Mapidefs.h</span></span>
  
> <span data-ttu-id="5af73-137">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="5af73-137">Provides data type definitions.</span></span>
    
<span data-ttu-id="5af73-138">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="5af73-138">Mapitags.h</span></span>
  
> <span data-ttu-id="5af73-139">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="5af73-139">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="5af73-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5af73-140">See also</span></span>



[<span data-ttu-id="5af73-141">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="5af73-141">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="5af73-142">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="5af73-142">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="5af73-143">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="5af73-143">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="5af73-144">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="5af73-144">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

