---
title: PidTagSearchFolderTemplateId 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagSearchFolderTemplateId
api_type:
- COM
ms.assetid: 56288f55-b3ba-42df-9c90-f9b5857f19a1
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 4e752d3264a64ad7b467947c44d01eb7c47ec863
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778372"
---
# <a name="pidtagsearchfoldertemplateid-canonical-property"></a><span data-ttu-id="ff477-103">PidTagSearchFolderTemplateId 规范属性</span><span class="sxs-lookup"><span data-stu-id="ff477-103">PidTagSearchFolderTemplateId Canonical Property</span></span>

  
  
<span data-ttu-id="ff477-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="ff477-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="ff477-105">包含用于搜索的模板的 ID。</span><span class="sxs-lookup"><span data-stu-id="ff477-105">Contains the ID of the template that is being used for the search.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="ff477-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="ff477-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="ff477-107">PR_WB_SF_TEMPLATE_ID</span><span class="sxs-lookup"><span data-stu-id="ff477-107">PR_WB_SF_TEMPLATE_ID</span></span>  <br/> |
|<span data-ttu-id="ff477-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="ff477-108">Identifier:</span></span>  <br/> |<span data-ttu-id="ff477-109">0x6841</span><span class="sxs-lookup"><span data-stu-id="ff477-109">0x6841</span></span>  <br/> |
|<span data-ttu-id="ff477-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="ff477-110">Data type:</span></span>  <br/> |<span data-ttu-id="ff477-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="ff477-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="ff477-112">区域：</span><span class="sxs-lookup"><span data-stu-id="ff477-112">Area:</span></span>  <br/> |<span data-ttu-id="ff477-113">搜索</span><span class="sxs-lookup"><span data-stu-id="ff477-113">Search</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="ff477-114">备注</span><span class="sxs-lookup"><span data-stu-id="ff477-114">Remarks</span></span>

<span data-ttu-id="ff477-115">搜索文件夹条件被指定的模板。</span><span class="sxs-lookup"><span data-stu-id="ff477-115">Search folder criteria is specified by a template.</span></span> <span data-ttu-id="ff477-116">此属性定义的搜索文件夹的邮件标识其相应的模板。</span><span class="sxs-lookup"><span data-stu-id="ff477-116">This property on the message that defines the search folder identifies its corresponding template.</span></span> <span data-ttu-id="ff477-117">除了定义搜索条件，模板还定义要从搜索中排除的文件夹，定义要从搜索中排除的项目并指定**PR_WB_SF_STORAGE_TYPE** ([PidTagSearchFolderStorageType](pidtagsearchfolderstoragetype-canonical-property.md)) 的值。</span><span class="sxs-lookup"><span data-stu-id="ff477-117">In addition to defining search criteria, a template also defines folders to exclude from the search, defines items to exclude from the search, and specifies the value of **PR_WB_SF_STORAGE_TYPE** ([PidTagSearchFolderStorageType](pidtagsearchfolderstoragetype-canonical-property.md)).</span></span>
  
<span data-ttu-id="ff477-118">有关搜索文件夹模板的详细信息，请参阅[[MS OXOSRCH]](http://msdn.microsoft.com/library/c72e49b8-78c7-4483-ad65-e46e9133673b%28Office.15%29.aspx) 。</span><span class="sxs-lookup"><span data-stu-id="ff477-118">For more information about Search Folder Templates see [[MS-OXOSRCH]](http://msdn.microsoft.com/library/c72e49b8-78c7-4483-ad65-e46e9133673b%28Office.15%29.aspx) .</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="ff477-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="ff477-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="ff477-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="ff477-120">Protocol specifications</span></span>

<span data-ttu-id="ff477-121">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ff477-121">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ff477-122">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="ff477-122">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="ff477-123">[[MS OXOSRCH]](http://msdn.microsoft.com/library/c72e49b8-78c7-4483-ad65-e46e9133673b%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ff477-123">[[MS-OXOSRCH]](http://msdn.microsoft.com/library/c72e49b8-78c7-4483-ad65-e46e9133673b%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ff477-124">指定的属性和操作的搜索文件夹列表配置的操作。</span><span class="sxs-lookup"><span data-stu-id="ff477-124">Specifies the properties and operations for manipulating a search folder list configuration.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="ff477-125">头文件</span><span class="sxs-lookup"><span data-stu-id="ff477-125">Header files</span></span>

<span data-ttu-id="ff477-126">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="ff477-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="ff477-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="ff477-127">Provides data type definitions.</span></span>
    
<span data-ttu-id="ff477-128">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="ff477-128">Mapitags.h</span></span>
  
> <span data-ttu-id="ff477-129">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="ff477-129">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="ff477-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ff477-130">See also</span></span>



[<span data-ttu-id="ff477-131">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="ff477-131">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="ff477-132">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="ff477-132">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="ff477-133">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="ff477-133">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="ff477-134">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="ff477-134">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

