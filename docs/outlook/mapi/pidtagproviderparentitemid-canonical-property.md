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
ms.openlocfilehash: 0f99cf38e65c75ce1ba74bf72d88e19f4fbfa03a
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33433414"
---
# <a name="pidtagproviderparentitemid-canonical-property"></a><span data-ttu-id="64471-103">PidTagProviderParentItemId 规范属性</span><span class="sxs-lookup"><span data-stu-id="64471-103">PidTagProviderParentItemId Canonical Property</span></span>

  
  
<span data-ttu-id="64471-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="64471-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="64471-105">指定文件夹或存储区中项目的父级的标识符。</span><span class="sxs-lookup"><span data-stu-id="64471-105">Specifies an identifier for the parent of a folder or an item in a store.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="64471-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="64471-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="64471-107">PR_PROVIDER_PARENT_ITEMID</span><span class="sxs-lookup"><span data-stu-id="64471-107">PR_PROVIDER_PARENT_ITEMID</span></span>  <br/> |
|<span data-ttu-id="64471-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="64471-108">Identifier:</span></span>  <br/> |<span data-ttu-id="64471-109">0x0EA4</span><span class="sxs-lookup"><span data-stu-id="64471-109">0x0EA4</span></span>  <br/> |
|<span data-ttu-id="64471-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="64471-110">Data type:</span></span>  <br/> |<span data-ttu-id="64471-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="64471-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="64471-112">区域：</span><span class="sxs-lookup"><span data-stu-id="64471-112">Area:</span></span>  <br/> |<span data-ttu-id="64471-113">MAPI 不可传输</span><span class="sxs-lookup"><span data-stu-id="64471-113">MAPI non-transmittable</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="64471-114">备注</span><span class="sxs-lookup"><span data-stu-id="64471-114">Remarks</span></span>

<span data-ttu-id="64471-115">存储提供程序可以为此属性的值指定文件夹或项目的父级，但应在会话之间保持值相同。</span><span class="sxs-lookup"><span data-stu-id="64471-115">Store providers can specify a value for this property for a parent of a folder or an item, but should keep the value the same between sessions.</span></span> <span data-ttu-id="64471-116">存储提供程序使用此属性标识从搜索引擎返回的搜索结果。</span><span class="sxs-lookup"><span data-stu-id="64471-116">Store providers use this property to identify search results returned from a search engine.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="64471-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="64471-117">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="64471-118">头文件</span><span class="sxs-lookup"><span data-stu-id="64471-118">Header files</span></span>

<span data-ttu-id="64471-119">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="64471-119">Mapidefs.h</span></span>
  
> <span data-ttu-id="64471-120">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="64471-120">Provides data type definitions.</span></span>
    
<span data-ttu-id="64471-121">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="64471-121">Mapitags.h</span></span>
  
> <span data-ttu-id="64471-122">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="64471-122">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="64471-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="64471-123">See also</span></span>



[<span data-ttu-id="64471-124">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="64471-124">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="64471-125">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="64471-125">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="64471-126">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="64471-126">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="64471-127">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="64471-127">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

