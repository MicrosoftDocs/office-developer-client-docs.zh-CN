---
title: MAPI 字符串属性
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 63d7360a-e3a3-4365-9d46-50df1c715bde
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 3e16a373ec35696f6d1a8ccc52263a1cf8570cfc
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22572324"
---
# <a name="mapi-string-properties"></a><span data-ttu-id="992e7-103">MAPI 字符串属性</span><span class="sxs-lookup"><span data-stu-id="992e7-103">MAPI String Properties</span></span>

  
  
<span data-ttu-id="992e7-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="992e7-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="992e7-105">MAPI 提供了三种不同的属性类型来描述字符串属性：</span><span class="sxs-lookup"><span data-stu-id="992e7-105">MAPI provides three different property types to describe string properties:</span></span>
  
<span data-ttu-id="992e7-106">PT_TSTRING</span><span class="sxs-lookup"><span data-stu-id="992e7-106">PT_TSTRING</span></span>
  
<span data-ttu-id="992e7-107">PT_STRING8</span><span class="sxs-lookup"><span data-stu-id="992e7-107">PT_STRING8</span></span>
  
<span data-ttu-id="992e7-108">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="992e7-108">PT_UNICODE</span></span>
  
<span data-ttu-id="992e7-109">字符串属性最常被定义为 PT_TSTRING。</span><span class="sxs-lookup"><span data-stu-id="992e7-109">String properties are most commonly defined as PT_TSTRING.</span></span> <span data-ttu-id="992e7-110">为其他字符串属性类型之一，具体取决于是否已定义 UNICODE 宏有条件地编译 PT_TSTRING 属性类型。</span><span class="sxs-lookup"><span data-stu-id="992e7-110">The PT_TSTRING property type conditionally compiles to one of the other string property types, depending depending on whether the UNICODE macro has been defined.</span></span> <span data-ttu-id="992e7-111">PT_STRING8 描述 ANSI 格式; 8 位 null 结尾的字符串字符串PT_UNICODE 描述双字节 null 结尾字符的字符串。</span><span class="sxs-lookup"><span data-stu-id="992e7-111">PT_STRING8 describes 8-bit null-terminated character strings in the ANSI format; PT_UNICODE describes double-byte null-terminated character strings.</span></span> 
  
<span data-ttu-id="992e7-112">通过客户端或服务提供商，或客户端和提供程序可以选择支持的 Unicode 字符串。</span><span class="sxs-lookup"><span data-stu-id="992e7-112">Either a client or a service provider, or both client and provider can choose to support Unicode character strings.</span></span> <span data-ttu-id="992e7-113">不需要。</span><span class="sxs-lookup"><span data-stu-id="992e7-113">It is not required.</span></span> <span data-ttu-id="992e7-114">支持仅 PT_STRING8 字符串的客户端可以运行的提供程序支持 Unicode，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="992e7-114">A client that supports only PT_STRING8 strings can operate with a provider that supports Unicode and vice versa.</span></span> <span data-ttu-id="992e7-115">若要启用此互操作性，客户端和服务提供商，请传递标志，MAPI_UNICODE 标志，以指示 Unicode 支持中涉及的字符串交换的方法。</span><span class="sxs-lookup"><span data-stu-id="992e7-115">To enable this interoperability, clients and service providers pass a flag, the MAPI_UNICODE flag, to indicate that Unicode is supported in methods that involve the exchange of character strings.</span></span> 
  
<span data-ttu-id="992e7-116">例如，假设客户端中支持 Unicode，并且需要检索文件夹的显示名称。</span><span class="sxs-lookup"><span data-stu-id="992e7-116">For example, suppose a client supports Unicode and needs to retrieve the display name of a folder.</span></span> <span data-ttu-id="992e7-117">编译的所有客户端的 PT_TSTRING 属性键入 PT_UNICODE。</span><span class="sxs-lookup"><span data-stu-id="992e7-117">All of the client's PT_TSTRING properties are compiled to type PT_UNICODE.</span></span> <span data-ttu-id="992e7-118">当客户端调用该文件夹的[IMAPIProp::GetProps](imapiprop-getprops.md)方法来检索其**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 属性时，它将传递 MAPI_UNICODE 标志以请求返回的显示名称字符串以 Unicode 格式.</span><span class="sxs-lookup"><span data-stu-id="992e7-118">When the client calls the folder's [IMAPIProp::GetProps](imapiprop-getprops.md) method to retrieve its **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) property, it passes the MAPI_UNICODE flag to request that the display name string be returned in the Unicode format.</span></span> 
  
