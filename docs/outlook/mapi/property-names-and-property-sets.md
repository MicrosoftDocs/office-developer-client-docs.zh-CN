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
# <a name="property-names-and-property-sets"></a><span data-ttu-id="3da4e-103">属性名称和属性集</span><span class="sxs-lookup"><span data-stu-id="3da4e-103">Property Names and Property Sets</span></span>

  
  
<span data-ttu-id="3da4e-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="3da4e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="3da4e-105">每个命名属性的名称都有两个部分：</span><span class="sxs-lookup"><span data-stu-id="3da4e-105">The name of every named property has two parts:</span></span>
  
- <span data-ttu-id="3da4e-106">用于指定属性集的全局唯一标识符或 GUID。</span><span class="sxs-lookup"><span data-stu-id="3da4e-106">A globally unique identifier, or GUID, that specifies a property set.</span></span>
    
- <span data-ttu-id="3da4e-107">Unicode 字符字符串或 32 位数值。</span><span class="sxs-lookup"><span data-stu-id="3da4e-107">A Unicode character string or 32-bit numeric value.</span></span> 
    
<span data-ttu-id="3da4e-108">命名属性的名称使用 [MAPINAMEID](mapinameid.md) 结构进行描述。</span><span class="sxs-lookup"><span data-stu-id="3da4e-108">Names of named properties are described using a [MAPINAMEID](mapinameid.md) structure.</span></span> <span data-ttu-id="3da4e-109">此结构包含一个属性集成员、一个以数字或字符串格式指定名称的成员，以及一个用来标识使用哪种格式的成员。</span><span class="sxs-lookup"><span data-stu-id="3da4e-109">This structure contains a property set member, a member for specifying the name in either numeric or string format, and a member for identifying which format is used.</span></span> <span data-ttu-id="3da4e-110">由于属性集是属性名称的一部分，因此不是可选的。</span><span class="sxs-lookup"><span data-stu-id="3da4e-110">Because the property set is part of the property's name, it is not optional.</span></span> <span data-ttu-id="3da4e-111">MAPI 定义了多个供客户端和服务提供商使用的属性集，但如果现有的属性集不合适，可以定义新的属性集。</span><span class="sxs-lookup"><span data-stu-id="3da4e-111">MAPI has defined several property sets for use by clients and service providers, but if an existing property set is inappropriate, a new property set can be defined.</span></span> <span data-ttu-id="3da4e-112">客户端和服务提供商可以通过调用 [CoCreateGUID](https://msdn.microsoft.com/library/ms688568.aspx) 函数定义自己的属性集。</span><span class="sxs-lookup"><span data-stu-id="3da4e-112">Clients and service providers can define their own property sets by calling [CoCreateGUID](https://msdn.microsoft.com/library/ms688568.aspx) function.</span></span> <span data-ttu-id="3da4e-113">通常，为自定义客户端应用程序创建这些属性集。</span><span class="sxs-lookup"><span data-stu-id="3da4e-113">Typically these property sets are created for custom client applications.</span></span> 
  
<span data-ttu-id="3da4e-114">MAPI 的属性集由以下常量表示：</span><span class="sxs-lookup"><span data-stu-id="3da4e-114">MAPI's property sets are represented by the following constants:</span></span>
  
<span data-ttu-id="3da4e-115">PS_MAPI</span><span class="sxs-lookup"><span data-stu-id="3da4e-115">PS_MAPI</span></span>
  
<span data-ttu-id="3da4e-116">PS_PUBLIC_STRINGS</span><span class="sxs-lookup"><span data-stu-id="3da4e-116">PS_PUBLIC_STRINGS</span></span>
  
<span data-ttu-id="3da4e-117">PS_ROUTING_EMAIL_ADDRESSES</span><span class="sxs-lookup"><span data-stu-id="3da4e-117">PS_ROUTING_EMAIL_ADDRESSES</span></span>
  
<span data-ttu-id="3da4e-118">PS_ROUTING_ADDRTYPE</span><span class="sxs-lookup"><span data-stu-id="3da4e-118">PS_ROUTING_ADDRTYPE</span></span>
  
