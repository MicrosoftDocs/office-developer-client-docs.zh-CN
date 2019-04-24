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
ms.openlocfilehash: d2afa598bf9b7949f2e9142611570ebbd048f7e3
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32360884"
---
# <a name="pidnamexsharingflavor-canonical-property"></a><span data-ttu-id="3f5d4-103">PidNameXSharingFlavor 规范属性</span><span class="sxs-lookup"><span data-stu-id="3f5d4-103">PidNameXSharingFlavor Canonical Property</span></span>

  
  
<span data-ttu-id="3f5d4-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="3f5d4-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="3f5d4-105">表示**dispidSharingFlavor** ([PidLidSharingFlavor](pidlidsharingflavor-canonical-property.md)) 属性的值。</span><span class="sxs-lookup"><span data-stu-id="3f5d4-105">Represents the value of the **dispidSharingFlavor** ([PidLidSharingFlavor](pidlidsharingflavor-canonical-property.md)) property.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="3f5d4-106">友好名称:</span><span class="sxs-lookup"><span data-stu-id="3f5d4-106">Friendly names:</span></span>  <br/> |<span data-ttu-id="3f5d4-107">无</span><span class="sxs-lookup"><span data-stu-id="3f5d4-107">None</span></span>  <br/> |
|<span data-ttu-id="3f5d4-108">属性集:</span><span class="sxs-lookup"><span data-stu-id="3f5d4-108">Property set:</span></span>  <br/> |<span data-ttu-id="3f5d4-109">PS_INTERNET_HEADERS</span><span class="sxs-lookup"><span data-stu-id="3f5d4-109">PS_INTERNET_HEADERS</span></span>  <br/> |
|<span data-ttu-id="3f5d4-110">属性名称:</span><span class="sxs-lookup"><span data-stu-id="3f5d4-110">Property name:</span></span>  <br/> |<span data-ttu-id="3f5d4-111">X 共享-风格</span><span class="sxs-lookup"><span data-stu-id="3f5d4-111">X-Sharing-Flavor</span></span>  <br/> |
|<span data-ttu-id="3f5d4-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="3f5d4-112">Data type:</span></span>  <br/> |<span data-ttu-id="3f5d4-113">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="3f5d4-113">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="3f5d4-114">区域：</span><span class="sxs-lookup"><span data-stu-id="3f5d4-114">Area:</span></span>  <br/> |<span data-ttu-id="3f5d4-115">共享</span><span class="sxs-lookup"><span data-stu-id="3f5d4-115">Sharing</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="3f5d4-116">注解</span><span class="sxs-lookup"><span data-stu-id="3f5d4-116">Remarks</span></span>

<span data-ttu-id="3f5d4-117">**dispidSharingFlavor**属性必须为下列值之一。</span><span class="sxs-lookup"><span data-stu-id="3f5d4-117">The **dispidSharingFlavor** property must be one of the following values.</span></span> 
  
|<span data-ttu-id="3f5d4-118">**值**</span><span class="sxs-lookup"><span data-stu-id="3f5d4-118">**Value**</span></span>|<span data-ttu-id="3f5d4-119">**共享邮件的类型**</span><span class="sxs-lookup"><span data-stu-id="3f5d4-119">**Type of Sharing Message**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3f5d4-120">0x00020310</span><span class="sxs-lookup"><span data-stu-id="3f5d4-120">0x00020310</span></span>  <br/> |<span data-ttu-id="3f5d4-121">特殊文件夹的共享邀请。</span><span class="sxs-lookup"><span data-stu-id="3f5d4-121">A sharing invitation for a special folder.</span></span>  <br/> |
|<span data-ttu-id="3f5d4-122">0x00000310</span><span class="sxs-lookup"><span data-stu-id="3f5d4-122">0x00000310</span></span>  <br/> |<span data-ttu-id="3f5d4-123">对不是特殊文件夹的文件夹的共享邀请。</span><span class="sxs-lookup"><span data-stu-id="3f5d4-123">A sharing invitation for a folder that is not a special folder.</span></span>  <br/> |
|<span data-ttu-id="3f5d4-124">0x00020500</span><span class="sxs-lookup"><span data-stu-id="3f5d4-124">0x00020500</span></span>  <br/> |<span data-ttu-id="3f5d4-125">共享请求。</span><span class="sxs-lookup"><span data-stu-id="3f5d4-125">A sharing request.</span></span>  <br/> |
|<span data-ttu-id="3f5d4-126">0x00020710</span><span class="sxs-lookup"><span data-stu-id="3f5d4-126">0x00020710</span></span>  <br/> |<span data-ttu-id="3f5d4-127">一个特殊文件夹的共享邀请和收件人的等效特殊文件夹的共享请求。</span><span class="sxs-lookup"><span data-stu-id="3f5d4-127">Both a sharing invitation for a special folder and a sharing request for the recipient's equivalent special folder.</span></span>  <br/> |
|<span data-ttu-id="3f5d4-128">0x00025100</span><span class="sxs-lookup"><span data-stu-id="3f5d4-128">0x00025100</span></span>  <br/> |<span data-ttu-id="3f5d4-129">拒绝请求的共享响应。</span><span class="sxs-lookup"><span data-stu-id="3f5d4-129">A sharing response that denies a request.</span></span>  <br/> |
|<span data-ttu-id="3f5d4-130">0x00023310</span><span class="sxs-lookup"><span data-stu-id="3f5d4-130">0x00023310</span></span>  <br/> |<span data-ttu-id="3f5d4-131">接受请求的共享响应 (也是一种共享邀请)。</span><span class="sxs-lookup"><span data-stu-id="3f5d4-131">A sharing response that accepts a request (also a type of sharing invitation).</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="3f5d4-132">相关资源</span><span class="sxs-lookup"><span data-stu-id="3f5d4-132">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="3f5d4-133">协议规范</span><span class="sxs-lookup"><span data-stu-id="3f5d4-133">Protocol specifications</span></span>

<span data-ttu-id="3f5d4-134">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="3f5d4-134">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="3f5d4-135">提供属性集定义和对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="3f5d4-135">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="3f5d4-136">[[毫秒-OXSHARE]](https://msdn.microsoft.com/library/e4e5bd27-d5e0-43f9-a6ea-550876724f3d%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="3f5d4-136">[[MS-OXSHARE]](https://msdn.microsoft.com/library/e4e5bd27-d5e0-43f9-a6ea-550876724f3d%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="3f5d4-137">在客户端之间共享邮箱文件夹。</span><span class="sxs-lookup"><span data-stu-id="3f5d4-137">Shares mailbox folders between clients.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="3f5d4-138">头文件</span><span class="sxs-lookup"><span data-stu-id="3f5d4-138">Header files</span></span>

<span data-ttu-id="3f5d4-139">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="3f5d4-139">Mapidefs.h</span></span>
  
> <span data-ttu-id="3f5d4-140">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="3f5d4-140">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="3f5d4-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3f5d4-141">See also</span></span>



[<span data-ttu-id="3f5d4-142">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="3f5d4-142">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="3f5d4-143">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="3f5d4-143">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="3f5d4-144">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="3f5d4-144">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="3f5d4-145">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="3f5d4-145">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

