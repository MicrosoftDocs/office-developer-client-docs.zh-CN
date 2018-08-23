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
ms.openlocfilehash: 1602d1753d9f7f6e6f407a85dab0a33255db7aae
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22585785"
---
# <a name="pidtagdetailstable-canonical-property"></a><span data-ttu-id="fd82e-103">PidTagDetailsTable 规范属性</span><span class="sxs-lookup"><span data-stu-id="fd82e-103">PidTagDetailsTable Canonical Property</span></span>

  
  
<span data-ttu-id="fd82e-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="fd82e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="fd82e-105">包含嵌入的显示 table 对象。</span><span class="sxs-lookup"><span data-stu-id="fd82e-105">Contains an embedded display table object.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="fd82e-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="fd82e-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="fd82e-107">PR_DETAILS_TABLE</span><span class="sxs-lookup"><span data-stu-id="fd82e-107">PR_DETAILS_TABLE</span></span>  <br/> |
|<span data-ttu-id="fd82e-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="fd82e-108">Identifier:</span></span>  <br/> |<span data-ttu-id="fd82e-109">0x3605</span><span class="sxs-lookup"><span data-stu-id="fd82e-109">0x3605</span></span>  <br/> |
|<span data-ttu-id="fd82e-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="fd82e-110">Data type:</span></span>  <br/> |<span data-ttu-id="fd82e-111">PT_OBJECT</span><span class="sxs-lookup"><span data-stu-id="fd82e-111">PT_OBJECT</span></span>  <br/> |
|<span data-ttu-id="fd82e-112">区域：</span><span class="sxs-lookup"><span data-stu-id="fd82e-112">Area:</span></span>  <br/> |<span data-ttu-id="fd82e-113">MAPI 容器</span><span class="sxs-lookup"><span data-stu-id="fd82e-113">MAPI container</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="fd82e-114">注解</span><span class="sxs-lookup"><span data-stu-id="fd82e-114">Remarks</span></span>

<span data-ttu-id="fd82e-115">将此属性传递给对象[IMAPIProp::OpenProperty](imapiprop-openproperty.md)方法返回的[IMAPITable](imapitableiunknown.md)接口可用于显示表的创建。</span><span class="sxs-lookup"><span data-stu-id="fd82e-115">Passing this property to the [IMAPIProp::OpenProperty](imapiprop-openproperty.md) method for the object returns an [IMAPITable](imapitableiunknown.md) interface that allows creation of the display table.</span></span> <span data-ttu-id="fd82e-116">MAPI 使用此表显示通讯簿对象的属性表以响应[IAddrBook::Details](iaddrbook-details.md)呼叫。</span><span class="sxs-lookup"><span data-stu-id="fd82e-116">MAPI uses this table to display property sheets for an address book object in response to an [IAddrBook::Details](iaddrbook-details.md) call.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="fd82e-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="fd82e-117">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="fd82e-118">头文件</span><span class="sxs-lookup"><span data-stu-id="fd82e-118">Header files</span></span>

<span data-ttu-id="fd82e-119">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="fd82e-119">Mapidefs.h</span></span>
  
> <span data-ttu-id="fd82e-120">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="fd82e-120">Provides data type definitions.</span></span>
    
<span data-ttu-id="fd82e-121">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="fd82e-121">Mapitags.h</span></span>
  
> <span data-ttu-id="fd82e-122">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="fd82e-122">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="fd82e-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fd82e-123">See also</span></span>



[<span data-ttu-id="fd82e-124">PidTagCreateTemplates 规范属性</span><span class="sxs-lookup"><span data-stu-id="fd82e-124">PidTagCreateTemplates Canonical Property</span></span>](pidtagcreatetemplates-canonical-property.md)
  
[<span data-ttu-id="fd82e-125">PidTagSearch 规范属性</span><span class="sxs-lookup"><span data-stu-id="fd82e-125">PidTagSearch Canonical Property</span></span>](pidtagsearch-canonical-property.md)


[<span data-ttu-id="fd82e-126">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="fd82e-126">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="fd82e-127">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="fd82e-127">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="fd82e-128">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="fd82e-128">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="fd82e-129">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="fd82e-129">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

