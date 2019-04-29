---
title: 定义新的 MAPI 属性
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 1a2325ea-ddfa-480f-b65f-f5b20471fb40
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 666ee413319765e39e25d586208f764afc93ae6b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33425013"
---
# <a name="defining-new-mapi-properties"></a><span data-ttu-id="fe151-103">定义新的 MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="fe151-103">Defining New MAPI Properties</span></span>

  
  
<span data-ttu-id="fe151-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="fe151-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="fe151-105">尽管 mapi 提供的用于客户端和服务提供商的大量属性, MAPI 也支持在必要时创建新属性。</span><span class="sxs-lookup"><span data-stu-id="fe151-105">In spite of the wealth of properties supplied by MAPI for use by clients and service providers, MAPI enables new properties to be created if necessary.</span></span> <span data-ttu-id="fe151-106">用于定义新的公共属性的一些有效方案包括客户端创建属性, 以支持新邮件类和服务提供程序创建新的属性以公开唯一的邮件系统功能。</span><span class="sxs-lookup"><span data-stu-id="fe151-106">Some of the valid scenarios for defining new public properties include a client creating properties to support a new message class and a service provider creating new properties to expose unique messaging system features.</span></span>
  
<span data-ttu-id="fe151-107">服务提供商对现有 MAPI 对象或邮件类别定义新属性的方法通常无效。</span><span class="sxs-lookup"><span data-stu-id="fe151-107">It is typically not valid for a service provider to define new properties for an existing MAPI object or message class.</span></span> <span data-ttu-id="fe151-108">使用 MAPI 的主要好处之一是, 设置了大量邮件系统元素的标准标识符和格式, 使用户能够无缝混合和匹配服务提供程序。</span><span class="sxs-lookup"><span data-stu-id="fe151-108">One of the primary benefits of using MAPI is that standard identifiers and formats for a large number of messaging system elements are set up, enabling users to seamlessly mix and match service providers.</span></span> <span data-ttu-id="fe151-109">使用非标准属性的服务提供程序不能和其他服务提供商一起使用。</span><span class="sxs-lookup"><span data-stu-id="fe151-109">Service providers that use nonstandard properties do not work as well with other service providers.</span></span> 
  
<span data-ttu-id="fe151-110">客户端可以通过以下方式创建新邮件类别的内容属性:</span><span class="sxs-lookup"><span data-stu-id="fe151-110">Clients can create content properties for new message classes by:</span></span>
  
- <span data-ttu-id="fe151-111">在指定范围内为邮件类别特定的内容属性使用属性标识符。</span><span class="sxs-lookup"><span data-stu-id="fe151-111">Using property identifiers within a designated range for message class-specific content properties.</span></span>
    
    - <span data-ttu-id="fe151-112">和</span><span class="sxs-lookup"><span data-stu-id="fe151-112">Or -</span></span>
    
- <span data-ttu-id="fe151-113">使用命名属性。</span><span class="sxs-lookup"><span data-stu-id="fe151-113">Using named properties.</span></span> 
    
<span data-ttu-id="fe151-114">第一种方法是首选方法, 因为并非所有服务提供程序都支持命名属性。</span><span class="sxs-lookup"><span data-stu-id="fe151-114">The first option is preferable because not all service providers support named properties.</span></span> <span data-ttu-id="fe151-115">MAPI 为客户端定义了两个单独的范围, 以供客户端用于新邮件类别特定的内容属性:</span><span class="sxs-lookup"><span data-stu-id="fe151-115">MAPI defines two separate ranges for clients to use for new message class-specific content properties:</span></span>
  
- <span data-ttu-id="fe151-116">0x6800 to 0x7BFF for 传输属性</span><span class="sxs-lookup"><span data-stu-id="fe151-116">0x6800 to 0x7BFF for transmittable properties</span></span>
    
- <span data-ttu-id="fe151-117">0x7C00 to 0x7FFF for nontransmittable 属性</span><span class="sxs-lookup"><span data-stu-id="fe151-117">0x7C00 to 0x7FFF for nontransmittable properties</span></span>
    
<span data-ttu-id="fe151-118">属性标识符必须位于预定义的范围内, 以帮助防止由不同供应商或用户定义的属性之间发生冲突。</span><span class="sxs-lookup"><span data-stu-id="fe151-118">Property identifiers must fall in predefined ranges to help prevent collisions between properties defined by different vendors or users.</span></span> <span data-ttu-id="fe151-119">但是, 这些区域中的属性的用户无法假定属性行为。</span><span class="sxs-lookup"><span data-stu-id="fe151-119">However, users of properties in these ranges cannot make assumptions as to the behavior of the properties.</span></span> <span data-ttu-id="fe151-120">创建新邮件类的每个客户端都有权访问这些区域;带有标识符_xxxx_的属性可表示一个邮件类别的一个行为和另一个邮件类别的另一个行为。</span><span class="sxs-lookup"><span data-stu-id="fe151-120">Every client that creates a new message class has access to these ranges; a property with identifier  _xxxx_ can mean one behavior for one message class and another behavior for another message class.</span></span> 
  
