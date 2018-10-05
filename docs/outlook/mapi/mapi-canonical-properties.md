---
title: MAPI 规范属性
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 29151beb-7436-401a-8072-58d4facd8458
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 4b017089a675727703de9e2ed4d584e7f77a778a
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25401564"
---
# <a name="mapi-canonical-properties"></a><span data-ttu-id="51251-103">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="51251-103">MAPI Canonical Properties</span></span>

  
  
<span data-ttu-id="51251-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="51251-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="51251-105">规范属性是一个虚拟属性表示的 MAPI 属性或定义具有相同属性标识符的多个 MAPI 属性。</span><span class="sxs-lookup"><span data-stu-id="51251-105">A canonical property is a virtual property that represents a MAPI property, or multiple MAPI properties defined with the same property identifier.</span></span> <span data-ttu-id="51251-106">规范属性仅用于加快一致的 MAPI 属性讨论或代码之外的文档中的标识。</span><span class="sxs-lookup"><span data-stu-id="51251-106">Canonical properties are only intended to facilitate consistent identification of MAPI properties in discussions or documentation outside of code.</span></span> <span data-ttu-id="51251-107">与 MAPI 定义已标记的属性名称不同规范属性名称不被指 MAPI 头文件中的全局常量。</span><span class="sxs-lookup"><span data-stu-id="51251-107">Unlike MAPI-defined tagged property names, canonical property names are not defined as global constants in MAPI header files.</span></span>
  
## <a name="naming-conventions"></a><span data-ttu-id="51251-108">命名约定</span><span class="sxs-lookup"><span data-stu-id="51251-108">Naming Conventions</span></span>

<span data-ttu-id="51251-109">属性规范名称开头前缀，"Pid"，表示"属性标识符"。</span><span class="sxs-lookup"><span data-stu-id="51251-109">Canonical property names begin with a prefix, "Pid", which represents "property identifier."</span></span> <span data-ttu-id="51251-110">根据属性是否已标记的属性、 的数字标识符的命名的属性或与字符串名称的命名的属性，前缀进一步限定"PidTag，"作为"PidLid，"和"PidName"分别。</span><span class="sxs-lookup"><span data-stu-id="51251-110">Depending on whether the property is a tagged property, a named property with a numerical identifier, or a named property with a string name, the prefix is further qualified as "PidTag," "PidLid," and "PidName" respectively.</span></span> <span data-ttu-id="51251-111">例如， [PidTagAccount](pidtagaccount-canonical-property.md)表示标记的属性，指定收件人的**PR_ACCOUNT** ([PidTagAccount](pidtagaccount-canonical-property.md))、 **PR_ACCOUNT_A** ([PidTagAccount](pidtagaccount-canonical-property.md)) 和**PR_ACCOUNT_W** ([PidTagAccount](pidtagaccount-canonical-property.md))帐户名;[PidLidContacts](pidlidcontacts-canonical-property.md)代表**dispidContacts**属性，具有的数字标识符，并指定一条消息; 相关联的联系人的名称的命名属性[PidNamePhishingStamp](pidnamephishingstamp-canonical-property.md)表示"https://schemas.microsoft.com/outlook/phishingstamp，"了字符串的名称，并将会出现网络钓鱼邮件标记的字符串指定的命名的属性。</span><span class="sxs-lookup"><span data-stu-id="51251-111">For example, [PidTagAccount](pidtagaccount-canonical-property.md) represents the tagged properties, **PR_ACCOUNT** ([PidTagAccount](pidtagaccount-canonical-property.md)), **PR_ACCOUNT_A** ([PidTagAccount](pidtagaccount-canonical-property.md)), and **PR_ACCOUNT_W** ([PidTagAccount](pidtagaccount-canonical-property.md)), that specify a recipient's account name; [PidLidContacts](pidlidcontacts-canonical-property.md) represents the **dispidContacts** property, a named property that has a numerical identifier and that specifies the name of contacts associated with a message; and [PidNamePhishingStamp](pidnamephishingstamp-canonical-property.md) represents "https://schemas.microsoft.com/outlook/phishingstamp," a named property that has a string name, and that specifies the string marking messages that are likely to be phishing.</span></span> 
  
## <a name="representing-similar-properties-using-one-canonical-property"></a><span data-ttu-id="51251-112">表示使用一个规范属性类似属性</span><span class="sxs-lookup"><span data-stu-id="51251-112">Representing Similar Properties Using One Canonical Property</span></span>

### <a name="identifying-properties-in-mapi"></a><span data-ttu-id="51251-113">MAPI 中的标识属性</span><span class="sxs-lookup"><span data-stu-id="51251-113">Identifying Properties in MAPI</span></span>

