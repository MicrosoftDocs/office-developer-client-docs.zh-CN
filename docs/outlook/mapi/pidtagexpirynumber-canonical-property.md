---
title: PidTagExpiryNumber 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagExpiryNumber
api_type:
- HeaderDef
ms.assetid: 644e8d3d-1792-4417-95a1-e978d0e6cd8e
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: da90347f5aacdb2fcac8547eddd5b89a0a44820d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32316364"
---
# <a name="pidtagexpirynumber-canonical-property"></a><span data-ttu-id="cf494-103">PidTagExpiryNumber 规范属性</span><span class="sxs-lookup"><span data-stu-id="cf494-103">PidTagExpiryNumber Canonical Property</span></span>

  
  
<span data-ttu-id="cf494-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="cf494-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="cf494-105">与[PidTagExpiryUnits](pidtagexpiryunits-canonical-property.md)  PR_EXPIRY_UNITS (一起定义) 发送时间。</span><span class="sxs-lookup"><span data-stu-id="cf494-105">Defines the expiry send time in conjunction with the **PR_EXPIRY_UNITS** ([PidTagExpiryUnits](pidtagexpiryunits-canonical-property.md)) property.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="cf494-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="cf494-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="cf494-107">PR_EXPIRY_NUMBER</span><span class="sxs-lookup"><span data-stu-id="cf494-107">PR_EXPIRY_NUMBER</span></span>  <br/> |
|<span data-ttu-id="cf494-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="cf494-108">Identifier:</span></span>  <br/> |<span data-ttu-id="cf494-109">0x3FED</span><span class="sxs-lookup"><span data-stu-id="cf494-109">0x3FED</span></span>  <br/> |
|<span data-ttu-id="cf494-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="cf494-110">Data type:</span></span>  <br/> |<span data-ttu-id="cf494-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="cf494-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="cf494-112">区域：</span><span class="sxs-lookup"><span data-stu-id="cf494-112">Area:</span></span>  <br/> |<span data-ttu-id="cf494-113">MAPI 状态</span><span class="sxs-lookup"><span data-stu-id="cf494-113">MAPI status</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="cf494-114">备注</span><span class="sxs-lookup"><span data-stu-id="cf494-114">Remarks</span></span>

<span data-ttu-id="cf494-115">此属性的值必须设置为 0 到 999 之间（如果存在）。</span><span class="sxs-lookup"><span data-stu-id="cf494-115">This property's value must be set between 0 and 999 inclusive, if it is present.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="cf494-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="cf494-116">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="cf494-117">协议规范</span><span class="sxs-lookup"><span data-stu-id="cf494-117">Protocol specifications</span></span>

<span data-ttu-id="cf494-118">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="cf494-118">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="cf494-119">指定电子邮件对象允许的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="cf494-119">Specifies the properties and operations that are permissible for email message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="cf494-120">头文件</span><span class="sxs-lookup"><span data-stu-id="cf494-120">Header files</span></span>

<span data-ttu-id="cf494-121">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="cf494-121">Mapidefs.h</span></span>
  
> <span data-ttu-id="cf494-122">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="cf494-122">Provides data type definitions.</span></span>
    
<span data-ttu-id="cf494-123">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="cf494-123">Mapitags.h</span></span>
  
> <span data-ttu-id="cf494-124">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="cf494-124">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="cf494-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cf494-125">See also</span></span>



[<span data-ttu-id="cf494-126">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="cf494-126">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="cf494-127">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="cf494-127">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="cf494-128">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="cf494-128">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="cf494-129">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="cf494-129">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

