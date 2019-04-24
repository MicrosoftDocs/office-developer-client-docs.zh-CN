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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32269935"
---
# <a name="pidtagcreatetemplates-canonical-property"></a><span data-ttu-id="76327-103">PidTagCreateTemplates 规范属性</span><span class="sxs-lookup"><span data-stu-id="76327-103">PidTagCreateTemplates Canonical Property</span></span>

  
  
<span data-ttu-id="76327-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="76327-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="76327-105">包含嵌入的 table 对象, 其中包含对话框模板条目标识符。</span><span class="sxs-lookup"><span data-stu-id="76327-105">Contains an embedded table object that contains dialog box template entry identifiers.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="76327-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="76327-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="76327-107">PR_CREATE_TEMPLATES</span><span class="sxs-lookup"><span data-stu-id="76327-107">PR_CREATE_TEMPLATES</span></span>  <br/> |
|<span data-ttu-id="76327-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="76327-108">Identifier:</span></span>  <br/> |<span data-ttu-id="76327-109">0x3604</span><span class="sxs-lookup"><span data-stu-id="76327-109">0x3604</span></span>  <br/> |
|<span data-ttu-id="76327-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="76327-110">Data type:</span></span>  <br/> |<span data-ttu-id="76327-111">PT_OBJECT</span><span class="sxs-lookup"><span data-stu-id="76327-111">PT_OBJECT</span></span>  <br/> |
|<span data-ttu-id="76327-112">区域：</span><span class="sxs-lookup"><span data-stu-id="76327-112">Area:</span></span>  <br/> |<span data-ttu-id="76327-113">通讯簿</span><span class="sxs-lookup"><span data-stu-id="76327-113">Address book</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="76327-114">注解</span><span class="sxs-lookup"><span data-stu-id="76327-114">Remarks</span></span>

<span data-ttu-id="76327-115">若要了解可以在容器中创建的模板对象, 请对该属性调用[IMAPIProp:: OpenProperty](imapiprop-openproperty.md)方法。</span><span class="sxs-lookup"><span data-stu-id="76327-115">To learn what template objects can be created inside a container, call the [IMAPIProp::OpenProperty](imapiprop-openproperty.md) method on this property.</span></span> <span data-ttu-id="76327-116">生成的对象是一个一次性表, 该表为您可以在容器中创建的所有模板提供条目标识符。</span><span class="sxs-lookup"><span data-stu-id="76327-116">The resulting object is the one-off table that gives the entry identifiers for all the templates that you can create inside the container.</span></span> 
  
<span data-ttu-id="76327-117">若要创建模板对象, 请从一次性表中的**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 列值调用容器对象的**CreateEntry**方法。</span><span class="sxs-lookup"><span data-stu-id="76327-117">To create the template objects, call the container object's **CreateEntry** method on the **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) column values from the one-off table.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="76327-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="76327-118">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="76327-119">头文件</span><span class="sxs-lookup"><span data-stu-id="76327-119">Header files</span></span>

<span data-ttu-id="76327-120">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="76327-120">Mapidefs.h</span></span>
  
> <span data-ttu-id="76327-121">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="76327-121">Provides data type definitions.</span></span>
    
<span data-ttu-id="76327-122">Mapitags</span><span class="sxs-lookup"><span data-stu-id="76327-122">Mapitags.h</span></span>
  
> <span data-ttu-id="76327-123">包含列为关联属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="76327-123">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="76327-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="76327-124">See also</span></span>



[<span data-ttu-id="76327-125">IABContainer::CreateEntry</span><span class="sxs-lookup"><span data-stu-id="76327-125">IABContainer::CreateEntry</span></span>](iabcontainer-createentry.md)


[<span data-ttu-id="76327-126">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="76327-126">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="76327-127">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="76327-127">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="76327-128">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="76327-128">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="76327-129">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="76327-129">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

