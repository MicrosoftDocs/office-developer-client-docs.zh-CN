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
ms.openlocfilehash: 2fc605c57936765f43d7a6941dcc8d40d058db2f
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34540474"
---
# <a name="mapi-canonical-properties"></a><span data-ttu-id="65e00-103">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="65e00-103">MAPI Canonical Properties</span></span>

  
  
<span data-ttu-id="65e00-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="65e00-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="65e00-105">规范属性是一个代表 MAPI 属性的虚拟属性，或者是使用同一属性标识符定义的多个 MAPI 属性。</span><span class="sxs-lookup"><span data-stu-id="65e00-105">A canonical property is a virtual property that represents a MAPI property, or multiple MAPI properties defined with the same property identifier.</span></span> <span data-ttu-id="65e00-106">规范属性仅用于促进在讨论或代码中对 MAPI 属性进行一致的标识。</span><span class="sxs-lookup"><span data-stu-id="65e00-106">Canonical properties are only intended to facilitate consistent identification of MAPI properties in discussions or documentation outside of code.</span></span> <span data-ttu-id="65e00-107">与 MAPI 定义的带标记的属性名称不同，规范属性名称不会在 MAPI 头文件中定义为全局常量。</span><span class="sxs-lookup"><span data-stu-id="65e00-107">Unlike MAPI-defined tagged property names, canonical property names are not defined as global constants in MAPI header files.</span></span>
  
## <a name="naming-conventions"></a><span data-ttu-id="65e00-108">命名约定</span><span class="sxs-lookup"><span data-stu-id="65e00-108">Naming Conventions</span></span>

<span data-ttu-id="65e00-109">规范属性名称以前缀"Pid"开头，它表示"属性标识符"。</span><span class="sxs-lookup"><span data-stu-id="65e00-109">Canonical property names begin with a prefix, "Pid", which represents "property identifier."</span></span> <span data-ttu-id="65e00-110">根据该属性是带标记的属性、具有数字标识符的命名属性还是具有字符串名称的命名属性，前缀将被分别进一步限定为"PidTag"、"PidLid"和"PidName"。</span><span class="sxs-lookup"><span data-stu-id="65e00-110">Depending on whether the property is a tagged property, a named property with a numerical identifier, or a named property with a string name, the prefix is further qualified as "PidTag," "PidLid," and "PidName" respectively.</span></span> <span data-ttu-id="65e00-111">例如 [，PidTagAccount](pidtagaccount-canonical-property.md)表示指定收件人帐户名称的带标记属性 PR_ACCOUNT **(** [PidTagAccount](pidtagaccount-canonical-property.md)) 、PR_ACCOUNT_A ([PidTagAccount](pidtagaccount-canonical-property.md)) 和 **PR_ACCOUNT_W** ([PidTagAccount](pidtagaccount-canonical-property.md)) ; [PidLidContacts](pidlidcontacts-canonical-property.md)表示 **dispidContacts** 属性，一个命名属性，具有数字标识符，并指定与邮件相关联的联系人的名称;和 [PidNamePhishingStamp](pidnamephishingstamp-canonical-property.md)表示"，"，一个命名属性，具有一个字符串名称，并指定标记可能是网络钓鱼 http://schemas.microsoft.com/outlook/phishingstamp 邮件的字符串。</span><span class="sxs-lookup"><span data-stu-id="65e00-111">For example, [PidTagAccount](pidtagaccount-canonical-property.md) represents the tagged properties, **PR_ACCOUNT** ([PidTagAccount](pidtagaccount-canonical-property.md)), **PR_ACCOUNT_A** ([PidTagAccount](pidtagaccount-canonical-property.md)), and **PR_ACCOUNT_W** ([PidTagAccount](pidtagaccount-canonical-property.md)), that specify a recipient's account name; [PidLidContacts](pidlidcontacts-canonical-property.md) represents the **dispidContacts** property, a named property that has a numerical identifier and that specifies the name of contacts associated with a message; and [PidNamePhishingStamp](pidnamephishingstamp-canonical-property.md) represents "http://schemas.microsoft.com/outlook/phishingstamp," a named property that has a string name, and that specifies the string marking messages that are likely to be phishing.</span></span> 
  
