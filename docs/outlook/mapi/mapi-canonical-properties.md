---
title: MAPI 规范属性
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 29151beb-7436-401a-8072-58d4facd8458
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 4b017089a675727703de9e2ed4d584e7f77a778a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32319052"
---
# <a name="mapi-canonical-properties"></a><span data-ttu-id="e64d2-103">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="e64d2-103">MAPI Canonical Properties</span></span>

  
  
<span data-ttu-id="e64d2-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e64d2-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e64d2-105">规范属性是一个虚拟属性, 表示 mapi 属性, 或使用同一属性标识符定义的多个 mapi 属性。</span><span class="sxs-lookup"><span data-stu-id="e64d2-105">A canonical property is a virtual property that represents a MAPI property, or multiple MAPI properties defined with the same property identifier.</span></span> <span data-ttu-id="e64d2-106">规范属性仅用于促进在讨论或代码外部的文档中一致标识 MAPI 属性。</span><span class="sxs-lookup"><span data-stu-id="e64d2-106">Canonical properties are only intended to facilitate consistent identification of MAPI properties in discussions or documentation outside of code.</span></span> <span data-ttu-id="e64d2-107">与 mapi 定义的标记属性名称不同, 规范属性名称不在 MAPI 头文件中定义为全局常量。</span><span class="sxs-lookup"><span data-stu-id="e64d2-107">Unlike MAPI-defined tagged property names, canonical property names are not defined as global constants in MAPI header files.</span></span>
  
## <a name="naming-conventions"></a><span data-ttu-id="e64d2-108">命名约定</span><span class="sxs-lookup"><span data-stu-id="e64d2-108">Naming Conventions</span></span>

<span data-ttu-id="e64d2-109">规范属性名称以前缀 "Pid" 开头, 后者表示 "属性标识符"。</span><span class="sxs-lookup"><span data-stu-id="e64d2-109">Canonical property names begin with a prefix, "Pid", which represents "property identifier."</span></span> <span data-ttu-id="e64d2-110">根据属性是否为标记属性、带有数值标识符的命名属性或具有字符串名称的命名属性, 前缀将分别被限定为 "PidTag"、"PidLid" 和 "PidName"。</span><span class="sxs-lookup"><span data-stu-id="e64d2-110">Depending on whether the property is a tagged property, a named property with a numerical identifier, or a named property with a string name, the prefix is further qualified as "PidTag," "PidLid," and "PidName" respectively.</span></span> <span data-ttu-id="e64d2-111">例如, [PidTagAccount](pidtagaccount-canonical-property.md)表示标记属性、 **PR_ACCOUNT** ([PidTagAccount](pidtagaccount-canonical-property.md))、 **PR_ACCOUNT_A** ([PidTagAccount](pidtagaccount-canonical-property.md)) 和**PR_ACCOUNT_W** ([PidTagAccount](pidtagaccount-canonical-property.md)), 后者指定收件人的帐户名称;[PidLidContacts](pidlidcontacts-canonical-property.md)表示**dispidContacts**属性, 该属性具有一个数值标识符, 用于指定与邮件关联的联系人的名称;和[PidNamePhishingStamp](pidnamephishingstamp-canonical-property.md)表示 "https://schemas.microsoft.com/outlook/phishingstamp," 具有字符串名称的命名属性, 并指定标记可能是网络钓鱼的邮件的字符串。</span><span class="sxs-lookup"><span data-stu-id="e64d2-111">For example, [PidTagAccount](pidtagaccount-canonical-property.md) represents the tagged properties, **PR_ACCOUNT** ([PidTagAccount](pidtagaccount-canonical-property.md)), **PR_ACCOUNT_A** ([PidTagAccount](pidtagaccount-canonical-property.md)), and **PR_ACCOUNT_W** ([PidTagAccount](pidtagaccount-canonical-property.md)), that specify a recipient's account name; [PidLidContacts](pidlidcontacts-canonical-property.md) represents the **dispidContacts** property, a named property that has a numerical identifier and that specifies the name of contacts associated with a message; and [PidNamePhishingStamp](pidnamephishingstamp-canonical-property.md) represents "https://schemas.microsoft.com/outlook/phishingstamp," a named property that has a string name, and that specifies the string marking messages that are likely to be phishing.</span></span> 
  
