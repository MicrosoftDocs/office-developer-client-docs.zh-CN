---
title: PidLidIsRecurring 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidIsRecurring
api_type:
- COM
ms.assetid: 1f8ecc22-badc-4278-a3c6-fcd398f5bf24
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: c21f2885f7e9475c2149e42e2a8d947311916b4f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776894"
---
# <a name="pidlidisrecurring-canonical-property"></a><span data-ttu-id="b0e21-103">PidLidIsRecurring 规范属性</span><span class="sxs-lookup"><span data-stu-id="b0e21-103">PidLidIsRecurring Canonical Property</span></span>

  
  
<span data-ttu-id="b0e21-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="b0e21-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="b0e21-105">指定对象是定期系列相关联。</span><span class="sxs-lookup"><span data-stu-id="b0e21-105">Specifies whether or not the object is associated with a recurring series.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="b0e21-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="b0e21-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="b0e21-107">LID_IS_RECURRING</span><span class="sxs-lookup"><span data-stu-id="b0e21-107">LID_IS_RECURRING</span></span>  <br/> |
|<span data-ttu-id="b0e21-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="b0e21-108">Property set:</span></span>  <br/> |<span data-ttu-id="b0e21-109">PSETID_Meeting</span><span class="sxs-lookup"><span data-stu-id="b0e21-109">PSETID_Meeting</span></span>  <br/> |
|<span data-ttu-id="b0e21-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="b0e21-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="b0e21-111">0x00000005</span><span class="sxs-lookup"><span data-stu-id="b0e21-111">0x00000005</span></span>  <br/> |
|<span data-ttu-id="b0e21-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="b0e21-112">Data type:</span></span>  <br/> |<span data-ttu-id="b0e21-113">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="b0e21-113">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="b0e21-114">区域：</span><span class="sxs-lookup"><span data-stu-id="b0e21-114">Area:</span></span>  <br/> |<span data-ttu-id="b0e21-115">会议</span><span class="sxs-lookup"><span data-stu-id="b0e21-115">Meetings</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="b0e21-116">备注</span><span class="sxs-lookup"><span data-stu-id="b0e21-116">Remarks</span></span>

<span data-ttu-id="b0e21-117">TRUE 表示该对象代表定期系列或异常 （包括孤立实例）。</span><span class="sxs-lookup"><span data-stu-id="b0e21-117">A value of TRUE indicates that the object represents either a recurring series or an exception (including an orphan instance).</span></span> <span data-ttu-id="b0e21-118">值为 FALSE 或不存在此属性，指示该对象代表单个实例。</span><span class="sxs-lookup"><span data-stu-id="b0e21-118">A value of FALSE, or the absence of this property, indicates that the object represents a single instance.</span></span> <span data-ttu-id="b0e21-119">请注意此属性与**PR_RECURRING** ([PidLidRecurring](pidlidrecurring-canonical-property.md)) 属性之间的差异。</span><span class="sxs-lookup"><span data-stu-id="b0e21-119">Note the difference between this property and the **PR_RECURRING** ([PidLidRecurring](pidlidrecurring-canonical-property.md)) property.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="b0e21-120">相关资源</span><span class="sxs-lookup"><span data-stu-id="b0e21-120">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="b0e21-121">协议规范</span><span class="sxs-lookup"><span data-stu-id="b0e21-121">Protocol specifications</span></span>

<span data-ttu-id="b0e21-122">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b0e21-122">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b0e21-123">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="b0e21-123">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="b0e21-124">[[MS OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b0e21-124">[[MS-OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b0e21-125">指定的属性和约会、 会议请求和响应消息的操作。</span><span class="sxs-lookup"><span data-stu-id="b0e21-125">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="b0e21-126">头文件</span><span class="sxs-lookup"><span data-stu-id="b0e21-126">Header files</span></span>

<span data-ttu-id="b0e21-127">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="b0e21-127">Mapidefs.h</span></span>
  
> <span data-ttu-id="b0e21-128">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="b0e21-128">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="b0e21-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b0e21-129">See also</span></span>



[<span data-ttu-id="b0e21-130">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="b0e21-130">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="b0e21-131">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="b0e21-131">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="b0e21-132">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="b0e21-132">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="b0e21-133">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="b0e21-133">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

