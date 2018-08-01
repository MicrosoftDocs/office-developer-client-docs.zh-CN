---
title: MAPI 字符集
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: fbe63916-b3eb-4ea7-bc42-80a8b0281b03
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 3f94823eb3f90ff9ac0f472a2de64e1904920d9c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776206"
---
# <a name="mapi-character-sets"></a><span data-ttu-id="4f958-103">MAPI 字符集</span><span class="sxs-lookup"><span data-stu-id="4f958-103">MAPI Character Sets</span></span>

  
  
<span data-ttu-id="4f958-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="4f958-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="4f958-105">MAPI 兼容的客户端应用程序和服务提供商可以使用 ANSI 字符 （单字节） 或 Unicode 字符 （双字节）。</span><span class="sxs-lookup"><span data-stu-id="4f958-105">MAPI-compliant client applications and service providers can use ANSI characters (single byte) or Unicode characters (double byte).</span></span> <span data-ttu-id="4f958-106">不支持 OEM 字符集。</span><span class="sxs-lookup"><span data-stu-id="4f958-106">OEM character sets are not supported.</span></span> <span data-ttu-id="4f958-107">OEM 字符串传递给 MAPI 方法或函数将导致该方法或函数失败。</span><span class="sxs-lookup"><span data-stu-id="4f958-107">An OEM string passed to a MAPI method or function will cause that method or function to fail.</span></span> <span data-ttu-id="4f958-108">使用 OEM 字符集中的文件名的客户端应用程序必须注意之前将它们传递给 MAPI 方法或函数将其转换为 ANSI。</span><span class="sxs-lookup"><span data-stu-id="4f958-108">Client applications that work with filenames in the OEM character set must be careful to convert them to ANSI before passing them to a MAPI method or function.</span></span>
  
<span data-ttu-id="4f958-109">支持 Unicode 字符集是可选的同时为客户端和服务提供程序。</span><span class="sxs-lookup"><span data-stu-id="4f958-109">Supporting the Unicode character set is optional, both for clients and service providers.</span></span> <span data-ttu-id="4f958-110">所有服务提供商应都编写自己的代码，以便他们可以编译而不考虑它们支持 Unicode。</span><span class="sxs-lookup"><span data-stu-id="4f958-110">All service providers should write their code so that they can compile regardless of whether or not they support Unicode.</span></span> <span data-ttu-id="4f958-111">客户端编译有条件地，具体取决于其级别的支持，但服务提供商不。</span><span class="sxs-lookup"><span data-stu-id="4f958-111">Clients compile conditionally, depending on their level of support, but service providers do not.</span></span> <span data-ttu-id="4f958-112">他们不应有字符集更改时重新编译。</span><span class="sxs-lookup"><span data-stu-id="4f958-112">They should not have to be recompiled when the character set changes.</span></span> <span data-ttu-id="4f958-113">在服务提供程序代码中为 nothing 应条件。</span><span class="sxs-lookup"><span data-stu-id="4f958-113">Nothing in service provider code should be conditional.</span></span> 
  
<span data-ttu-id="4f958-114">当客户端或服务提供程序支持 Unicode 使方法调用包含字符串作为输入或输出参数，它们会设置 MAPI_UNICODE 标志。</span><span class="sxs-lookup"><span data-stu-id="4f958-114">When clients or service providers that support Unicode make a method call that includes character strings as input or output parameters, they set the MAPI_UNICODE flag.</span></span> <span data-ttu-id="4f958-115">设置此标志指示的实现的所有传入字符串是否 Unicode 字符串。</span><span class="sxs-lookup"><span data-stu-id="4f958-115">Setting this flag indicates to the implementation that all incoming strings are Unicode strings.</span></span> <span data-ttu-id="4f958-116">输出，设置传递的所有字符串都后从实现此标志请求应为 Unicode 字符串如果可能。</span><span class="sxs-lookup"><span data-stu-id="4f958-116">On output, setting this flag requests that all strings passed back from the implementation should be Unicode strings if possible.</span></span> <span data-ttu-id="4f958-117">支持 Unicode 的方法实现方注释将遵守请求;不提供 Unicode 支持的方法实现方注释将不符合要求。</span><span class="sxs-lookup"><span data-stu-id="4f958-117">Method implementers that support Unicode will comply with the request; method implementers that do not provide Unicode support will not comply.</span></span> <span data-ttu-id="4f958-118">不在 Unicode 格式的字符串属性是类型 PT_STRING8。</span><span class="sxs-lookup"><span data-stu-id="4f958-118">String properties that are not in Unicode format are of type PT_STRING8.</span></span>
  