## <a name="representing-similar-properties-using-one-canonical-property"></a><span data-ttu-id="e64d2-112">使用一个规范属性表示类似的属性</span><span class="sxs-lookup"><span data-stu-id="e64d2-112">Representing Similar Properties Using One Canonical Property</span></span>

### <a name="identifying-properties-in-mapi"></a><span data-ttu-id="e64d2-113">标识 MAPI 中的属性</span><span class="sxs-lookup"><span data-stu-id="e64d2-113">Identifying Properties in MAPI</span></span>

<span data-ttu-id="e64d2-114">MAPI 中的所有属性均由一个不带符号的16位值的属性标识符标识。</span><span class="sxs-lookup"><span data-stu-id="e64d2-114">All properties in MAPI are identified by a property identifier that is an unsigned 16-bit value.</span></span> <span data-ttu-id="e64d2-115">属性标识符和属性类型 (另一个无符号的16位值) 构成属性的属性标记。</span><span class="sxs-lookup"><span data-stu-id="e64d2-115">The property identifier and the property type (another unsigned 16-bit value) constitute a property tag for the property.</span></span> 
  
<span data-ttu-id="e64d2-116">MAPI 使用属性标记来唯一定义属性。</span><span class="sxs-lookup"><span data-stu-id="e64d2-116">MAPI uses a property tag to uniquely define properties.</span></span> <span data-ttu-id="e64d2-117">具有相同属性标记的属性 (如**PR_BUSINESS2_TELEPHONE_NUMBER** ([PidTagBusiness2TelephoneNumber](pidtagbusiness2telephonenumber-canonical-property.md)) 和**PR_OFFICE2_TELEPHONE_NUMBER** ([PidTagBusiness2TelephoneNumber](pidtagbusiness2telephonenumber-canonical-property.md))) 被视为相同MAPI 中的属性。</span><span class="sxs-lookup"><span data-stu-id="e64d2-117">Properties that have the same property tag, like **PR_BUSINESS2_TELEPHONE_NUMBER** ([PidTagBusiness2TelephoneNumber](pidtagbusiness2telephonenumber-canonical-property.md)) and **PR_OFFICE2_TELEPHONE_NUMBER** ([PidTagBusiness2TelephoneNumber](pidtagbusiness2telephonenumber-canonical-property.md)), are considered identical properties in MAPI.</span></span> <span data-ttu-id="e64d2-118">有关 MAPI 为自己的属性定义的属性标记的列表, 请参阅 mapi 头文件 Mapitags。</span><span class="sxs-lookup"><span data-stu-id="e64d2-118">For a list of property tags that MAPI has defined for its own properties, see the MAPI header file, Mapitags.h.</span></span>
  
<span data-ttu-id="e64d2-119">请注意, MAPI 将属性标识符分成区域。</span><span class="sxs-lookup"><span data-stu-id="e64d2-119">Note that MAPI divides property identifiers into ranges.</span></span> <span data-ttu-id="e64d2-120">其中, 标识符位于范围内表示其使用和所有权。</span><span class="sxs-lookup"><span data-stu-id="e64d2-120">Where an identifier falls in the range indicates its use and ownership.</span></span> <span data-ttu-id="e64d2-121">标记属性的属性标识符位于0x0001 到0x7FFF 的范围内。</span><span class="sxs-lookup"><span data-stu-id="e64d2-121">The property identifiers of tagged properties fall in the range of 0x0001 to 0x7FFF.</span></span> <span data-ttu-id="e64d2-122">在此范围内是 MAPI 定义的属性的属性标识符, 这些属性位于0x0001 到0x3FFF 的范围中。</span><span class="sxs-lookup"><span data-stu-id="e64d2-122">Within this range are the property identifiers of MAPI-defined properties, which fall in the range of 0x0001 to 0x3FFF.</span></span> <span data-ttu-id="e64d2-123">命名属性的属性标识符介于0x8000 和0x8FFF 之间。</span><span class="sxs-lookup"><span data-stu-id="e64d2-123">The property identifiers of named properties fall in the range from 0x8000 to 0x8FFF.</span></span> 
  
