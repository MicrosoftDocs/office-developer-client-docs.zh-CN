---
title: PidTagCreateTemplates 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagCreateTemplates
api_type:
- HeaderDef
ms.assetid: d2530009-5de3-4872-a0a5-be1389c4206e
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 08cf1faa0c3cc4cf61e2253b0026361704fdd0e2
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33438181"
---
# <a name="pidtagcreatetemplates-canonical-property"></a><span data-ttu-id="d3eed-103">PidTagCreateTemplates 规范属性</span><span class="sxs-lookup"><span data-stu-id="d3eed-103">PidTagCreateTemplates Canonical Property</span></span>

  
  
<span data-ttu-id="d3eed-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d3eed-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d3eed-105">包含包含对话框模板条目标识符的嵌入表对象。</span><span class="sxs-lookup"><span data-stu-id="d3eed-105">Contains an embedded table object that contains dialog box template entry identifiers.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="d3eed-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="d3eed-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="d3eed-107">PR_CREATE_TEMPLATES</span><span class="sxs-lookup"><span data-stu-id="d3eed-107">PR_CREATE_TEMPLATES</span></span>  <br/> |
|<span data-ttu-id="d3eed-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="d3eed-108">Identifier:</span></span>  <br/> |<span data-ttu-id="d3eed-109">0x3604</span><span class="sxs-lookup"><span data-stu-id="d3eed-109">0x3604</span></span>  <br/> |
|<span data-ttu-id="d3eed-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="d3eed-110">Data type:</span></span>  <br/> |<span data-ttu-id="d3eed-111">PT_OBJECT</span><span class="sxs-lookup"><span data-stu-id="d3eed-111">PT_OBJECT</span></span>  <br/> |
|<span data-ttu-id="d3eed-112">区域：</span><span class="sxs-lookup"><span data-stu-id="d3eed-112">Area:</span></span>  <br/> |<span data-ttu-id="d3eed-113">通讯簿</span><span class="sxs-lookup"><span data-stu-id="d3eed-113">Address book</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="d3eed-114">备注</span><span class="sxs-lookup"><span data-stu-id="d3eed-114">Remarks</span></span>

<span data-ttu-id="d3eed-115">若要了解可以在容器内创建哪些模板对象，请对此属性调用 [IMAPIProp：：OpenProperty](imapiprop-openproperty.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="d3eed-115">To learn what template objects can be created inside a container, call the [IMAPIProp::OpenProperty](imapiprop-openproperty.md) method on this property.</span></span> <span data-ttu-id="d3eed-116">生成的对象是一对一表，它提供可在容器内创建的所有模板的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="d3eed-116">The resulting object is the one-off table that gives the entry identifiers for all the templates that you can create inside the container.</span></span> 
  
<span data-ttu-id="d3eed-117">若要创建模板对象，请对 PR_ENTRYID ([PidTagEntryId](pidtagentryid-canonical-property.md)) 一次表中的列值调用容器对象的 **CreateEntry** 方法。 </span><span class="sxs-lookup"><span data-stu-id="d3eed-117">To create the template objects, call the container object's **CreateEntry** method on the **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) column values from the one-off table.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="d3eed-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="d3eed-118">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="d3eed-119">头文件</span><span class="sxs-lookup"><span data-stu-id="d3eed-119">Header files</span></span>

<span data-ttu-id="d3eed-120">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="d3eed-120">Mapidefs.h</span></span>
  
> <span data-ttu-id="d3eed-121">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="d3eed-121">Provides data type definitions.</span></span>
    
<span data-ttu-id="d3eed-122">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="d3eed-122">Mapitags.h</span></span>
  
> <span data-ttu-id="d3eed-123">包含作为关联属性列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="d3eed-123">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="d3eed-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d3eed-124">See also</span></span>



[<span data-ttu-id="d3eed-125">IABContainer::CreateEntry</span><span class="sxs-lookup"><span data-stu-id="d3eed-125">IABContainer::CreateEntry</span></span>](iabcontainer-createentry.md)


[<span data-ttu-id="d3eed-126">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="d3eed-126">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="d3eed-127">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="d3eed-127">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="d3eed-128">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="d3eed-128">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="d3eed-129">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="d3eed-129">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

