---
title: 属性名称和属性集
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: cb216f5c-c965-4372-a15b-82090a410266
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: fa9d6afcaf1b360f37e8c8873c9d1a823fcd4888
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32328544"
---
# <a name="property-names-and-property-sets"></a><span data-ttu-id="d1bf4-103">属性名称和属性集</span><span class="sxs-lookup"><span data-stu-id="d1bf4-103">Property Names and Property Sets</span></span>

  
  
<span data-ttu-id="d1bf4-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d1bf4-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d1bf4-105">每个命名属性的名称包含两个部分:</span><span class="sxs-lookup"><span data-stu-id="d1bf4-105">The name of every named property has two parts:</span></span>
  
- <span data-ttu-id="d1bf4-106">指定属性集的全局唯一标识符 (即 GUID)。</span><span class="sxs-lookup"><span data-stu-id="d1bf4-106">A globally unique identifier, or GUID, that specifies a property set.</span></span>
    
- <span data-ttu-id="d1bf4-107">一个 Unicode 字符字符串或32位数字值。</span><span class="sxs-lookup"><span data-stu-id="d1bf4-107">A Unicode character string or 32-bit numeric value.</span></span> 
    
<span data-ttu-id="d1bf4-108">命名属性的名称使用[MAPINAMEID](mapinameid.md)结构进行描述。</span><span class="sxs-lookup"><span data-stu-id="d1bf4-108">Names of named properties are described using a [MAPINAMEID](mapinameid.md) structure.</span></span> <span data-ttu-id="d1bf4-109">此结构包含一个属性集成员、用于指定数字或字符串格式的名称的成员, 以及用于标识所使用的格式的成员。</span><span class="sxs-lookup"><span data-stu-id="d1bf4-109">This structure contains a property set member, a member for specifying the name in either numeric or string format, and a member for identifying which format is used.</span></span> <span data-ttu-id="d1bf4-110">由于属性集是属性名称的一部分, 因此它不是可选的。</span><span class="sxs-lookup"><span data-stu-id="d1bf4-110">Because the property set is part of the property's name, it is not optional.</span></span> <span data-ttu-id="d1bf4-111">MAPI 定义了多个用于客户端和服务提供程序的属性集, 但如果现有属性集不合适, 则可以定义新的属性集。</span><span class="sxs-lookup"><span data-stu-id="d1bf4-111">MAPI has defined several property sets for use by clients and service providers, but if an existing property set is inappropriate, a new property set can be defined.</span></span> <span data-ttu-id="d1bf4-112">客户端和服务提供程序可以通过调用[CoCreateGUID](https://msdn.microsoft.com/library/ms688568.aspx)函数来定义其自己的属性集。</span><span class="sxs-lookup"><span data-stu-id="d1bf4-112">Clients and service providers can define their own property sets by calling [CoCreateGUID](https://msdn.microsoft.com/library/ms688568.aspx) function.</span></span> <span data-ttu-id="d1bf4-113">通常, 这些属性集是为自定义客户端应用程序创建的。</span><span class="sxs-lookup"><span data-stu-id="d1bf4-113">Typically these property sets are created for custom client applications.</span></span> 
  
<span data-ttu-id="d1bf4-114">MAPI 的属性集由下列常量表示:</span><span class="sxs-lookup"><span data-stu-id="d1bf4-114">MAPI's property sets are represented by the following constants:</span></span>
  
<span data-ttu-id="d1bf4-115">PS_MAPI</span><span class="sxs-lookup"><span data-stu-id="d1bf4-115">PS_MAPI</span></span>
  
<span data-ttu-id="d1bf4-116">PS_PUBLIC_STRINGS</span><span class="sxs-lookup"><span data-stu-id="d1bf4-116">PS_PUBLIC_STRINGS</span></span>
  
<span data-ttu-id="d1bf4-117">PS_ROUTING_EMAIL_ADDRESSES</span><span class="sxs-lookup"><span data-stu-id="d1bf4-117">PS_ROUTING_EMAIL_ADDRESSES</span></span>
  
<span data-ttu-id="d1bf4-118">PS_ROUTING_ADDRTYPE</span><span class="sxs-lookup"><span data-stu-id="d1bf4-118">PS_ROUTING_ADDRTYPE</span></span>
  