<span data-ttu-id="e64d2-124">命名属性由属性集另外设置, 或者是 long ID (盖子), 它是一个无符号的32位值或一个字符串。</span><span class="sxs-lookup"><span data-stu-id="e64d2-124">Named properties are additionally attributed by a property set, and either a long ID (LID), which is an unsigned 32-bit value, or a string.</span></span> <span data-ttu-id="e64d2-125">属性集是一个 GUID, 用于标识一组具有类似用途的命名属性。</span><span class="sxs-lookup"><span data-stu-id="e64d2-125">A property set is a GUID that identifies a group of named properties with a similar purpose.</span></span> <span data-ttu-id="e64d2-126">属性集和盖子或字符串名称用于获取或设置命名属性。</span><span class="sxs-lookup"><span data-stu-id="e64d2-126">The property set and LID or string name are used to get or set the named property.</span></span>
  
### <a name="property-type"></a><span data-ttu-id="e64d2-127">属性类型</span><span class="sxs-lookup"><span data-stu-id="e64d2-127">Property Type</span></span>

<span data-ttu-id="e64d2-128">除了标识符之外, 属性的特性按指定该属性所允许的值类型的数据类型。</span><span class="sxs-lookup"><span data-stu-id="e64d2-128">Aside from identifiers, a property is attributed by a data type that specifies the type of values allowed for that property.</span></span>
  
<span data-ttu-id="e64d2-129">对于字符串类型的属性, 取决于对基础平台中的 Unicode 的支持, 该属性可以是类型 PT_STRING8 (以 null 结尾的8位字符串) 或 PT_UNICODE (以 null 结尾的 Unicode 字符串)。</span><span class="sxs-lookup"><span data-stu-id="e64d2-129">For properties that are of the string type, depending on the support for Unicode in the underlying platform, the property can be of type PT_STRING8 (null-terminated 8-bit character string) or PT_UNICODE (null-terminated Unicode string).</span></span> <span data-ttu-id="e64d2-130">可以使用 PT_TSTRING 类型定义属性, 并根据编译设置, PT_TSTRING 默认为支持 unicode 的平台的 Unicode 字符串, 或者是支持 ANSI 或 DBCS 的平台的 PT_STRING8 字符串。</span><span class="sxs-lookup"><span data-stu-id="e64d2-130">A property can be defined with the PT_TSTRING type, and depending on compilation settings, PT_TSTRING defaults to a Unicode string for platforms that support Unicode, or to a PT_STRING8 string for platforms that support ANSI or DBCS.</span></span> <span data-ttu-id="e64d2-131">通常情况下, 字符串类型的属性由三个相似的名称 (例如**PR_ACCOUNT**、 **PR_ACCOUNT_A**和**PR_ACCOUNT_W**) 标识, 分别为 PT_TSTRING、PT_STRING8 和 PT_UNICODE 类型。</span><span class="sxs-lookup"><span data-stu-id="e64d2-131">It is common that a string-typed property is identified by three similar names, such as **PR_ACCOUNT**, **PR_ACCOUNT_A**, and **PR_ACCOUNT_W**, which are of the type PT_TSTRING, PT_STRING8, and PT_UNICODE respectively.</span></span>
  
<span data-ttu-id="e64d2-132">有关与类型相关的属性类型和宏的详细信息, 请参阅 MAPI 头文件 mapidefs.h。</span><span class="sxs-lookup"><span data-stu-id="e64d2-132">For more information on property types and macros related to types, see the MAPI header file, Mapidefs.h.</span></span>
  
