---
title: PidTagContentCount 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagContentCount
api_type:
- HeaderDef
ms.assetid: 27c75031-a968-4636-98a6-4a5b7422f57c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 3c542b07eac626da5fbbb6a96b4545ad3c8558b6
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777487"
---
# <a name="pidtagcontentcount-canonical-property"></a><span data-ttu-id="b15a4-103">PidTagContentCount 规范属性</span><span class="sxs-lookup"><span data-stu-id="b15a4-103">PidTagContentCount Canonical Property</span></span>

  
  
<span data-ttu-id="b15a4-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="b15a4-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="b15a4-105">计算出的消息存储库包含文件夹中的消息的数。</span><span class="sxs-lookup"><span data-stu-id="b15a4-105">Contains the number of messages in a folder, as computed by the message store.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="b15a4-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="b15a4-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="b15a4-107">PR_CONTENT_COUNT</span><span class="sxs-lookup"><span data-stu-id="b15a4-107">PR_CONTENT_COUNT</span></span>  <br/> |
|<span data-ttu-id="b15a4-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="b15a4-108">Identifier:</span></span>  <br/> |<span data-ttu-id="b15a4-109">0x3602</span><span class="sxs-lookup"><span data-stu-id="b15a4-109">0x3602</span></span>  <br/> |
|<span data-ttu-id="b15a4-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="b15a4-110">Data type:</span></span>  <br/> |<span data-ttu-id="b15a4-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="b15a4-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="b15a4-112">区域：</span><span class="sxs-lookup"><span data-stu-id="b15a4-112">Area:</span></span>  <br/> |<span data-ttu-id="b15a4-113">Folder</span><span class="sxs-lookup"><span data-stu-id="b15a4-113">Folder</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="b15a4-114">说明</span><span class="sxs-lookup"><span data-stu-id="b15a4-114">Remarks</span></span>

<span data-ttu-id="b15a4-115">消息存储通过计算此属性用于两个不同的但相关，目的。</span><span class="sxs-lookup"><span data-stu-id="b15a4-115">This property computed by the message store is used for two different, though related, purposes.</span></span> <span data-ttu-id="b15a4-116">MapiFolder 对象，它包含文件夹中的消息的数。</span><span class="sxs-lookup"><span data-stu-id="b15a4-116">On a MapiFolder object, it contains the number of messages in a folder.</span></span> <span data-ttu-id="b15a4-117">在分类 MAPI 表中的标题行中，它包含非关联的标题行所对应的类别中的消息数。</span><span class="sxs-lookup"><span data-stu-id="b15a4-117">In a heading row in categorized MAPI tables, it contains the number of non-associated messages in the category corresponding to that heading row.</span></span>
  
<span data-ttu-id="b15a4-118">此属性中包含的数字不包括文件夹中的相关联的条目。</span><span class="sxs-lookup"><span data-stu-id="b15a4-118">The number contained in this property does not include associated entries in the folder.</span></span> <span data-ttu-id="b15a4-119">**PR_CONTENT_UNREAD**([PidTagContentUnreadCount](pidtagcontentunreadcount-canonical-property.md)) 包含的文件夹的未读邮件的计数。</span><span class="sxs-lookup"><span data-stu-id="b15a4-119">**PR_CONTENT_UNREAD** ([PidTagContentUnreadCount](pidtagcontentunreadcount-canonical-property.md)) contains the count of unread messages for the folder.</span></span> <span data-ttu-id="b15a4-120">客户端应用程序可以读取但不是能更改此属性和**PR_CONTENT_UNREAD**。</span><span class="sxs-lookup"><span data-stu-id="b15a4-120">A client application can read but not change this property and **PR_CONTENT_UNREAD**.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="b15a4-121">相关资源</span><span class="sxs-lookup"><span data-stu-id="b15a4-121">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="b15a4-122">协议规范</span><span class="sxs-lookup"><span data-stu-id="b15a4-122">Protocol specifications</span></span>

<span data-ttu-id="b15a4-123">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b15a4-123">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b15a4-124">提供了相关的 Microsoft Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="b15a4-124">Provides references to related Microsoft Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="b15a4-125">[[MS OXCFOLD]](http://msdn.microsoft.com/library/c0f31b95-c07f-486c-98d9-535ed9705fbf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b15a4-125">[[MS-OXCFOLD]](http://msdn.microsoft.com/library/c0f31b95-c07f-486c-98d9-535ed9705fbf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b15a4-126">处理文件夹的操作。</span><span class="sxs-lookup"><span data-stu-id="b15a4-126">Handles folder operations.</span></span>
    
<span data-ttu-id="b15a4-127">[[MS OXCTABL]](http://msdn.microsoft.com/library/d33612dc-36a8-4623-8a26-c156cf8aae4b%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b15a4-127">[[MS-OXCTABL]](http://msdn.microsoft.com/library/d33612dc-36a8-4623-8a26-c156cf8aae4b%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b15a4-128">包含允许的操作的核心 table 对象。</span><span class="sxs-lookup"><span data-stu-id="b15a4-128">Includes permissible operations for the core table objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="b15a4-129">头文件</span><span class="sxs-lookup"><span data-stu-id="b15a4-129">Header files</span></span>

<span data-ttu-id="b15a4-130">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="b15a4-130">Mapidefs.h</span></span>
  
> <span data-ttu-id="b15a4-131">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="b15a4-131">Provides data type definitions.</span></span>
    
<span data-ttu-id="b15a4-132">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="b15a4-132">Mapitags.h</span></span>
  
> <span data-ttu-id="b15a4-133">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="b15a4-133">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="b15a4-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b15a4-134">See also</span></span>



[<span data-ttu-id="b15a4-135">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="b15a4-135">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="b15a4-136">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="b15a4-136">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="b15a4-137">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="b15a4-137">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="b15a4-138">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="b15a4-138">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

