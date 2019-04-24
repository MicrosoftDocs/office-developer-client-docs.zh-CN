---
title: PidTagMappingSignature 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagMappingSignature
api_type:
- HeaderDef
ms.assetid: a5e9f807-12a9-4bc9-a6a5-17579e747ffa
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: d12e8510686f51698981c47327f79ef40d3ec342
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32342537"
---
# <a name="pidtagmappingsignature-canonical-property"></a><span data-ttu-id="e1b3b-103">PidTagMappingSignature 规范属性</span><span class="sxs-lookup"><span data-stu-id="e1b3b-103">PidTagMappingSignature Canonical Property</span></span>

  
  
<span data-ttu-id="e1b3b-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e1b3b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e1b3b-105">包含特定 MAPI 对象的命名属性的映射签名。</span><span class="sxs-lookup"><span data-stu-id="e1b3b-105">Contains the mapping signature for named properties of a particular MAPI object.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="e1b3b-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="e1b3b-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="e1b3b-107">PR_MAPPING_SIGNATURE</span><span class="sxs-lookup"><span data-stu-id="e1b3b-107">PR_MAPPING_SIGNATURE</span></span>  <br/> |
|<span data-ttu-id="e1b3b-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="e1b3b-108">Identifier:</span></span>  <br/> |<span data-ttu-id="e1b3b-109">0x0FF8</span><span class="sxs-lookup"><span data-stu-id="e1b3b-109">0x0FF8</span></span>  <br/> |
|<span data-ttu-id="e1b3b-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="e1b3b-110">Data type:</span></span>  <br/> |<span data-ttu-id="e1b3b-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="e1b3b-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="e1b3b-112">区域：</span><span class="sxs-lookup"><span data-stu-id="e1b3b-112">Area:</span></span>  <br/> |<span data-ttu-id="e1b3b-113">其他</span><span class="sxs-lookup"><span data-stu-id="e1b3b-113">Miscellaneous</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="e1b3b-114">注解</span><span class="sxs-lookup"><span data-stu-id="e1b3b-114">Remarks</span></span>

<span data-ttu-id="e1b3b-115">建议具有命名属性的对象将公开此属性。</span><span class="sxs-lookup"><span data-stu-id="e1b3b-115">It is recommended that objects having named properties expose this property.</span></span> <span data-ttu-id="e1b3b-116">将命名属性从一个对象复制到另一个对象时, 客户端应用程序应检查这两个对象的**PR_MAPPING_SIGNATURE**属性。</span><span class="sxs-lookup"><span data-stu-id="e1b3b-116">A client application should check the **PR_MAPPING_SIGNATURE** property of both objects when copying named properties from one object to another.</span></span> <span data-ttu-id="e1b3b-117">使用此属性可以最大限度地减少已复制属性的名称和标识符之间的转换。</span><span class="sxs-lookup"><span data-stu-id="e1b3b-117">Use of this property can minimize translating between copied properties' names and identifiers.</span></span> 
  
<span data-ttu-id="e1b3b-118">如果给定 MAPI 对象的此属性不存在, 则该对象具有自己的唯一名称和标识符映射。</span><span class="sxs-lookup"><span data-stu-id="e1b3b-118">If this property does not exist for a given MAPI object, then the object has its own unique mapping of names and identifiers.</span></span> <span data-ttu-id="e1b3b-119">在这种情况下, 客户端必须在源对象上调用[IMAPIProp:: GetNamesFromIDs](imapiprop-getnamesfromids.md)方法, 然后对 destination 对象调用[IMAPIProp:: GetIDsFromNames](imapiprop-getidsfromnames.md)方法。</span><span class="sxs-lookup"><span data-stu-id="e1b3b-119">In this case the client must call the [IMAPIProp::GetNamesFromIDs](imapiprop-getnamesfromids.md) method on the source object and then the [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md) method on the destination object.</span></span> 
  
<span data-ttu-id="e1b3b-120">当两个对象具有相同的**PR_MAPPING_SIGNATURE**值时, 客户端无需将名称转换为标识符, 也不需要将标识符转换为 name。</span><span class="sxs-lookup"><span data-stu-id="e1b3b-120">When two objects have the same **PR_MAPPING_SIGNATURE** value, the client does not need to translate name to identifier and identifier to name.</span></span> <span data-ttu-id="e1b3b-121">客户端可以直接在源上调用[IMAPIProp:: GetProps](imapiprop-getprops.md)方法, 然后调用目标上的[IMAPIProp:: SetProps](imapiprop-setprops.md)方法。</span><span class="sxs-lookup"><span data-stu-id="e1b3b-121">The client can simply call the [IMAPIProp::GetProps](imapiprop-getprops.md) method on the source and then the [IMAPIProp::SetProps](imapiprop-setprops.md) method on the destination.</span></span> <span data-ttu-id="e1b3b-122">对于执行命名属性的自定义复制的客户端, 以及实现[IMAPIProp:: CopyTo](imapiprop-copyto.md)和[IMAPIProp:: CopyProps](imapiprop-copyprops.md)方法的提供程序, 这是很方便的。</span><span class="sxs-lookup"><span data-stu-id="e1b3b-122">This is convenient for clients that perform custom copying of named properties, and for providers implementing the [IMAPIProp::CopyTo](imapiprop-copyto.md) and [IMAPIProp::CopyProps](imapiprop-copyprops.md) methods.</span></span> 
  
<span data-ttu-id="e1b3b-123">有关命名属性和名称和标识符映射的详细信息, 请参阅[MAPI 命名属性](mapi-named-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="e1b3b-123">For more information on named properties and mapping of names and identifiers, see [MAPI Named Properties](mapi-named-properties.md).</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="e1b3b-124">相关资源</span><span class="sxs-lookup"><span data-stu-id="e1b3b-124">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="e1b3b-125">协议规范</span><span class="sxs-lookup"><span data-stu-id="e1b3b-125">Protocol specifications</span></span>

<span data-ttu-id="e1b3b-126">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="e1b3b-126">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="e1b3b-127">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="e1b3b-127">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="e1b3b-128">[[毫秒-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="e1b3b-128">[[MS-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="e1b3b-129">指定用户、联系人、组和资源列表的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="e1b3b-129">Specifies the properties and operations for lists of users, contacts, groups, and resources.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="e1b3b-130">头文件</span><span class="sxs-lookup"><span data-stu-id="e1b3b-130">Header files</span></span>

<span data-ttu-id="e1b3b-131">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="e1b3b-131">Mapidefs.h</span></span>
  
> <span data-ttu-id="e1b3b-132">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="e1b3b-132">Provides data type definitions.</span></span>
    
<span data-ttu-id="e1b3b-133">Mapitags</span><span class="sxs-lookup"><span data-stu-id="e1b3b-133">Mapitags.h</span></span>
  
> <span data-ttu-id="e1b3b-134">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="e1b3b-134">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="e1b3b-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e1b3b-135">See also</span></span>



[<span data-ttu-id="e1b3b-136">MAPINAMEID</span><span class="sxs-lookup"><span data-stu-id="e1b3b-136">MAPINAMEID</span></span>](mapinameid.md)


[<span data-ttu-id="e1b3b-137">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="e1b3b-137">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="e1b3b-138">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="e1b3b-138">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="e1b3b-139">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="e1b3b-139">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="e1b3b-140">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="e1b3b-140">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

