---
title: PidTagSearchFolderDefinition 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagSearchFolderDefinition
api_type:
- COM
ms.assetid: a61056e7-365c-4972-abf7-26e2ab07105d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 3b4e5fa7228cf243c79a8ec0c9e2b73b7da21c6f
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25398785"
---
# <a name="pidtagsearchfolderdefinition-canonical-property"></a><span data-ttu-id="32fdd-103">PidTagSearchFolderDefinition 规范属性</span><span class="sxs-lookup"><span data-stu-id="32fdd-103">PidTagSearchFolderDefinition Canonical Property</span></span>

  
  
<span data-ttu-id="32fdd-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="32fdd-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="32fdd-105">包含指定的搜索条件的数据。</span><span class="sxs-lookup"><span data-stu-id="32fdd-105">Contains data that specifies the search criteria.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="32fdd-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="32fdd-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="32fdd-107">PR_WB_SF_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="32fdd-107">PR_WB_SF_DEFINITION</span></span>  <br/> |
|<span data-ttu-id="32fdd-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="32fdd-108">Identifier:</span></span>  <br/> |<span data-ttu-id="32fdd-109">0x6845</span><span class="sxs-lookup"><span data-stu-id="32fdd-109">0x6845</span></span>  <br/> |
|<span data-ttu-id="32fdd-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="32fdd-110">Data type:</span></span>  <br/> |<span data-ttu-id="32fdd-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="32fdd-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="32fdd-112">区域：</span><span class="sxs-lookup"><span data-stu-id="32fdd-112">Area:</span></span>  <br/> |<span data-ttu-id="32fdd-113">搜索</span><span class="sxs-lookup"><span data-stu-id="32fdd-113">Search</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="32fdd-114">说明</span><span class="sxs-lookup"><span data-stu-id="32fdd-114">Remarks</span></span>

<span data-ttu-id="32fdd-115">包含此属性中的二进制大型对象 (BLOB) 的每个字段的特定内容取决于**PidTagSearchFolderTemplateId** ([PidTagSearchFolderTemplateId](pidtagsearchfoldertemplateid-canonical-property.md)) 属性中指定的模板 ID。</span><span class="sxs-lookup"><span data-stu-id="32fdd-115">The specific content of each field of the binary large object (BLOB) contained in this property is dependent upon the template ID that is specified in **PidTagSearchFolderTemplateId** ([PidTagSearchFolderTemplateId](pidtagsearchfoldertemplateid-canonical-property.md)) property.</span></span> <span data-ttu-id="32fdd-116">有关 BLOB 结构和搜索模板的信息，请参阅[[MS OXOSRCH]](https://msdn.microsoft.com/library/c72e49b8-78c7-4483-ad65-e46e9133673b%28Office.15%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="32fdd-116">For information about the BLOB structure and search templates, see [[MS-OXOSRCH]](https://msdn.microsoft.com/library/c72e49b8-78c7-4483-ad65-e46e9133673b%28Office.15%29.aspx).</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="32fdd-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="32fdd-117">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="32fdd-118">协议规范</span><span class="sxs-lookup"><span data-stu-id="32fdd-118">Protocol specifications</span></span>

<span data-ttu-id="32fdd-119">[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="32fdd-119">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="32fdd-120">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="32fdd-120">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="32fdd-121">[[MS OXOSRCH]](https://msdn.microsoft.com/library/c72e49b8-78c7-4483-ad65-e46e9133673b%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="32fdd-121">[[MS-OXOSRCH]](https://msdn.microsoft.com/library/c72e49b8-78c7-4483-ad65-e46e9133673b%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="32fdd-122">指定的属性和操作的搜索文件夹列表配置的操作。</span><span class="sxs-lookup"><span data-stu-id="32fdd-122">Specifies the properties and operations for manipulating a search folder list configuration.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="32fdd-123">头文件</span><span class="sxs-lookup"><span data-stu-id="32fdd-123">Header files</span></span>

<span data-ttu-id="32fdd-124">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="32fdd-124">Mapidefs.h</span></span>
  
> <span data-ttu-id="32fdd-125">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="32fdd-125">Provides data type definitions.</span></span>
    
<span data-ttu-id="32fdd-126">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="32fdd-126">Mapitags.h</span></span>
  
> <span data-ttu-id="32fdd-127">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="32fdd-127">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="32fdd-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="32fdd-128">See also</span></span>



[<span data-ttu-id="32fdd-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="32fdd-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="32fdd-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="32fdd-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="32fdd-131">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="32fdd-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="32fdd-132">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="32fdd-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

