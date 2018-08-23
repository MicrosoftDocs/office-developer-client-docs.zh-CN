---
title: 属性名称和属性集
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: cb216f5c-c965-4372-a15b-82090a410266
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 0272464d9a397f169b27aa15c80a17b49a3e9977
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22571827"
---
# <a name="property-names-and-property-sets"></a><span data-ttu-id="cce55-103">属性名称和属性集</span><span class="sxs-lookup"><span data-stu-id="cce55-103">Property Names and Property Sets</span></span>

  
  
<span data-ttu-id="cce55-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="cce55-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="cce55-105">每个命名属性的名称具有两个部分：</span><span class="sxs-lookup"><span data-stu-id="cce55-105">The name of every named property has two parts:</span></span>
  
- <span data-ttu-id="cce55-106">全局唯一标识符或用于指定属性集 GUID。</span><span class="sxs-lookup"><span data-stu-id="cce55-106">A globally unique identifier, or GUID, that specifies a property set.</span></span>
    
- <span data-ttu-id="cce55-107">Unicode 字符串或 32 位数字值。</span><span class="sxs-lookup"><span data-stu-id="cce55-107">A Unicode character string or 32-bit numeric value.</span></span> 
    
<span data-ttu-id="cce55-108">介绍了使用[MAPINAMEID](mapinameid.md)结构的命名属性的名称。</span><span class="sxs-lookup"><span data-stu-id="cce55-108">Names of named properties are described using a [MAPINAMEID](mapinameid.md) structure.</span></span> <span data-ttu-id="cce55-109">此结构包含属性集成员、 数字或字符串的格式，指定名称的成员和确定使用哪种格式的成员。</span><span class="sxs-lookup"><span data-stu-id="cce55-109">This structure contains a property set member, a member for specifying the name in either numeric or string format, and a member for identifying which format is used.</span></span> <span data-ttu-id="cce55-110">由于属性集的属性名称的一部分，它不是可选。</span><span class="sxs-lookup"><span data-stu-id="cce55-110">Because the property set is part of the property's name, it is not optional.</span></span> <span data-ttu-id="cce55-111">MAPI 定义了供客户端和服务提供商使用的多个属性集，但如果不合适现有属性集，可以定义一组新属性。</span><span class="sxs-lookup"><span data-stu-id="cce55-111">MAPI has defined several property sets for use by clients and service providers, but if an existing property set is inappropriate, a new property set can be defined.</span></span> <span data-ttu-id="cce55-112">客户端和服务提供商可以通过调用[CoCreateGUID](http://msdn.microsoft.com/en-us/library/ms688568.aspx)函数来定义自己的属性集。</span><span class="sxs-lookup"><span data-stu-id="cce55-112">Clients and service providers can define their own property sets by calling [CoCreateGUID](http://msdn.microsoft.com/en-us/library/ms688568.aspx) function.</span></span> <span data-ttu-id="cce55-113">通常这些属性集创建自定义客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="cce55-113">Typically these property sets are created for custom client applications.</span></span> 
  
<span data-ttu-id="cce55-114">MAPI 的属性集由以下常量表示：</span><span class="sxs-lookup"><span data-stu-id="cce55-114">MAPI's property sets are represented by the following constants:</span></span>
  
<span data-ttu-id="cce55-115">PS_MAPI</span><span class="sxs-lookup"><span data-stu-id="cce55-115">PS_MAPI</span></span>
  
<span data-ttu-id="cce55-116">PS_PUBLIC_STRINGS</span><span class="sxs-lookup"><span data-stu-id="cce55-116">PS_PUBLIC_STRINGS</span></span>
  
<span data-ttu-id="cce55-117">PS_ROUTING_EMAIL_ADDRESSES</span><span class="sxs-lookup"><span data-stu-id="cce55-117">PS_ROUTING_EMAIL_ADDRESSES</span></span>
  
<span data-ttu-id="cce55-118">PS_ROUTING_ADDRTYPE</span><span class="sxs-lookup"><span data-stu-id="cce55-118">PS_ROUTING_ADDRTYPE</span></span>
  
