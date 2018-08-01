---
title: 定义新的 MAPI 属性
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 1a2325ea-ddfa-480f-b65f-f5b20471fb40
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 68e877568565cfcc30b60e9b21f55b7dc1600b28
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774771"
---
# <a name="defining-new-mapi-properties"></a><span data-ttu-id="c8c2d-103">定义新的 MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="c8c2d-103">Defining New MAPI Properties</span></span>

  
  
<span data-ttu-id="c8c2d-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="c8c2d-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="c8c2d-105">丰富的属性以供客户端和服务提供商提供的 MAPI，尽管 MAPI 启用要创建必要的新属性。</span><span class="sxs-lookup"><span data-stu-id="c8c2d-105">In spite of the wealth of properties supplied by MAPI for use by clients and service providers, MAPI enables new properties to be created if necessary.</span></span> <span data-ttu-id="c8c2d-106">定义新的公共属性的有效方案的一些包括客户端创建属性以支持新的邮件类和服务提供程序创建新属性公开唯一消息系统功能。</span><span class="sxs-lookup"><span data-stu-id="c8c2d-106">Some of the valid scenarios for defining new public properties include a client creating properties to support a new message class and a service provider creating new properties to expose unique messaging system features.</span></span>
  
<span data-ttu-id="c8c2d-107">通常不有效的服务提供程序定义的现有 MAPI 对象或消息类的新属性。</span><span class="sxs-lookup"><span data-stu-id="c8c2d-107">It is typically not valid for a service provider to define new properties for an existing MAPI object or message class.</span></span> <span data-ttu-id="c8c2d-108">使用 MAPI 的主要优点之一是标准的标识符和格式的大量元素设置，使用户能够无缝混合和匹配的邮件系统的服务提供商。</span><span class="sxs-lookup"><span data-stu-id="c8c2d-108">One of the primary benefits of using MAPI is that standard identifiers and formats for a large number of messaging system elements are set up, enabling users to seamlessly mix and match service providers.</span></span> <span data-ttu-id="c8c2d-109">使用非标准属性的服务提供商无效以及与其他服务提供商。</span><span class="sxs-lookup"><span data-stu-id="c8c2d-109">Service providers that use nonstandard properties do not work as well with other service providers.</span></span> 
  
<span data-ttu-id="c8c2d-110">客户端可以创建的新邮件类的内容属性：</span><span class="sxs-lookup"><span data-stu-id="c8c2d-110">Clients can create content properties for new message classes by:</span></span>
  
- <span data-ttu-id="c8c2d-111">使用邮件类特定内容属性属性指定范围内的标识符。</span><span class="sxs-lookup"><span data-stu-id="c8c2d-111">Using property identifiers within a designated range for message class-specific content properties.</span></span>
    
    - <span data-ttu-id="c8c2d-112">或者-</span><span class="sxs-lookup"><span data-stu-id="c8c2d-112">Or -</span></span>
    
- <span data-ttu-id="c8c2d-113">使用命名的属性。</span><span class="sxs-lookup"><span data-stu-id="c8c2d-113">Using named properties.</span></span> 
    
<span data-ttu-id="c8c2d-114">最好是第一个选项，因为并非所有服务提供商都支持命名的属性。</span><span class="sxs-lookup"><span data-stu-id="c8c2d-114">The first option is preferable because not all service providers support named properties.</span></span> <span data-ttu-id="c8c2d-115">MAPI 定义为客户端用于新的邮件类特定内容属性的两个单独的范围：</span><span class="sxs-lookup"><span data-stu-id="c8c2d-115">MAPI defines two separate ranges for clients to use for new message class-specific content properties:</span></span>
  
- <span data-ttu-id="c8c2d-116">0x6800 到 0x7BFF 可传送属性</span><span class="sxs-lookup"><span data-stu-id="c8c2d-116">0x6800 to 0x7BFF for transmittable properties</span></span>
    
- <span data-ttu-id="c8c2d-117">0x7C00 到 0x7FFF nontransmittable 属性</span><span class="sxs-lookup"><span data-stu-id="c8c2d-117">0x7C00 to 0x7FFF for nontransmittable properties</span></span>
    
<span data-ttu-id="c8c2d-118">为了帮助防止其他供应商或用户定义的属性之间的冲突的预定义范围中必须属于属性标识符。</span><span class="sxs-lookup"><span data-stu-id="c8c2d-118">Property identifiers must fall in predefined ranges to help prevent collisions between properties defined by different vendors or users.</span></span> <span data-ttu-id="c8c2d-119">但是，这些范围中的属性的用户无法进行假设来对行为的属性。</span><span class="sxs-lookup"><span data-stu-id="c8c2d-119">However, users of properties in these ranges cannot make assumptions as to the behavior of the properties.</span></span> <span data-ttu-id="c8c2d-120">创建新的邮件类的每个客户端有权访问这些范围;一个邮件类的一个行为和另一个邮件类的另一个行为，可能意味着标识符_格式_的属性。</span><span class="sxs-lookup"><span data-stu-id="c8c2d-120">Every client that creates a new message class has access to these ranges; a property with identifier  _xxxx_ can mean one behavior for one message class and another behavior for another message class.</span></span> 
  
