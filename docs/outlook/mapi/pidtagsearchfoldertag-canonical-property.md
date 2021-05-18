---
title: PidTagSearchFolderTag 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_type:
- COM
ms.assetid: b7a88387-72ff-49e5-b73a-8bafab635658
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a4ad72c147abebfe9863d19690bc9f27f00544a2
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32282318"
---
# <a name="pidtagsearchfoldertag-canonical-property"></a><span data-ttu-id="54817-103">PidTagSearchFolderTag 规范属性</span><span class="sxs-lookup"><span data-stu-id="54817-103">PidTagSearchFolderTag Canonical Property</span></span>

  
  
<span data-ttu-id="54817-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="54817-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="54817-105">包含用于将此定义邮件与匹配的搜索文件夹容器同步的值。</span><span class="sxs-lookup"><span data-stu-id="54817-105">Contains the value used to synchronize this definition message with the matching search folder container.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="54817-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="54817-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="54817-107">PR_WB_SF_TAG</span><span class="sxs-lookup"><span data-stu-id="54817-107">PR_WB_SF_TAG</span></span>  <br/> |
|<span data-ttu-id="54817-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="54817-108">Identifier:</span></span>  <br/> |<span data-ttu-id="54817-109">0x6847</span><span class="sxs-lookup"><span data-stu-id="54817-109">0x6847</span></span>  <br/> |
|<span data-ttu-id="54817-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="54817-110">Data type:</span></span>  <br/> |<span data-ttu-id="54817-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="54817-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="54817-112">区域：</span><span class="sxs-lookup"><span data-stu-id="54817-112">Area:</span></span>  <br/> |<span data-ttu-id="54817-113">搜索</span><span class="sxs-lookup"><span data-stu-id="54817-113">Search</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="54817-114">备注</span><span class="sxs-lookup"><span data-stu-id="54817-114">Remarks</span></span>

<span data-ttu-id="54817-115">更改定义消息时，将更改此属性。</span><span class="sxs-lookup"><span data-stu-id="54817-115">This property is changed when the definition message is changed.</span></span> <span data-ttu-id="54817-116">它必须更改每个迭代，但它可能并不唯一。</span><span class="sxs-lookup"><span data-stu-id="54817-116">It must change each iteration, but it may not be unique.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="54817-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="54817-117">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="54817-118">协议规范</span><span class="sxs-lookup"><span data-stu-id="54817-118">Protocol specifications</span></span>

<span data-ttu-id="54817-119">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="54817-119">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="54817-120">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="54817-120">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="54817-121">[[MS-OXOSRCH]](https://msdn.microsoft.com/library/c72e49b8-78c7-4483-ad65-e46e9133673b%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="54817-121">[[MS-OXOSRCH]](https://msdn.microsoft.com/library/c72e49b8-78c7-4483-ad65-e46e9133673b%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="54817-122">指定用于操作搜索文件夹列表配置的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="54817-122">Specifies the properties and operations for manipulating a search folder list configuration.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="54817-123">头文件</span><span class="sxs-lookup"><span data-stu-id="54817-123">Header files</span></span>

<span data-ttu-id="54817-124">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="54817-124">Mapidefs.h</span></span>
  
> <span data-ttu-id="54817-125">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="54817-125">Provides data type definitions.</span></span>
    
<span data-ttu-id="54817-126">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="54817-126">Mapitags.h</span></span>
  
> <span data-ttu-id="54817-127">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="54817-127">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="54817-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="54817-128">See also</span></span>



[<span data-ttu-id="54817-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="54817-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="54817-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="54817-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="54817-131">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="54817-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="54817-132">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="54817-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

