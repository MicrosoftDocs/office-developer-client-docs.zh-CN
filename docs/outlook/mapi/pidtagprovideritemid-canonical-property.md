---
title: PidTagProviderItemId 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagProviderItemId
api_type:
- COM
ms.assetid: fadbf1af-32c2-43ea-8475-15b31b2a9e68
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 35a2d88ec838a9a76355ba6580e9cdbb3f28de56
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778104"
---
# <a name="pidtagprovideritemid-canonical-property"></a><span data-ttu-id="5bd3d-103">PidTagProviderItemId 规范属性</span><span class="sxs-lookup"><span data-stu-id="5bd3d-103">PidTagProviderItemId Canonical Property</span></span>

  
  
<span data-ttu-id="5bd3d-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="5bd3d-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="5bd3d-105">指定存储区中的文件夹或项目的标识符。</span><span class="sxs-lookup"><span data-stu-id="5bd3d-105">Specifies an identifier for a folder or an item in a store.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="5bd3d-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="5bd3d-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="5bd3d-107">PR_PROVIDER_ITEMID</span><span class="sxs-lookup"><span data-stu-id="5bd3d-107">PR_PROVIDER_ITEMID</span></span>  <br/> |
|<span data-ttu-id="5bd3d-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="5bd3d-108">Identifier:</span></span>  <br/> |<span data-ttu-id="5bd3d-109">0x0EA3</span><span class="sxs-lookup"><span data-stu-id="5bd3d-109">0x0EA3</span></span>  <br/> |
|<span data-ttu-id="5bd3d-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="5bd3d-110">Data type:</span></span>  <br/> |<span data-ttu-id="5bd3d-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="5bd3d-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="5bd3d-112">区域：</span><span class="sxs-lookup"><span data-stu-id="5bd3d-112">Area:</span></span>  <br/> |<span data-ttu-id="5bd3d-113">MapiNonTransmittable</span><span class="sxs-lookup"><span data-stu-id="5bd3d-113">MapiNonTransmittable</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="5bd3d-114">备注</span><span class="sxs-lookup"><span data-stu-id="5bd3d-114">Remarks</span></span>

<span data-ttu-id="5bd3d-115">存储提供程序可以指定的文件夹或项目，此属性的值，但应保留值之间会话相同。</span><span class="sxs-lookup"><span data-stu-id="5bd3d-115">Store providers can specify a value for this property for a folder or an item, but should keep the value the same between sessions.</span></span> <span data-ttu-id="5bd3d-116">存储提供程序使用此属性标识的搜索引擎从返回的搜索结果。</span><span class="sxs-lookup"><span data-stu-id="5bd3d-116">Store providers use this property to identify search results returned from a search engine.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="5bd3d-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="5bd3d-117">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="5bd3d-118">头文件</span><span class="sxs-lookup"><span data-stu-id="5bd3d-118">Header files</span></span>

<span data-ttu-id="5bd3d-119">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="5bd3d-119">Mapidefs.h</span></span>
  
> <span data-ttu-id="5bd3d-120">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="5bd3d-120">Provides data type definitions.</span></span>
    
<span data-ttu-id="5bd3d-121">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="5bd3d-121">Mapitags.h</span></span>
  
> <span data-ttu-id="5bd3d-122">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="5bd3d-122">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="5bd3d-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5bd3d-123">See also</span></span>



[<span data-ttu-id="5bd3d-124">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="5bd3d-124">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="5bd3d-125">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="5bd3d-125">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="5bd3d-126">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="5bd3d-126">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="5bd3d-127">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="5bd3d-127">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