<span data-ttu-id="c8c2d-121">命名的属性用于保证特定属性是唯一的邮件类。</span><span class="sxs-lookup"><span data-stu-id="c8c2d-121">Named properties are used to guarantee a specific property is unique to a message class.</span></span> <span data-ttu-id="c8c2d-122">命名的属性标识符启动 0x8000 范围中。</span><span class="sxs-lookup"><span data-stu-id="c8c2d-122">Named property identifiers start in the 0x8000 range.</span></span> <span data-ttu-id="c8c2d-123">客户端定义一个或多个名称，然后调用的消息存储[IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md)方法与每个名称相关联的标识符。</span><span class="sxs-lookup"><span data-stu-id="c8c2d-123">Clients define one or more names and then call the message store's [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md) method to associate an identifier with each name.</span></span> <span data-ttu-id="c8c2d-124">命名的属性可以由客户端或服务提供商，用于定义的任何对象的新属性，仅当对象的所有者支持命名的属性。</span><span class="sxs-lookup"><span data-stu-id="c8c2d-124">Named properties can be used by clients or service providers to define new properties for any object only if the owner of the object supports named properties.</span></span> <span data-ttu-id="c8c2d-125">这些属性的用户呼叫**GetIDsFromNames**和相关的**IMAPIProp**方法， [GetNamesFromIDs](imapiprop-getnamesfromids.md)，名称和其标识符之间进行映射。</span><span class="sxs-lookup"><span data-stu-id="c8c2d-125">Users of these properties call **GetIDsFromNames** and a related **IMAPIProp** method, [GetNamesFromIDs](imapiprop-getnamesfromids.md), to map between a name and its identifier.</span></span>
  
<span data-ttu-id="c8c2d-126">所有属性，新的或现有，必须都使用一的组预定义的属性类型。</span><span class="sxs-lookup"><span data-stu-id="c8c2d-126">All properties, new or existing, must use the set of predefined property types.</span></span> <span data-ttu-id="c8c2d-127">无法添加新的属性类型，不能修改或删除现有的类型。</span><span class="sxs-lookup"><span data-stu-id="c8c2d-127">New property types cannot be added and existing types cannot be modified or deleted.</span></span> <span data-ttu-id="c8c2d-128">简单、 小属性，如单字符或 16 位整数属性可以存储在任何适当的类型。</span><span class="sxs-lookup"><span data-stu-id="c8c2d-128">Simple, small properties, such as single-character or 16-bit integer properties, can be stored in any appropriate type.</span></span> <span data-ttu-id="c8c2d-129">例如，可以作为**ULONG**存储整数和字符串可以存储为**PT_STRING8**。</span><span class="sxs-lookup"><span data-stu-id="c8c2d-129">For example, integers can be stored as **ULONG** and strings can be stored as **PT_STRING8**.</span></span> 
  
<span data-ttu-id="c8c2d-130">使用**PT_BINARY**类型指示计数的字节数组。</span><span class="sxs-lookup"><span data-stu-id="c8c2d-130">Use the **PT_BINARY** type to indicate a counted byte array.</span></span> <span data-ttu-id="c8c2d-131">此属性类型可用于扩展的可以对象中存储的数据类型。</span><span class="sxs-lookup"><span data-stu-id="c8c2d-131">This property type is useful for extending the types of data that can be stored in an object.</span></span> <span data-ttu-id="c8c2d-132">序列中传输字节和任何假定所做的数据的含义。</span><span class="sxs-lookup"><span data-stu-id="c8c2d-132">Bytes are transmitted in sequence and no assumptions are made about the meaning of the data.</span></span> <span data-ttu-id="c8c2d-133">当客户端应用程序读取利用这种属性的数据时，数据是从存储方式不变。</span><span class="sxs-lookup"><span data-stu-id="c8c2d-133">When a client application reads data out of such a property, the data is unchanged from how it was stored.</span></span> <span data-ttu-id="c8c2d-134">客户端必须执行任何所需的字节交换跨 Cpu 移动数据。</span><span class="sxs-lookup"><span data-stu-id="c8c2d-134">The client must perform any necessary byte swapping when moving data across CPUs.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="c8c2d-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c8c2d-135">See also</span></span>



[<span data-ttu-id="c8c2d-136">MAPI 属性概述</span><span class="sxs-lookup"><span data-stu-id="c8c2d-136">MAPI Property Overview</span></span>](mapi-property-overview.md)

