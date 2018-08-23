---
title: PidTagAbSearchPath 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagAbSearchPath
api_type:
- HeaderDef
ms.assetid: dfb7ce1b-8e2f-4360-a7d3-876ff5163c34
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: e489d5ccef9dcec9cdad08c068276e69fdf09566
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22567970"
---
# <a name="pidtagabsearchpath-canonical-property"></a><span data-ttu-id="4dc1d-103">PidTagAbSearchPath 规范属性</span><span class="sxs-lookup"><span data-stu-id="4dc1d-103">PidTagAbSearchPath Canonical Property</span></span>

  
  
<span data-ttu-id="4dc1d-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="4dc1d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="4dc1d-105">包含要搜索来解析名称的通讯簿容器的项标识符的列表。</span><span class="sxs-lookup"><span data-stu-id="4dc1d-105">Contains a list of entry identifiers for address book containers that are to be searched to resolve names.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="4dc1d-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="4dc1d-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="4dc1d-107">PR_AB_SEARCH_PATH</span><span class="sxs-lookup"><span data-stu-id="4dc1d-107">PR_AB_SEARCH_PATH</span></span>  <br/> |
|<span data-ttu-id="4dc1d-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="4dc1d-108">Identifier:</span></span>  <br/> |<span data-ttu-id="4dc1d-109">0x3D05</span><span class="sxs-lookup"><span data-stu-id="4dc1d-109">0x3D05</span></span>  <br/> |
|<span data-ttu-id="4dc1d-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="4dc1d-110">Data type:</span></span>  <br/> |<span data-ttu-id="4dc1d-111">PT_MV_BINARY</span><span class="sxs-lookup"><span data-stu-id="4dc1d-111">PT_MV_BINARY</span></span>  <br/> |
|<span data-ttu-id="4dc1d-112">区域：</span><span class="sxs-lookup"><span data-stu-id="4dc1d-112">Area:</span></span>  <br/> |<span data-ttu-id="4dc1d-113">通讯簿</span><span class="sxs-lookup"><span data-stu-id="4dc1d-113">Address book</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="4dc1d-114">注解</span><span class="sxs-lookup"><span data-stu-id="4dc1d-114">Remarks</span></span>

<span data-ttu-id="4dc1d-115">不要使用此属性。</span><span class="sxs-lookup"><span data-stu-id="4dc1d-115">Do not use this property.</span></span> <span data-ttu-id="4dc1d-116">它是通过 MAPI 供使用。</span><span class="sxs-lookup"><span data-stu-id="4dc1d-116">It is reserved for use by MAPI.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="4dc1d-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="4dc1d-117">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="4dc1d-118">头文件</span><span class="sxs-lookup"><span data-stu-id="4dc1d-118">Header files</span></span>

<span data-ttu-id="4dc1d-119">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="4dc1d-119">Mapitags.h</span></span>
  
> <span data-ttu-id="4dc1d-120">包含列为相关属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="4dc1d-120">Contains definitions of properties listed as associated properties.</span></span>
    
<span data-ttu-id="4dc1d-121">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="4dc1d-121">Mapidefs.h</span></span>
  
> <span data-ttu-id="4dc1d-122">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="4dc1d-122">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="4dc1d-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4dc1d-123">See also</span></span>



[<span data-ttu-id="4dc1d-124">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="4dc1d-124">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="4dc1d-125">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="4dc1d-125">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="4dc1d-126">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="4dc1d-126">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="4dc1d-127">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="4dc1d-127">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

