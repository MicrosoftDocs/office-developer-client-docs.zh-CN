---
title: MAPI 字符串属性
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 63d7360a-e3a3-4365-9d46-50df1c715bde
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 9720b649eadecc73d84d98926674a1786796ba70
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33431391"
---
# <a name="mapi-string-properties"></a><span data-ttu-id="509c1-103">MAPI 字符串属性</span><span class="sxs-lookup"><span data-stu-id="509c1-103">MAPI String Properties</span></span>

  
  
<span data-ttu-id="509c1-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="509c1-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="509c1-105">MAPI 提供了三种不同的属性类型来描述字符串属性:</span><span class="sxs-lookup"><span data-stu-id="509c1-105">MAPI provides three different property types to describe string properties:</span></span>
  
<span data-ttu-id="509c1-106">PT_TSTRING</span><span class="sxs-lookup"><span data-stu-id="509c1-106">PT_TSTRING</span></span>
  
<span data-ttu-id="509c1-107">PT_STRING8</span><span class="sxs-lookup"><span data-stu-id="509c1-107">PT_STRING8</span></span>
  
<span data-ttu-id="509c1-108">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="509c1-108">PT_UNICODE</span></span>
  
<span data-ttu-id="509c1-109">字符串属性最常定义为 PT_TSTRING。</span><span class="sxs-lookup"><span data-stu-id="509c1-109">String properties are most commonly defined as PT_TSTRING.</span></span> <span data-ttu-id="509c1-110">PT_TSTRING 属性类型有条件地编译为其他字符串属性类型之一, 具体取决于是否已定义 UNICODE 宏。</span><span class="sxs-lookup"><span data-stu-id="509c1-110">The PT_TSTRING property type conditionally compiles to one of the other string property types, depending depending on whether the UNICODE macro has been defined.</span></span> <span data-ttu-id="509c1-111">PT_STRING8 介绍了 ANSI 格式的8位 null 结尾字符字符串;PT_UNICODE 描述双字节以 null 结尾的字符串。</span><span class="sxs-lookup"><span data-stu-id="509c1-111">PT_STRING8 describes 8-bit null-terminated character strings in the ANSI format; PT_UNICODE describes double-byte null-terminated character strings.</span></span> 
  
<span data-ttu-id="509c1-112">客户端或服务提供商, 或者客户端和提供程序都可以选择支持 Unicode 字符字符串。</span><span class="sxs-lookup"><span data-stu-id="509c1-112">Either a client or a service provider, or both client and provider can choose to support Unicode character strings.</span></span> <span data-ttu-id="509c1-113">这不是必需的。</span><span class="sxs-lookup"><span data-stu-id="509c1-113">It is not required.</span></span> <span data-ttu-id="509c1-114">仅支持 PT_STRING8 字符串的客户端可以使用支持 Unicode 的提供程序运行, 反之亦然。</span><span class="sxs-lookup"><span data-stu-id="509c1-114">A client that supports only PT_STRING8 strings can operate with a provider that supports Unicode and vice versa.</span></span> <span data-ttu-id="509c1-115">若要启用此互操作性, 客户端和服务提供程序将传递一个标志, 即 MAPI_UNICODE 标志, 以指示涉及交换字符字符串的方法中支持 UNICODE。</span><span class="sxs-lookup"><span data-stu-id="509c1-115">To enable this interoperability, clients and service providers pass a flag, the MAPI_UNICODE flag, to indicate that Unicode is supported in methods that involve the exchange of character strings.</span></span> 
  
<span data-ttu-id="509c1-116">例如, 假设客户端支持 Unicode 并需要检索文件夹的显示名称。</span><span class="sxs-lookup"><span data-stu-id="509c1-116">For example, suppose a client supports Unicode and needs to retrieve the display name of a folder.</span></span> <span data-ttu-id="509c1-117">将所有客户端的 PT_TSTRING 属性编译为 PT_UNICODE 类型。</span><span class="sxs-lookup"><span data-stu-id="509c1-117">All of the client's PT_TSTRING properties are compiled to type PT_UNICODE.</span></span> <span data-ttu-id="509c1-118">当客户端调用文件夹的[IMAPIProp:: GetProps](imapiprop-getprops.md)方法以检索其**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 属性时, 它会传递 MAPI_UNICODE 标志以请求以 UNICODE 格式返回显示名称字符串。.</span><span class="sxs-lookup"><span data-stu-id="509c1-118">When the client calls the folder's [IMAPIProp::GetProps](imapiprop-getprops.md) method to retrieve its **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) property, it passes the MAPI_UNICODE flag to request that the display name string be returned in the Unicode format.</span></span> 
  
