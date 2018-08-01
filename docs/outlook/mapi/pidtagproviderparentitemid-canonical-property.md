---
title: PidTagProviderParentItemId 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagProviderParentItemId
api_type:
- COM
ms.assetid: 6adb8e85-ae56-4542-8b19-ed3cfe7fe522
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 96a9d153fadbe8b4c8baa8532b8c99771b1d7987
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778079"
---
# <a name="pidtagproviderparentitemid-canonical-property"></a><span data-ttu-id="35d11-103">PidTagProviderParentItemId 规范属性</span><span class="sxs-lookup"><span data-stu-id="35d11-103">PidTagProviderParentItemId Canonical Property</span></span>

  
  
<span data-ttu-id="35d11-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="35d11-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="35d11-105">指定父文件夹或存储中的项的标识符。</span><span class="sxs-lookup"><span data-stu-id="35d11-105">Specifies an identifier for the parent of a folder or an item in a store.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="35d11-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="35d11-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="35d11-107">PR_PROVIDER_PARENT_ITEMID</span><span class="sxs-lookup"><span data-stu-id="35d11-107">PR_PROVIDER_PARENT_ITEMID</span></span>  <br/> |
|<span data-ttu-id="35d11-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="35d11-108">Identifier:</span></span>  <br/> |<span data-ttu-id="35d11-109">0x0EA4</span><span class="sxs-lookup"><span data-stu-id="35d11-109">0x0EA4</span></span>  <br/> |
|<span data-ttu-id="35d11-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="35d11-110">Data type:</span></span>  <br/> |<span data-ttu-id="35d11-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="35d11-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="35d11-112">区域：</span><span class="sxs-lookup"><span data-stu-id="35d11-112">Area:</span></span>  <br/> |<span data-ttu-id="35d11-113">MAPI 非可传送</span><span class="sxs-lookup"><span data-stu-id="35d11-113">MAPI non-transmittable</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="35d11-114">说明</span><span class="sxs-lookup"><span data-stu-id="35d11-114">Remarks</span></span>

<span data-ttu-id="35d11-115">存储提供程序的文件夹或项目的父对象可以指定此属性的值，但应保留值之间会话相同。</span><span class="sxs-lookup"><span data-stu-id="35d11-115">Store providers can specify a value for this property for a parent of a folder or an item, but should keep the value the same between sessions.</span></span> <span data-ttu-id="35d11-116">存储提供程序使用此属性标识的搜索引擎从返回的搜索结果。</span><span class="sxs-lookup"><span data-stu-id="35d11-116">Store providers use this property to identify search results returned from a search engine.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="35d11-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="35d11-117">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="35d11-118">头文件</span><span class="sxs-lookup"><span data-stu-id="35d11-118">Header files</span></span>

<span data-ttu-id="35d11-119">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="35d11-119">Mapidefs.h</span></span>
  
> <span data-ttu-id="35d11-120">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="35d11-120">Provides data type definitions.</span></span>
    
<span data-ttu-id="35d11-121">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="35d11-121">Mapitags.h</span></span>
  
> <span data-ttu-id="35d11-122">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="35d11-122">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="35d11-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="35d11-123">See also</span></span>



[<span data-ttu-id="35d11-124">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="35d11-124">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="35d11-125">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="35d11-125">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="35d11-126">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="35d11-126">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="35d11-127">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="35d11-127">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

