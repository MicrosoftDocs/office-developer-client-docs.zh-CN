---
title: PidTagContentUnreadCount 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagContentUnreadCount
api_type:
- HeaderDef
ms.assetid: 4fe207e9-a77f-46b9-b51d-d989847a9d02
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: ce7092840037345ae99b31c39cfbd4ac96b99ff5
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777493"
---
# <a name="pidtagcontentunreadcount-canonical-property"></a><span data-ttu-id="99f1b-103">PidTagContentUnreadCount 规范属性</span><span class="sxs-lookup"><span data-stu-id="99f1b-103">PidTagContentUnreadCount Canonical Property</span></span>

  
  
<span data-ttu-id="99f1b-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="99f1b-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="99f1b-105">计算出的消息存储库包含文件夹中的未读邮件数。</span><span class="sxs-lookup"><span data-stu-id="99f1b-105">Contains the number of unread messages in a folder, as computed by the message store.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="99f1b-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="99f1b-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="99f1b-107">PR_CONTENT_UNREAD</span><span class="sxs-lookup"><span data-stu-id="99f1b-107">PR_CONTENT_UNREAD</span></span>  <br/> |
|<span data-ttu-id="99f1b-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="99f1b-108">Identifier:</span></span>  <br/> |<span data-ttu-id="99f1b-109">0x3603</span><span class="sxs-lookup"><span data-stu-id="99f1b-109">0x3603</span></span>  <br/> |
|<span data-ttu-id="99f1b-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="99f1b-110">Data type:</span></span>  <br/> |<span data-ttu-id="99f1b-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="99f1b-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="99f1b-112">区域：</span><span class="sxs-lookup"><span data-stu-id="99f1b-112">Area:</span></span>  <br/> |<span data-ttu-id="99f1b-113">Folder</span><span class="sxs-lookup"><span data-stu-id="99f1b-113">Folder</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="99f1b-114">说明</span><span class="sxs-lookup"><span data-stu-id="99f1b-114">Remarks</span></span>

<span data-ttu-id="99f1b-115">消息存储通过计算此属性用于两个不同的但相关，目的。</span><span class="sxs-lookup"><span data-stu-id="99f1b-115">This property computed by the message store is used for two different, though related, purposes.</span></span> <span data-ttu-id="99f1b-116">MAPI folder 对象，它包含文件夹中的消息的数。</span><span class="sxs-lookup"><span data-stu-id="99f1b-116">On a MAPI folder object, it contains the number of messages in a folder.</span></span> <span data-ttu-id="99f1b-117">在分类 MAPI 表中的标题行中，它包含该标题行所对应的类别中的未读非关联消息的数目。</span><span class="sxs-lookup"><span data-stu-id="99f1b-117">In a heading row in categorized MAPI tables, it contains the number of unread non-associated messages in the category corresponding to that heading row.</span></span>
  
<span data-ttu-id="99f1b-118">此属性包含**PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 属性中未设置 MSGFLAG_READ 标志是文件夹内容表中的消息数。</span><span class="sxs-lookup"><span data-stu-id="99f1b-118">This property contains the number of messages in the folder contents table for which the MSGFLAG_READ flag is not set in the **PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) property.</span></span> <span data-ttu-id="99f1b-119">**PR_CONTENT_COUNT** ([PidTagContentCount](pidtagcontentcount-canonical-property.md)) 属性包含的文件夹的邮件总数计数。</span><span class="sxs-lookup"><span data-stu-id="99f1b-119">The **PR_CONTENT_COUNT** ([PidTagContentCount](pidtagcontentcount-canonical-property.md)) property contains the total message count for the folder.</span></span> <span data-ttu-id="99f1b-120">**PR_CONTENT_COUNT**和此属性是只读的客户端。</span><span class="sxs-lookup"><span data-stu-id="99f1b-120">The **PR_CONTENT_COUNT** and this property are read-only to clients.</span></span> 
  
<span data-ttu-id="99f1b-121">某些客户端应用程序显示根据该属性的值不同类别的标题行。</span><span class="sxs-lookup"><span data-stu-id="99f1b-121">Some client applications display the heading row of a category differently depending on the value of this property.</span></span> <span data-ttu-id="99f1b-122">例如，客户端可以显示包含未读的邮件以粗体显示的类别。</span><span class="sxs-lookup"><span data-stu-id="99f1b-122">For example, a client can display a category that includes unread messages in bold.</span></span> <span data-ttu-id="99f1b-123">此属性不能用作类别并尝试使用，以便从[IMAPITable::SortTable](imapitable-sorttable.md)方法返回 MAPI_E_INVALID_PARAMETER 值中的结果，正在进行。</span><span class="sxs-lookup"><span data-stu-id="99f1b-123">This property cannot be used as a category and an attempt to do so results in the MAPI_E_INVALID_PARAMETER value being returned from the [IMAPITable::SortTable](imapitable-sorttable.md) method.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="99f1b-124">相关资源</span><span class="sxs-lookup"><span data-stu-id="99f1b-124">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="99f1b-125">协议规范</span><span class="sxs-lookup"><span data-stu-id="99f1b-125">Protocol specifications</span></span>

<span data-ttu-id="99f1b-126">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="99f1b-126">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="99f1b-127">提供了相关的 Microsoft Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="99f1b-127">Provides references to related Microsoft Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="99f1b-128">[[MS OXCFOLD]](http://msdn.microsoft.com/library/c0f31b95-c07f-486c-98d9-535ed9705fbf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="99f1b-128">[[MS-OXCFOLD]](http://msdn.microsoft.com/library/c0f31b95-c07f-486c-98d9-535ed9705fbf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="99f1b-129">处理文件夹的操作。</span><span class="sxs-lookup"><span data-stu-id="99f1b-129">Handles folder operations.</span></span>
    
<span data-ttu-id="99f1b-130">[[MS OXCTABL]](http://msdn.microsoft.com/library/d33612dc-36a8-4623-8a26-c156cf8aae4b%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="99f1b-130">[[MS-OXCTABL]](http://msdn.microsoft.com/library/d33612dc-36a8-4623-8a26-c156cf8aae4b%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="99f1b-131">包含允许的操作的核心 table 对象。</span><span class="sxs-lookup"><span data-stu-id="99f1b-131">Includes permissible operations for the core table objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="99f1b-132">头文件</span><span class="sxs-lookup"><span data-stu-id="99f1b-132">Header files</span></span>

<span data-ttu-id="99f1b-133">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="99f1b-133">Mapidefs.h</span></span>
  
> <span data-ttu-id="99f1b-134">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="99f1b-134">Provides data type definitions.</span></span>
    
<span data-ttu-id="99f1b-135">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="99f1b-135">Mapitags.h</span></span>
  
> <span data-ttu-id="99f1b-136">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="99f1b-136">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="99f1b-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="99f1b-137">See also</span></span>



[<span data-ttu-id="99f1b-138">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="99f1b-138">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="99f1b-139">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="99f1b-139">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="99f1b-140">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="99f1b-140">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="99f1b-141">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="99f1b-141">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

