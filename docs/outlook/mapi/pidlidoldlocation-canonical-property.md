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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32345029"
---
# <a name="pidlidoldlocation-canonical-property"></a><span data-ttu-id="67865-103">PidLidOldLocation 规范属性</span><span class="sxs-lookup"><span data-stu-id="67865-103">PidLidOldLocation Canonical Property</span></span>

  
  
<span data-ttu-id="67865-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="67865-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="67865-105">指示会议更新前 **dispidLocation** ([PidLidLocation](pidlidlocation-canonical-property.md)) 属性的原始值。</span><span class="sxs-lookup"><span data-stu-id="67865-105">Indicates the original value of the **dispidLocation** ([PidLidLocation](pidlidlocation-canonical-property.md)) property before a meeting update.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="67865-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="67865-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="67865-107">dispidOldLocation</span><span class="sxs-lookup"><span data-stu-id="67865-107">dispidOldLocation</span></span>  <br/> |
|<span data-ttu-id="67865-108">属性集：</span><span class="sxs-lookup"><span data-stu-id="67865-108">Property set:</span></span>  <br/> |<span data-ttu-id="67865-109">PSETID_Meeting</span><span class="sxs-lookup"><span data-stu-id="67865-109">PSETID_Meeting</span></span>  <br/> |
|<span data-ttu-id="67865-110">LONG ID (的一) ：</span><span class="sxs-lookup"><span data-stu-id="67865-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="67865-111">0x00000028</span><span class="sxs-lookup"><span data-stu-id="67865-111">0x00000028</span></span>  <br/> |
|<span data-ttu-id="67865-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="67865-112">Data type:</span></span>  <br/> |<span data-ttu-id="67865-113">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="67865-113">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="67865-114">区域：</span><span class="sxs-lookup"><span data-stu-id="67865-114">Area:</span></span>  <br/> |<span data-ttu-id="67865-115">会议</span><span class="sxs-lookup"><span data-stu-id="67865-115">Meetings</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="67865-116">备注</span><span class="sxs-lookup"><span data-stu-id="67865-116">Remarks</span></span>

<span data-ttu-id="67865-117">此属性不是必需的。</span><span class="sxs-lookup"><span data-stu-id="67865-117">This property is not required.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="67865-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="67865-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="67865-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="67865-119">Protocol specifications</span></span>

<span data-ttu-id="67865-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="67865-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="67865-121">提供属性集定义和对相关协议规范Exchange Server引用。</span><span class="sxs-lookup"><span data-stu-id="67865-121">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="67865-122">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="67865-122">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="67865-123">指定约会、会议请求和响应邮件的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="67865-123">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="67865-124">头文件</span><span class="sxs-lookup"><span data-stu-id="67865-124">Header files</span></span>

<span data-ttu-id="67865-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="67865-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="67865-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="67865-126">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="67865-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="67865-127">See also</span></span>



[<span data-ttu-id="67865-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="67865-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="67865-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="67865-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="67865-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="67865-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="67865-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="67865-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