## <a name="representing-similar-properties-using-one-canonical-property"></a><span data-ttu-id="65e00-112">使用一个规范属性表示类似的属性</span><span class="sxs-lookup"><span data-stu-id="65e00-112">Representing Similar Properties Using One Canonical Property</span></span>

### <a name="identifying-properties-in-mapi"></a><span data-ttu-id="65e00-113">标识 MAPI 中的属性</span><span class="sxs-lookup"><span data-stu-id="65e00-113">Identifying Properties in MAPI</span></span>

<span data-ttu-id="65e00-114">MAPI 中所有属性都由无符号 16 位值的属性标识符标识。</span><span class="sxs-lookup"><span data-stu-id="65e00-114">All properties in MAPI are identified by a property identifier that is an unsigned 16-bit value.</span></span> <span data-ttu-id="65e00-115">属性标识符和属性类型 (另一个未签名的 16 位) 构成属性的属性标记。</span><span class="sxs-lookup"><span data-stu-id="65e00-115">The property identifier and the property type (another unsigned 16-bit value) constitute a property tag for the property.</span></span> 
  
<span data-ttu-id="65e00-116">MAPI 使用属性标记唯一地定义属性。</span><span class="sxs-lookup"><span data-stu-id="65e00-116">MAPI uses a property tag to uniquely define properties.</span></span> <span data-ttu-id="65e00-117">具有相同属性标记的属性（如 **PR_BUSINESS2_TELEPHONE_NUMBER** ([PidTagBusiness2TelephoneNumber](pidtagbusiness2telephonenumber-canonical-property.md)) 和 **PR_OFFICE2_TELEPHONE_NUMBER** ([PidTagBusiness2TelephoneNumber](pidtagbusiness2telephonenumber-canonical-property.md)) ）在 MAPI 中被视为相同的属性。</span><span class="sxs-lookup"><span data-stu-id="65e00-117">Properties that have the same property tag, like **PR_BUSINESS2_TELEPHONE_NUMBER** ([PidTagBusiness2TelephoneNumber](pidtagbusiness2telephonenumber-canonical-property.md)) and **PR_OFFICE2_TELEPHONE_NUMBER** ([PidTagBusiness2TelephoneNumber](pidtagbusiness2telephonenumber-canonical-property.md)), are considered identical properties in MAPI.</span></span> <span data-ttu-id="65e00-118">有关 MAPI 为其自身的属性定义的属性标记的列表，请参阅 MAPI 头文件 Mapitags.h。</span><span class="sxs-lookup"><span data-stu-id="65e00-118">For a list of property tags that MAPI has defined for its own properties, see the MAPI header file, Mapitags.h.</span></span>
  
<span data-ttu-id="65e00-119">请注意，MAPI 将属性标识符划分为范围。</span><span class="sxs-lookup"><span data-stu-id="65e00-119">Note that MAPI divides property identifiers into ranges.</span></span> <span data-ttu-id="65e00-120">标识符在范围中的何处指示其使用和所有权。</span><span class="sxs-lookup"><span data-stu-id="65e00-120">Where an identifier falls in the range indicates its use and ownership.</span></span> <span data-ttu-id="65e00-121">标记属性的属性标识符位于0x0001 0x7FFF。</span><span class="sxs-lookup"><span data-stu-id="65e00-121">The property identifiers of tagged properties fall in the range of 0x0001 to 0x7FFF.</span></span> <span data-ttu-id="65e00-122">在此范围内是 MAPI 定义属性的属性标识符，这些属性属于0x0001范围0x3FFF。</span><span class="sxs-lookup"><span data-stu-id="65e00-122">Within this range are the property identifiers of MAPI-defined properties, which fall in the range of 0x0001 to 0x3FFF.</span></span> <span data-ttu-id="65e00-123">命名属性的属性标识符的范围从 0x8000 到 0x8FFF。</span><span class="sxs-lookup"><span data-stu-id="65e00-123">The property identifiers of named properties fall in the range from 0x8000 to 0x8FFF.</span></span> 
  
