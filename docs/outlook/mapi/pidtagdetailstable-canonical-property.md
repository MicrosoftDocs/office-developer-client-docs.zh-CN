---
title: PidTagDetailsTable 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagDetailsTable
api_type:
- HeaderDef
ms.assetid: 7a0ccad3-f497-4871-b733-771e6cb8ef6a
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 74eae4a4ed742c3bb90496f5975ad7dac6ff798f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32360835"
---
# <a name="pidtagdetailstable-canonical-property"></a><span data-ttu-id="acb65-103">PidTagDetailsTable 规范属性</span><span class="sxs-lookup"><span data-stu-id="acb65-103">PidTagDetailsTable Canonical Property</span></span>

  
  
<span data-ttu-id="acb65-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="acb65-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="acb65-105">包含嵌入的显示表对象。</span><span class="sxs-lookup"><span data-stu-id="acb65-105">Contains an embedded display table object.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="acb65-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="acb65-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="acb65-107">PR_DETAILS_TABLE</span><span class="sxs-lookup"><span data-stu-id="acb65-107">PR_DETAILS_TABLE</span></span>  <br/> |
|<span data-ttu-id="acb65-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="acb65-108">Identifier:</span></span>  <br/> |<span data-ttu-id="acb65-109">0x3605</span><span class="sxs-lookup"><span data-stu-id="acb65-109">0x3605</span></span>  <br/> |
|<span data-ttu-id="acb65-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="acb65-110">Data type:</span></span>  <br/> |<span data-ttu-id="acb65-111">PT_OBJECT</span><span class="sxs-lookup"><span data-stu-id="acb65-111">PT_OBJECT</span></span>  <br/> |
|<span data-ttu-id="acb65-112">区域：</span><span class="sxs-lookup"><span data-stu-id="acb65-112">Area:</span></span>  <br/> |<span data-ttu-id="acb65-113">MAPI 容器</span><span class="sxs-lookup"><span data-stu-id="acb65-113">MAPI container</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="acb65-114">注解</span><span class="sxs-lookup"><span data-stu-id="acb65-114">Remarks</span></span>

<span data-ttu-id="acb65-115">将此属性传递给对象的[IMAPIProp:: OpenProperty](imapiprop-openproperty.md)方法将返回允许创建显示表的[IMAPITable](imapitableiunknown.md)接口。</span><span class="sxs-lookup"><span data-stu-id="acb65-115">Passing this property to the [IMAPIProp::OpenProperty](imapiprop-openproperty.md) method for the object returns an [IMAPITable](imapitableiunknown.md) interface that allows creation of the display table.</span></span> <span data-ttu-id="acb65-116">MAPI 使用此表显示通讯簿对象的属性表以响应[IAddrBook::D etails](iaddrbook-details.md)调用。</span><span class="sxs-lookup"><span data-stu-id="acb65-116">MAPI uses this table to display property sheets for an address book object in response to an [IAddrBook::Details](iaddrbook-details.md) call.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="acb65-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="acb65-117">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="acb65-118">头文件</span><span class="sxs-lookup"><span data-stu-id="acb65-118">Header files</span></span>

<span data-ttu-id="acb65-119">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="acb65-119">Mapidefs.h</span></span>
  
> <span data-ttu-id="acb65-120">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="acb65-120">Provides data type definitions.</span></span>
    
<span data-ttu-id="acb65-121">Mapitags</span><span class="sxs-lookup"><span data-stu-id="acb65-121">Mapitags.h</span></span>
  
> <span data-ttu-id="acb65-122">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="acb65-122">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="acb65-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="acb65-123">See also</span></span>



[<span data-ttu-id="acb65-124">PidTagCreateTemplates 规范属性</span><span class="sxs-lookup"><span data-stu-id="acb65-124">PidTagCreateTemplates Canonical Property</span></span>](pidtagcreatetemplates-canonical-property.md)
  
[<span data-ttu-id="acb65-125">PidTagSearch 规范属性</span><span class="sxs-lookup"><span data-stu-id="acb65-125">PidTagSearch Canonical Property</span></span>](pidtagsearch-canonical-property.md)


[<span data-ttu-id="acb65-126">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="acb65-126">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="acb65-127">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="acb65-127">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="acb65-128">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="acb65-128">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="acb65-129">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="acb65-129">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

