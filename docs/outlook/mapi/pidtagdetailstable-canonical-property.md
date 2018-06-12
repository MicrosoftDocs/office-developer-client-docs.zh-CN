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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: a267f9a9fb8d97256cf7a448b453d04db2118180
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777547"
---
# <a name="pidtagdetailstable-canonical-property"></a><span data-ttu-id="044c3-103">PidTagDetailsTable 规范属性</span><span class="sxs-lookup"><span data-stu-id="044c3-103">PidTagDetailsTable Canonical Property</span></span>

  
  
<span data-ttu-id="044c3-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="044c3-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="044c3-105">包含嵌入的显示 table 对象。</span><span class="sxs-lookup"><span data-stu-id="044c3-105">Contains an embedded display table object.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="044c3-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="044c3-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="044c3-107">PR_DETAILS_TABLE</span><span class="sxs-lookup"><span data-stu-id="044c3-107">PR_DETAILS_TABLE</span></span>  <br/> |
|<span data-ttu-id="044c3-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="044c3-108">Identifier:</span></span>  <br/> |<span data-ttu-id="044c3-109">0x3605</span><span class="sxs-lookup"><span data-stu-id="044c3-109">0x3605</span></span>  <br/> |
|<span data-ttu-id="044c3-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="044c3-110">Data type:</span></span>  <br/> |<span data-ttu-id="044c3-111">PT_OBJECT</span><span class="sxs-lookup"><span data-stu-id="044c3-111">PT_OBJECT</span></span>  <br/> |
|<span data-ttu-id="044c3-112">区域：</span><span class="sxs-lookup"><span data-stu-id="044c3-112">Area:</span></span>  <br/> |<span data-ttu-id="044c3-113">MAPI 容器</span><span class="sxs-lookup"><span data-stu-id="044c3-113">MAPI container</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="044c3-114">备注</span><span class="sxs-lookup"><span data-stu-id="044c3-114">Remarks</span></span>

<span data-ttu-id="044c3-115">将此属性传递给对象[IMAPIProp::OpenProperty](imapiprop-openproperty.md)方法返回的[IMAPITable](imapitableiunknown.md)接口可用于显示表的创建。</span><span class="sxs-lookup"><span data-stu-id="044c3-115">Passing this property to the [IMAPIProp::OpenProperty](imapiprop-openproperty.md) method for the object returns an [IMAPITable](imapitableiunknown.md) interface that allows creation of the display table.</span></span> <span data-ttu-id="044c3-116">MAPI 使用此表显示通讯簿对象的属性表以响应[IAddrBook::Details](iaddrbook-details.md)呼叫。</span><span class="sxs-lookup"><span data-stu-id="044c3-116">MAPI uses this table to display property sheets for an address book object in response to an [IAddrBook::Details](iaddrbook-details.md) call.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="044c3-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="044c3-117">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="044c3-118">头文件</span><span class="sxs-lookup"><span data-stu-id="044c3-118">Header files</span></span>

<span data-ttu-id="044c3-119">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="044c3-119">Mapidefs.h</span></span>
  
> <span data-ttu-id="044c3-120">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="044c3-120">Provides data type definitions.</span></span>
    
<span data-ttu-id="044c3-121">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="044c3-121">Mapitags.h</span></span>
  
> <span data-ttu-id="044c3-122">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="044c3-122">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="044c3-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="044c3-123">See also</span></span>



[<span data-ttu-id="044c3-124">PidTagCreateTemplates 规范属性</span><span class="sxs-lookup"><span data-stu-id="044c3-124">PidTagCreateTemplates Canonical Property</span></span>](pidtagcreatetemplates-canonical-property.md)
  
[<span data-ttu-id="044c3-125">PidTagSearch 规范属性</span><span class="sxs-lookup"><span data-stu-id="044c3-125">PidTagSearch Canonical Property</span></span>](pidtagsearch-canonical-property.md)


[<span data-ttu-id="044c3-126">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="044c3-126">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="044c3-127">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="044c3-127">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="044c3-128">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="044c3-128">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="044c3-129">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="044c3-129">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