<span data-ttu-id="3da4e-119">PS_ROUTING_SEARCH_KEY</span><span class="sxs-lookup"><span data-stu-id="3da4e-119">PS_ROUTING_SEARCH_KEY</span></span>
  
<span data-ttu-id="3da4e-120">PS_ROUTING_DISPLAY_NAME</span><span class="sxs-lookup"><span data-stu-id="3da4e-120">PS_ROUTING_DISPLAY_NAME</span></span>
  
<span data-ttu-id="3da4e-121">PS_ROUTING_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="3da4e-121">PS_ROUTING_ENTRYID</span></span>
  
<span data-ttu-id="3da4e-122">保留PS_MAPI属性集;服务提供商使用此属性为标识符低于命名属性范围的属性生成名称。</span><span class="sxs-lookup"><span data-stu-id="3da4e-122">The PS_MAPI property set is reserved; it is used by service providers to generate names for properties with identifiers below the named property range.</span></span> <span data-ttu-id="3da4e-123">客户端PS_PUBLIC_STRINGS IPM 邮件的命名属性使用属性集。</span><span class="sxs-lookup"><span data-stu-id="3da4e-123">The PS_PUBLIC_STRINGS property set is used by clients for named properties of IPM messages.</span></span> <span data-ttu-id="3da4e-124">由于 PS_PUBLIC_STRINGS 属性集的命名属性显示在客户端的用户界面中，因此属于 IPC 邮件类的不可访问邮件（如那些属于 IPC 邮件类的邮件）应避免使用此属性集创建命名属性。</span><span class="sxs-lookup"><span data-stu-id="3da4e-124">Because named properties in the PS_PUBLIC_STRINGS property set appear in a client's user interface, nonvisible messages such as those that belong to the IPC message class should avoid creating named properties with this property set.</span></span> <span data-ttu-id="3da4e-125">相反，它们应在特定于邮件类的范围（从 0x6800 到 0x7FFF）内创建属性。</span><span class="sxs-lookup"><span data-stu-id="3da4e-125">Instead, they should create properties in the message class-specific range, 0x6800 through 0x7FFF.</span></span>
  
<span data-ttu-id="3da4e-126">其他属性设置用于描述通常是路由列表成员的收件人的命名属性。</span><span class="sxs-lookup"><span data-stu-id="3da4e-126">The other property sets hold named properties describing recipients that are typically members of a routing list.</span></span> <span data-ttu-id="3da4e-127">包含的信息类型与与收件人列表属性关联的属性相同，网关理解这些属性集内的属性，以要求映射目标邮件系统。</span><span class="sxs-lookup"><span data-stu-id="3da4e-127">Containing the same type of information as the properties that are associated with recipient list properties, properties in these property sets are understood by gateways to require mapping for a target messaging system.</span></span> <span data-ttu-id="3da4e-128">由于有五种类型的信息用于描述属性，MAPI 定义了五种不同的属性集。</span><span class="sxs-lookup"><span data-stu-id="3da4e-128">Because there are five types of information for describing properties, MAPI has defined five different property sets.</span></span> <span data-ttu-id="3da4e-129">发送必须为其路由列表成员包含地址和地址类型的邮件的客户端会为 PS_ROUTING_EMAIL_ADDRESSES 和 PS_ROUTING_ADDRTYPE 属性集的每个成员分配命名属性。</span><span class="sxs-lookup"><span data-stu-id="3da4e-129">A client sending a message that must include an address and address type for its routing list members assigns a named property for each member in the PS_ROUTING_EMAIL_ADDRESSES and PS_ROUTING_ADDRTYPE property sets.</span></span> <span data-ttu-id="3da4e-130">这可确保地址和地址类型在发送到外消息系统时保持可行。</span><span class="sxs-lookup"><span data-stu-id="3da4e-130">This ensures that the address and address type remain viable when sent to a foreign messaging system.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3da4e-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3da4e-131">See also</span></span>



[<span data-ttu-id="3da4e-132">MAPI 命名属性</span><span class="sxs-lookup"><span data-stu-id="3da4e-132">MAPI Named Properties</span></span>](mapi-named-properties.md)

