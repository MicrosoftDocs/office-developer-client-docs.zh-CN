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
# <a name="pidtagmappingsignature-canonical-property"></a><span data-ttu-id="ca33f-103">PidTagMappingSignature 规范属性</span><span class="sxs-lookup"><span data-stu-id="ca33f-103">PidTagMappingSignature Canonical Property</span></span>

  
  
<span data-ttu-id="ca33f-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ca33f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ca33f-105">包含特定 MAPI 对象的命名属性的映射签名。</span><span class="sxs-lookup"><span data-stu-id="ca33f-105">Contains the mapping signature for named properties of a particular MAPI object.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="ca33f-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="ca33f-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="ca33f-107">PR_MAPPING_SIGNATURE</span><span class="sxs-lookup"><span data-stu-id="ca33f-107">PR_MAPPING_SIGNATURE</span></span>  <br/> |
|<span data-ttu-id="ca33f-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="ca33f-108">Identifier:</span></span>  <br/> |<span data-ttu-id="ca33f-109">0x0FF8</span><span class="sxs-lookup"><span data-stu-id="ca33f-109">0x0FF8</span></span>  <br/> |
|<span data-ttu-id="ca33f-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="ca33f-110">Data type:</span></span>  <br/> |<span data-ttu-id="ca33f-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="ca33f-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="ca33f-112">区域：</span><span class="sxs-lookup"><span data-stu-id="ca33f-112">Area:</span></span>  <br/> |<span data-ttu-id="ca33f-113">其他</span><span class="sxs-lookup"><span data-stu-id="ca33f-113">Miscellaneous</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="ca33f-114">备注</span><span class="sxs-lookup"><span data-stu-id="ca33f-114">Remarks</span></span>

<span data-ttu-id="ca33f-115">建议具有命名属性的对象公开此属性。</span><span class="sxs-lookup"><span data-stu-id="ca33f-115">It is recommended that objects having named properties expose this property.</span></span> <span data-ttu-id="ca33f-116">在将命名属性 **从一个对象PR_MAPPING_SIGNATURE** 另一个对象时，客户端应用程序应检查这两个对象的 PR_MAPPING_SIGNATURE 属性。</span><span class="sxs-lookup"><span data-stu-id="ca33f-116">A client application should check the **PR_MAPPING_SIGNATURE** property of both objects when copying named properties from one object to another.</span></span> <span data-ttu-id="ca33f-117">使用此属性可以最大程度地减少复制的属性的名称和标识符之间的转换。</span><span class="sxs-lookup"><span data-stu-id="ca33f-117">Use of this property can minimize translating between copied properties' names and identifiers.</span></span> 
  
<span data-ttu-id="ca33f-118">如果给定 MAPI 对象不存在此属性，则该对象具有其自己的名称和标识符的唯一映射。</span><span class="sxs-lookup"><span data-stu-id="ca33f-118">If this property does not exist for a given MAPI object, then the object has its own unique mapping of names and identifiers.</span></span> <span data-ttu-id="ca33f-119">在这种情况下，客户端必须对源对象调用 [IMAPIProp：：GetNamesFromIDs](imapiprop-getnamesfromids.md) 方法，然后在目标对象上调用 [IMAPIProp：：GetIDsFromNames](imapiprop-getidsfromnames.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="ca33f-119">In this case the client must call the [IMAPIProp::GetNamesFromIDs](imapiprop-getnamesfromids.md) method on the source object and then the [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md) method on the destination object.</span></span> 
  
<span data-ttu-id="ca33f-120">当两个对象具有相同的PR_MAPPING_SIGNATURE值时，客户端无需将名称转换为标识符，而将标识符转换为名称。</span><span class="sxs-lookup"><span data-stu-id="ca33f-120">When two objects have the same **PR_MAPPING_SIGNATURE** value, the client does not need to translate name to identifier and identifier to name.</span></span> <span data-ttu-id="ca33f-121">客户端只需对源调用 [IMAPIProp：：GetProps](imapiprop-getprops.md) 方法，然后在目标上调用 [IMAPIProp：：SetProps](imapiprop-setprops.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="ca33f-121">The client can simply call the [IMAPIProp::GetProps](imapiprop-getprops.md) method on the source and then the [IMAPIProp::SetProps](imapiprop-setprops.md) method on the destination.</span></span> <span data-ttu-id="ca33f-122">这便于执行命名属性的自定义复制的客户端，以及实现 [IMAPIProp：：CopyTo](imapiprop-copyto.md) 和 [IMAPIProp：：CopyProps 方法的提供程序](imapiprop-copyprops.md) 。</span><span class="sxs-lookup"><span data-stu-id="ca33f-122">This is convenient for clients that perform custom copying of named properties, and for providers implementing the [IMAPIProp::CopyTo](imapiprop-copyto.md) and [IMAPIProp::CopyProps](imapiprop-copyprops.md) methods.</span></span> 
  
<span data-ttu-id="ca33f-123">有关命名属性以及名称和标识符映射的信息，请参阅 [MAPI Named Properties](mapi-named-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="ca33f-123">For more information on named properties and mapping of names and identifiers, see [MAPI Named Properties](mapi-named-properties.md).</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="ca33f-124">相关资源</span><span class="sxs-lookup"><span data-stu-id="ca33f-124">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="ca33f-125">协议规范</span><span class="sxs-lookup"><span data-stu-id="ca33f-125">Protocol specifications</span></span>

<span data-ttu-id="ca33f-126">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ca33f-126">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ca33f-127">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="ca33f-127">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="ca33f-128">[[MS-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ca33f-128">[[MS-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ca33f-129">指定用户、联系人、组和资源的列表的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="ca33f-129">Specifies the properties and operations for lists of users, contacts, groups, and resources.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="ca33f-130">头文件</span><span class="sxs-lookup"><span data-stu-id="ca33f-130">Header files</span></span>

<span data-ttu-id="ca33f-131">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="ca33f-131">Mapidefs.h</span></span>
  
> <span data-ttu-id="ca33f-132">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="ca33f-132">Provides data type definitions.</span></span>
    
<span data-ttu-id="ca33f-133">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="ca33f-133">Mapitags.h</span></span>
  
> <span data-ttu-id="ca33f-134">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="ca33f-134">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="ca33f-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ca33f-135">See also</span></span>



[<span data-ttu-id="ca33f-136">MAPINAMEID</span><span class="sxs-lookup"><span data-stu-id="ca33f-136">MAPINAMEID</span></span>](mapinameid.md)


[<span data-ttu-id="ca33f-137">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="ca33f-137">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="ca33f-138">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="ca33f-138">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="ca33f-139">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="ca33f-139">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="ca33f-140">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="ca33f-140">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

