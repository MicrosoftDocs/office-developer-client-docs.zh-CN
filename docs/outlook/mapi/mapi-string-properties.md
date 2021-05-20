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
# <a name="mapi-string-properties"></a><span data-ttu-id="8481f-103">MAPI 字符串属性</span><span class="sxs-lookup"><span data-stu-id="8481f-103">MAPI String Properties</span></span>

  
  
<span data-ttu-id="8481f-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="8481f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="8481f-105">MAPI 提供了三种不同的属性类型来描述字符串属性：</span><span class="sxs-lookup"><span data-stu-id="8481f-105">MAPI provides three different property types to describe string properties:</span></span>
  
<span data-ttu-id="8481f-106">PT_TSTRING</span><span class="sxs-lookup"><span data-stu-id="8481f-106">PT_TSTRING</span></span>
  
<span data-ttu-id="8481f-107">PT_STRING8</span><span class="sxs-lookup"><span data-stu-id="8481f-107">PT_STRING8</span></span>
  
<span data-ttu-id="8481f-108">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="8481f-108">PT_UNICODE</span></span>
  
<span data-ttu-id="8481f-109">字符串属性最常定义为PT_TSTRING。</span><span class="sxs-lookup"><span data-stu-id="8481f-109">String properties are most commonly defined as PT_TSTRING.</span></span> <span data-ttu-id="8481f-110">该属性PT_TSTRING类型有条件地编译为其他字符串属性类型之一，具体取决于是否已定义 UNICODE 宏。</span><span class="sxs-lookup"><span data-stu-id="8481f-110">The PT_TSTRING property type conditionally compiles to one of the other string property types, depending depending on whether the UNICODE macro has been defined.</span></span> <span data-ttu-id="8481f-111">PT_STRING8 ANSI 格式描述 8 位以 null 结束的字符串;PT_UNICODE双字节以 null 结束的字符串。</span><span class="sxs-lookup"><span data-stu-id="8481f-111">PT_STRING8 describes 8-bit null-terminated character strings in the ANSI format; PT_UNICODE describes double-byte null-terminated character strings.</span></span> 
  
<span data-ttu-id="8481f-112">客户端或服务提供商，或者客户端和提供程序都可以选择支持 Unicode 字符串。</span><span class="sxs-lookup"><span data-stu-id="8481f-112">Either a client or a service provider, or both client and provider can choose to support Unicode character strings.</span></span> <span data-ttu-id="8481f-113">这不是必需的。</span><span class="sxs-lookup"><span data-stu-id="8481f-113">It is not required.</span></span> <span data-ttu-id="8481f-114">仅支持字符串的PT_STRING8可以与支持 Unicode 的提供程序一起操作，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="8481f-114">A client that supports only PT_STRING8 strings can operate with a provider that supports Unicode and vice versa.</span></span> <span data-ttu-id="8481f-115">为了启用此互操作性，客户端和服务提供商传递一个标志MAPI_UNICODE标志，以指示涉及字符串交换的方法支持 Unicode。</span><span class="sxs-lookup"><span data-stu-id="8481f-115">To enable this interoperability, clients and service providers pass a flag, the MAPI_UNICODE flag, to indicate that Unicode is supported in methods that involve the exchange of character strings.</span></span> 
  
<span data-ttu-id="8481f-116">例如，假设客户端支持 Unicode 并需要检索显示名称的名称。</span><span class="sxs-lookup"><span data-stu-id="8481f-116">For example, suppose a client supports Unicode and needs to retrieve the display name of a folder.</span></span> <span data-ttu-id="8481f-117">将编译客户端的所有PT_TSTRING属性以键入PT_UNICODE。</span><span class="sxs-lookup"><span data-stu-id="8481f-117">All of the client's PT_TSTRING properties are compiled to type PT_UNICODE.</span></span> <span data-ttu-id="8481f-118">当客户端调用文件夹 [的 IMAPIProp：：GetProps](imapiprop-getprops.md) 方法来检索其 **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 属性时，它会传递 MAPI_UNICODE 标志以请求以 Unicode 格式返回 显示名称 字符串。</span><span class="sxs-lookup"><span data-stu-id="8481f-118">When the client calls the folder's [IMAPIProp::GetProps](imapiprop-getprops.md) method to retrieve its **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) property, it passes the MAPI_UNICODE flag to request that the display name string be returned in the Unicode format.</span></span> 
  