<span data-ttu-id="992e7-119">客户端和服务提供商需要注意的指定在方法调用中的字符集是仅请求。</span><span class="sxs-lookup"><span data-stu-id="992e7-119">Clients and service providers need to be aware that specifying a character set in a method call is only a request.</span></span> <span data-ttu-id="992e7-120">支持一个或两个字符设置为最多为对象的实施。</span><span class="sxs-lookup"><span data-stu-id="992e7-120">Supporting one or both character sets is up to the implementer of the object.</span></span> <span data-ttu-id="992e7-121">但是，建议以支持两个字符集，因为它允许他们能够实现更广泛分发比支持只有一组提供程序的服务提供商。</span><span class="sxs-lookup"><span data-stu-id="992e7-121">However, service providers are encouraged to support both character sets because it allows them to achieve more widespread distribution than providers that support only one set.</span></span> 
  
<span data-ttu-id="992e7-122">字符串属性可以增长得很大，如可以二进制属性 — 使用属性的属性键入 PT_BINARY。</span><span class="sxs-lookup"><span data-stu-id="992e7-122">String properties can grow to be quite large as can binary properties — properties that use the property type PT_BINARY.</span></span> <span data-ttu-id="992e7-123">为了便于使用大型属性，MAPI 允许服务提供商设置这些属性强制实施大小限制。</span><span class="sxs-lookup"><span data-stu-id="992e7-123">To ease working with large properties, MAPI allows service providers setting these properties to enforce size limits.</span></span> <span data-ttu-id="992e7-124">这些限制可以有所不同，具体取决于：</span><span class="sxs-lookup"><span data-stu-id="992e7-124">These limits can vary, depending on:</span></span>
  
- <span data-ttu-id="992e7-125">是否正在属性读取或写入。</span><span class="sxs-lookup"><span data-stu-id="992e7-125">Whether the properties are being read or written.</span></span>
    
- <span data-ttu-id="992e7-126">如何服务提供商实现**IMAPIProp**方法。</span><span class="sxs-lookup"><span data-stu-id="992e7-126">How the service provider implements the **IMAPIProp** methods.</span></span> 
    
- <span data-ttu-id="992e7-127">运行时的注意事项，例如内存限制。</span><span class="sxs-lookup"><span data-stu-id="992e7-127">Runtime considerations, such as memory constraints.</span></span>
    
- <span data-ttu-id="992e7-128">字符集转换问题。</span><span class="sxs-lookup"><span data-stu-id="992e7-128">Character set translation issues.</span></span> 
    
<span data-ttu-id="992e7-129">此外可以在字符串上放置大小限制，因为它是有时可能使大型属性的值的所有可见时使用的列中的二进制属性设置的表。</span><span class="sxs-lookup"><span data-stu-id="992e7-129">Size limits can also be placed on string and binary properties when they are used in the column set of a table because it is sometimes impossible to make all of a large property's value visible.</span></span> <span data-ttu-id="992e7-130">许多服务提供商截断大的字符串或 255 个字节的表中使用的二进制属性。</span><span class="sxs-lookup"><span data-stu-id="992e7-130">Many service providers truncate large string or binary properties that are used in tables to 255 bytes.</span></span> 
  
<span data-ttu-id="992e7-131">当客户端调用对象的**GetProps**或**SetProps**方法来处理大的字符串或二进制属性，并调用将失败，因为属性大小时，该方法将返回错误值 MAPI_E_NOT_ENOUGH_MEMORY。</span><span class="sxs-lookup"><span data-stu-id="992e7-131">When a client calls an object's **GetProps** or **SetProps** method to work with a large string or binary property and the call fails because of the property size, the method returns the error value MAPI_E_NOT_ENOUGH_MEMORY.</span></span> <span data-ttu-id="992e7-132">如果是**GetProps**出现故障的特定属性，可以通过调用[IMAPIProp::OpenProperty](imapiprop-openproperty.md)并通过接口标识指定 IID_IStream 请求访问**IStream**恢复客户端。</span><span class="sxs-lookup"><span data-stu-id="992e7-132">If it is **GetProps** that is failing for a specific property, the client can recover by calling [IMAPIProp::OpenProperty](imapiprop-openproperty.md) and requesting the **IStream** for access by specifying IID_IStream as the interface identifier.</span></span> <span data-ttu-id="992e7-133">使用**OpenProperty**，客户端可以检索使用如是更适合使用大型属性的**IStream**接口的大型属性。</span><span class="sxs-lookup"><span data-stu-id="992e7-133">Using **OpenProperty**, the client can retrieve a large property using an interface such as **IStream** that is better suited for working with large properties.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="992e7-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="992e7-134">See also</span></span>



[<span data-ttu-id="992e7-135">MAPI 属性概述</span><span class="sxs-lookup"><span data-stu-id="992e7-135">MAPI Property Overview</span></span>](mapi-property-overview.md)