### <a name="identifying-similar-properties"></a><span data-ttu-id="e64d2-133">标识相似的属性</span><span class="sxs-lookup"><span data-stu-id="e64d2-133">Identifying Similar Properties</span></span>

<span data-ttu-id="e64d2-134">在当前 MAPI 属性的 "横向" 中, 发现某个属性在不同的属性名称下公开, 这并不常见, 它们都是用相同的属性标识符定义的。</span><span class="sxs-lookup"><span data-stu-id="e64d2-134">In the current MAPI property landscape, it is not uncommon to find that a property has been exposed under different property names, all of which are defined with the same property identifier.</span></span> <span data-ttu-id="e64d2-135">例如, 标记属性**PR_BUSINESS2_TELEPHONE_NUMBER**和**PR_OFFICE2_TELEPHONE_NUMBER**在 Mapitags 中定义为具有相同的属性标识符和类型。</span><span class="sxs-lookup"><span data-stu-id="e64d2-135">For example, the tagged properties, **PR_BUSINESS2_TELEPHONE_NUMBER** and **PR_OFFICE2_TELEPHONE_NUMBER**, are defined in Mapitags.h to have the same property identifier and type.</span></span> <span data-ttu-id="e64d2-136">与以下两个属性密切相关:</span><span class="sxs-lookup"><span data-stu-id="e64d2-136">Closely related to these two properties are:</span></span>
  
- <span data-ttu-id="e64d2-137">**PR_BUSINESS2_TELEPHONE_NUMBER_A**</span><span class="sxs-lookup"><span data-stu-id="e64d2-137">**PR_BUSINESS2_TELEPHONE_NUMBER_A**</span></span>
    
- <span data-ttu-id="e64d2-138">**PR_BUSINESS2_TELEPHONE_NUMBER_W**</span><span class="sxs-lookup"><span data-stu-id="e64d2-138">**PR_BUSINESS2_TELEPHONE_NUMBER_W**</span></span>
    
- <span data-ttu-id="e64d2-139">**PR_OFFICE2_TELEPHONE_NUMBER_A**</span><span class="sxs-lookup"><span data-stu-id="e64d2-139">**PR_OFFICE2_TELEPHONE_NUMBER_A**</span></span>
    
- <span data-ttu-id="e64d2-140">**PR_OFFICE2_TELEPHONE_NUMBER_W**</span><span class="sxs-lookup"><span data-stu-id="e64d2-140">**PR_OFFICE2_TELEPHONE_NUMBER_W**</span></span>
    
<span data-ttu-id="e64d2-141">将 "_A" 后缀的属性键入为 PT_STRING8, 并将那些具有 "_W" 后缀的属性键入为 PT_UNICODE。</span><span class="sxs-lookup"><span data-stu-id="e64d2-141">The properties with the "_A" suffix are typed as PT_STRING8, and those with the "_W" suffix are typed as PT_UNICODE.</span></span>
  
<span data-ttu-id="e64d2-142">在此示例中, 规范属性 ( **PidTagBusiness2TelephoneNumber** ) 的目的是, 使用一个标识符, 并以一致的方式 (使用 "Pid" 前缀) 在所有 MAPI 中实现更紧密关联的 mapi 属性。属性.</span><span class="sxs-lookup"><span data-stu-id="e64d2-142">The purpose of a canonical property, **PidTagBusiness2TelephoneNumber** in this example, is to facilitate referencing such closely affiliated MAPI properties using one identifier, and in a consistent way (using the "Pid" prefix) across all MAPI properties.</span></span> <span data-ttu-id="e64d2-143">若要查找规范属性表示的真实 MAPI 属性, 请参阅[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)。</span><span class="sxs-lookup"><span data-stu-id="e64d2-143">To find which real MAPI properties a canonical property represents, see [Mapping Canonical Property Names to MAPI Names](mapping-canonical-property-names-to-mapi-names.md).</span></span> <span data-ttu-id="e64d2-144">若要查找与 mapi 属性相关联的规范属性, 请参阅[将 mapi 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)。</span><span class="sxs-lookup"><span data-stu-id="e64d2-144">To find the canonical property that a MAPI property is associated with, see [Mapping MAPI Names to Canonical Property Names](mapping-mapi-names-to-canonical-property-names.md).</span></span>
  
