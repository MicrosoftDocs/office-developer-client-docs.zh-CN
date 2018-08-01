---
title: PidTagSearchFolderEfpFlags 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagSearchFolderEfpFlags
api_type:
- COM
ms.assetid: ef82a75f-a09f-4880-ba6a-e739b16422a3
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: e98416ba7796c66d719adcc27ba8029b7908bb79
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778381"
---
# <a name="pidtagsearchfolderefpflags-canonical-property"></a><span data-ttu-id="fcddc-103">PidTagSearchFolderEfpFlags 规范属性</span><span class="sxs-lookup"><span data-stu-id="fcddc-103">PidTagSearchFolderEfpFlags Canonical Property</span></span>

  
  
<span data-ttu-id="fcddc-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="fcddc-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="fcddc-105">包含应用于的搜索文件夹的搜索文件夹容器的扩展的文件夹标志。</span><span class="sxs-lookup"><span data-stu-id="fcddc-105">Contains extended folder flags that apply to the search folder container for the search folder.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="fcddc-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="fcddc-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="fcddc-107">PR_WB_SF_EFP_FLAGS</span><span class="sxs-lookup"><span data-stu-id="fcddc-107">PR_WB_SF_EFP_FLAGS</span></span>  <br/> |
|<span data-ttu-id="fcddc-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="fcddc-108">Identifier:</span></span>  <br/> |<span data-ttu-id="fcddc-109">0x6848</span><span class="sxs-lookup"><span data-stu-id="fcddc-109">0x6848</span></span>  <br/> |
|<span data-ttu-id="fcddc-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="fcddc-110">Data type:</span></span>  <br/> |<span data-ttu-id="fcddc-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="fcddc-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="fcddc-112">区域：</span><span class="sxs-lookup"><span data-stu-id="fcddc-112">Area:</span></span>  <br/> |<span data-ttu-id="fcddc-113">搜索</span><span class="sxs-lookup"><span data-stu-id="fcddc-113">Search</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="fcddc-114">说明</span><span class="sxs-lookup"><span data-stu-id="fcddc-114">Remarks</span></span>

<span data-ttu-id="fcddc-115">具体而言，此属性应包含**PR_EXTENDED_FOLDER_FLAGS** ([PidTagExtendedFolderFlags](pidtagextendedfolderflags-canonical-property.md)) 属性和字段 b 的文件夹中的**ExtendedFlags**子属性中的标志。</span><span class="sxs-lookup"><span data-stu-id="fcddc-115">This property should specifically contain the flags in the **PR_EXTENDED_FOLDER_FLAGS** ([PidTagExtendedFolderFlags](pidtagextendedfolderflags-canonical-property.md)) property, and the **ExtendedFlags** sub-property, in field b for the folder.</span></span> <span data-ttu-id="fcddc-116">有关文件夹标志信息，请参阅[[MS OXOCFG]](http://msdn.microsoft.com/library/7d466dd5-c156-4da9-9a01-75c78e7e1a67%28Office.15%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="fcddc-116">For information about folder flags see the [[MS-OXOCFG]](http://msdn.microsoft.com/library/7d466dd5-c156-4da9-9a01-75c78e7e1a67%28Office.15%29.aspx).</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="fcddc-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="fcddc-117">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="fcddc-118">协议规范</span><span class="sxs-lookup"><span data-stu-id="fcddc-118">Protocol specifications</span></span>

<span data-ttu-id="fcddc-119">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="fcddc-119">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="fcddc-120">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="fcddc-120">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="fcddc-121">[[MS OXOSRCH]](http://msdn.microsoft.com/library/c72e49b8-78c7-4483-ad65-e46e9133673b%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="fcddc-121">[[MS-OXOSRCH]](http://msdn.microsoft.com/library/c72e49b8-78c7-4483-ad65-e46e9133673b%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="fcddc-122">指定的属性和操作的搜索文件夹列表配置的操作。</span><span class="sxs-lookup"><span data-stu-id="fcddc-122">Specifies the properties and operations for manipulating a search folder list configuration.</span></span>
    
<span data-ttu-id="fcddc-123">[[MS OXOCFG]](http://msdn.microsoft.com/library/7d466dd5-c156-4da9-9a01-75c78e7e1a67%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="fcddc-123">[[MS-OXOCFG]](http://msdn.microsoft.com/library/7d466dd5-c156-4da9-9a01-75c78e7e1a67%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="fcddc-124">指定的位置和客户端和服务器配置数据，如共享的类别列表和工作时间的属性。</span><span class="sxs-lookup"><span data-stu-id="fcddc-124">Specifies the location and properties of client and server configuration data, such as shared category lists and working hours.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="fcddc-125">头文件</span><span class="sxs-lookup"><span data-stu-id="fcddc-125">Header files</span></span>

<span data-ttu-id="fcddc-126">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="fcddc-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="fcddc-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="fcddc-127">Provides data type definitions.</span></span>
    
<span data-ttu-id="fcddc-128">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="fcddc-128">Mapitags.h</span></span>
  
> <span data-ttu-id="fcddc-129">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="fcddc-129">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="fcddc-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fcddc-130">See also</span></span>



[<span data-ttu-id="fcddc-131">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="fcddc-131">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="fcddc-132">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="fcddc-132">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="fcddc-133">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="fcddc-133">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="fcddc-134">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="fcddc-134">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

