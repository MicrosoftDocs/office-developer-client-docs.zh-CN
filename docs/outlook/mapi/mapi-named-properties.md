---
title: MAPI 命名属性
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 464b1297-9d90-47bd-afc4-3dc63b106cb7
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 5a6ba7af5e497ba59b43e9b80cfc9595961ed10e
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22579541"
---
# <a name="mapi-named-properties"></a><span data-ttu-id="f592c-103">MAPI 命名属性</span><span class="sxs-lookup"><span data-stu-id="f592c-103">MAPI Named Properties</span></span>
 
<span data-ttu-id="f592c-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f592c-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f592c-105">MAPI 提供的工具，用于为属性分配名称、 将这些名称映射到唯一标识符，以及使此映射持久。</span><span class="sxs-lookup"><span data-stu-id="f592c-105">MAPI provides a facility for assigning names to properties, for mapping these names to unique identifiers, and for making this mapping persistent.</span></span> <span data-ttu-id="f592c-106">永久名称标识符映射到可确保跨会话保持有效属性名称。</span><span class="sxs-lookup"><span data-stu-id="f592c-106">Persistent name to identifier mapping ensures that property names remain valid across sessions.</span></span>
  
<span data-ttu-id="f592c-107">若要定义的命名的属性，客户端或服务提供程序构成一个名称，并将其存储在[MAPINAMEID](mapinameid.md)结构中。</span><span class="sxs-lookup"><span data-stu-id="f592c-107">To define a named property, a client or service provider makes up a name and stores it in a [MAPINAMEID](mapinameid.md) structure.</span></span> <span data-ttu-id="f592c-108">由于名称组成的 32 位的全局唯一标识符，或 GUID，以及任一 Unicode 字符字符串或数字值的命名属性的创建者可以创建有意义的名称，而不必担心重复。</span><span class="sxs-lookup"><span data-stu-id="f592c-108">Because names are made up of a 32-bit globally unique identifier, or GUID, and either a Unicode character string or numeric value, creators of named properties can create meaningful names without fear of duplication.</span></span> <span data-ttu-id="f592c-109">名称是唯一的而不考虑其标识符的值可以使用它们。</span><span class="sxs-lookup"><span data-stu-id="f592c-109">Names are unique and they can be used without regard to the value of their identifiers.</span></span> 
  
<span data-ttu-id="f592c-110">若要支持命名的属性，一个服务提供程序实现两种方法 — [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md)和[IMAPIProp::GetNamesFromIDs](imapiprop-getnamesfromids.md) — 名称和标识符之间翻译并允许其[IMAPIProp::GetProps](imapiprop-getprops.md) [IMAPIProp::SetProps](imapiprop-setprops.md)方法来检索和修改与命名的属性区域中的标识符的属性。</span><span class="sxs-lookup"><span data-stu-id="f592c-110">To support named properties, a service provider implements two methods — [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md) and [IMAPIProp::GetNamesFromIDs](imapiprop-getnamesfromids.md) — to translate between names and identifiers and to allow its [IMAPIProp::GetProps](imapiprop-getprops.md)[IMAPIProp::SetProps](imapiprop-setprops.md) methods to retrieve and modify properties with identifiers in the named property range.</span></span> <span data-ttu-id="f592c-111">命名的属性标识符的范围是 0x8000 和 0xFFFE 之间。</span><span class="sxs-lookup"><span data-stu-id="f592c-111">The range for named property identifiers is between 0x8000 and 0xFFFE.</span></span> 
  
<span data-ttu-id="f592c-112">实现**IMAPIProp**接口的任何对象才能支持命名的属性。</span><span class="sxs-lookup"><span data-stu-id="f592c-112">Any object that implements the **IMAPIProp** interface can support named properties.</span></span> <span data-ttu-id="f592c-113">通讯簿提供程序使其他提供程序复制到其容器和消息中的条目存储提供程序可用于创建任意消息类型需要提供此支持。</span><span class="sxs-lookup"><span data-stu-id="f592c-113">Address book providers that allow entries from other providers to be copied into their containers and message store providers that can be used to create arbitrary message types are required to supply this support.</span></span> <span data-ttu-id="f592c-114">它是所有其他服务提供程序选项。</span><span class="sxs-lookup"><span data-stu-id="f592c-114">It is an option for all other service providers.</span></span> <span data-ttu-id="f592c-115">提供程序不支持的命名属性返回 MAPI_E_NO_SUPPORT 从**GetIDsFromNames**和**GetNamesFromIDs**方法和拒绝**中设置的 0x8000 或更高版本，使其返回 MAPI_E_UNEXPECTED 标识符与任何属性SPropProblemarray**。</span><span class="sxs-lookup"><span data-stu-id="f592c-115">Providers that do not support named properties return MAPI_E_NO_SUPPORT from the **GetIDsFromNames** and **GetNamesFromIDs** methods and refuse to set any properties with identifiers of 0x8000 or greater, returning MAPI_E_UNEXPECTED in the **SPropProblemarray**.</span></span>
  
<span data-ttu-id="f592c-116">创建属性的名称是一种方法的客户端可以定义为现有或自定义邮件类的新属性。</span><span class="sxs-lookup"><span data-stu-id="f592c-116">Creating names for properties is one way for clients to define new properties for existing or custom message classes.</span></span> <span data-ttu-id="f592c-117">服务提供商可以使用命名的属性公开其邮件系统的独特功能。</span><span class="sxs-lookup"><span data-stu-id="f592c-117">Service providers can use named properties to expose unique features of their messaging systems.</span></span> <span data-ttu-id="f592c-118">尚未命名属性的另一个用于旨在提供用小于 0x8000 标识符属性中引用的另一种方法。</span><span class="sxs-lookup"><span data-stu-id="f592c-118">Yet another use for named properties is to provide an alternate way of referring to properties with identifiers below 0x8000.</span></span> 
  
<span data-ttu-id="f592c-119">例如，客户端无法使用类似于下面的代码的代码检索所有对象的命名属性的名称：</span><span class="sxs-lookup"><span data-stu-id="f592c-119">For example, a client could use code similar to the following code to retrieve the names for all of an object's named properties:</span></span>
  
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

<span data-ttu-id="f592c-120">要从 PS_PUBLIC_STRINGS 属性集申请所有名称，客户端将如下所示替换 PS_PUBLIC_STRINGS 的属性集参数中的 NULL:</span><span class="sxs-lookup"><span data-stu-id="f592c-120">To request all names from the PS_PUBLIC_STRINGS property set, a client would replace the NULL in the property set parameter to PS_PUBLIC_STRINGS as follows:</span></span> 
  
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

## <a name="see-also"></a><span data-ttu-id="f592c-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f592c-121">See also</span></span>

- [<span data-ttu-id="f592c-122">MAPI 属性概述</span><span class="sxs-lookup"><span data-stu-id="f592c-122">MAPI Property Overview</span></span>](mapi-property-overview.md)