<span data-ttu-id="51251-114">由标识符，它是无符号的 16 位值标识 MAPI 中的所有属性。</span><span class="sxs-lookup"><span data-stu-id="51251-114">All properties in MAPI are identified by a property identifier that is an unsigned 16-bit value.</span></span> <span data-ttu-id="51251-115">属性标识符和属性类型 （另一个无符号 16 位值） 组成的属性的属性标记。</span><span class="sxs-lookup"><span data-stu-id="51251-115">The property identifier and the property type (another unsigned 16-bit value) constitute a property tag for the property.</span></span> 
  
<span data-ttu-id="51251-116">MAPI 使用属性标记来唯一定义属性。</span><span class="sxs-lookup"><span data-stu-id="51251-116">MAPI uses a property tag to uniquely define properties.</span></span> <span data-ttu-id="51251-117">具有相同的属性标记，如**PR_BUSINESS2_TELEPHONE_NUMBER** ([PidTagBusiness2TelephoneNumber](pidtagbusiness2telephonenumber-canonical-property.md)) 和**PR_OFFICE2_TELEPHONE_NUMBER** ([PidTagBusiness2TelephoneNumber](pidtagbusiness2telephonenumber-canonical-property.md)) 的属性被视为相同MAPI 中的属性。</span><span class="sxs-lookup"><span data-stu-id="51251-117">Properties that have the same property tag, like **PR_BUSINESS2_TELEPHONE_NUMBER** ([PidTagBusiness2TelephoneNumber](pidtagbusiness2telephonenumber-canonical-property.md)) and **PR_OFFICE2_TELEPHONE_NUMBER** ([PidTagBusiness2TelephoneNumber](pidtagbusiness2telephonenumber-canonical-property.md)), are considered identical properties in MAPI.</span></span> <span data-ttu-id="51251-118">自己属性定义了 MAPI 的属性标记的列表，请参阅 Mapitags.h 的 MAPI 头文件。</span><span class="sxs-lookup"><span data-stu-id="51251-118">For a list of property tags that MAPI has defined for its own properties, see the MAPI header file, Mapitags.h.</span></span>
  
<span data-ttu-id="51251-119">请注意，MAPI 将分为范围的属性标识符。</span><span class="sxs-lookup"><span data-stu-id="51251-119">Note that MAPI divides property identifiers into ranges.</span></span> <span data-ttu-id="51251-120">标识符属于范围中的其中指示其使用情况和所有权。</span><span class="sxs-lookup"><span data-stu-id="51251-120">Where an identifier falls in the range indicates its use and ownership.</span></span> <span data-ttu-id="51251-121">0x0001 到 0x7FFF 范围中属于标记属性的属性的标识符。</span><span class="sxs-lookup"><span data-stu-id="51251-121">The property identifiers of tagged properties fall in the range of 0x0001 to 0x7FFF.</span></span> <span data-ttu-id="51251-122">在此范围内是 MAPI 定义的属性，其 0x0001 到 0x3FFF 的范围的属性的标识符。</span><span class="sxs-lookup"><span data-stu-id="51251-122">Within this range are the property identifiers of MAPI-defined properties, which fall in the range of 0x0001 to 0x3FFF.</span></span> <span data-ttu-id="51251-123">命名的属性某范围中从 0x8000 到 0x8FFF 属性标识符。</span><span class="sxs-lookup"><span data-stu-id="51251-123">The property identifiers of named properties fall in the range from 0x8000 to 0x8FFF.</span></span> 
  
<span data-ttu-id="51251-124">命名的属性此外特性的属性集，以及长 ID （盖），这是一个无符号的 32 位值或字符串。</span><span class="sxs-lookup"><span data-stu-id="51251-124">Named properties are additionally attributed by a property set, and either a long ID (LID), which is an unsigned 32-bit value, or a string.</span></span> <span data-ttu-id="51251-125">属性集是一组命名属性标识与用途相似的 GUID。</span><span class="sxs-lookup"><span data-stu-id="51251-125">A property set is a GUID that identifies a group of named properties with a similar purpose.</span></span> <span data-ttu-id="51251-126">属性集和盖或字符串的名称用于获取或设置的命名的属性。</span><span class="sxs-lookup"><span data-stu-id="51251-126">The property set and LID or string name are used to get or set the named property.</span></span>
  
### <a name="property-type"></a><span data-ttu-id="51251-127">属性类型</span><span class="sxs-lookup"><span data-stu-id="51251-127">Property Type</span></span>

<span data-ttu-id="51251-128">除了标识符，通过指定允许该属性的值的类型的数据类型归功属性。</span><span class="sxs-lookup"><span data-stu-id="51251-128">Aside from identifiers, a property is attributed by a data type that specifies the type of values allowed for that property.</span></span>
  
