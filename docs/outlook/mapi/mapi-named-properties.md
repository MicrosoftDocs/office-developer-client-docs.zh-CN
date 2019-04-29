---
title: MAPI 命名属性
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 464b1297-9d90-47bd-afc4-3dc63b106cb7
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: d83b98b4f06c648676852673a694a63b78f568b0
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435045"
---
# <a name="mapi-named-properties"></a><span data-ttu-id="f2add-103">MAPI 命名属性</span><span class="sxs-lookup"><span data-stu-id="f2add-103">MAPI Named Properties</span></span>
 
<span data-ttu-id="f2add-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f2add-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f2add-105">MAPI 提供了用于为属性分配名称、将这些名称映射为唯一标识符以及使此映射持久的功能。</span><span class="sxs-lookup"><span data-stu-id="f2add-105">MAPI provides a facility for assigning names to properties, for mapping these names to unique identifiers, and for making this mapping persistent.</span></span> <span data-ttu-id="f2add-106">标识符映射的永久名称可确保属性名称在会话中保持有效。</span><span class="sxs-lookup"><span data-stu-id="f2add-106">Persistent name to identifier mapping ensures that property names remain valid across sessions.</span></span>
  
<span data-ttu-id="f2add-107">若要定义命名属性, 客户端或服务提供程序构成了一个名称, 并将其存储在[MAPINAMEID](mapinameid.md)结构中。</span><span class="sxs-lookup"><span data-stu-id="f2add-107">To define a named property, a client or service provider makes up a name and stores it in a [MAPINAMEID](mapinameid.md) structure.</span></span> <span data-ttu-id="f2add-108">由于名称由32位全局唯一标识符 (即 GUID) 和 Unicode 字符字符串或数值组成, 因此命名属性的创建者可以创建有意义的名称, 而不会担心重复。</span><span class="sxs-lookup"><span data-stu-id="f2add-108">Because names are made up of a 32-bit globally unique identifier, or GUID, and either a Unicode character string or numeric value, creators of named properties can create meaningful names without fear of duplication.</span></span> <span data-ttu-id="f2add-109">名称是唯一的, 可以使用它们, 而无需考虑其标识符的值。</span><span class="sxs-lookup"><span data-stu-id="f2add-109">Names are unique and they can be used without regard to the value of their identifiers.</span></span> 
  
<span data-ttu-id="f2add-110">若要支持命名属性, 服务提供程序可实现两个方法 ( [IMAPIProp:: GetIDsFromNames](imapiprop-getidsfromnames.md)和[IMAPIProp:: GetNamesFromIDs](imapiprop-getnamesfromids.md) ), 以便在名称和标识符之间进行转换, 并允许其[IMAPIProp:: GetProps](imapiprop-getprops.md) [IMAPIProp:: SetProps](imapiprop-setprops.md)用于检索和修改命名属性范围中的标识符的属性的方法。</span><span class="sxs-lookup"><span data-stu-id="f2add-110">To support named properties, a service provider implements two methods — [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md) and [IMAPIProp::GetNamesFromIDs](imapiprop-getnamesfromids.md) — to translate between names and identifiers and to allow its [IMAPIProp::GetProps](imapiprop-getprops.md)[IMAPIProp::SetProps](imapiprop-setprops.md) methods to retrieve and modify properties with identifiers in the named property range.</span></span> <span data-ttu-id="f2add-111">命名属性标识符的范围介于0x8000 和0xFFFE 之间。</span><span class="sxs-lookup"><span data-stu-id="f2add-111">The range for named property identifiers is between 0x8000 and 0xFFFE.</span></span> 
  
