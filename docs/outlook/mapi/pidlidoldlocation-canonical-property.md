---
title: PidLidOldLocation 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidOldLocation
api_type:
- COM
ms.assetid: 5d31791b-c30d-4a97-b2d3-18cbe0e98792
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: f985aecb3d685833f3f680adba96cd49a22b6cc0
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25389671"
---
# <a name="pidlidoldlocation-canonical-property"></a><span data-ttu-id="3e557-103">PidLidOldLocation 规范属性</span><span class="sxs-lookup"><span data-stu-id="3e557-103">PidLidOldLocation Canonical Property</span></span>

  
  
<span data-ttu-id="3e557-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="3e557-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="3e557-105">指示会议更新之前的**dispidLocation** ([PidLidLocation](pidlidlocation-canonical-property.md)) 属性的原始值。</span><span class="sxs-lookup"><span data-stu-id="3e557-105">Indicates the original value of the **dispidLocation** ([PidLidLocation](pidlidlocation-canonical-property.md)) property before a meeting update.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="3e557-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="3e557-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="3e557-107">dispidOldLocation</span><span class="sxs-lookup"><span data-stu-id="3e557-107">dispidOldLocation</span></span>  <br/> |
|<span data-ttu-id="3e557-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="3e557-108">Property set:</span></span>  <br/> |<span data-ttu-id="3e557-109">PSETID_Meeting</span><span class="sxs-lookup"><span data-stu-id="3e557-109">PSETID_Meeting</span></span>  <br/> |
|<span data-ttu-id="3e557-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="3e557-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="3e557-111">0x00000028</span><span class="sxs-lookup"><span data-stu-id="3e557-111">0x00000028</span></span>  <br/> |
|<span data-ttu-id="3e557-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="3e557-112">Data type:</span></span>  <br/> |<span data-ttu-id="3e557-113">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="3e557-113">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="3e557-114">区域：</span><span class="sxs-lookup"><span data-stu-id="3e557-114">Area:</span></span>  <br/> |<span data-ttu-id="3e557-115">会议</span><span class="sxs-lookup"><span data-stu-id="3e557-115">Meetings</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="3e557-116">说明</span><span class="sxs-lookup"><span data-stu-id="3e557-116">Remarks</span></span>

<span data-ttu-id="3e557-117">此属性不是必需的。</span><span class="sxs-lookup"><span data-stu-id="3e557-117">This property is not required.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="3e557-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="3e557-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="3e557-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="3e557-119">Protocol specifications</span></span>

<span data-ttu-id="3e557-120">[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="3e557-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="3e557-121">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="3e557-121">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="3e557-122">[[MS OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="3e557-122">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="3e557-123">指定的属性和约会、 会议请求和响应消息的操作。</span><span class="sxs-lookup"><span data-stu-id="3e557-123">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="3e557-124">头文件</span><span class="sxs-lookup"><span data-stu-id="3e557-124">Header files</span></span>

<span data-ttu-id="3e557-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="3e557-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="3e557-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="3e557-126">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="3e557-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3e557-127">See also</span></span>



[<span data-ttu-id="3e557-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="3e557-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="3e557-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="3e557-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="3e557-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="3e557-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="3e557-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="3e557-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