<span data-ttu-id="65e00-124">命名属性还由属性集和一个长 ID (一个（无符号的 32 位值）) 一个 LONG ID 或一个字符串。</span><span class="sxs-lookup"><span data-stu-id="65e00-124">Named properties are additionally attributed by a property set, and either a long ID (LID), which is an unsigned 32-bit value, or a string.</span></span> <span data-ttu-id="65e00-125">属性集是标识一组具有相似用途的命名属性的 GUID。</span><span class="sxs-lookup"><span data-stu-id="65e00-125">A property set is a GUID that identifies a group of named properties with a similar purpose.</span></span> <span data-ttu-id="65e00-126">属性集和一个或多个 STRING 名称用于获取或设置命名属性。</span><span class="sxs-lookup"><span data-stu-id="65e00-126">The property set and LID or string name are used to get or set the named property.</span></span>
  
### <a name="property-type"></a><span data-ttu-id="65e00-127">属性类型</span><span class="sxs-lookup"><span data-stu-id="65e00-127">Property Type</span></span>

<span data-ttu-id="65e00-128">除标识符外，属性由指定该属性数据类型类型的属性。</span><span class="sxs-lookup"><span data-stu-id="65e00-128">Aside from identifiers, a property is attributed by a data type that specifies the type of values allowed for that property.</span></span>
  
<span data-ttu-id="65e00-129">对于字符串类型的属性，该属性的类型可以是 PT_STRING8 (以 null 结尾的 8 位字符字符串) 或 PT_UNICODE (以 null 结尾的 Unicode 字符串) 。</span><span class="sxs-lookup"><span data-stu-id="65e00-129">For properties that are of the string type, depending on the support for Unicode in the underlying platform, the property can be of type PT_STRING8 (null-terminated 8-bit character string) or PT_UNICODE (null-terminated Unicode string).</span></span> <span data-ttu-id="65e00-130">可以使用 PT_TSTRING 类型定义属性，根据编译设置，PT_TSTRING 默认为支持 Unicode 的平台的 Unicode 字符串，或者支持 ANSI 或 DBCS 的平台的 PT_STRING8 字符串。</span><span class="sxs-lookup"><span data-stu-id="65e00-130">A property can be defined with the PT_TSTRING type, and depending on compilation settings, PT_TSTRING defaults to a Unicode string for platforms that support Unicode, or to a PT_STRING8 string for platforms that support ANSI or DBCS.</span></span> <span data-ttu-id="65e00-131">通常，字符串类型属性由三个相似的名称（如 **PR_ACCOUNT、PR_ACCOUNT_A** 和 **PR_ACCOUNT_W）** 标识，它们分别类型为 PT_TSTRING、PT_STRING8 和 PT_UNICODE。</span><span class="sxs-lookup"><span data-stu-id="65e00-131">It is common that a string-typed property is identified by three similar names, such as **PR_ACCOUNT**, **PR_ACCOUNT_A**, and **PR_ACCOUNT_W**, which are of the type PT_TSTRING, PT_STRING8, and PT_UNICODE respectively.</span></span>
  
<span data-ttu-id="65e00-132">有关与类型相关的属性类型和宏详细信息，请参阅 MAPI 头文件 Mapidefs.h。</span><span class="sxs-lookup"><span data-stu-id="65e00-132">For more information on property types and macros related to types, see the MAPI header file, Mapidefs.h.</span></span>
  