<span data-ttu-id="fe151-121">命名属性用于保证特定属性对邮件类是唯一的。</span><span class="sxs-lookup"><span data-stu-id="fe151-121">Named properties are used to guarantee a specific property is unique to a message class.</span></span> <span data-ttu-id="fe151-122">命名属性标识符以0x8000 范围开始。</span><span class="sxs-lookup"><span data-stu-id="fe151-122">Named property identifiers start in the 0x8000 range.</span></span> <span data-ttu-id="fe151-123">客户端定义一个或多个名称, 然后调用邮件存储区的[IMAPIProp:: GetIDsFromNames](imapiprop-getidsfromnames.md)方法将标识符与每个名称相关联。</span><span class="sxs-lookup"><span data-stu-id="fe151-123">Clients define one or more names and then call the message store's [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md) method to associate an identifier with each name.</span></span> <span data-ttu-id="fe151-124">只有当对象的所有者支持命名属性时, 客户端或服务提供程序才能使用命名属性为任何对象定义新属性。</span><span class="sxs-lookup"><span data-stu-id="fe151-124">Named properties can be used by clients or service providers to define new properties for any object only if the owner of the object supports named properties.</span></span> <span data-ttu-id="fe151-125">这些属性的用户调用**GetIDsFromNames**和相关的**IMAPIProp**方法[GetNamesFromIDs](imapiprop-getnamesfromids.md), 以在名称和其标识符之间进行映射。</span><span class="sxs-lookup"><span data-stu-id="fe151-125">Users of these properties call **GetIDsFromNames** and a related **IMAPIProp** method, [GetNamesFromIDs](imapiprop-getnamesfromids.md), to map between a name and its identifier.</span></span>
  
<span data-ttu-id="fe151-126">所有属性 (新的或现有的) 都必须使用预定义的属性类型集。</span><span class="sxs-lookup"><span data-stu-id="fe151-126">All properties, new or existing, must use the set of predefined property types.</span></span> <span data-ttu-id="fe151-127">无法添加新的属性类型, 并且无法修改或删除现有类型。</span><span class="sxs-lookup"><span data-stu-id="fe151-127">New property types cannot be added and existing types cannot be modified or deleted.</span></span> <span data-ttu-id="fe151-128">简单、较小的属性 (例如单字符或16位整数属性) 可以存储在任何适当的类型中。</span><span class="sxs-lookup"><span data-stu-id="fe151-128">Simple, small properties, such as single-character or 16-bit integer properties, can be stored in any appropriate type.</span></span> <span data-ttu-id="fe151-129">例如, 可以将整数存储为**ULONG** , 并且可以将字符串存储为**PT_STRING8**。</span><span class="sxs-lookup"><span data-stu-id="fe151-129">For example, integers can be stored as **ULONG** and strings can be stored as **PT_STRING8**.</span></span> 
  
<span data-ttu-id="fe151-130">使用**PT_BINARY**类型指示计数的字节数组。</span><span class="sxs-lookup"><span data-stu-id="fe151-130">Use the **PT_BINARY** type to indicate a counted byte array.</span></span> <span data-ttu-id="fe151-131">此属性类型对扩展可存储在对象中的数据类型很有用。</span><span class="sxs-lookup"><span data-stu-id="fe151-131">This property type is useful for extending the types of data that can be stored in an object.</span></span> <span data-ttu-id="fe151-132">字节按顺序传输, 并且不会对数据的含义进行假设。</span><span class="sxs-lookup"><span data-stu-id="fe151-132">Bytes are transmitted in sequence and no assumptions are made about the meaning of the data.</span></span> <span data-ttu-id="fe151-133">当客户端应用程序从这种属性中读取数据时, 数据不会因存储的方式而改变。</span><span class="sxs-lookup"><span data-stu-id="fe151-133">When a client application reads data out of such a property, the data is unchanged from how it was stored.</span></span> <span data-ttu-id="fe151-134">当跨 cpu 移动数据时, 客户端必须执行任何必要的字节交换。</span><span class="sxs-lookup"><span data-stu-id="fe151-134">The client must perform any necessary byte swapping when moving data across CPUs.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="fe151-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fe151-135">See also</span></span>



[<span data-ttu-id="fe151-136">MAPI 属性概述</span><span class="sxs-lookup"><span data-stu-id="fe151-136">MAPI Property Overview</span></span>](mapi-property-overview.md)

