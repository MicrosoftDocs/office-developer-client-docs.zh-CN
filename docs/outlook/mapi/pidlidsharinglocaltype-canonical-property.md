---
title: PidLidSharingLocalType 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidSharingLocalType
api_type:
- COM
ms.assetid: 6ac438a1-d36f-424f-b4b4-d6f2d26fd350
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: f24486270f5f20596e76781c7ddf4cbc90e17a11
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22583951"
---
# <a name="pidlidsharinglocaltype-canonical-property"></a><span data-ttu-id="612e7-103">PidLidSharingLocalType 规范属性</span><span class="sxs-lookup"><span data-stu-id="612e7-103">PidLidSharingLocalType Canonical Property</span></span>

  
  
<span data-ttu-id="612e7-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="612e7-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="612e7-105">指定要共享的文件夹的**PR_CONTAINER_CLASS** ([PidTagContainerClass](pidtagcontainerclass-canonical-property.md)) 属性的值。</span><span class="sxs-lookup"><span data-stu-id="612e7-105">Specifies the value of the **PR_CONTAINER_CLASS** ([PidTagContainerClass](pidtagcontainerclass-canonical-property.md)) property of the folder that is being shared.</span></span> <span data-ttu-id="612e7-106">这是邮件的共享的属性。</span><span class="sxs-lookup"><span data-stu-id="612e7-106">This is a property of a sharing message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="612e7-107">相关属性：</span><span class="sxs-lookup"><span data-stu-id="612e7-107">Associated properties:</span></span>  <br/> |<span data-ttu-id="612e7-108">dispidSharingLocalType</span><span class="sxs-lookup"><span data-stu-id="612e7-108">dispidSharingLocalType</span></span>  <br/> |
|<span data-ttu-id="612e7-109">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="612e7-109">Property set:</span></span>  <br/> |<span data-ttu-id="612e7-110">PSETID_Sharing</span><span class="sxs-lookup"><span data-stu-id="612e7-110">PSETID_Sharing</span></span>  <br/> |
|<span data-ttu-id="612e7-111">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="612e7-111">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="612e7-112">0x00008A14</span><span class="sxs-lookup"><span data-stu-id="612e7-112">0x00008A14</span></span>  <br/> |
|<span data-ttu-id="612e7-113">数据类型：</span><span class="sxs-lookup"><span data-stu-id="612e7-113">Data type:</span></span>  <br/> |<span data-ttu-id="612e7-114">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="612e7-114">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="612e7-115">区域：</span><span class="sxs-lookup"><span data-stu-id="612e7-115">Area:</span></span>  <br/> |<span data-ttu-id="612e7-116">共享</span><span class="sxs-lookup"><span data-stu-id="612e7-116">Sharing</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="612e7-117">注解</span><span class="sxs-lookup"><span data-stu-id="612e7-117">Remarks</span></span>

<span data-ttu-id="612e7-118">此属性的值必须是下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="612e7-118">The value of this property must be one of the following:</span></span>
  
- <span data-ttu-id="612e7-119">"IPF。约会"</span><span class="sxs-lookup"><span data-stu-id="612e7-119">"IPF.Appointment"</span></span>
    
- <span data-ttu-id="612e7-120">"IPF。联系人"</span><span class="sxs-lookup"><span data-stu-id="612e7-120">"IPF.Contact"</span></span>
    
- <span data-ttu-id="612e7-121">"IPF。任务"</span><span class="sxs-lookup"><span data-stu-id="612e7-121">"IPF.Task"</span></span>
    
- <span data-ttu-id="612e7-122">"IPF。便笺"</span><span class="sxs-lookup"><span data-stu-id="612e7-122">"IPF.StickyNote"</span></span>
    
- <span data-ttu-id="612e7-123">"IPF。日记"</span><span class="sxs-lookup"><span data-stu-id="612e7-123">"IPF.Journal"</span></span>
    
## <a name="related-resources"></a><span data-ttu-id="612e7-124">相关资源</span><span class="sxs-lookup"><span data-stu-id="612e7-124">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="612e7-125">协议规范</span><span class="sxs-lookup"><span data-stu-id="612e7-125">Protocol specifications</span></span>

<span data-ttu-id="612e7-126">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="612e7-126">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="612e7-127">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="612e7-127">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="612e7-128">[[MS OXSHARE]](http://msdn.microsoft.com/library/e4e5bd27-d5e0-43f9-a6ea-550876724f3d%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="612e7-128">[[MS-OXSHARE]](http://msdn.microsoft.com/library/e4e5bd27-d5e0-43f9-a6ea-550876724f3d%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="612e7-129">共享客户端之间的邮箱文件夹。</span><span class="sxs-lookup"><span data-stu-id="612e7-129">Shares mailbox folders between clients.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="612e7-130">头文件</span><span class="sxs-lookup"><span data-stu-id="612e7-130">Header files</span></span>

<span data-ttu-id="612e7-131">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="612e7-131">Mapidefs.h</span></span>
  
> <span data-ttu-id="612e7-132">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="612e7-132">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="612e7-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="612e7-133">See also</span></span>



[<span data-ttu-id="612e7-134">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="612e7-134">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="612e7-135">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="612e7-135">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="612e7-136">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="612e7-136">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="612e7-137">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="612e7-137">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