<span data-ttu-id="8481f-119">客户端和服务提供商需要知道，在方法调用中指定字符集只是一个请求。</span><span class="sxs-lookup"><span data-stu-id="8481f-119">Clients and service providers need to be aware that specifying a character set in a method call is only a request.</span></span> <span data-ttu-id="8481f-120">支持一个或两个字符集由对象的实现者决定。</span><span class="sxs-lookup"><span data-stu-id="8481f-120">Supporting one or both character sets is up to the implementer of the object.</span></span> <span data-ttu-id="8481f-121">但是，鼓励服务提供商支持这两种字符集，因为它允许它们实现比仅支持一个字符集的提供程序更普遍分发。</span><span class="sxs-lookup"><span data-stu-id="8481f-121">However, service providers are encouraged to support both character sets because it allows them to achieve more widespread distribution than providers that support only one set.</span></span> 
  
<span data-ttu-id="8481f-122">字符串属性可以像二进制属性（使用属性类型或属性类型的属性）一样PT_BINARY。</span><span class="sxs-lookup"><span data-stu-id="8481f-122">String properties can grow to be quite large as can binary properties — properties that use the property type PT_BINARY.</span></span> <span data-ttu-id="8481f-123">为了便于使用大型属性，MAPI 允许设置这些属性的服务提供商强制实施大小限制。</span><span class="sxs-lookup"><span data-stu-id="8481f-123">To ease working with large properties, MAPI allows service providers setting these properties to enforce size limits.</span></span> <span data-ttu-id="8481f-124">这些限制可能会有所不同，具体取决于：</span><span class="sxs-lookup"><span data-stu-id="8481f-124">These limits can vary, depending on:</span></span>
  
- <span data-ttu-id="8481f-125">属性是正在读取还是写入。</span><span class="sxs-lookup"><span data-stu-id="8481f-125">Whether the properties are being read or written.</span></span>
    
- <span data-ttu-id="8481f-126">服务提供商如何实现 **IMAPIProp** 方法。</span><span class="sxs-lookup"><span data-stu-id="8481f-126">How the service provider implements the **IMAPIProp** methods.</span></span> 
    
- <span data-ttu-id="8481f-127">运行时注意事项，如内存约束。</span><span class="sxs-lookup"><span data-stu-id="8481f-127">Runtime considerations, such as memory constraints.</span></span>
    
- <span data-ttu-id="8481f-128">字符集转换问题。</span><span class="sxs-lookup"><span data-stu-id="8481f-128">Character set translation issues.</span></span> 
    
<span data-ttu-id="8481f-129">当在表的列集内使用字符串和二进制属性时，还可以对它们设置大小限制，因为有时不可能使所有大型属性的值都可见。</span><span class="sxs-lookup"><span data-stu-id="8481f-129">Size limits can also be placed on string and binary properties when they are used in the column set of a table because it is sometimes impossible to make all of a large property's value visible.</span></span> <span data-ttu-id="8481f-130">许多服务提供商将表中使用的大型字符串或二进制属性截断为 255 字节。</span><span class="sxs-lookup"><span data-stu-id="8481f-130">Many service providers truncate large string or binary properties that are used in tables to 255 bytes.</span></span> 
  
<span data-ttu-id="8481f-131">当客户端调用对象的 **GetProps** 或 **SetProps** 方法以使用大型字符串或二进制属性时，由于属性大小，调用失败，该方法将返回错误值 MAPI_E_NOT_ENOUGH_MEMORY。</span><span class="sxs-lookup"><span data-stu-id="8481f-131">When a client calls an object's **GetProps** or **SetProps** method to work with a large string or binary property and the call fails because of the property size, the method returns the error value MAPI_E_NOT_ENOUGH_MEMORY.</span></span> <span data-ttu-id="8481f-132">如果 **GetProps** 无法用于特定属性，则客户端可以通过调用 [IMAPIProp：：OpenProperty](imapiprop-openproperty.md) 并请求 **IStream（** 将 IID_IStream 指定为接口标识符）进行恢复。</span><span class="sxs-lookup"><span data-stu-id="8481f-132">If it is **GetProps** that is failing for a specific property, the client can recover by calling [IMAPIProp::OpenProperty](imapiprop-openproperty.md) and requesting the **IStream** for access by specifying IID_IStream as the interface identifier.</span></span> <span data-ttu-id="8481f-133">通过使用 **OpenProperty，** 客户端可以使用更适合使用大型属性的接口（如 **IStream）** 检索大型属性。</span><span class="sxs-lookup"><span data-stu-id="8481f-133">Using **OpenProperty**, the client can retrieve a large property using an interface such as **IStream** that is better suited for working with large properties.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="8481f-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8481f-134">See also</span></span>



[<span data-ttu-id="8481f-135">MAPI 属性概述</span><span class="sxs-lookup"><span data-stu-id="8481f-135">MAPI Property Overview</span></span>](mapi-property-overview.md)

