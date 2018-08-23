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
ms.openlocfilehash: e8bed42ee44e48540df52e806c7113e02b60cd07
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22593632"
---
# <a name="pidtagitemtemporaryflags-canonical-property"></a><span data-ttu-id="3f8b2-103">PidTagItemTemporaryflags 规范属性</span><span class="sxs-lookup"><span data-stu-id="3f8b2-103">PidTagItemTemporaryflags Canonical Property</span></span>

  
  
<span data-ttu-id="3f8b2-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="3f8b2-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="3f8b2-105">包含一个标志，指示已读取，但未标记为已读消息。</span><span class="sxs-lookup"><span data-stu-id="3f8b2-105">Contains a flag that indicates that a message has been read, but not marked as read.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="3f8b2-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="3f8b2-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="3f8b2-107">PR_ITEM_TMPFLAGS</span><span class="sxs-lookup"><span data-stu-id="3f8b2-107">PR_ITEM_TMPFLAGS</span></span>  <br/> |
|<span data-ttu-id="3f8b2-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="3f8b2-108">Identifier:</span></span>  <br/> |<span data-ttu-id="3f8b2-109">0x1097</span><span class="sxs-lookup"><span data-stu-id="3f8b2-109">0x1097</span></span>  <br/> |
|<span data-ttu-id="3f8b2-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="3f8b2-110">Data type:</span></span>  <br/> |<span data-ttu-id="3f8b2-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="3f8b2-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="3f8b2-112">区域：</span><span class="sxs-lookup"><span data-stu-id="3f8b2-112">Area:</span></span>  <br/> |<span data-ttu-id="3f8b2-113">常规消息</span><span class="sxs-lookup"><span data-stu-id="3f8b2-113">General messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="3f8b2-114">注解</span><span class="sxs-lookup"><span data-stu-id="3f8b2-114">Remarks</span></span>

<span data-ttu-id="3f8b2-115">此属性用于在 Outlook 的未读邮件搜索文件夹保持联系的而不实际将其标记为已读，将它们从文件夹中删除已读取的消息。</span><span class="sxs-lookup"><span data-stu-id="3f8b2-115">This property is used in Outlook's Unread Messages search folder to keep track of which messages have been read without actually marking them as read, which would remove them from the folder.</span></span> <span data-ttu-id="3f8b2-116">当视图更改此属性删除和项目被标记为阅读。</span><span class="sxs-lookup"><span data-stu-id="3f8b2-116">When the view changes this property is removed and the item is marked as read.</span></span> <span data-ttu-id="3f8b2-117">此属性将不会同步到 Exchange 服务器。</span><span class="sxs-lookup"><span data-stu-id="3f8b2-117">This property will not synchronize to the Exchange Server.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="3f8b2-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="3f8b2-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="3f8b2-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="3f8b2-119">Protocol specifications</span></span>

<span data-ttu-id="3f8b2-120">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="3f8b2-120">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="3f8b2-121">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="3f8b2-121">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="3f8b2-122">[[MS OXCFOLD]](http://msdn.microsoft.com/library/c0f31b95-c07f-486c-98d9-535ed9705fbf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="3f8b2-122">[[MS-OXCFOLD]](http://msdn.microsoft.com/library/c0f31b95-c07f-486c-98d9-535ed9705fbf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="3f8b2-123">处理文件夹的操作。</span><span class="sxs-lookup"><span data-stu-id="3f8b2-123">Handles folder operations.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="3f8b2-124">头文件</span><span class="sxs-lookup"><span data-stu-id="3f8b2-124">Header files</span></span>

<span data-ttu-id="3f8b2-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="3f8b2-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="3f8b2-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="3f8b2-126">Provides data type definitions.</span></span>
    
<span data-ttu-id="3f8b2-127">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="3f8b2-127">Mapitags.h</span></span>
  
> <span data-ttu-id="3f8b2-128">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="3f8b2-128">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="3f8b2-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3f8b2-129">See also</span></span>



[<span data-ttu-id="3f8b2-130">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="3f8b2-130">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="3f8b2-131">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="3f8b2-131">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="3f8b2-132">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="3f8b2-132">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="3f8b2-133">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="3f8b2-133">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

