---
title: PidTagSubfolders 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagSubfolders
api_type:
- COM
ms.assetid: b456b07b-4d83-46bf-a305-4f322ea7dbd1
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: acde7f18324d5642f7b8f8b5aa25721c4019ce3a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778473"
---
# <a name="pidtagsubfolders-canonical-property"></a><span data-ttu-id="c7c9e-103">PidTagSubfolders 规范属性</span><span class="sxs-lookup"><span data-stu-id="c7c9e-103">PidTagSubfolders Canonical Property</span></span>

  
  
<span data-ttu-id="c7c9e-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="c7c9e-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="c7c9e-105">包含 TRUE，则文件夹包含子文件夹。</span><span class="sxs-lookup"><span data-stu-id="c7c9e-105">Contains TRUE if a folder contains subfolders.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="c7c9e-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="c7c9e-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="c7c9e-107">PR_SUBFOLDERS</span><span class="sxs-lookup"><span data-stu-id="c7c9e-107">PR_SUBFOLDERS</span></span>  <br/> |
|<span data-ttu-id="c7c9e-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="c7c9e-108">Identifier:</span></span>  <br/> |<span data-ttu-id="c7c9e-109">0x360A</span><span class="sxs-lookup"><span data-stu-id="c7c9e-109">0x360A</span></span>  <br/> |
|<span data-ttu-id="c7c9e-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="c7c9e-110">Data type:</span></span>  <br/> |<span data-ttu-id="c7c9e-111">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="c7c9e-111">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="c7c9e-112">区域：</span><span class="sxs-lookup"><span data-stu-id="c7c9e-112">Area:</span></span>  <br/> |<span data-ttu-id="c7c9e-113">MAPI 容器</span><span class="sxs-lookup"><span data-stu-id="c7c9e-113">MAPI container</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="c7c9e-114">备注</span><span class="sxs-lookup"><span data-stu-id="c7c9e-114">Remarks</span></span>

<span data-ttu-id="c7c9e-115">消息存储必须提供此属性的所有文件夹。</span><span class="sxs-lookup"><span data-stu-id="c7c9e-115">Message stores must supply this property for all folders.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="c7c9e-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="c7c9e-116">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="c7c9e-117">协议规范</span><span class="sxs-lookup"><span data-stu-id="c7c9e-117">Protocol specifications</span></span>

<span data-ttu-id="c7c9e-118">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="c7c9e-118">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="c7c9e-119">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="c7c9e-119">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="c7c9e-120">[[MS OXCFOLD]](http://msdn.microsoft.com/library/c0f31b95-c07f-486c-98d9-535ed9705fbf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="c7c9e-120">[[MS-OXCFOLD]](http://msdn.microsoft.com/library/c0f31b95-c07f-486c-98d9-535ed9705fbf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="c7c9e-121">处理文件夹的操作。</span><span class="sxs-lookup"><span data-stu-id="c7c9e-121">Handles folder operations.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="c7c9e-122">头文件</span><span class="sxs-lookup"><span data-stu-id="c7c9e-122">Header files</span></span>

<span data-ttu-id="c7c9e-123">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="c7c9e-123">Mapidefs.h</span></span>
  
> <span data-ttu-id="c7c9e-124">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="c7c9e-124">Provides data type definitions.</span></span>
    
<span data-ttu-id="c7c9e-125">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="c7c9e-125">Mapitags.h</span></span>
  
> <span data-ttu-id="c7c9e-126">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="c7c9e-126">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="c7c9e-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c7c9e-127">See also</span></span>



[<span data-ttu-id="c7c9e-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="c7c9e-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="c7c9e-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="c7c9e-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="c7c9e-130">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="c7c9e-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="c7c9e-131">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="c7c9e-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