<span data-ttu-id="cce55-119">PS_ROUTING_SEARCH_KEY</span><span class="sxs-lookup"><span data-stu-id="cce55-119">PS_ROUTING_SEARCH_KEY</span></span>
  
<span data-ttu-id="cce55-120">PS_ROUTING_DISPLAY_NAME</span><span class="sxs-lookup"><span data-stu-id="cce55-120">PS_ROUTING_DISPLAY_NAME</span></span>
  
<span data-ttu-id="cce55-121">PS_ROUTING_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="cce55-121">PS_ROUTING_ENTRYID</span></span>
  
<span data-ttu-id="cce55-122">专门 PS_MAPI 属性集;服务提供商使用它可生成与范围的命名的属性的标识符的属性的名称。</span><span class="sxs-lookup"><span data-stu-id="cce55-122">The PS_MAPI property set is reserved; it is used by service providers to generate names for properties with identifiers below the named property range.</span></span> <span data-ttu-id="cce55-123">客户端使用 PS_PUBLIC_STRINGS 属性集 IPM 消息的命名属性。</span><span class="sxs-lookup"><span data-stu-id="cce55-123">The PS_PUBLIC_STRINGS property set is used by clients for named properties of IPM messages.</span></span> <span data-ttu-id="cce55-124">因为命名 PS_PUBLIC_STRINGS 设置的属性中的属性显示在客户端的用户界面中，不可见的消息如那些属于 IPC 邮件类应避免创建名为该属性设置的属性。</span><span class="sxs-lookup"><span data-stu-id="cce55-124">Because named properties in the PS_PUBLIC_STRINGS property set appear in a client's user interface, nonvisible messages such as those that belong to the IPC message class should avoid creating named properties with this property set.</span></span> <span data-ttu-id="cce55-125">相反，他们应在邮件类特定区域中，通过 0x7FFF 0x6800 创建属性。</span><span class="sxs-lookup"><span data-stu-id="cce55-125">Instead, they should create properties in the message class-specific range, 0x6800 through 0x7FFF.</span></span>
  
<span data-ttu-id="cce55-126">其他属性集保留描述通常路由列表中的成员的收件人的命名的属性。</span><span class="sxs-lookup"><span data-stu-id="cce55-126">The other property sets hold named properties describing recipients that are typically members of a routing list.</span></span> <span data-ttu-id="cce55-127">包含相同类型的收件人列表属性与关联的属性的信息，这些属性集的属性可理解的网关需要映射的邮件系统的目标。</span><span class="sxs-lookup"><span data-stu-id="cce55-127">Containing the same type of information as the properties that are associated with recipient list properties, properties in these property sets are understood by gateways to require mapping for a target messaging system.</span></span> <span data-ttu-id="cce55-128">有五种类型的描述属性的信息，因为 MAPI 定义了五个不同的属性集。</span><span class="sxs-lookup"><span data-stu-id="cce55-128">Because there are five types of information for describing properties, MAPI has defined five different property sets.</span></span> <span data-ttu-id="cce55-129">客户端发送一条消息，必须包括地址和地址类型为其路由列表成员分配一个 PS_ROUTING_EMAIL_ADDRESSES 中每个成员的命名的属性和 PS_ROUTING_ADDRTYPE 属性设置。</span><span class="sxs-lookup"><span data-stu-id="cce55-129">A client sending a message that must include an address and address type for its routing list members assigns a named property for each member in the PS_ROUTING_EMAIL_ADDRESSES and PS_ROUTING_ADDRTYPE property sets.</span></span> <span data-ttu-id="cce55-130">这样可以确保地址和地址类型保持可行时发送给外部邮件系统。</span><span class="sxs-lookup"><span data-stu-id="cce55-130">This ensures that the address and address type remain viable when sent to a foreign messaging system.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="cce55-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cce55-131">See also</span></span>



[<span data-ttu-id="cce55-132">MAPI 命名属性</span><span class="sxs-lookup"><span data-stu-id="cce55-132">MAPI Named Properties</span></span>](mapi-named-properties.md)

