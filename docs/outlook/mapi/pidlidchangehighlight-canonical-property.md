---
title: PidLidChangeHighlight 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidChangeHighlight
api_type:
- COM
ms.assetid: cd57a5be-5550-4492-acb9-52255fac9014
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: bbac700c2bf5a0e17967cbf94b68b03627a47256
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25383827"
---
# <a name="pidlidchangehighlight-canonical-property"></a><span data-ttu-id="e980c-103">PidLidChangeHighlight 规范属性</span><span class="sxs-lookup"><span data-stu-id="e980c-103">PidLidChangeHighlight Canonical Property</span></span>

  
  
<span data-ttu-id="e980c-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e980c-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e980c-105">指定位字段，该值指示如何会议对象更改。</span><span class="sxs-lookup"><span data-stu-id="e980c-105">Specifies a bit field that indicates how the meeting object changed.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="e980c-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="e980c-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="e980c-107">dispidChangeHighlight</span><span class="sxs-lookup"><span data-stu-id="e980c-107">dispidChangeHighlight</span></span>  <br/> |
|<span data-ttu-id="e980c-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="e980c-108">Property set:</span></span>  <br/> |<span data-ttu-id="e980c-109">PSETID_Appointment</span><span class="sxs-lookup"><span data-stu-id="e980c-109">PSETID_Appointment</span></span>  <br/> |
|<span data-ttu-id="e980c-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="e980c-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="e980c-111">0x00008204</span><span class="sxs-lookup"><span data-stu-id="e980c-111">0x00008204</span></span>  <br/> |
|<span data-ttu-id="e980c-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="e980c-112">Data type:</span></span>  <br/> |<span data-ttu-id="e980c-113">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="e980c-113">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="e980c-114">区域：</span><span class="sxs-lookup"><span data-stu-id="e980c-114">Area:</span></span>  <br/> |<span data-ttu-id="e980c-115">会议</span><span class="sxs-lookup"><span data-stu-id="e980c-115">Meetings</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="e980c-116">说明</span><span class="sxs-lookup"><span data-stu-id="e980c-116">Remarks</span></span>

<span data-ttu-id="e980c-117">此属性不是必需的。</span><span class="sxs-lookup"><span data-stu-id="e980c-117">This property is not required.</span></span> <span data-ttu-id="e980c-118">可以设置的单个标志详见[[MS OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="e980c-118">The individual flags that can be set are detailed in [[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx).</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="e980c-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="e980c-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="e980c-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="e980c-120">Protocol specifications</span></span>

<span data-ttu-id="e980c-121">[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="e980c-121">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="e980c-122">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="e980c-122">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="e980c-123">[[MS OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="e980c-123">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="e980c-124">指定的属性和约会、 会议请求和响应消息的操作。</span><span class="sxs-lookup"><span data-stu-id="e980c-124">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="e980c-125">头文件</span><span class="sxs-lookup"><span data-stu-id="e980c-125">Header files</span></span>

<span data-ttu-id="e980c-126">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="e980c-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="e980c-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="e980c-127">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="e980c-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e980c-128">See also</span></span>



[<span data-ttu-id="e980c-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="e980c-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="e980c-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="e980c-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="e980c-131">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="e980c-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="e980c-132">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="e980c-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

