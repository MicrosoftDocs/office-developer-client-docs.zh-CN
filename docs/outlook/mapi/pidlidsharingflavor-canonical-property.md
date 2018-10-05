---
title: PidLidSharingFlavor 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidSharingFlavor
api_type:
- COM
ms.assetid: c91ab5c7-82ac-4895-bf54-2863ca5e2410
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 21144af15e7a36f54af3032f735c391b3038305b
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25383609"
---
# <a name="pidlidsharingflavor-canonical-property"></a><span data-ttu-id="c1558-103">PidLidSharingFlavor 规范属性</span><span class="sxs-lookup"><span data-stu-id="c1558-103">PidLidSharingFlavor Canonical Property</span></span>

  
  
<span data-ttu-id="c1558-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c1558-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c1558-105">将指定的共享邮件的属性。</span><span class="sxs-lookup"><span data-stu-id="c1558-105">Designates as a property of a sharing message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="c1558-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="c1558-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="c1558-107">dispidSharingFlavor</span><span class="sxs-lookup"><span data-stu-id="c1558-107">dispidSharingFlavor</span></span>  <br/> |
|<span data-ttu-id="c1558-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="c1558-108">Property set:</span></span>  <br/> |<span data-ttu-id="c1558-109">PSETID_Sharing</span><span class="sxs-lookup"><span data-stu-id="c1558-109">PSETID_Sharing</span></span>  <br/> |
|<span data-ttu-id="c1558-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="c1558-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="c1558-111">0x00008A18</span><span class="sxs-lookup"><span data-stu-id="c1558-111">0x00008A18</span></span>  <br/> |
|<span data-ttu-id="c1558-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="c1558-112">Data type:</span></span>  <br/> |<span data-ttu-id="c1558-113">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="c1558-113">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="c1558-114">区域：</span><span class="sxs-lookup"><span data-stu-id="c1558-114">Area:</span></span>  <br/> |<span data-ttu-id="c1558-115">共享</span><span class="sxs-lookup"><span data-stu-id="c1558-115">Sharing</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="c1558-116">说明</span><span class="sxs-lookup"><span data-stu-id="c1558-116">Remarks</span></span>

<span data-ttu-id="c1558-117">此属性的值必须是下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="c1558-117">The value of this property must be one of the following:</span></span>
  
|<span data-ttu-id="c1558-118">**值**</span><span class="sxs-lookup"><span data-stu-id="c1558-118">**Value**</span></span>|<span data-ttu-id="c1558-119">**共享 Message 对象的类型**</span><span class="sxs-lookup"><span data-stu-id="c1558-119">**Type of Sharing Message object**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c1558-120">0x00020310</span><span class="sxs-lookup"><span data-stu-id="c1558-120">0x00020310</span></span>  <br/> |<span data-ttu-id="c1558-121">特殊文件夹的共享邀请。</span><span class="sxs-lookup"><span data-stu-id="c1558-121">A sharing invitation for a special folder.</span></span>  <br/> |
|<span data-ttu-id="c1558-122">0x00000310</span><span class="sxs-lookup"><span data-stu-id="c1558-122">0x00000310</span></span>  <br/> |<span data-ttu-id="c1558-123">不是一个特殊文件夹的文件夹共享邀请。</span><span class="sxs-lookup"><span data-stu-id="c1558-123">A sharing invitation for a folder that is not a special folder.</span></span>  <br/> |
|<span data-ttu-id="c1558-124">0x00020500</span><span class="sxs-lookup"><span data-stu-id="c1558-124">0x00020500</span></span>  <br/> |<span data-ttu-id="c1558-125">共享请求。</span><span class="sxs-lookup"><span data-stu-id="c1558-125">A sharing request.</span></span>  <br/> |
|<span data-ttu-id="c1558-126">0x00020710</span><span class="sxs-lookup"><span data-stu-id="c1558-126">0x00020710</span></span>  <br/> |<span data-ttu-id="c1558-127">这两个共享邀请的特殊文件夹和共享请求收件人的等效的特殊文件夹。</span><span class="sxs-lookup"><span data-stu-id="c1558-127">Both a sharing invitation for a special folder and a sharing request for the recipient's equivalent special folder.</span></span>  <br/> |
|<span data-ttu-id="c1558-128">0x00025100</span><span class="sxs-lookup"><span data-stu-id="c1558-128">0x00025100</span></span>  <br/> |<span data-ttu-id="c1558-129">共享响应拒绝请求。</span><span class="sxs-lookup"><span data-stu-id="c1558-129">A sharing response denying a request.</span></span>  <br/> |
|<span data-ttu-id="c1558-130">0x00023310</span><span class="sxs-lookup"><span data-stu-id="c1558-130">0x00023310</span></span>  <br/> |<span data-ttu-id="c1558-131">接受请求 （还一类型的共享邀请） 共享响应。</span><span class="sxs-lookup"><span data-stu-id="c1558-131">A sharing response accepting a request (also a type of sharing invitation).</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="c1558-132">相关资源</span><span class="sxs-lookup"><span data-stu-id="c1558-132">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="c1558-133">协议规范</span><span class="sxs-lookup"><span data-stu-id="c1558-133">Protocol specifications</span></span>

<span data-ttu-id="c1558-134">[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="c1558-134">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="c1558-135">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="c1558-135">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="c1558-136">[[MS OXSHARE]](https://msdn.microsoft.com/library/e4e5bd27-d5e0-43f9-a6ea-550876724f3d%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="c1558-136">[[MS-OXSHARE]](https://msdn.microsoft.com/library/e4e5bd27-d5e0-43f9-a6ea-550876724f3d%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="c1558-137">共享客户端之间的邮箱文件夹。</span><span class="sxs-lookup"><span data-stu-id="c1558-137">Shares mailbox folders between clients.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="c1558-138">头文件</span><span class="sxs-lookup"><span data-stu-id="c1558-138">Header files</span></span>

<span data-ttu-id="c1558-139">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="c1558-139">Mapidefs.h</span></span>
  
> <span data-ttu-id="c1558-140">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="c1558-140">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="c1558-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c1558-141">See also</span></span>



[<span data-ttu-id="c1558-142">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="c1558-142">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="c1558-143">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="c1558-143">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="c1558-144">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="c1558-144">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="c1558-145">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="c1558-145">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

