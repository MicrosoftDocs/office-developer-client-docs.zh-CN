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
ms.openlocfilehash: b5f806f838d617a6265279ee7e58dc2e28a662b2
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776722"
---
# <a name="pidlidchangehighlight-canonical-property"></a><span data-ttu-id="67692-103">PidLidChangeHighlight 规范属性</span><span class="sxs-lookup"><span data-stu-id="67692-103">PidLidChangeHighlight Canonical Property</span></span>

  
  
<span data-ttu-id="67692-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="67692-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="67692-105">指定位字段，该值指示如何会议对象更改。</span><span class="sxs-lookup"><span data-stu-id="67692-105">Specifies a bit field that indicates how the meeting object changed.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="67692-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="67692-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="67692-107">dispidChangeHighlight</span><span class="sxs-lookup"><span data-stu-id="67692-107">dispidChangeHighlight</span></span>  <br/> |
|<span data-ttu-id="67692-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="67692-108">Property set:</span></span>  <br/> |<span data-ttu-id="67692-109">PSETID_Appointment</span><span class="sxs-lookup"><span data-stu-id="67692-109">PSETID_Appointment</span></span>  <br/> |
|<span data-ttu-id="67692-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="67692-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="67692-111">0x00008204</span><span class="sxs-lookup"><span data-stu-id="67692-111">0x00008204</span></span>  <br/> |
|<span data-ttu-id="67692-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="67692-112">Data type:</span></span>  <br/> |<span data-ttu-id="67692-113">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="67692-113">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="67692-114">区域：</span><span class="sxs-lookup"><span data-stu-id="67692-114">Area:</span></span>  <br/> |<span data-ttu-id="67692-115">会议</span><span class="sxs-lookup"><span data-stu-id="67692-115">Meetings</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="67692-116">说明</span><span class="sxs-lookup"><span data-stu-id="67692-116">Remarks</span></span>

<span data-ttu-id="67692-117">此属性不是必需的。</span><span class="sxs-lookup"><span data-stu-id="67692-117">This property is not required.</span></span> <span data-ttu-id="67692-118">可以设置的单个标志详见[[MS OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="67692-118">The individual flags that can be set are detailed in [[MS-OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx).</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="67692-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="67692-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="67692-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="67692-120">Protocol specifications</span></span>

<span data-ttu-id="67692-121">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="67692-121">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="67692-122">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="67692-122">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="67692-123">[[MS OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="67692-123">[[MS-OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="67692-124">指定的属性和约会、 会议请求和响应消息的操作。</span><span class="sxs-lookup"><span data-stu-id="67692-124">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="67692-125">头文件</span><span class="sxs-lookup"><span data-stu-id="67692-125">Header files</span></span>

<span data-ttu-id="67692-126">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="67692-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="67692-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="67692-127">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="67692-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="67692-128">See also</span></span>



[<span data-ttu-id="67692-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="67692-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="67692-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="67692-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="67692-131">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="67692-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="67692-132">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="67692-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

