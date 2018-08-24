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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: e0f13b0b8d2f7eb6fd7ba60e9e351b62251aa13d
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22572835"
---
# <a name="pidtagprovideritemid-canonical-property"></a><span data-ttu-id="163b7-103">PidTagProviderItemId 规范属性</span><span class="sxs-lookup"><span data-stu-id="163b7-103">PidTagProviderItemId Canonical Property</span></span>

  
  
<span data-ttu-id="163b7-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="163b7-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="163b7-105">指定存储区中的文件夹或项目的标识符。</span><span class="sxs-lookup"><span data-stu-id="163b7-105">Specifies an identifier for a folder or an item in a store.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="163b7-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="163b7-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="163b7-107">PR_PROVIDER_ITEMID</span><span class="sxs-lookup"><span data-stu-id="163b7-107">PR_PROVIDER_ITEMID</span></span>  <br/> |
|<span data-ttu-id="163b7-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="163b7-108">Identifier:</span></span>  <br/> |<span data-ttu-id="163b7-109">0x0EA3</span><span class="sxs-lookup"><span data-stu-id="163b7-109">0x0EA3</span></span>  <br/> |
|<span data-ttu-id="163b7-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="163b7-110">Data type:</span></span>  <br/> |<span data-ttu-id="163b7-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="163b7-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="163b7-112">区域：</span><span class="sxs-lookup"><span data-stu-id="163b7-112">Area:</span></span>  <br/> |<span data-ttu-id="163b7-113">MapiNonTransmittable</span><span class="sxs-lookup"><span data-stu-id="163b7-113">MapiNonTransmittable</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="163b7-114">注解</span><span class="sxs-lookup"><span data-stu-id="163b7-114">Remarks</span></span>

<span data-ttu-id="163b7-115">存储提供程序可以指定的文件夹或项目，此属性的值，但应保留值之间会话相同。</span><span class="sxs-lookup"><span data-stu-id="163b7-115">Store providers can specify a value for this property for a folder or an item, but should keep the value the same between sessions.</span></span> <span data-ttu-id="163b7-116">存储提供程序使用此属性标识的搜索引擎从返回的搜索结果。</span><span class="sxs-lookup"><span data-stu-id="163b7-116">Store providers use this property to identify search results returned from a search engine.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="163b7-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="163b7-117">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="163b7-118">头文件</span><span class="sxs-lookup"><span data-stu-id="163b7-118">Header files</span></span>

<span data-ttu-id="163b7-119">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="163b7-119">Mapidefs.h</span></span>
  
> <span data-ttu-id="163b7-120">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="163b7-120">Provides data type definitions.</span></span>
    
<span data-ttu-id="163b7-121">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="163b7-121">Mapitags.h</span></span>
  
> <span data-ttu-id="163b7-122">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="163b7-122">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="163b7-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="163b7-123">See also</span></span>



[<span data-ttu-id="163b7-124">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="163b7-124">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="163b7-125">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="163b7-125">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="163b7-126">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="163b7-126">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="163b7-127">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="163b7-127">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

