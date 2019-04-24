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
ms.openlocfilehash: 7e9994da72bbc38a546f220e5ecf8768b80c6f1f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32331953"
---
# <a name="pidtagcontentcount-canonical-property"></a><span data-ttu-id="d2747-103">PidTagContentCount 规范属性</span><span class="sxs-lookup"><span data-stu-id="d2747-103">PidTagContentCount Canonical Property</span></span>

  
  
<span data-ttu-id="d2747-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d2747-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d2747-105">包含文件夹中的邮件数, 由邮件存储区计算得出。</span><span class="sxs-lookup"><span data-stu-id="d2747-105">Contains the number of messages in a folder, as computed by the message store.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="d2747-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="d2747-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="d2747-107">PR_CONTENT_COUNT</span><span class="sxs-lookup"><span data-stu-id="d2747-107">PR_CONTENT_COUNT</span></span>  <br/> |
|<span data-ttu-id="d2747-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="d2747-108">Identifier:</span></span>  <br/> |<span data-ttu-id="d2747-109">0x3602</span><span class="sxs-lookup"><span data-stu-id="d2747-109">0x3602</span></span>  <br/> |
|<span data-ttu-id="d2747-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="d2747-110">Data type:</span></span>  <br/> |<span data-ttu-id="d2747-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="d2747-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="d2747-112">区域：</span><span class="sxs-lookup"><span data-stu-id="d2747-112">Area:</span></span>  <br/> |<span data-ttu-id="d2747-113">Folder</span><span class="sxs-lookup"><span data-stu-id="d2747-113">Folder</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="d2747-114">注解</span><span class="sxs-lookup"><span data-stu-id="d2747-114">Remarks</span></span>

<span data-ttu-id="d2747-115">此属性由邮件存储区计算, 但有两种不同的用途。</span><span class="sxs-lookup"><span data-stu-id="d2747-115">This property computed by the message store is used for two different, though related, purposes.</span></span> <span data-ttu-id="d2747-116">在 MapiFolder 对象上, 它包含文件夹中的邮件数。</span><span class="sxs-lookup"><span data-stu-id="d2747-116">On a MapiFolder object, it contains the number of messages in a folder.</span></span> <span data-ttu-id="d2747-117">在分类 MAPI 表的标题行中, 它包含与标题行对应的类别中的非关联邮件数。</span><span class="sxs-lookup"><span data-stu-id="d2747-117">In a heading row in categorized MAPI tables, it contains the number of non-associated messages in the category corresponding to that heading row.</span></span>
  
<span data-ttu-id="d2747-118">此属性中包含的数字不包含文件夹中的关联项。</span><span class="sxs-lookup"><span data-stu-id="d2747-118">The number contained in this property does not include associated entries in the folder.</span></span> <span data-ttu-id="d2747-119">**PR_CONTENT_UNREAD**([PidTagContentUnreadCount](pidtagcontentunreadcount-canonical-property.md)) 包含文件夹的未读邮件数。</span><span class="sxs-lookup"><span data-stu-id="d2747-119">**PR_CONTENT_UNREAD** ([PidTagContentUnreadCount](pidtagcontentunreadcount-canonical-property.md)) contains the count of unread messages for the folder.</span></span> <span data-ttu-id="d2747-120">客户端应用程序可以读取但不能更改此属性和**PR_CONTENT_UNREAD**。</span><span class="sxs-lookup"><span data-stu-id="d2747-120">A client application can read but not change this property and **PR_CONTENT_UNREAD**.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="d2747-121">相关资源</span><span class="sxs-lookup"><span data-stu-id="d2747-121">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="d2747-122">协议规范</span><span class="sxs-lookup"><span data-stu-id="d2747-122">Protocol specifications</span></span>

<span data-ttu-id="d2747-123">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="d2747-123">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="d2747-124">提供对相关 Microsoft Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="d2747-124">Provides references to related Microsoft Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="d2747-125">[[毫秒-OXCFOLD]](https://msdn.microsoft.com/library/c0f31b95-c07f-486c-98d9-535ed9705fbf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="d2747-125">[[MS-OXCFOLD]](https://msdn.microsoft.com/library/c0f31b95-c07f-486c-98d9-535ed9705fbf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="d2747-126">处理文件夹操作。</span><span class="sxs-lookup"><span data-stu-id="d2747-126">Handles folder operations.</span></span>
    
<span data-ttu-id="d2747-127">[[毫秒-OXCTABL]](https://msdn.microsoft.com/library/d33612dc-36a8-4623-8a26-c156cf8aae4b%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="d2747-127">[[MS-OXCTABL]](https://msdn.microsoft.com/library/d33612dc-36a8-4623-8a26-c156cf8aae4b%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="d2747-128">包括核心表对象的允许操作。</span><span class="sxs-lookup"><span data-stu-id="d2747-128">Includes permissible operations for the core table objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="d2747-129">头文件</span><span class="sxs-lookup"><span data-stu-id="d2747-129">Header files</span></span>

<span data-ttu-id="d2747-130">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="d2747-130">Mapidefs.h</span></span>
  
> <span data-ttu-id="d2747-131">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="d2747-131">Provides data type definitions.</span></span>
    
<span data-ttu-id="d2747-132">Mapitags</span><span class="sxs-lookup"><span data-stu-id="d2747-132">Mapitags.h</span></span>
  
> <span data-ttu-id="d2747-133">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="d2747-133">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="d2747-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d2747-134">See also</span></span>



[<span data-ttu-id="d2747-135">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="d2747-135">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="d2747-136">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="d2747-136">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="d2747-137">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="d2747-137">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="d2747-138">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="d2747-138">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