<span data-ttu-id="f2add-112">任何实现**IMAPIProp**接口的对象都可以支持命名属性。</span><span class="sxs-lookup"><span data-stu-id="f2add-112">Any object that implements the **IMAPIProp** interface can support named properties.</span></span> <span data-ttu-id="f2add-113">需要将来自其他提供商的条目复制到其容器中的通讯簿提供程序和可用于创建任意邮件类型的邮件存储提供程序, 以提供此支持。</span><span class="sxs-lookup"><span data-stu-id="f2add-113">Address book providers that allow entries from other providers to be copied into their containers and message store providers that can be used to create arbitrary message types are required to supply this support.</span></span> <span data-ttu-id="f2add-114">对于所有其他服务提供程序, 都是一个选项。</span><span class="sxs-lookup"><span data-stu-id="f2add-114">It is an option for all other service providers.</span></span> <span data-ttu-id="f2add-115">不支持命名属性的提供程序从**GetIDsFromNames**和**GetNamesFromIDs**方法返回 MAPI_E_NO_SUPPORT, 并拒绝设置具有0x8000 或更高标识符的任何属性, 并返回 MAPI_E_UNEXPECTED 在**SPropProblemarray**。</span><span class="sxs-lookup"><span data-stu-id="f2add-115">Providers that do not support named properties return MAPI_E_NO_SUPPORT from the **GetIDsFromNames** and **GetNamesFromIDs** methods and refuse to set any properties with identifiers of 0x8000 or greater, returning MAPI_E_UNEXPECTED in the **SPropProblemarray**.</span></span>
  
<span data-ttu-id="f2add-116">为属性创建名称是客户端为现有或自定义邮件类别定义新属性的一种方法。</span><span class="sxs-lookup"><span data-stu-id="f2add-116">Creating names for properties is one way for clients to define new properties for existing or custom message classes.</span></span> <span data-ttu-id="f2add-117">服务提供程序可以使用命名属性来公开其邮件系统的独特功能。</span><span class="sxs-lookup"><span data-stu-id="f2add-117">Service providers can use named properties to expose unique features of their messaging systems.</span></span> <span data-ttu-id="f2add-118">另一种用于命名属性的方法是提供另一种方法, 用于引用小于0x8000 的标识符的属性。</span><span class="sxs-lookup"><span data-stu-id="f2add-118">Yet another use for named properties is to provide an alternate way of referring to properties with identifiers below 0x8000.</span></span> 
  
<span data-ttu-id="f2add-119">例如, 客户端可以使用与以下代码类似的代码检索对象的所有命名属性的名称:</span><span class="sxs-lookup"><span data-stu-id="f2add-119">For example, a client could use code similar to the following code to retrieve the names for all of an object's named properties:</span></span>
  
```cpp
LPSPropTagArray FAR *    lppPropTags = NULL;
LPGUID                   lpPropSetGuid = NULL;
ULONG FAR *              lpcPropNames;
LPMAPINAMEID FAR * FAR * lpppPropNames;
lpMAPIProp->GetNamesFromIDs (lppPropTags,
                             lpPropSetGuid,
                             0,
                             lpcPropNames,
                             lpppPropNames);
 
```

<span data-ttu-id="f2add-120">若要请求 PS_PUBLIC_STRINGS 属性集中的所有名称, 客户端会将属性集参数中的 NULL 替换为 PS_PUBLIC_STRINGS, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="f2add-120">To request all names from the PS_PUBLIC_STRINGS property set, a client would replace the NULL in the property set parameter to PS_PUBLIC_STRINGS as follows:</span></span> 
  
```cpp
LPSPropTagArray FAR *    lppPropTags = NULL;
LPGUID                   lpPropSetGuid = &PS_PUBLIC_STRINGS;
ULONG FAR *              lpcPropNames;
LPMAPINAMEID FAR * FAR * lpppPropNames;
lpMAPIProp->GetNamesFromIDs (lppPropTags,
                             lpPropSetGuid,
                             0,
                             lpcPropNames,
                             lpppPropNames);
 
```

## <a name="see-also"></a><span data-ttu-id="f2add-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f2add-121">See also</span></span>

- [<span data-ttu-id="f2add-122">MAPI 属性概述</span><span class="sxs-lookup"><span data-stu-id="f2add-122">MAPI Property Overview</span></span>](mapi-property-overview.md)