<span data-ttu-id="509c1-119">客户端和服务提供商需要注意, 在方法调用中指定字符集只是一个请求。</span><span class="sxs-lookup"><span data-stu-id="509c1-119">Clients and service providers need to be aware that specifying a character set in a method call is only a request.</span></span> <span data-ttu-id="509c1-120">支持一个或两个字符集由对象的实施者负责。</span><span class="sxs-lookup"><span data-stu-id="509c1-120">Supporting one or both character sets is up to the implementer of the object.</span></span> <span data-ttu-id="509c1-121">但是, 建议服务提供商支持这两个字符集, 因为它允许他们实现比仅支持一个集的提供程序更广泛的分布。</span><span class="sxs-lookup"><span data-stu-id="509c1-121">However, service providers are encouraged to support both character sets because it allows them to achieve more widespread distribution than providers that support only one set.</span></span> 
  
<span data-ttu-id="509c1-122">对于 binary 属性 (使用属性类型 PT_BINARY 的属性), 字符串属性可能会变得非常大。</span><span class="sxs-lookup"><span data-stu-id="509c1-122">String properties can grow to be quite large as can binary properties — properties that use the property type PT_BINARY.</span></span> <span data-ttu-id="509c1-123">为了简化大型属性的使用, MAPI 允许服务提供程序设置这些属性来强制大小限制。</span><span class="sxs-lookup"><span data-stu-id="509c1-123">To ease working with large properties, MAPI allows service providers setting these properties to enforce size limits.</span></span> <span data-ttu-id="509c1-124">这些限制可能会有所不同, 具体取决于:</span><span class="sxs-lookup"><span data-stu-id="509c1-124">These limits can vary, depending on:</span></span>
  
- <span data-ttu-id="509c1-125">是否正在读取或写入属性。</span><span class="sxs-lookup"><span data-stu-id="509c1-125">Whether the properties are being read or written.</span></span>
    
- <span data-ttu-id="509c1-126">服务提供程序如何实现**IMAPIProp**方法。</span><span class="sxs-lookup"><span data-stu-id="509c1-126">How the service provider implements the **IMAPIProp** methods.</span></span> 
    
- <span data-ttu-id="509c1-127">运行时注意事项, 如内存约束。</span><span class="sxs-lookup"><span data-stu-id="509c1-127">Runtime considerations, such as memory constraints.</span></span>
    
- <span data-ttu-id="509c1-128">字符集转换问题。</span><span class="sxs-lookup"><span data-stu-id="509c1-128">Character set translation issues.</span></span> 
    
<span data-ttu-id="509c1-129">在表的列集中使用时, 还可以对 string 和 binary 属性放置大小限制, 因为有时无法使所有大型属性的值可见。</span><span class="sxs-lookup"><span data-stu-id="509c1-129">Size limits can also be placed on string and binary properties when they are used in the column set of a table because it is sometimes impossible to make all of a large property's value visible.</span></span> <span data-ttu-id="509c1-130">许多服务提供程序会将在表中使用的大型字符串或二进制属性截断为255字节。</span><span class="sxs-lookup"><span data-stu-id="509c1-130">Many service providers truncate large string or binary properties that are used in tables to 255 bytes.</span></span> 
  
<span data-ttu-id="509c1-131">当客户端调用对象的**GetProps**或**SetProps**方法来处理大型字符串或二进制属性, 并且由于属性大小而导致调用失败时, 该方法将返回错误值 MAPI_E_NOT_ENOUGH_MEMORY。</span><span class="sxs-lookup"><span data-stu-id="509c1-131">When a client calls an object's **GetProps** or **SetProps** method to work with a large string or binary property and the call fails because of the property size, the method returns the error value MAPI_E_NOT_ENOUGH_MEMORY.</span></span> <span data-ttu-id="509c1-132">如果它是特定属性失败的**GetProps** , 客户端可以通过将 IID_IStream 指定为接口标识符, 调用[IMAPIProp:: OpenProperty](imapiprop-openproperty.md)并请求**IStream**进行访问来进行恢复。</span><span class="sxs-lookup"><span data-stu-id="509c1-132">If it is **GetProps** that is failing for a specific property, the client can recover by calling [IMAPIProp::OpenProperty](imapiprop-openproperty.md) and requesting the **IStream** for access by specifying IID_IStream as the interface identifier.</span></span> <span data-ttu-id="509c1-133">通过使用**OpenProperty**, 客户端可以使用接口 (如**IStream** ) 检索大型属性, 后者更适合处理大型属性。</span><span class="sxs-lookup"><span data-stu-id="509c1-133">Using **OpenProperty**, the client can retrieve a large property using an interface such as **IStream** that is better suited for working with large properties.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="509c1-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="509c1-134">See also</span></span>



[<span data-ttu-id="509c1-135">MAPI 属性概述</span><span class="sxs-lookup"><span data-stu-id="509c1-135">MAPI Property Overview</span></span>](mapi-property-overview.md)

