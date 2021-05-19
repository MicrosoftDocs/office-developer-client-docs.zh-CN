---
title: PidTagItemTemporaryflags 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagItemTemporaryflags
api_type:
- HeaderDef
ms.assetid: 8066de8e-2b77-4bac-8df3-e64b03ee42b9
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: ec092e6cc6174e156dbfe7784143c9d74715eef7
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32357699"
---
# <a name="pidtagitemtemporaryflags-canonical-property"></a><span data-ttu-id="4efe5-103">PidTagItemTemporaryflags 规范属性</span><span class="sxs-lookup"><span data-stu-id="4efe5-103">PidTagItemTemporaryflags Canonical Property</span></span>

  
  
<span data-ttu-id="4efe5-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="4efe5-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="4efe5-105">包含一个标志，指示邮件已被读取，但没有标记为已读。</span><span class="sxs-lookup"><span data-stu-id="4efe5-105">Contains a flag that indicates that a message has been read, but not marked as read.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="4efe5-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="4efe5-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="4efe5-107">PR_ITEM_TMPFLAGS</span><span class="sxs-lookup"><span data-stu-id="4efe5-107">PR_ITEM_TMPFLAGS</span></span>  <br/> |
|<span data-ttu-id="4efe5-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="4efe5-108">Identifier:</span></span>  <br/> |<span data-ttu-id="4efe5-109">0x1097</span><span class="sxs-lookup"><span data-stu-id="4efe5-109">0x1097</span></span>  <br/> |
|<span data-ttu-id="4efe5-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="4efe5-110">Data type:</span></span>  <br/> |<span data-ttu-id="4efe5-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="4efe5-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="4efe5-112">区域：</span><span class="sxs-lookup"><span data-stu-id="4efe5-112">Area:</span></span>  <br/> |<span data-ttu-id="4efe5-113">常规消息</span><span class="sxs-lookup"><span data-stu-id="4efe5-113">General messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="4efe5-114">备注</span><span class="sxs-lookup"><span data-stu-id="4efe5-114">Remarks</span></span>

<span data-ttu-id="4efe5-115">此属性用于 Outlook 的"未读邮件"搜索文件夹中，以跟踪已阅读的邮件，而不实际将其标记为已读，这会从文件夹中删除邮件。</span><span class="sxs-lookup"><span data-stu-id="4efe5-115">This property is used in Outlook's Unread Messages search folder to keep track of which messages have been read without actually marking them as read, which would remove them from the folder.</span></span> <span data-ttu-id="4efe5-116">当视图更改时，将删除此属性，将项目标记为已读。</span><span class="sxs-lookup"><span data-stu-id="4efe5-116">When the view changes this property is removed and the item is marked as read.</span></span> <span data-ttu-id="4efe5-117">此属性不会同步到Exchange Server。</span><span class="sxs-lookup"><span data-stu-id="4efe5-117">This property will not synchronize to the Exchange Server.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="4efe5-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="4efe5-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="4efe5-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="4efe5-119">Protocol specifications</span></span>

<span data-ttu-id="4efe5-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="4efe5-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="4efe5-121">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="4efe5-121">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="4efe5-122">[[MS-OXCFOLD]](https://msdn.microsoft.com/library/c0f31b95-c07f-486c-98d9-535ed9705fbf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="4efe5-122">[[MS-OXCFOLD]](https://msdn.microsoft.com/library/c0f31b95-c07f-486c-98d9-535ed9705fbf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="4efe5-123">处理文件夹操作。</span><span class="sxs-lookup"><span data-stu-id="4efe5-123">Handles folder operations.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="4efe5-124">头文件</span><span class="sxs-lookup"><span data-stu-id="4efe5-124">Header files</span></span>

<span data-ttu-id="4efe5-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="4efe5-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="4efe5-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="4efe5-126">Provides data type definitions.</span></span>
    
<span data-ttu-id="4efe5-127">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="4efe5-127">Mapitags.h</span></span>
  
> <span data-ttu-id="4efe5-128">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="4efe5-128">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="4efe5-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4efe5-129">See also</span></span>



[<span data-ttu-id="4efe5-130">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="4efe5-130">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="4efe5-131">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="4efe5-131">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="4efe5-132">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="4efe5-132">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="4efe5-133">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="4efe5-133">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