### <a name="identifying-similar-properties"></a><span data-ttu-id="65e00-133">标识相似属性</span><span class="sxs-lookup"><span data-stu-id="65e00-133">Identifying Similar Properties</span></span>

<span data-ttu-id="65e00-134">在当前 MAPI 属性的横向，发现一个属性已在不同的属性名称下公开，所有这些名称都使用相同的属性标识符进行定义的情况很常见。</span><span class="sxs-lookup"><span data-stu-id="65e00-134">In the current MAPI property landscape, it is not uncommon to find that a property has been exposed under different property names, all of which are defined with the same property identifier.</span></span> <span data-ttu-id="65e00-135">例如，标记属性 **（PR_BUSINESS2_TELEPHONE_NUMBER** 和 **PR_OFFICE2_TELEPHONE_NUMBER**）在 Mapitags.h 中定义，以具有相同的属性标识符和类型。</span><span class="sxs-lookup"><span data-stu-id="65e00-135">For example, the tagged properties, **PR_BUSINESS2_TELEPHONE_NUMBER** and **PR_OFFICE2_TELEPHONE_NUMBER**, are defined in Mapitags.h to have the same property identifier and type.</span></span> <span data-ttu-id="65e00-136">与这两个属性密切相关的有：</span><span class="sxs-lookup"><span data-stu-id="65e00-136">Closely related to these two properties are:</span></span>
  
- <span data-ttu-id="65e00-137">**PR_BUSINESS2_TELEPHONE_NUMBER_A**</span><span class="sxs-lookup"><span data-stu-id="65e00-137">**PR_BUSINESS2_TELEPHONE_NUMBER_A**</span></span>
    
- <span data-ttu-id="65e00-138">**PR_BUSINESS2_TELEPHONE_NUMBER_W**</span><span class="sxs-lookup"><span data-stu-id="65e00-138">**PR_BUSINESS2_TELEPHONE_NUMBER_W**</span></span>
    
- <span data-ttu-id="65e00-139">**PR_OFFICE2_TELEPHONE_NUMBER_A**</span><span class="sxs-lookup"><span data-stu-id="65e00-139">**PR_OFFICE2_TELEPHONE_NUMBER_A**</span></span>
    
- <span data-ttu-id="65e00-140">**PR_OFFICE2_TELEPHONE_NUMBER_W**</span><span class="sxs-lookup"><span data-stu-id="65e00-140">**PR_OFFICE2_TELEPHONE_NUMBER_W**</span></span>
    
<span data-ttu-id="65e00-141">具有"_A"后缀的属性类型为 PT_STRING8，具有"_W"后缀的属性类型为 PT_UNICODE。</span><span class="sxs-lookup"><span data-stu-id="65e00-141">The properties with the "_A" suffix are typed as PT_STRING8, and those with the "_W" suffix are typed as PT_UNICODE.</span></span>
  
<span data-ttu-id="65e00-142">规范属性（此示例中为 **PidTagBusiness2TelephoneNumber）** 的目的是为了便于使用一个标识符引用这种紧密关联 MAPI 属性，并便于在所有 MAPI 属性之间使用"Pid"前缀 (以一致的方式引用) 。</span><span class="sxs-lookup"><span data-stu-id="65e00-142">The purpose of a canonical property, **PidTagBusiness2TelephoneNumber** in this example, is to facilitate referencing such closely affiliated MAPI properties using one identifier, and in a consistent way (using the "Pid" prefix) across all MAPI properties.</span></span> <span data-ttu-id="65e00-143">若要查找规范属性表示哪些真实的 MAPI 属性，请参阅将规范属性名称映射到 [MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)。</span><span class="sxs-lookup"><span data-stu-id="65e00-143">To find which real MAPI properties a canonical property represents, see [Mapping Canonical Property Names to MAPI Names](mapping-canonical-property-names-to-mapi-names.md).</span></span> <span data-ttu-id="65e00-144">若要查找 MAPI 属性与之关联的规范属性，请参阅[MapI Names to Canonical Property Names。](mapping-mapi-names-to-canonical-property-names.md)</span><span class="sxs-lookup"><span data-stu-id="65e00-144">To find the canonical property that a MAPI property is associated with, see [Mapping MAPI Names to Canonical Property Names](mapping-mapi-names-to-canonical-property-names.md).</span></span>
  
