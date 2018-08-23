---
title: PidTagSearchFolderLastUsed 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagSearchFolderLastUsed
api_type:
- COM
ms.assetid: e4071307-6205-4079-ab65-7499d14f145c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 6cafa336bf915abd35de07a11ee65baf9ac4d69f
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22572688"
---
# <a name="pidtagsearchfolderlastused-canonical-property"></a><span data-ttu-id="1d8f8-103">PidTagSearchFolderLastUsed 规范属性</span><span class="sxs-lookup"><span data-stu-id="1d8f8-103">PidTagSearchFolderLastUsed Canonical Property</span></span>

  
  
<span data-ttu-id="1d8f8-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="1d8f8-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="1d8f8-105">表示的上次访问文件夹。</span><span class="sxs-lookup"><span data-stu-id="1d8f8-105">Represents the last time the folder was accessed.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="1d8f8-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="1d8f8-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="1d8f8-107">PR_WB_SF_LAST_USED</span><span class="sxs-lookup"><span data-stu-id="1d8f8-107">PR_WB_SF_LAST_USED</span></span>  <br/> |
|<span data-ttu-id="1d8f8-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="1d8f8-108">Identifier:</span></span>  <br/> |<span data-ttu-id="1d8f8-109">0x6834</span><span class="sxs-lookup"><span data-stu-id="1d8f8-109">0x6834</span></span>  <br/> |
|<span data-ttu-id="1d8f8-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="1d8f8-110">Data type:</span></span>  <br/> |<span data-ttu-id="1d8f8-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="1d8f8-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="1d8f8-112">区域：</span><span class="sxs-lookup"><span data-stu-id="1d8f8-112">Area:</span></span>  <br/> |<span data-ttu-id="1d8f8-113">搜索</span><span class="sxs-lookup"><span data-stu-id="1d8f8-113">Search</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="1d8f8-114">注解</span><span class="sxs-lookup"><span data-stu-id="1d8f8-114">Remarks</span></span>

<span data-ttu-id="1d8f8-115">此属性的格式必须为协调世界时 (UTC) 午夜 1601 年 1 月 1 日以来的分钟数。</span><span class="sxs-lookup"><span data-stu-id="1d8f8-115">This property must be formatted as the number of minutes since midnight Coordinated Universal Time (UTC) January 1, 1601.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="1d8f8-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="1d8f8-116">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="1d8f8-117">协议规范</span><span class="sxs-lookup"><span data-stu-id="1d8f8-117">Protocol specifications</span></span>

<span data-ttu-id="1d8f8-118">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="1d8f8-118">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="1d8f8-119">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="1d8f8-119">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="1d8f8-120">[[MS OXOSRCH]](http://msdn.microsoft.com/library/c72e49b8-78c7-4483-ad65-e46e9133673b%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="1d8f8-120">[[MS-OXOSRCH]](http://msdn.microsoft.com/library/c72e49b8-78c7-4483-ad65-e46e9133673b%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="1d8f8-121">指定的属性和操作的搜索文件夹列表配置的操作。</span><span class="sxs-lookup"><span data-stu-id="1d8f8-121">Specifies the properties and operations for manipulating a search folder list configuration.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="1d8f8-122">头文件</span><span class="sxs-lookup"><span data-stu-id="1d8f8-122">Header files</span></span>

<span data-ttu-id="1d8f8-123">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="1d8f8-123">Mapidefs.h</span></span>
  
> <span data-ttu-id="1d8f8-124">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="1d8f8-124">Provides data type definitions.</span></span>
    
<span data-ttu-id="1d8f8-125">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="1d8f8-125">Mapitags.h</span></span>
  
> <span data-ttu-id="1d8f8-126">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="1d8f8-126">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="1d8f8-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1d8f8-127">See also</span></span>



[<span data-ttu-id="1d8f8-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="1d8f8-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="1d8f8-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="1d8f8-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="1d8f8-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="1d8f8-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="1d8f8-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="1d8f8-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

