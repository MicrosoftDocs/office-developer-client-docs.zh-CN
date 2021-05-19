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
# <a name="defining-new-mapi-properties"></a><span data-ttu-id="aab98-103">定义新的 MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="aab98-103">Defining New MAPI Properties</span></span>

  
  
<span data-ttu-id="aab98-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="aab98-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="aab98-105">尽管 MAPI 提供了大量供客户端和服务提供商使用的属性，但 MAPI 仍支持在必要时新建属性。</span><span class="sxs-lookup"><span data-stu-id="aab98-105">In spite of the wealth of properties supplied by MAPI for use by clients and service providers, MAPI enables new properties to be created if necessary.</span></span> <span data-ttu-id="aab98-106">定义新的公共属性的一些有效方案包括客户端创建属性以支持新邮件类，以及服务提供商创建新属性来公开唯一的邮件系统功能。</span><span class="sxs-lookup"><span data-stu-id="aab98-106">Some of the valid scenarios for defining new public properties include a client creating properties to support a new message class and a service provider creating new properties to expose unique messaging system features.</span></span>
  
<span data-ttu-id="aab98-107">服务提供商通常无效为现有 MAPI 对象或邮件类定义新属性。</span><span class="sxs-lookup"><span data-stu-id="aab98-107">It is typically not valid for a service provider to define new properties for an existing MAPI object or message class.</span></span> <span data-ttu-id="aab98-108">使用 MAPI 的主要好处之一是设置大量邮件系统元素的标准标识符和格式，使用户能够无缝混合和匹配服务提供商。</span><span class="sxs-lookup"><span data-stu-id="aab98-108">One of the primary benefits of using MAPI is that standard identifiers and formats for a large number of messaging system elements are set up, enabling users to seamlessly mix and match service providers.</span></span> <span data-ttu-id="aab98-109">使用非标准属性的服务提供商不能很好地与其他服务提供商一起工作。</span><span class="sxs-lookup"><span data-stu-id="aab98-109">Service providers that use nonstandard properties do not work as well with other service providers.</span></span> 
  
<span data-ttu-id="aab98-110">客户端可以通过：为新邮件类创建内容属性：</span><span class="sxs-lookup"><span data-stu-id="aab98-110">Clients can create content properties for new message classes by:</span></span>
  
- <span data-ttu-id="aab98-111">在指定范围内对特定于邮件类的内容属性使用属性标识符。</span><span class="sxs-lookup"><span data-stu-id="aab98-111">Using property identifiers within a designated range for message class-specific content properties.</span></span>
    
    - <span data-ttu-id="aab98-112">或 -</span><span class="sxs-lookup"><span data-stu-id="aab98-112">Or -</span></span>
    
- <span data-ttu-id="aab98-113">使用命名属性。</span><span class="sxs-lookup"><span data-stu-id="aab98-113">Using named properties.</span></span> 
    
<span data-ttu-id="aab98-114">首选第一个选项，因为并非所有服务提供商都支持命名属性。</span><span class="sxs-lookup"><span data-stu-id="aab98-114">The first option is preferable because not all service providers support named properties.</span></span> <span data-ttu-id="aab98-115">MAPI 为客户端定义两个单独的范围以用于新的特定于邮件类的内容属性：</span><span class="sxs-lookup"><span data-stu-id="aab98-115">MAPI defines two separate ranges for clients to use for new message class-specific content properties:</span></span>
  
- <span data-ttu-id="aab98-116">0x6800可0x7BFF属性的自定义属性</span><span class="sxs-lookup"><span data-stu-id="aab98-116">0x6800 to 0x7BFF for transmittable properties</span></span>
    
- <span data-ttu-id="aab98-117">0x7C00 0x7FFF属性的自定义设置</span><span class="sxs-lookup"><span data-stu-id="aab98-117">0x7C00 to 0x7FFF for nontransmittable properties</span></span>
    
<span data-ttu-id="aab98-118">属性标识符必须属于预定义的范围，以帮助防止由不同供应商或用户定义的属性之间发生冲突。</span><span class="sxs-lookup"><span data-stu-id="aab98-118">Property identifiers must fall in predefined ranges to help prevent collisions between properties defined by different vendors or users.</span></span> <span data-ttu-id="aab98-119">但是，这些范围中的属性用户不能对属性的行为做出假设。</span><span class="sxs-lookup"><span data-stu-id="aab98-119">However, users of properties in these ranges cannot make assumptions as to the behavior of the properties.</span></span> <span data-ttu-id="aab98-120">每个创建新邮件类的客户端都有权访问这些范围;标识符为  _xxxx_ 的属性可以表示一个邮件类的一个行为，另一个邮件类的另一个行为。</span><span class="sxs-lookup"><span data-stu-id="aab98-120">Every client that creates a new message class has access to these ranges; a property with identifier  _xxxx_ can mean one behavior for one message class and another behavior for another message class.</span></span> 
  
