---
title: PidNameXSharingFlavor 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidNameXSharingFlavor
api_type:
- COM
ms.assetid: 7757fde1-564b-4f3a-9b9e-f80a143690ea
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 1f07a11c47c6785bc9a166f11bde8f2e5ef464a0
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777255"
---
# <a name="pidnamexsharingflavor-canonical-property"></a><span data-ttu-id="d784b-103">PidNameXSharingFlavor 规范属性</span><span class="sxs-lookup"><span data-stu-id="d784b-103">PidNameXSharingFlavor Canonical Property</span></span>

  
  
<span data-ttu-id="d784b-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="d784b-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="d784b-105">代表**dispidSharingFlavor** ([PidLidSharingFlavor](pidlidsharingflavor-canonical-property.md)) 属性的值。</span><span class="sxs-lookup"><span data-stu-id="d784b-105">Represents the value of the **dispidSharingFlavor** ([PidLidSharingFlavor](pidlidsharingflavor-canonical-property.md)) property.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="d784b-106">友好名称：</span><span class="sxs-lookup"><span data-stu-id="d784b-106">Friendly names:</span></span>  <br/> |<span data-ttu-id="d784b-107">无</span><span class="sxs-lookup"><span data-stu-id="d784b-107">None</span></span>  <br/> |
|<span data-ttu-id="d784b-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="d784b-108">Property set:</span></span>  <br/> |<span data-ttu-id="d784b-109">PS_INTERNET_HEADERS</span><span class="sxs-lookup"><span data-stu-id="d784b-109">PS_INTERNET_HEADERS</span></span>  <br/> |
|<span data-ttu-id="d784b-110">属性名称：</span><span class="sxs-lookup"><span data-stu-id="d784b-110">Property name:</span></span>  <br/> |<span data-ttu-id="d784b-111">X 共享风格</span><span class="sxs-lookup"><span data-stu-id="d784b-111">X-Sharing-Flavor</span></span>  <br/> |
|<span data-ttu-id="d784b-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="d784b-112">Data type:</span></span>  <br/> |<span data-ttu-id="d784b-113">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="d784b-113">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="d784b-114">区域：</span><span class="sxs-lookup"><span data-stu-id="d784b-114">Area:</span></span>  <br/> |<span data-ttu-id="d784b-115">共享</span><span class="sxs-lookup"><span data-stu-id="d784b-115">Sharing</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="d784b-116">说明</span><span class="sxs-lookup"><span data-stu-id="d784b-116">Remarks</span></span>

<span data-ttu-id="d784b-117">**DispidSharingFlavor**属性必须为下列值之一。</span><span class="sxs-lookup"><span data-stu-id="d784b-117">The **dispidSharingFlavor** property must be one of the following values.</span></span> 
  
|<span data-ttu-id="d784b-118">**值**</span><span class="sxs-lookup"><span data-stu-id="d784b-118">**Value**</span></span>|<span data-ttu-id="d784b-119">**类型的共享邮件**</span><span class="sxs-lookup"><span data-stu-id="d784b-119">**Type of Sharing Message**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d784b-120">0x00020310</span><span class="sxs-lookup"><span data-stu-id="d784b-120">0x00020310</span></span>  <br/> |<span data-ttu-id="d784b-121">特殊文件夹的共享邀请。</span><span class="sxs-lookup"><span data-stu-id="d784b-121">A sharing invitation for a special folder.</span></span>  <br/> |
|<span data-ttu-id="d784b-122">0x00000310</span><span class="sxs-lookup"><span data-stu-id="d784b-122">0x00000310</span></span>  <br/> |<span data-ttu-id="d784b-123">不是一个特殊文件夹的文件夹共享邀请。</span><span class="sxs-lookup"><span data-stu-id="d784b-123">A sharing invitation for a folder that is not a special folder.</span></span>  <br/> |
|<span data-ttu-id="d784b-124">0x00020500</span><span class="sxs-lookup"><span data-stu-id="d784b-124">0x00020500</span></span>  <br/> |<span data-ttu-id="d784b-125">共享请求。</span><span class="sxs-lookup"><span data-stu-id="d784b-125">A sharing request.</span></span>  <br/> |
|<span data-ttu-id="d784b-126">0x00020710</span><span class="sxs-lookup"><span data-stu-id="d784b-126">0x00020710</span></span>  <br/> |<span data-ttu-id="d784b-127">这两个共享邀请的特殊文件夹和共享请求收件人的等效的特殊文件夹。</span><span class="sxs-lookup"><span data-stu-id="d784b-127">Both a sharing invitation for a special folder and a sharing request for the recipient's equivalent special folder.</span></span>  <br/> |
|<span data-ttu-id="d784b-128">0x00025100</span><span class="sxs-lookup"><span data-stu-id="d784b-128">0x00025100</span></span>  <br/> |<span data-ttu-id="d784b-129">一个共享响应，其中将拒绝请求。</span><span class="sxs-lookup"><span data-stu-id="d784b-129">A sharing response that denies a request.</span></span>  <br/> |
|<span data-ttu-id="d784b-130">0x00023310</span><span class="sxs-lookup"><span data-stu-id="d784b-130">0x00023310</span></span>  <br/> |<span data-ttu-id="d784b-131">接受的请求 （还一类型的共享邀请） 共享响应。</span><span class="sxs-lookup"><span data-stu-id="d784b-131">A sharing response that accepts a request (also a type of sharing invitation).</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="d784b-132">相关资源</span><span class="sxs-lookup"><span data-stu-id="d784b-132">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="d784b-133">协议规范</span><span class="sxs-lookup"><span data-stu-id="d784b-133">Protocol specifications</span></span>

<span data-ttu-id="d784b-134">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="d784b-134">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="d784b-135">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="d784b-135">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="d784b-136">[[MS OXSHARE]](http://msdn.microsoft.com/library/e4e5bd27-d5e0-43f9-a6ea-550876724f3d%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="d784b-136">[[MS-OXSHARE]](http://msdn.microsoft.com/library/e4e5bd27-d5e0-43f9-a6ea-550876724f3d%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="d784b-137">共享客户端之间的邮箱文件夹。</span><span class="sxs-lookup"><span data-stu-id="d784b-137">Shares mailbox folders between clients.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="d784b-138">头文件</span><span class="sxs-lookup"><span data-stu-id="d784b-138">Header files</span></span>

<span data-ttu-id="d784b-139">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="d784b-139">Mapidefs.h</span></span>
  
> <span data-ttu-id="d784b-140">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="d784b-140">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="d784b-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d784b-141">See also</span></span>



[<span data-ttu-id="d784b-142">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="d784b-142">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="d784b-143">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="d784b-143">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="d784b-144">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="d784b-144">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="d784b-145">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="d784b-145">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

