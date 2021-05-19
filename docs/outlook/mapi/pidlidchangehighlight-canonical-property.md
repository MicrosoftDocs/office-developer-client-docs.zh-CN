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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32344938"
---
# <a name="pidlidchangehighlight-canonical-property"></a><span data-ttu-id="dc9dc-103">PidLidChangeHighlight 规范属性</span><span class="sxs-lookup"><span data-stu-id="dc9dc-103">PidLidChangeHighlight Canonical Property</span></span>

  
  
<span data-ttu-id="dc9dc-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="dc9dc-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="dc9dc-105">指定指示会议对象如何更改的位字段。</span><span class="sxs-lookup"><span data-stu-id="dc9dc-105">Specifies a bit field that indicates how the meeting object changed.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="dc9dc-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="dc9dc-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="dc9dc-107">dispidChangeHighlight</span><span class="sxs-lookup"><span data-stu-id="dc9dc-107">dispidChangeHighlight</span></span>  <br/> |
|<span data-ttu-id="dc9dc-108">属性集：</span><span class="sxs-lookup"><span data-stu-id="dc9dc-108">Property set:</span></span>  <br/> |<span data-ttu-id="dc9dc-109">PSETID_Appointment</span><span class="sxs-lookup"><span data-stu-id="dc9dc-109">PSETID_Appointment</span></span>  <br/> |
|<span data-ttu-id="dc9dc-110">LONG ID (的一) ：</span><span class="sxs-lookup"><span data-stu-id="dc9dc-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="dc9dc-111">0x00008204</span><span class="sxs-lookup"><span data-stu-id="dc9dc-111">0x00008204</span></span>  <br/> |
|<span data-ttu-id="dc9dc-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="dc9dc-112">Data type:</span></span>  <br/> |<span data-ttu-id="dc9dc-113">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="dc9dc-113">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="dc9dc-114">区域：</span><span class="sxs-lookup"><span data-stu-id="dc9dc-114">Area:</span></span>  <br/> |<span data-ttu-id="dc9dc-115">会议</span><span class="sxs-lookup"><span data-stu-id="dc9dc-115">Meetings</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="dc9dc-116">备注</span><span class="sxs-lookup"><span data-stu-id="dc9dc-116">Remarks</span></span>

<span data-ttu-id="dc9dc-117">此属性不是必需的。</span><span class="sxs-lookup"><span data-stu-id="dc9dc-117">This property is not required.</span></span> <span data-ttu-id="dc9dc-118">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)中详细说明了可以设置的个人标志。</span><span class="sxs-lookup"><span data-stu-id="dc9dc-118">The individual flags that can be set are detailed in [[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx).</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="dc9dc-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="dc9dc-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="dc9dc-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="dc9dc-120">Protocol specifications</span></span>

<span data-ttu-id="dc9dc-121">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="dc9dc-121">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="dc9dc-122">提供属性集定义和对相关协议规范Exchange Server引用。</span><span class="sxs-lookup"><span data-stu-id="dc9dc-122">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="dc9dc-123">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="dc9dc-123">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="dc9dc-124">指定约会、会议请求和响应邮件的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="dc9dc-124">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="dc9dc-125">头文件</span><span class="sxs-lookup"><span data-stu-id="dc9dc-125">Header files</span></span>

<span data-ttu-id="dc9dc-126">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="dc9dc-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="dc9dc-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="dc9dc-127">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="dc9dc-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dc9dc-128">See also</span></span>



[<span data-ttu-id="dc9dc-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="dc9dc-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="dc9dc-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="dc9dc-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="dc9dc-131">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="dc9dc-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="dc9dc-132">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="dc9dc-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