<span data-ttu-id="51251-129">属性的 string 类型，具体取决于 Unicode 基础平台中, 支持的属性可以是类型 PT_STRING8 （null 结尾的 8 位字符的字符串） 或 PT_UNICODE （null 结尾的 Unicode 字符串）。</span><span class="sxs-lookup"><span data-stu-id="51251-129">For properties that are of the string type, depending on the support for Unicode in the underlying platform, the property can be of type PT_STRING8 (null-terminated 8-bit character string) or PT_UNICODE (null-terminated Unicode string).</span></span> <span data-ttu-id="51251-130">可以使用 PT_TSTRING 类型、 定义的属性，并且根据编译设置 PT_TSTRING 默认为支持 Unicode，平台的 Unicode 字符串或 ANSI 或 DBCS 支持的平台 PT_STRING8 字符串。</span><span class="sxs-lookup"><span data-stu-id="51251-130">A property can be defined with the PT_TSTRING type, and depending on compilation settings, PT_TSTRING defaults to a Unicode string for platforms that support Unicode, or to a PT_STRING8 string for platforms that support ANSI or DBCS.</span></span> <span data-ttu-id="51251-131">很常见，字符串类型的属性是由三个类似的名称，例如**PR_ACCOUNT**、 **PR_ACCOUNT_A**和**PR_ACCOUNT_W**，这些类型的选项均进行 PT_TSTRING、 PT_STRING8 和 PT_UNICODE 分别。</span><span class="sxs-lookup"><span data-stu-id="51251-131">It is common that a string-typed property is identified by three similar names, such as **PR_ACCOUNT**, **PR_ACCOUNT_A**, and **PR_ACCOUNT_W**, which are of the type PT_TSTRING, PT_STRING8, and PT_UNICODE respectively.</span></span>
  
<span data-ttu-id="51251-132">属性类型和宏与类型相关的详细信息，请参阅 Mapidefs.h 的 MAPI 头文件。</span><span class="sxs-lookup"><span data-stu-id="51251-132">For more information on property types and macros related to types, see the MAPI header file, Mapidefs.h.</span></span>
  
### <a name="identifying-similar-properties"></a><span data-ttu-id="51251-133">标识类似属性</span><span class="sxs-lookup"><span data-stu-id="51251-133">Identifying Similar Properties</span></span>

<span data-ttu-id="51251-134">在当前的 MAPI 属性横向，不中查找已在不同的属性名称，所有这些都具有相同属性标识符已定义下公开这些属性。</span><span class="sxs-lookup"><span data-stu-id="51251-134">In the current MAPI property landscape, it is not uncommon to find that a property has been exposed under different property names, all of which are defined with the same property identifier.</span></span> <span data-ttu-id="51251-135">例如，已标记的属性， **PR_BUSINESS2_TELEPHONE_NUMBER**和**PR_OFFICE2_TELEPHONE_NUMBER**，Mapitags.h 具有的相同属性标识符和类型中定义。</span><span class="sxs-lookup"><span data-stu-id="51251-135">For example, the tagged properties, **PR_BUSINESS2_TELEPHONE_NUMBER** and **PR_OFFICE2_TELEPHONE_NUMBER**, are defined in Mapitags.h to have the same property identifier and type.</span></span> <span data-ttu-id="51251-136">紧密相关这两个属性：</span><span class="sxs-lookup"><span data-stu-id="51251-136">Closely related to these two properties are:</span></span>
  
- <span data-ttu-id="51251-137">**PR_BUSINESS2_TELEPHONE_NUMBER_A**</span><span class="sxs-lookup"><span data-stu-id="51251-137">**PR_BUSINESS2_TELEPHONE_NUMBER_A**</span></span>
    
- <span data-ttu-id="51251-138">**PR_BUSINESS2_TELEPHONE_NUMBER_W**</span><span class="sxs-lookup"><span data-stu-id="51251-138">**PR_BUSINESS2_TELEPHONE_NUMBER_W**</span></span>
    
- <span data-ttu-id="51251-139">**PR_OFFICE2_TELEPHONE_NUMBER_A**</span><span class="sxs-lookup"><span data-stu-id="51251-139">**PR_OFFICE2_TELEPHONE_NUMBER_A**</span></span>
    
- <span data-ttu-id="51251-140">**PR_OFFICE2_TELEPHONE_NUMBER_W**</span><span class="sxs-lookup"><span data-stu-id="51251-140">**PR_OFFICE2_TELEPHONE_NUMBER_W**</span></span>
    
<span data-ttu-id="51251-141">与"_A"后缀的属性的类型为 PT_STRING8，并具有"_W"后缀的类型为 PT_UNICODE。</span><span class="sxs-lookup"><span data-stu-id="51251-141">The properties with the "_A" suffix are typed as PT_STRING8, and those with the "_W" suffix are typed as PT_UNICODE.</span></span>
  