## <a name="mapi-support-of-canonical-property-names"></a><span data-ttu-id="e64d2-145">规范属性名称的 MAPI 支持</span><span class="sxs-lookup"><span data-stu-id="e64d2-145">MAPI Support of Canonical Property Names</span></span>

<span data-ttu-id="e64d2-146">由于规范属性不是真正的属性, 并且不是在 MAPI 头文件中定义的, 因此不应在代码中使用规范属性名称;相反, 应继续在代码中使用确切的 MAPI 属性名称。</span><span class="sxs-lookup"><span data-stu-id="e64d2-146">Because canonical properties are not real properties and are not defined in MAPI header files, you should not use canonical property names in code; instead, you should continue to use the exact MAPI property names in code.</span></span> <span data-ttu-id="e64d2-147">例如, 可以将**PR_BUSINESS2_TELEPHONE_NUMBER**和**PR_OFFICE2_TELEPHONE_NUMBER**引用为**PidTagBusiness2TelephoneNumber**, 并使用**PR_BUSINESS2_TELEPHONE_NUMBER**或 PR_OFFICE2_ 的代码之外的代码。 \*\*\*\* 代码中的 TELEPHONE_NUMBER。</span><span class="sxs-lookup"><span data-stu-id="e64d2-147">For example, you can refer **PR_BUSINESS2_TELEPHONE_NUMBER** and **PR_OFFICE2_TELEPHONE_NUMBER** outside of code as **PidTagBusiness2TelephoneNumber**, and use either **PR_BUSINESS2_TELEPHONE_NUMBER** or **PR_OFFICE2_TELEPHONE_NUMBER** in code.</span></span> 
  
<span data-ttu-id="e64d2-148">如果您必须在代码中使用规范属性名称, 则必须先在您自己的头文件中定义它们。</span><span class="sxs-lookup"><span data-stu-id="e64d2-148">If you must use canonical property names in your code, you must first define them in your own header files.</span></span>
  
## <a name="canonical-property-names-and-exchange-protocol-specifications"></a><span data-ttu-id="e64d2-149">规范属性名称和 Exchange 协议规范</span><span class="sxs-lookup"><span data-stu-id="e64d2-149">Canonical Property Names and Exchange Protocol Specifications</span></span>

<span data-ttu-id="e64d2-150">规范名称在 exchange server 用于与其他 Microsoft 产品通信的 microsoft Exchange server 协议规范中引用。</span><span class="sxs-lookup"><span data-stu-id="e64d2-150">Canonical names are referenced in Microsoft Exchange Server protocol specifications that are used by Exchange Server to communicate with other Microsoft products.</span></span> <span data-ttu-id="e64d2-151">有关 Exchange 协议规范所引用的邮件对象属性的详细信息, 请参阅[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="e64d2-151">For more information about message object properties referenced by Exchange protocol specifications, see [[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e64d2-152">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e64d2-152">See also</span></span>



[<span data-ttu-id="e64d2-153">MAPI 属性标记</span><span class="sxs-lookup"><span data-stu-id="e64d2-153">MAPI Property Tags</span></span>](mapi-property-tags.md)
  
[<span data-ttu-id="e64d2-154">MAPI 属性标识符概述</span><span class="sxs-lookup"><span data-stu-id="e64d2-154">MAPI Property Identifier Overview</span></span>](mapi-property-identifier-overview.md)
  
[<span data-ttu-id="e64d2-155">MAPI 属性类型概述</span><span class="sxs-lookup"><span data-stu-id="e64d2-155">MAPI Property Type Overview</span></span>](mapi-property-type-overview.md)

