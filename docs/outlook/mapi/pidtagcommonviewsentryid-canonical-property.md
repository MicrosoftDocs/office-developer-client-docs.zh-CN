---
title: PidTagCommonViewsEntryId 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagCommonViewsEntryId
api_type:
- HeaderDef
ms.assetid: cd9e6a46-2112-4663-891e-5e57b22c0950
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7449e59227b147d34c2329175d0251dbb9c427b6
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22581340"
---
# <a name="pidtagcommonviewsentryid-canonical-property"></a><span data-ttu-id="c6a21-103">PidTagCommonViewsEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="c6a21-103">PidTagCommonViewsEntryId Canonical Property</span></span>

  
  
<span data-ttu-id="c6a21-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c6a21-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c6a21-105">包含预定义的公共视图文件夹的项标识符。</span><span class="sxs-lookup"><span data-stu-id="c6a21-105">Contains the entry identifier of the predefined common view folder.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="c6a21-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="c6a21-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="c6a21-107">PR_COMMON_VIEWS_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="c6a21-107">PR_COMMON_VIEWS_ENTRYID</span></span>  <br/> |
|<span data-ttu-id="c6a21-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="c6a21-108">Identifier:</span></span>  <br/> |<span data-ttu-id="c6a21-109">0x35E6</span><span class="sxs-lookup"><span data-stu-id="c6a21-109">0x35E6</span></span>  <br/> |
|<span data-ttu-id="c6a21-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="c6a21-110">Data type:</span></span>  <br/> |<span data-ttu-id="c6a21-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="c6a21-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="c6a21-112">区域：</span><span class="sxs-lookup"><span data-stu-id="c6a21-112">Area:</span></span>  <br/> |<span data-ttu-id="c6a21-113">Outlook 应用程序</span><span class="sxs-lookup"><span data-stu-id="c6a21-113">Outlook application</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="c6a21-114">注解</span><span class="sxs-lookup"><span data-stu-id="c6a21-114">Remarks</span></span>

<span data-ttu-id="c6a21-115">公共视图文件夹包含一组预定义的标准视图说明符，而视图文件夹包含由消息的用户定义的说明符。</span><span class="sxs-lookup"><span data-stu-id="c6a21-115">The common view folder contains a predefined set of standard view specifiers, while the view folder contains specifiers defined by a messaging user.</span></span> <span data-ttu-id="c6a21-116">这些文件夹，不可见人际邮件 (IPM) 层次结构中，可以包含多个视图说明符，每个存储为邮件。</span><span class="sxs-lookup"><span data-stu-id="c6a21-116">These folders, which are not visible in the interpersonal message (IPM) hierarchy, can hold many view specifiers, each one stored as a message.</span></span> <span data-ttu-id="c6a21-117">客户端应用程序可以选择合并两个说明符集并使其同时可用。</span><span class="sxs-lookup"><span data-stu-id="c6a21-117">A client application can choose to merge the two sets of specifiers and make them both available.</span></span> 
  
<span data-ttu-id="c6a21-118">视图的详细信息，请参阅[查看文件夹](mapi-view-folders.md)。</span><span class="sxs-lookup"><span data-stu-id="c6a21-118">For more information on views, see [View Folders](mapi-view-folders.md).</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="c6a21-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="c6a21-119">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="c6a21-120">头文件</span><span class="sxs-lookup"><span data-stu-id="c6a21-120">Header files</span></span>

<span data-ttu-id="c6a21-121">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="c6a21-121">Mapidefs.h</span></span>
  
> <span data-ttu-id="c6a21-122">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="c6a21-122">Provides data type definitions.</span></span>
    
<span data-ttu-id="c6a21-123">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="c6a21-123">Mapitags.h</span></span>
  
> <span data-ttu-id="c6a21-124">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="c6a21-124">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="c6a21-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c6a21-125">See also</span></span>



[<span data-ttu-id="c6a21-126">PidTagDefaultViewEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="c6a21-126">PidTagDefaultViewEntryId Canonical Property</span></span>](pidtagdefaultviewentryid-canonical-property.md)
  
[<span data-ttu-id="c6a21-127">PidTagViewsEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="c6a21-127">PidTagViewsEntryId Canonical Property</span></span>](pidtagviewsentryid-canonical-property.md)


[<span data-ttu-id="c6a21-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="c6a21-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="c6a21-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="c6a21-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="c6a21-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="c6a21-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="c6a21-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="c6a21-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