## <a name="mapi-support-of-canonical-property-names"></a><span data-ttu-id="65e00-145">对规范属性名称的 MAPI 支持</span><span class="sxs-lookup"><span data-stu-id="65e00-145">MAPI Support of Canonical Property Names</span></span>

<span data-ttu-id="65e00-146">由于规范属性不是真实属性，并且未在 MAPI 头文件中定义，因此不应在代码中使用规范属性名称;相反，你应该继续在代码中使用确切的 MAPI 属性名称。</span><span class="sxs-lookup"><span data-stu-id="65e00-146">Because canonical properties are not real properties and are not defined in MAPI header files, you should not use canonical property names in code; instead, you should continue to use the exact MAPI property names in code.</span></span> <span data-ttu-id="65e00-147">例如，可以将代码 **PR_BUSINESS2_TELEPHONE_NUMBER** **PidTagBusiness2TelephoneNumber** PR_OFFICE2_TELEPHONE_NUMBER代码外部的 PR_BUSINESS2_TELEPHONE_NUMBER 和 PR_OFFICE2_TELEPHONE_NUMBER 代码。  </span><span class="sxs-lookup"><span data-stu-id="65e00-147">For example, you can refer **PR_BUSINESS2_TELEPHONE_NUMBER** and **PR_OFFICE2_TELEPHONE_NUMBER** outside of code as **PidTagBusiness2TelephoneNumber**, and use either **PR_BUSINESS2_TELEPHONE_NUMBER** or **PR_OFFICE2_TELEPHONE_NUMBER** in code.</span></span> 
  
<span data-ttu-id="65e00-148">如果您必须在代码中使用规范属性名称，则必须先在您自己的头文件中定义它们。</span><span class="sxs-lookup"><span data-stu-id="65e00-148">If you must use canonical property names in your code, you must first define them in your own header files.</span></span>
  
## <a name="canonical-property-names-and-exchange-protocol-specifications"></a><span data-ttu-id="65e00-149">规范属性名称和Exchange协议规范</span><span class="sxs-lookup"><span data-stu-id="65e00-149">Canonical Property Names and Exchange Protocol Specifications</span></span>

<span data-ttu-id="65e00-150">规范名称在 Microsoft Exchange Server协议规范中引用，Exchange Server用于与其他 Microsoft 产品进行通信。</span><span class="sxs-lookup"><span data-stu-id="65e00-150">Canonical names are referenced in Microsoft Exchange Server protocol specifications that are used by Exchange Server to communicate with other Microsoft products.</span></span> <span data-ttu-id="65e00-151">有关由协议规范引用的邮件对象Exchange，请参阅[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="65e00-151">For more information about message object properties referenced by Exchange protocol specifications, see [[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="65e00-152">另请参阅</span><span class="sxs-lookup"><span data-stu-id="65e00-152">See also</span></span>



[<span data-ttu-id="65e00-153">MAPI 属性标记</span><span class="sxs-lookup"><span data-stu-id="65e00-153">MAPI Property Tags</span></span>](mapi-property-tags.md)
  
[<span data-ttu-id="65e00-154">MAPI 属性标识符概述</span><span class="sxs-lookup"><span data-stu-id="65e00-154">MAPI Property Identifier Overview</span></span>](mapi-property-identifier-overview.md)
  
[<span data-ttu-id="65e00-155">MAPI 属性类型概述</span><span class="sxs-lookup"><span data-stu-id="65e00-155">MAPI Property Type Overview</span></span>](mapi-property-type-overview.md)