<span data-ttu-id="4f958-119">MAPI 头文件 MAPIDEFS 中定义**fMapiUnicode**常量。H 以表示默认字符集。</span><span class="sxs-lookup"><span data-stu-id="4f958-119">MAPI defines the **fMapiUnicode** constant in the header file MAPIDEFS.H to represent the default character set.</span></span> <span data-ttu-id="4f958-120">如果客户端或服务提供程序支持 Unicode， **fMapiUnicode**设置为 MAPI_UNICODE。</span><span class="sxs-lookup"><span data-stu-id="4f958-120">If a client or service provider supports Unicode, **fMapiUnicode** is set to MAPI_UNICODE.</span></span> <span data-ttu-id="4f958-121">客户端和不支持 Unicode 的服务提供商设置**fMapiUnicode**为零。</span><span class="sxs-lookup"><span data-stu-id="4f958-121">Clients and service providers that do not support Unicode set **fMapiUnicode** to zero.</span></span> 
  
<span data-ttu-id="4f958-122">服务提供程序不支持 Unicode 应：</span><span class="sxs-lookup"><span data-stu-id="4f958-122">Service providers that do not support Unicode should:</span></span>
  
- <span data-ttu-id="4f958-123">拒绝执行字符集之间的转换。</span><span class="sxs-lookup"><span data-stu-id="4f958-123">Refuse to perform conversions between character sets.</span></span>
    
- <span data-ttu-id="4f958-124">从不方法调用中传递 MAPI_UNICODE 标志。</span><span class="sxs-lookup"><span data-stu-id="4f958-124">Never pass the MAPI_UNICODE flag in method calls.</span></span>
    
- <span data-ttu-id="4f958-125">当传入 MAPI_UNICODE 标志，则返回 MAPI_E_BAD_CHARWIDTH。</span><span class="sxs-lookup"><span data-stu-id="4f958-125">Return MAPI_E_BAD_CHARWIDTH when the MAPI_UNICODE flag is passed in.</span></span>
    
- <span data-ttu-id="4f958-126">显式声明 ANSI 字符串属性。</span><span class="sxs-lookup"><span data-stu-id="4f958-126">Declare ANSI string properties explicitly.</span></span> 
    
<span data-ttu-id="4f958-127">服务提供商还可以返回 MAPI_E_BAD_CHARWIDTH 仅支持 Unicode 和客户端时不要传递 MAPI_UNICODE 标志。</span><span class="sxs-lookup"><span data-stu-id="4f958-127">Service providers can also return MAPI_E_BAD_CHARWIDTH when they only support Unicode and clients do not pass the MAPI_UNICODE flag.</span></span> 
  
 <span data-ttu-id="4f958-128">MAPI 的当前版本中支持 Unicode，在下列方法：</span><span class="sxs-lookup"><span data-stu-id="4f958-128">The current version of MAPI supports Unicode in the following methods:</span></span> 
  
[<span data-ttu-id="4f958-129">IAddrBook::Address</span><span class="sxs-lookup"><span data-stu-id="4f958-129">IAddrBook::Address</span></span>](iaddrbook-address.md)
  
[<span data-ttu-id="4f958-130">IAddrBook::CreateOneOff</span><span class="sxs-lookup"><span data-stu-id="4f958-130">IAddrBook::CreateOneOff</span></span>](iaddrbook-createoneoff.md)
  
[<span data-ttu-id="4f958-131">IAddrBook::Details</span><span class="sxs-lookup"><span data-stu-id="4f958-131">IAddrBook::Details</span></span>](iaddrbook-details.md)
  
[<span data-ttu-id="4f958-132">IAddrBook::ResolveName</span><span class="sxs-lookup"><span data-stu-id="4f958-132">IAddrBook::ResolveName</span></span>](iaddrbook-resolvename.md)
  
<span data-ttu-id="4f958-133">[IMAPIProp::GetLastError](imapiprop-getlasterror.md)（仅适用于**IAddrBook**实现）</span><span class="sxs-lookup"><span data-stu-id="4f958-133">[IMAPIProp::GetLastError](imapiprop-getlasterror.md) (**IAddrBook** implementation only)</span></span> 
  
<span data-ttu-id="4f958-134">对于这些方法，调用方可以预期任何返回的字符串为 Unicode 字符串。</span><span class="sxs-lookup"><span data-stu-id="4f958-134">For these methods, callers can expect any returned strings to be Unicode strings.</span></span> <span data-ttu-id="4f958-135">从 MAPI 实现的任何其他方法返回的字符串将 ANSI 字符串。</span><span class="sxs-lookup"><span data-stu-id="4f958-135">Character strings returned from MAPI implementations of any other method will be ANSI character strings.</span></span>
  

