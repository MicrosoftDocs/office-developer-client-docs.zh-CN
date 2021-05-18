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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 078dfcc7c24870cf95a2a4b2385c34fbeb64fac0
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32326850"
---
# <a name="pidtagjunkthreshold-canonical-property"></a><span data-ttu-id="04e4a-103">PidTagJunkThreshold 规范属性</span><span class="sxs-lookup"><span data-stu-id="04e4a-103">PidTagJunkThreshold Canonical Property</span></span>

  
  
<span data-ttu-id="04e4a-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="04e4a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="04e4a-105">指示应如何将主动传入的邮件发送到"垃圾邮件"文件夹。</span><span class="sxs-lookup"><span data-stu-id="04e4a-105">Indicates how aggressively incoming mail should be sent to the Junk Email folder.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="04e4a-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="04e4a-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="04e4a-107">PR_JUNK_THRESHOLD</span><span class="sxs-lookup"><span data-stu-id="04e4a-107">PR_JUNK_THRESHOLD</span></span>  <br/> |
|<span data-ttu-id="04e4a-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="04e4a-108">Identifier:</span></span>  <br/> |<span data-ttu-id="04e4a-109">0x6101</span><span class="sxs-lookup"><span data-stu-id="04e4a-109">0x6101</span></span>  <br/> |
|<span data-ttu-id="04e4a-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="04e4a-110">Data type:</span></span>  <br/> |<span data-ttu-id="04e4a-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="04e4a-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="04e4a-112">区域：</span><span class="sxs-lookup"><span data-stu-id="04e4a-112">Area:</span></span>  <br/> |<span data-ttu-id="04e4a-113">垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="04e4a-113">Spam</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="04e4a-114">备注</span><span class="sxs-lookup"><span data-stu-id="04e4a-114">Remarks</span></span>

<span data-ttu-id="04e4a-115">此属性对应于高/低/无筛选器设置。</span><span class="sxs-lookup"><span data-stu-id="04e4a-115">This property corresponds to the high / low / none filter setting.</span></span> <span data-ttu-id="04e4a-116">值"0xFFFFFFFF"表示不应应用垃圾邮件筛选，但是仍必须应用阻止列表。</span><span class="sxs-lookup"><span data-stu-id="04e4a-116">A value of "0xFFFFFFFF" indicates that spam filtering should not be applied, however block lists must still be applied.</span></span> <span data-ttu-id="04e4a-117">值"0x80000000"表示所有邮件都是垃圾邮件，但来自受信任发件人列表发件人的邮件或发送到受信任收件人列表上的收件人的邮件除外。</span><span class="sxs-lookup"><span data-stu-id="04e4a-117">A value of "0x80000000" indicates that all mail is spam except those messages from senders on the trusted senders list or sent to recipients on the trusted recipients list.</span></span> <span data-ttu-id="04e4a-118">其值如下所示：</span><span class="sxs-lookup"><span data-stu-id="04e4a-118">Values for this are as follows:</span></span>
  
|<span data-ttu-id="04e4a-119">**值**</span><span class="sxs-lookup"><span data-stu-id="04e4a-119">**Value**</span></span>|<span data-ttu-id="04e4a-120">**说明**</span><span class="sxs-lookup"><span data-stu-id="04e4a-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="04e4a-121">0xFFFFFFFF</span><span class="sxs-lookup"><span data-stu-id="04e4a-121">0xFFFFFFFF</span></span>  <br/> |<span data-ttu-id="04e4a-122">无垃圾邮件筛选</span><span class="sxs-lookup"><span data-stu-id="04e4a-122">No spam filtering</span></span>  <br/> |
|<span data-ttu-id="04e4a-123">0x00000006</span><span class="sxs-lookup"><span data-stu-id="04e4a-123">0x00000006</span></span>  <br/> |<span data-ttu-id="04e4a-124">低垃圾邮件筛选</span><span class="sxs-lookup"><span data-stu-id="04e4a-124">Low spam filtering</span></span>  <br/> |
|<span data-ttu-id="04e4a-125">0x00000003</span><span class="sxs-lookup"><span data-stu-id="04e4a-125">0x00000003</span></span>  <br/> |<span data-ttu-id="04e4a-126">高垃圾邮件筛选</span><span class="sxs-lookup"><span data-stu-id="04e4a-126">High spam filtering</span></span>  <br/> |
|<span data-ttu-id="04e4a-127">0x80000000</span><span class="sxs-lookup"><span data-stu-id="04e4a-127">0x80000000</span></span>  <br/> |<span data-ttu-id="04e4a-128">仅受信任列表</span><span class="sxs-lookup"><span data-stu-id="04e4a-128">Trusted Lists Only</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="04e4a-129">相关资源</span><span class="sxs-lookup"><span data-stu-id="04e4a-129">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="04e4a-130">协议规范</span><span class="sxs-lookup"><span data-stu-id="04e4a-130">Protocol specifications</span></span>

<span data-ttu-id="04e4a-131">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="04e4a-131">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="04e4a-132">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="04e4a-132">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="04e4a-133">[[MS-OXCSPAM]](https://msdn.microsoft.com/library/522f8587-4aed-4cd6-831b-40bd87862189%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="04e4a-133">[[MS-OXCSPAM]](https://msdn.microsoft.com/library/522f8587-4aed-4cd6-831b-40bd87862189%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="04e4a-134">允许/阻止列表的处理和垃圾邮件的确定。</span><span class="sxs-lookup"><span data-stu-id="04e4a-134">Enables the handling of allow/block lists and the determination of junk email messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="04e4a-135">头文件</span><span class="sxs-lookup"><span data-stu-id="04e4a-135">Header files</span></span>

<span data-ttu-id="04e4a-136">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="04e4a-136">Mapidefs.h</span></span>
  
> <span data-ttu-id="04e4a-137">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="04e4a-137">Provides data type definitions.</span></span>
    
<span data-ttu-id="04e4a-138">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="04e4a-138">Mapitags.h</span></span>
  
> <span data-ttu-id="04e4a-139">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="04e4a-139">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="04e4a-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="04e4a-140">See also</span></span>



[<span data-ttu-id="04e4a-141">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="04e4a-141">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="04e4a-142">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="04e4a-142">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="04e4a-143">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="04e4a-143">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="04e4a-144">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="04e4a-144">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