<span data-ttu-id="aab98-121">命名属性用于保证特定属性对于邮件类是唯一的。</span><span class="sxs-lookup"><span data-stu-id="aab98-121">Named properties are used to guarantee a specific property is unique to a message class.</span></span> <span data-ttu-id="aab98-122">命名属性标识符从0x8000开始。</span><span class="sxs-lookup"><span data-stu-id="aab98-122">Named property identifiers start in the 0x8000 range.</span></span> <span data-ttu-id="aab98-123">客户端定义一个或多个名称，然后调用消息存储的 [IMAPIProp：：GetIDsFromNames](imapiprop-getidsfromnames.md) 方法以将标识符与每个名称关联。</span><span class="sxs-lookup"><span data-stu-id="aab98-123">Clients define one or more names and then call the message store's [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md) method to associate an identifier with each name.</span></span> <span data-ttu-id="aab98-124">只有在对象的所有者支持命名属性时，客户端或服务提供商才能使用命名属性定义任何对象的新属性。</span><span class="sxs-lookup"><span data-stu-id="aab98-124">Named properties can be used by clients or service providers to define new properties for any object only if the owner of the object supports named properties.</span></span> <span data-ttu-id="aab98-125">这些属性的用户调用 **GetIDsFromNames** 和相关 **IMAPIProp** 方法 [GetNamesFromIDs，](imapiprop-getnamesfromids.md)以在名称及其标识符之间映射。</span><span class="sxs-lookup"><span data-stu-id="aab98-125">Users of these properties call **GetIDsFromNames** and a related **IMAPIProp** method, [GetNamesFromIDs](imapiprop-getnamesfromids.md), to map between a name and its identifier.</span></span>
  
<span data-ttu-id="aab98-126">所有属性（新属性或现有属性）都必须使用预定义属性类型集。</span><span class="sxs-lookup"><span data-stu-id="aab98-126">All properties, new or existing, must use the set of predefined property types.</span></span> <span data-ttu-id="aab98-127">无法添加新属性类型，并且无法修改或删除现有类型。</span><span class="sxs-lookup"><span data-stu-id="aab98-127">New property types cannot be added and existing types cannot be modified or deleted.</span></span> <span data-ttu-id="aab98-128">简单的小属性（如单字符或 16 位整数属性）可以存储在任何适当的类型中。</span><span class="sxs-lookup"><span data-stu-id="aab98-128">Simple, small properties, such as single-character or 16-bit integer properties, can be stored in any appropriate type.</span></span> <span data-ttu-id="aab98-129">例如，整数可以存储为 **ULONG，** 字符串可以存储 **为PT_STRING8。**</span><span class="sxs-lookup"><span data-stu-id="aab98-129">For example, integers can be stored as **ULONG** and strings can be stored as **PT_STRING8**.</span></span> 
  
<span data-ttu-id="aab98-130">使用 **PT_BINARY** 类型指示计数的字节数组。</span><span class="sxs-lookup"><span data-stu-id="aab98-130">Use the **PT_BINARY** type to indicate a counted byte array.</span></span> <span data-ttu-id="aab98-131">此属性类型对于扩展可存储在对象中的数据类型非常有用。</span><span class="sxs-lookup"><span data-stu-id="aab98-131">This property type is useful for extending the types of data that can be stored in an object.</span></span> <span data-ttu-id="aab98-132">字节按顺序传输，并且未对数据的含义做出任何假设。</span><span class="sxs-lookup"><span data-stu-id="aab98-132">Bytes are transmitted in sequence and no assumptions are made about the meaning of the data.</span></span> <span data-ttu-id="aab98-133">当客户端应用程序从此类属性中读取数据时，数据与数据的存储方法保持不变。</span><span class="sxs-lookup"><span data-stu-id="aab98-133">When a client application reads data out of such a property, the data is unchanged from how it was stored.</span></span> <span data-ttu-id="aab98-134">在 CPU 之间移动数据时，客户端必须执行任何必要的字节交换。</span><span class="sxs-lookup"><span data-stu-id="aab98-134">The client must perform any necessary byte swapping when moving data across CPUs.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="aab98-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="aab98-135">See also</span></span>



[<span data-ttu-id="aab98-136">MAPI 属性概述</span><span class="sxs-lookup"><span data-stu-id="aab98-136">MAPI Property Overview</span></span>](mapi-property-overview.md)

