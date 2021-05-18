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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: c920cd42a27c03ffcff63bbd2e0049ddb6f81158
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32315433"
---
# <a name="pidlidisrecurring-canonical-property"></a><span data-ttu-id="20e5d-103">PidLidIsRecurring 规范属性</span><span class="sxs-lookup"><span data-stu-id="20e5d-103">PidLidIsRecurring Canonical Property</span></span>

  
  
<span data-ttu-id="20e5d-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="20e5d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="20e5d-105">指定对象是否与定期系列关联。</span><span class="sxs-lookup"><span data-stu-id="20e5d-105">Specifies whether or not the object is associated with a recurring series.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="20e5d-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="20e5d-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="20e5d-107">LID_IS_RECURRING</span><span class="sxs-lookup"><span data-stu-id="20e5d-107">LID_IS_RECURRING</span></span>  <br/> |
|<span data-ttu-id="20e5d-108">属性集：</span><span class="sxs-lookup"><span data-stu-id="20e5d-108">Property set:</span></span>  <br/> |<span data-ttu-id="20e5d-109">PSETID_Meeting</span><span class="sxs-lookup"><span data-stu-id="20e5d-109">PSETID_Meeting</span></span>  <br/> |
|<span data-ttu-id="20e5d-110">LONG ID (的一) ：</span><span class="sxs-lookup"><span data-stu-id="20e5d-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="20e5d-111">0x00000005</span><span class="sxs-lookup"><span data-stu-id="20e5d-111">0x00000005</span></span>  <br/> |
|<span data-ttu-id="20e5d-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="20e5d-112">Data type:</span></span>  <br/> |<span data-ttu-id="20e5d-113">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="20e5d-113">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="20e5d-114">区域：</span><span class="sxs-lookup"><span data-stu-id="20e5d-114">Area:</span></span>  <br/> |<span data-ttu-id="20e5d-115">会议</span><span class="sxs-lookup"><span data-stu-id="20e5d-115">Meetings</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="20e5d-116">备注</span><span class="sxs-lookup"><span data-stu-id="20e5d-116">Remarks</span></span>

<span data-ttu-id="20e5d-117">TRUE 值表示对象表示定期系列或异常 (包括孤立实例) 。</span><span class="sxs-lookup"><span data-stu-id="20e5d-117">A value of TRUE indicates that the object represents either a recurring series or an exception (including an orphan instance).</span></span> <span data-ttu-id="20e5d-118">FALSE 值或缺少此属性，表示对象表示单个实例。</span><span class="sxs-lookup"><span data-stu-id="20e5d-118">A value of FALSE, or the absence of this property, indicates that the object represents a single instance.</span></span> <span data-ttu-id="20e5d-119">请注意此属性与[PidLidRecurring](pidlidrecurring-canonical-property.md) PR_RECURRING (值) 差异。 </span><span class="sxs-lookup"><span data-stu-id="20e5d-119">Note the difference between this property and the **PR_RECURRING** ([PidLidRecurring](pidlidrecurring-canonical-property.md)) property.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="20e5d-120">相关资源</span><span class="sxs-lookup"><span data-stu-id="20e5d-120">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="20e5d-121">协议规范</span><span class="sxs-lookup"><span data-stu-id="20e5d-121">Protocol specifications</span></span>

<span data-ttu-id="20e5d-122">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="20e5d-122">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="20e5d-123">提供属性集定义和对相关协议规范Exchange Server引用。</span><span class="sxs-lookup"><span data-stu-id="20e5d-123">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="20e5d-124">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="20e5d-124">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="20e5d-125">指定约会、会议请求和响应邮件的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="20e5d-125">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="20e5d-126">头文件</span><span class="sxs-lookup"><span data-stu-id="20e5d-126">Header files</span></span>

<span data-ttu-id="20e5d-127">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="20e5d-127">Mapidefs.h</span></span>
  
> <span data-ttu-id="20e5d-128">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="20e5d-128">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="20e5d-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="20e5d-129">See also</span></span>



[<span data-ttu-id="20e5d-130">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="20e5d-130">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="20e5d-131">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="20e5d-131">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="20e5d-132">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="20e5d-132">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="20e5d-133">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="20e5d-133">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