<span data-ttu-id="d1bf4-119">PS_ROUTING_SEARCH_KEY</span><span class="sxs-lookup"><span data-stu-id="d1bf4-119">PS_ROUTING_SEARCH_KEY</span></span>
  
<span data-ttu-id="d1bf4-120">PS_ROUTING_DISPLAY_NAME</span><span class="sxs-lookup"><span data-stu-id="d1bf4-120">PS_ROUTING_DISPLAY_NAME</span></span>
  
<span data-ttu-id="d1bf4-121">PS_ROUTING_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="d1bf4-121">PS_ROUTING_ENTRYID</span></span>
  
<span data-ttu-id="d1bf4-122">PS_MAPI 属性集是保留的;服务提供程序使用它为具有命名属性范围下的标识符的属性生成名称。</span><span class="sxs-lookup"><span data-stu-id="d1bf4-122">The PS_MAPI property set is reserved; it is used by service providers to generate names for properties with identifiers below the named property range.</span></span> <span data-ttu-id="d1bf4-123">PS_PUBLIC_STRINGS 属性集由客户端用于 IPM 邮件的命名属性。</span><span class="sxs-lookup"><span data-stu-id="d1bf4-123">The PS_PUBLIC_STRINGS property set is used by clients for named properties of IPM messages.</span></span> <span data-ttu-id="d1bf4-124">由于 PS_PUBLIC_STRINGS 属性集中的命名属性将出现在客户端的用户界面中, 因此 nonvisible 邮件 (如属于 IPC 邮件类的邮件) 应避免使用此属性集创建命名属性。</span><span class="sxs-lookup"><span data-stu-id="d1bf4-124">Because named properties in the PS_PUBLIC_STRINGS property set appear in a client's user interface, nonvisible messages such as those that belong to the IPC message class should avoid creating named properties with this property set.</span></span> <span data-ttu-id="d1bf4-125">相反, 它们应在特定于邮件类别的范围 (0x6800 到 0x7FFF) 中创建属性。</span><span class="sxs-lookup"><span data-stu-id="d1bf4-125">Instead, they should create properties in the message class-specific range, 0x6800 through 0x7FFF.</span></span>
  
<span data-ttu-id="d1bf4-126">其他属性集保留了描述通常是路由列表成员的收件人的命名属性。</span><span class="sxs-lookup"><span data-stu-id="d1bf4-126">The other property sets hold named properties describing recipients that are typically members of a routing list.</span></span> <span data-ttu-id="d1bf4-127">包含与收件人列表属性相关联的属性的相同类型的信息, 网关将理解这些属性集中的属性, 以要求对目标邮件系统进行映射。</span><span class="sxs-lookup"><span data-stu-id="d1bf4-127">Containing the same type of information as the properties that are associated with recipient list properties, properties in these property sets are understood by gateways to require mapping for a target messaging system.</span></span> <span data-ttu-id="d1bf4-128">由于有五种类型的信息可用于描述属性, 因此 MAPI 定义了五个不同的属性集。</span><span class="sxs-lookup"><span data-stu-id="d1bf4-128">Because there are five types of information for describing properties, MAPI has defined five different property sets.</span></span> <span data-ttu-id="d1bf4-129">发送邮件时, 如果客户端发送的邮件必须包含其路由列表成员的地址和地址类型, 则为 PS_ROUTING_EMAIL_ADDRESSES 和 PS_ROUTING_ADDRTYPE 属性集中的每个成员分配一个命名属性。</span><span class="sxs-lookup"><span data-stu-id="d1bf4-129">A client sending a message that must include an address and address type for its routing list members assigns a named property for each member in the PS_ROUTING_EMAIL_ADDRESSES and PS_ROUTING_ADDRTYPE property sets.</span></span> <span data-ttu-id="d1bf4-130">这样可确保地址和地址类型在发送到外部邮件系统时仍然可用。</span><span class="sxs-lookup"><span data-stu-id="d1bf4-130">This ensures that the address and address type remain viable when sent to a foreign messaging system.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d1bf4-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d1bf4-131">See also</span></span>



[<span data-ttu-id="d1bf4-132">MAPI 命名属性</span><span class="sxs-lookup"><span data-stu-id="d1bf4-132">MAPI Named Properties</span></span>](mapi-named-properties.md)

