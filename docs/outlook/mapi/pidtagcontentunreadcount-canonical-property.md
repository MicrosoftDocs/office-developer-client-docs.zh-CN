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
ms.openlocfilehash: 9572a053182aaa59020a6816736b8a4b92e778b7
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32331869"
---
# <a name="pidtagcontentunreadcount-canonical-property"></a><span data-ttu-id="d94fd-103">PidTagContentUnreadCount 规范属性</span><span class="sxs-lookup"><span data-stu-id="d94fd-103">PidTagContentUnreadCount Canonical Property</span></span>

  
  
<span data-ttu-id="d94fd-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d94fd-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d94fd-105">包含文件夹中的未读邮件数, 由邮件存储区计算得出。</span><span class="sxs-lookup"><span data-stu-id="d94fd-105">Contains the number of unread messages in a folder, as computed by the message store.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="d94fd-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="d94fd-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="d94fd-107">PR_CONTENT_UNREAD</span><span class="sxs-lookup"><span data-stu-id="d94fd-107">PR_CONTENT_UNREAD</span></span>  <br/> |
|<span data-ttu-id="d94fd-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="d94fd-108">Identifier:</span></span>  <br/> |<span data-ttu-id="d94fd-109">0x3603</span><span class="sxs-lookup"><span data-stu-id="d94fd-109">0x3603</span></span>  <br/> |
|<span data-ttu-id="d94fd-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="d94fd-110">Data type:</span></span>  <br/> |<span data-ttu-id="d94fd-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="d94fd-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="d94fd-112">区域：</span><span class="sxs-lookup"><span data-stu-id="d94fd-112">Area:</span></span>  <br/> |<span data-ttu-id="d94fd-113">Folder</span><span class="sxs-lookup"><span data-stu-id="d94fd-113">Folder</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="d94fd-114">注解</span><span class="sxs-lookup"><span data-stu-id="d94fd-114">Remarks</span></span>

<span data-ttu-id="d94fd-115">此属性由邮件存储区计算, 但有两种不同的用途。</span><span class="sxs-lookup"><span data-stu-id="d94fd-115">This property computed by the message store is used for two different, though related, purposes.</span></span> <span data-ttu-id="d94fd-116">在 MAPI 文件夹对象中, 它包含文件夹中的邮件数。</span><span class="sxs-lookup"><span data-stu-id="d94fd-116">On a MAPI folder object, it contains the number of messages in a folder.</span></span> <span data-ttu-id="d94fd-117">在分类 MAPI 表的标题行中, 它包含与标题行对应的类别中未读的非关联邮件数。</span><span class="sxs-lookup"><span data-stu-id="d94fd-117">In a heading row in categorized MAPI tables, it contains the number of unread non-associated messages in the category corresponding to that heading row.</span></span>
  
<span data-ttu-id="d94fd-118">此属性包含未在**PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 属性中为其 MSGFLAG_READ 标记设置的文件夹内容表中的邮件数。</span><span class="sxs-lookup"><span data-stu-id="d94fd-118">This property contains the number of messages in the folder contents table for which the MSGFLAG_READ flag is not set in the **PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) property.</span></span> <span data-ttu-id="d94fd-119">**PR_CONTENT_COUNT** ([PidTagContentCount](pidtagcontentcount-canonical-property.md)) 属性包含文件夹的总邮件数。</span><span class="sxs-lookup"><span data-stu-id="d94fd-119">The **PR_CONTENT_COUNT** ([PidTagContentCount](pidtagcontentcount-canonical-property.md)) property contains the total message count for the folder.</span></span> <span data-ttu-id="d94fd-120">**PR_CONTENT_COUNT**和此属性对客户端是只读的。</span><span class="sxs-lookup"><span data-stu-id="d94fd-120">The **PR_CONTENT_COUNT** and this property are read-only to clients.</span></span> 
  
<span data-ttu-id="d94fd-121">某些客户端应用程序以不同的方式显示类别的标题行, 具体取决于此属性的值。</span><span class="sxs-lookup"><span data-stu-id="d94fd-121">Some client applications display the heading row of a category differently depending on the value of this property.</span></span> <span data-ttu-id="d94fd-122">例如, 客户端可以显示包含以粗体显示的未读邮件的类别。</span><span class="sxs-lookup"><span data-stu-id="d94fd-122">For example, a client can display a category that includes unread messages in bold.</span></span> <span data-ttu-id="d94fd-123">此属性不能用作类别, 尝试执行此操作会导致从[IMAPITable:: SortTable](imapitable-sorttable.md)方法返回的 MAPI_E_INVALID_PARAMETER 值。</span><span class="sxs-lookup"><span data-stu-id="d94fd-123">This property cannot be used as a category and an attempt to do so results in the MAPI_E_INVALID_PARAMETER value being returned from the [IMAPITable::SortTable](imapitable-sorttable.md) method.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="d94fd-124">相关资源</span><span class="sxs-lookup"><span data-stu-id="d94fd-124">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="d94fd-125">协议规范</span><span class="sxs-lookup"><span data-stu-id="d94fd-125">Protocol specifications</span></span>

<span data-ttu-id="d94fd-126">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="d94fd-126">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="d94fd-127">提供对相关 Microsoft Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="d94fd-127">Provides references to related Microsoft Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="d94fd-128">[[毫秒-OXCFOLD]](https://msdn.microsoft.com/library/c0f31b95-c07f-486c-98d9-535ed9705fbf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="d94fd-128">[[MS-OXCFOLD]](https://msdn.microsoft.com/library/c0f31b95-c07f-486c-98d9-535ed9705fbf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="d94fd-129">处理文件夹操作。</span><span class="sxs-lookup"><span data-stu-id="d94fd-129">Handles folder operations.</span></span>
    
<span data-ttu-id="d94fd-130">[[毫秒-OXCTABL]](https://msdn.microsoft.com/library/d33612dc-36a8-4623-8a26-c156cf8aae4b%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="d94fd-130">[[MS-OXCTABL]](https://msdn.microsoft.com/library/d33612dc-36a8-4623-8a26-c156cf8aae4b%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="d94fd-131">包括核心表对象的允许操作。</span><span class="sxs-lookup"><span data-stu-id="d94fd-131">Includes permissible operations for the core table objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="d94fd-132">头文件</span><span class="sxs-lookup"><span data-stu-id="d94fd-132">Header files</span></span>

<span data-ttu-id="d94fd-133">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="d94fd-133">Mapidefs.h</span></span>
  
> <span data-ttu-id="d94fd-134">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="d94fd-134">Provides data type definitions.</span></span>
    
<span data-ttu-id="d94fd-135">Mapitags</span><span class="sxs-lookup"><span data-stu-id="d94fd-135">Mapitags.h</span></span>
  
> <span data-ttu-id="d94fd-136">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="d94fd-136">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="d94fd-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d94fd-137">See also</span></span>



[<span data-ttu-id="d94fd-138">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="d94fd-138">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="d94fd-139">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="d94fd-139">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="d94fd-140">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="d94fd-140">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="d94fd-141">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="d94fd-141">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