<span data-ttu-id="51251-142">规范属性，在此示例中， **PidTagBusiness2TelephoneNumber**的目的是为了方便引用使用一个标识符，此类紧密附属的 MAPI 属性和中跨所有 MAPI 以一致方式 （使用"Pid"前缀）属性。</span><span class="sxs-lookup"><span data-stu-id="51251-142">The purpose of a canonical property, **PidTagBusiness2TelephoneNumber** in this example, is to facilitate referencing such closely affiliated MAPI properties using one identifier, and in a consistent way (using the "Pid" prefix) across all MAPI properties.</span></span> <span data-ttu-id="51251-143">若要查找的实际规范属性表示的 MAPI 属性，请参阅[到 MAPI 名称映射规范属性名称](mapping-canonical-property-names-to-mapi-names.md)。</span><span class="sxs-lookup"><span data-stu-id="51251-143">To find which real MAPI properties a canonical property represents, see [Mapping Canonical Property Names to MAPI Names](mapping-canonical-property-names-to-mapi-names.md).</span></span> <span data-ttu-id="51251-144">若要查找与 MAPI 属性关联的规范属性，请参阅[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)。</span><span class="sxs-lookup"><span data-stu-id="51251-144">To find the canonical property that a MAPI property is associated with, see [Mapping MAPI Names to Canonical Property Names](mapping-mapi-names-to-canonical-property-names.md).</span></span>
  
## <a name="mapi-support-of-canonical-property-names"></a><span data-ttu-id="51251-145">MAPI 的属性规范名称的支持</span><span class="sxs-lookup"><span data-stu-id="51251-145">MAPI Support of Canonical Property Names</span></span>

<span data-ttu-id="51251-146">因为规范属性不是真实属性，并且未定义 MAPI 头文件中，不应在代码中; 使用规范属性名称相反，您应继续在代码中使用的确切的 MAPI 属性名。</span><span class="sxs-lookup"><span data-stu-id="51251-146">Because canonical properties are not real properties and are not defined in MAPI header files, you should not use canonical property names in code; instead, you should continue to use the exact MAPI property names in code.</span></span> <span data-ttu-id="51251-147">例如，可以为**PidTagBusiness2TelephoneNumber**，代码之外，请参阅**PR_BUSINESS2_TELEPHONE_NUMBER**和**PR_OFFICE2_TELEPHONE_NUMBER**并使用**PR_BUSINESS2_TELEPHONE_NUMBER**或**PR_OFFICE2_TELEPHONE_NUMBER**在代码中。</span><span class="sxs-lookup"><span data-stu-id="51251-147">For example, you can refer **PR_BUSINESS2_TELEPHONE_NUMBER** and **PR_OFFICE2_TELEPHONE_NUMBER** outside of code as **PidTagBusiness2TelephoneNumber**, and use either **PR_BUSINESS2_TELEPHONE_NUMBER** or **PR_OFFICE2_TELEPHONE_NUMBER** in code.</span></span> 
  
<span data-ttu-id="51251-148">如果您必须在代码中使用规范属性名称，因此您必须首先在您自己的头文件中定义它们。</span><span class="sxs-lookup"><span data-stu-id="51251-148">If you must use canonical property names in your code, you must first define them in your own header files.</span></span>
  
## <a name="canonical-property-names-and-exchange-protocol-specifications"></a><span data-ttu-id="51251-149">规范属性名称和 Exchange 协议规范</span><span class="sxs-lookup"><span data-stu-id="51251-149">Canonical Property Names and Exchange Protocol Specifications</span></span>

<span data-ttu-id="51251-150">规范名称中使用 Exchange Server 与其他 Microsoft 产品进行通信的 Microsoft Exchange Server 协议规范引用。</span><span class="sxs-lookup"><span data-stu-id="51251-150">Canonical names are referenced in Microsoft Exchange Server protocol specifications that are used by Exchange Server to communicate with other Microsoft products.</span></span> <span data-ttu-id="51251-151">有关 Exchange 协议规范所引用的消息对象属性的详细信息，请参阅[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="51251-151">For more information about message object properties referenced by Exchange protocol specifications, see [[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="51251-152">另请参阅</span><span class="sxs-lookup"><span data-stu-id="51251-152">See also</span></span>



[<span data-ttu-id="51251-153">MAPI 属性标记</span><span class="sxs-lookup"><span data-stu-id="51251-153">MAPI Property Tags</span></span>](mapi-property-tags.md)
  
[<span data-ttu-id="51251-154">MAPI 属性标识符概述</span><span class="sxs-lookup"><span data-stu-id="51251-154">MAPI Property Identifier Overview</span></span>](mapi-property-identifier-overview.md)
  
[<span data-ttu-id="51251-155">MAPI 属性类型概述</span><span class="sxs-lookup"><span data-stu-id="51251-155">MAPI Property Type Overview</span></span>](mapi-property-type-overview.md)

