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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 7d91ed369b3a6e8b4f62534d49b202b46c327baa
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777423"
---
# <a name="pidtagcommonviewsentryid-canonical-property"></a><span data-ttu-id="48c6a-103">PidTagCommonViewsEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="48c6a-103">PidTagCommonViewsEntryId Canonical Property</span></span>

  
  
<span data-ttu-id="48c6a-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="48c6a-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="48c6a-105">包含预定义的公共视图文件夹的项标识符。</span><span class="sxs-lookup"><span data-stu-id="48c6a-105">Contains the entry identifier of the predefined common view folder.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="48c6a-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="48c6a-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="48c6a-107">PR_COMMON_VIEWS_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="48c6a-107">PR_COMMON_VIEWS_ENTRYID</span></span>  <br/> |
|<span data-ttu-id="48c6a-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="48c6a-108">Identifier:</span></span>  <br/> |<span data-ttu-id="48c6a-109">0x35E6</span><span class="sxs-lookup"><span data-stu-id="48c6a-109">0x35E6</span></span>  <br/> |
|<span data-ttu-id="48c6a-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="48c6a-110">Data type:</span></span>  <br/> |<span data-ttu-id="48c6a-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="48c6a-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="48c6a-112">区域：</span><span class="sxs-lookup"><span data-stu-id="48c6a-112">Area:</span></span>  <br/> |<span data-ttu-id="48c6a-113">Outlook 应用程序</span><span class="sxs-lookup"><span data-stu-id="48c6a-113">Outlook application</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="48c6a-114">备注</span><span class="sxs-lookup"><span data-stu-id="48c6a-114">Remarks</span></span>

<span data-ttu-id="48c6a-115">公共视图文件夹包含一组预定义的标准视图说明符，而视图文件夹包含由消息的用户定义的说明符。</span><span class="sxs-lookup"><span data-stu-id="48c6a-115">The common view folder contains a predefined set of standard view specifiers, while the view folder contains specifiers defined by a messaging user.</span></span> <span data-ttu-id="48c6a-116">这些文件夹，不可见人际邮件 (IPM) 层次结构中，可以包含多个视图说明符，每个存储为邮件。</span><span class="sxs-lookup"><span data-stu-id="48c6a-116">These folders, which are not visible in the interpersonal message (IPM) hierarchy, can hold many view specifiers, each one stored as a message.</span></span> <span data-ttu-id="48c6a-117">客户端应用程序可以选择合并两个说明符集并使其同时可用。</span><span class="sxs-lookup"><span data-stu-id="48c6a-117">A client application can choose to merge the two sets of specifiers and make them both available.</span></span> 
  
<span data-ttu-id="48c6a-118">视图的详细信息，请参阅[查看文件夹](mapi-view-folders.md)。</span><span class="sxs-lookup"><span data-stu-id="48c6a-118">For more information on views, see [View Folders](mapi-view-folders.md).</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="48c6a-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="48c6a-119">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="48c6a-120">头文件</span><span class="sxs-lookup"><span data-stu-id="48c6a-120">Header files</span></span>

<span data-ttu-id="48c6a-121">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="48c6a-121">Mapidefs.h</span></span>
  
> <span data-ttu-id="48c6a-122">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="48c6a-122">Provides data type definitions.</span></span>
    
<span data-ttu-id="48c6a-123">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="48c6a-123">Mapitags.h</span></span>
  
> <span data-ttu-id="48c6a-124">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="48c6a-124">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="48c6a-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="48c6a-125">See also</span></span>



[<span data-ttu-id="48c6a-126">PidTagDefaultViewEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="48c6a-126">PidTagDefaultViewEntryId Canonical Property</span></span>](pidtagdefaultviewentryid-canonical-property.md)
  
[<span data-ttu-id="48c6a-127">PidTagViewsEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="48c6a-127">PidTagViewsEntryId Canonical Property</span></span>](pidtagviewsentryid-canonical-property.md)


[<span data-ttu-id="48c6a-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="48c6a-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="48c6a-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="48c6a-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="48c6a-130">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="48c6a-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="48c6a-131">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="48c6a-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

