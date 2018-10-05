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
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25396223"
---
# <a name="pidtagmappingsignature-canonical-property"></a><span data-ttu-id="59cae-103">PidTagMappingSignature 规范属性</span><span class="sxs-lookup"><span data-stu-id="59cae-103">PidTagMappingSignature Canonical Property</span></span>

  
  
<span data-ttu-id="59cae-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="59cae-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="59cae-105">包含特定 MAPI 对象的命名属性的映射签名。</span><span class="sxs-lookup"><span data-stu-id="59cae-105">Contains the mapping signature for named properties of a particular MAPI object.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="59cae-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="59cae-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="59cae-107">PR_MAPPING_SIGNATURE</span><span class="sxs-lookup"><span data-stu-id="59cae-107">PR_MAPPING_SIGNATURE</span></span>  <br/> |
|<span data-ttu-id="59cae-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="59cae-108">Identifier:</span></span>  <br/> |<span data-ttu-id="59cae-109">0x0FF8</span><span class="sxs-lookup"><span data-stu-id="59cae-109">0x0FF8</span></span>  <br/> |
|<span data-ttu-id="59cae-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="59cae-110">Data type:</span></span>  <br/> |<span data-ttu-id="59cae-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="59cae-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="59cae-112">区域：</span><span class="sxs-lookup"><span data-stu-id="59cae-112">Area:</span></span>  <br/> |<span data-ttu-id="59cae-113">其他</span><span class="sxs-lookup"><span data-stu-id="59cae-113">Miscellaneous</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="59cae-114">说明</span><span class="sxs-lookup"><span data-stu-id="59cae-114">Remarks</span></span>

<span data-ttu-id="59cae-115">建议具有命名属性的对象公开此属性。</span><span class="sxs-lookup"><span data-stu-id="59cae-115">It is recommended that objects having named properties expose this property.</span></span> <span data-ttu-id="59cae-116">客户端应用程序应该检查这两个对象的**PR_MAPPING_SIGNATURE**属性时复制命名到另一个对象的属性。</span><span class="sxs-lookup"><span data-stu-id="59cae-116">A client application should check the **PR_MAPPING_SIGNATURE** property of both objects when copying named properties from one object to another.</span></span> <span data-ttu-id="59cae-117">使用此属性可以减少翻译之间复制的属性的名称和标识符。</span><span class="sxs-lookup"><span data-stu-id="59cae-117">Use of this property can minimize translating between copied properties' names and identifiers.</span></span> 
  
<span data-ttu-id="59cae-118">如果给定 MAPI 对象，该属性不存在，该对象将具有其自己的名称和标识符的唯一映射。</span><span class="sxs-lookup"><span data-stu-id="59cae-118">If this property does not exist for a given MAPI object, then the object has its own unique mapping of names and identifiers.</span></span> <span data-ttu-id="59cae-119">在这种情况下客户端必须对源对象，然后对目标对象的[IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md)方法调用[IMAPIProp::GetNamesFromIDs](imapiprop-getnamesfromids.md)方法。</span><span class="sxs-lookup"><span data-stu-id="59cae-119">In this case the client must call the [IMAPIProp::GetNamesFromIDs](imapiprop-getnamesfromids.md) method on the source object and then the [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md) method on the destination object.</span></span> 
  
<span data-ttu-id="59cae-120">当两个对象具有相同的**PR_MAPPING_SIGNATURE**值时，则不需要翻译名称标识符和标识符名称与客户端。</span><span class="sxs-lookup"><span data-stu-id="59cae-120">When two objects have the same **PR_MAPPING_SIGNATURE** value, the client does not need to translate name to identifier and identifier to name.</span></span> <span data-ttu-id="59cae-121">客户端可以只需调用[IMAPIProp::GetProps](imapiprop-getprops.md)方法对源和[IMAPIProp::SetProps](imapiprop-setprops.md)方法在目标位置。</span><span class="sxs-lookup"><span data-stu-id="59cae-121">The client can simply call the [IMAPIProp::GetProps](imapiprop-getprops.md) method on the source and then the [IMAPIProp::SetProps](imapiprop-setprops.md) method on the destination.</span></span> <span data-ttu-id="59cae-122">这很方便的客户端的执行的命名属性的自定义复制和提供程序实现的[IMAPIProp::CopyTo](imapiprop-copyto.md)和[IMAPIProp::CopyProps](imapiprop-copyprops.md)方法。</span><span class="sxs-lookup"><span data-stu-id="59cae-122">This is convenient for clients that perform custom copying of named properties, and for providers implementing the [IMAPIProp::CopyTo](imapiprop-copyto.md) and [IMAPIProp::CopyProps](imapiprop-copyprops.md) methods.</span></span> 
  
<span data-ttu-id="59cae-123">命名的属性和映射的名称和标识符的详细信息，请参阅[MAPI 命名属性](mapi-named-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="59cae-123">For more information on named properties and mapping of names and identifiers, see [MAPI Named Properties](mapi-named-properties.md).</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="59cae-124">相关资源</span><span class="sxs-lookup"><span data-stu-id="59cae-124">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="59cae-125">协议规范</span><span class="sxs-lookup"><span data-stu-id="59cae-125">Protocol specifications</span></span>

<span data-ttu-id="59cae-126">[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="59cae-126">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="59cae-127">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="59cae-127">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="59cae-128">[[MS OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="59cae-128">[[MS-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="59cae-129">指定的属性和用户、 联系人、 组和资源的操作列表。</span><span class="sxs-lookup"><span data-stu-id="59cae-129">Specifies the properties and operations for lists of users, contacts, groups, and resources.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="59cae-130">头文件</span><span class="sxs-lookup"><span data-stu-id="59cae-130">Header files</span></span>

<span data-ttu-id="59cae-131">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="59cae-131">Mapidefs.h</span></span>
  
> <span data-ttu-id="59cae-132">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="59cae-132">Provides data type definitions.</span></span>
    
<span data-ttu-id="59cae-133">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="59cae-133">Mapitags.h</span></span>
  
> <span data-ttu-id="59cae-134">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="59cae-134">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="59cae-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="59cae-135">See also</span></span>



[<span data-ttu-id="59cae-136">MAPINAMEID</span><span class="sxs-lookup"><span data-stu-id="59cae-136">MAPINAMEID</span></span>](mapinameid.md)


[<span data-ttu-id="59cae-137">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="59cae-137">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="59cae-138">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="59cae-138">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="59cae-139">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="59cae-139">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="59cae-140">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="59cae-140">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

