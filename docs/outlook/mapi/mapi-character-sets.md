---
title: MAPI 字符集
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: fbe63916-b3eb-4ea7-bc42-80a8b0281b03
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 898883d8c93b69762883a502b7a4313b3417d0d3
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33417551"
---
# <a name="mapi-character-sets"></a><span data-ttu-id="a7391-103">MAPI 字符集</span><span class="sxs-lookup"><span data-stu-id="a7391-103">MAPI Character Sets</span></span>

  
  
<span data-ttu-id="a7391-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a7391-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a7391-105">符合 MAPI 的客户端应用程序和服务提供商可以使用 ANSI 字符 (字节字符) Unicode 字符 (双字节) 。</span><span class="sxs-lookup"><span data-stu-id="a7391-105">MAPI-compliant client applications and service providers can use ANSI characters (single byte) or Unicode characters (double byte).</span></span> <span data-ttu-id="a7391-106">不支持 OEM 字符集。</span><span class="sxs-lookup"><span data-stu-id="a7391-106">OEM character sets are not supported.</span></span> <span data-ttu-id="a7391-107">传递给 MAPI 方法或函数的 OEM 字符串将导致该方法或函数失败。</span><span class="sxs-lookup"><span data-stu-id="a7391-107">An OEM string passed to a MAPI method or function will cause that method or function to fail.</span></span> <span data-ttu-id="a7391-108">处理 OEM 字符集内文件名的客户端应用程序在将它们传递到 MAPI 方法或函数之前，必须小心将其转换为 ANSI。</span><span class="sxs-lookup"><span data-stu-id="a7391-108">Client applications that work with filenames in the OEM character set must be careful to convert them to ANSI before passing them to a MAPI method or function.</span></span>
  
<span data-ttu-id="a7391-109">对于客户端和服务提供商，支持 Unicode 字符集是可选的。</span><span class="sxs-lookup"><span data-stu-id="a7391-109">Supporting the Unicode character set is optional, both for clients and service providers.</span></span> <span data-ttu-id="a7391-110">所有服务提供商都应编写其代码，以便无论它们是否支持 Unicode，都可以进行编译。</span><span class="sxs-lookup"><span data-stu-id="a7391-110">All service providers should write their code so that they can compile regardless of whether or not they support Unicode.</span></span> <span data-ttu-id="a7391-111">客户端有条件地编译，具体取决于其支持级别，但服务提供商没有。</span><span class="sxs-lookup"><span data-stu-id="a7391-111">Clients compile conditionally, depending on their level of support, but service providers do not.</span></span> <span data-ttu-id="a7391-112">当字符集更改时，它们不应重新编译。</span><span class="sxs-lookup"><span data-stu-id="a7391-112">They should not have to be recompiled when the character set changes.</span></span> <span data-ttu-id="a7391-113">服务提供程序代码中没有任何内容应具有条件。</span><span class="sxs-lookup"><span data-stu-id="a7391-113">Nothing in service provider code should be conditional.</span></span> 
  
<span data-ttu-id="a7391-114">当支持 Unicode 的客户端或服务提供商进行包含字符串作为输入或输出参数的方法调用时，它们MAPI_UNICODE标志。</span><span class="sxs-lookup"><span data-stu-id="a7391-114">When clients or service providers that support Unicode make a method call that includes character strings as input or output parameters, they set the MAPI_UNICODE flag.</span></span> <span data-ttu-id="a7391-115">设置此标志将指示实现所有传入字符串都是 Unicode 字符串。</span><span class="sxs-lookup"><span data-stu-id="a7391-115">Setting this flag indicates to the implementation that all incoming strings are Unicode strings.</span></span> <span data-ttu-id="a7391-116">在输出上，如果可能，设置此标志将请求从实现传递回的所有字符串应为 Unicode 字符串。</span><span class="sxs-lookup"><span data-stu-id="a7391-116">On output, setting this flag requests that all strings passed back from the implementation should be Unicode strings if possible.</span></span> <span data-ttu-id="a7391-117">支持 Unicode 的方法实施者将符合请求;不提供 Unicode 支持的方法实施者将不符合。</span><span class="sxs-lookup"><span data-stu-id="a7391-117">Method implementers that support Unicode will comply with the request; method implementers that do not provide Unicode support will not comply.</span></span> <span data-ttu-id="a7391-118">非 Unicode 格式的字符串属性的类型PT_STRING8。</span><span class="sxs-lookup"><span data-stu-id="a7391-118">String properties that are not in Unicode format are of type PT_STRING8.</span></span>
  
<span data-ttu-id="a7391-119">MAPI 定义头文件 MAPIDEFS 中的 **fMapiUnicode** 常量。H 表示默认字符集。</span><span class="sxs-lookup"><span data-stu-id="a7391-119">MAPI defines the **fMapiUnicode** constant in the header file MAPIDEFS.H to represent the default character set.</span></span> <span data-ttu-id="a7391-120">如果客户端或服务提供商支持 Unicode， **则 fMapiUnicode** 将设置为 MAPI_UNICODE。</span><span class="sxs-lookup"><span data-stu-id="a7391-120">If a client or service provider supports Unicode, **fMapiUnicode** is set to MAPI_UNICODE.</span></span> <span data-ttu-id="a7391-121">不支持 Unicode 的客户端和服务提供商将 **fMapiUnicode 设置为** 零。</span><span class="sxs-lookup"><span data-stu-id="a7391-121">Clients and service providers that do not support Unicode set **fMapiUnicode** to zero.</span></span> 
  
<span data-ttu-id="a7391-122">不支持 Unicode 的服务提供商应：</span><span class="sxs-lookup"><span data-stu-id="a7391-122">Service providers that do not support Unicode should:</span></span>
  
- <span data-ttu-id="a7391-123">拒绝在字符集之间执行转换。</span><span class="sxs-lookup"><span data-stu-id="a7391-123">Refuse to perform conversions between character sets.</span></span>
    
- <span data-ttu-id="a7391-124">从不在方法MAPI_UNICODE传递该标志。</span><span class="sxs-lookup"><span data-stu-id="a7391-124">Never pass the MAPI_UNICODE flag in method calls.</span></span>
    
- <span data-ttu-id="a7391-125">返回MAPI_E_BAD_CHARWIDTH传入MAPI_UNICODE时返回值。</span><span class="sxs-lookup"><span data-stu-id="a7391-125">Return MAPI_E_BAD_CHARWIDTH when the MAPI_UNICODE flag is passed in.</span></span>
    
- <span data-ttu-id="a7391-126">显式声明 ANSI 字符串属性。</span><span class="sxs-lookup"><span data-stu-id="a7391-126">Declare ANSI string properties explicitly.</span></span> 
    
<span data-ttu-id="a7391-127">当服务提供商仅支持 Unicode MAPI_E_BAD_CHARWIDTH客户端不传递 Unicode 标志时，它们也可以返回MAPI_UNICODE值。</span><span class="sxs-lookup"><span data-stu-id="a7391-127">Service providers can also return MAPI_E_BAD_CHARWIDTH when they only support Unicode and clients do not pass the MAPI_UNICODE flag.</span></span> 
  
 <span data-ttu-id="a7391-128">MAPI 的当前版本支持以下方法中的 Unicode：</span><span class="sxs-lookup"><span data-stu-id="a7391-128">The current version of MAPI supports Unicode in the following methods:</span></span> 
  
[<span data-ttu-id="a7391-129">IAddrBook::Address</span><span class="sxs-lookup"><span data-stu-id="a7391-129">IAddrBook::Address</span></span>](iaddrbook-address.md)
  
[<span data-ttu-id="a7391-130">IAddrBook::CreateOneOff</span><span class="sxs-lookup"><span data-stu-id="a7391-130">IAddrBook::CreateOneOff</span></span>](iaddrbook-createoneoff.md)
  
[<span data-ttu-id="a7391-131">IAddrBook::Details</span><span class="sxs-lookup"><span data-stu-id="a7391-131">IAddrBook::Details</span></span>](iaddrbook-details.md)
  
[<span data-ttu-id="a7391-132">IAddrBook::ResolveName</span><span class="sxs-lookup"><span data-stu-id="a7391-132">IAddrBook::ResolveName</span></span>](iaddrbook-resolvename.md)
  
<span data-ttu-id="a7391-133">[IMAPIProp：：GetLastError](imapiprop-getlasterror.md) (**IAddrBook** 实现) </span><span class="sxs-lookup"><span data-stu-id="a7391-133">[IMAPIProp::GetLastError](imapiprop-getlasterror.md) (**IAddrBook** implementation only)</span></span> 
  
<span data-ttu-id="a7391-134">对于这些方法，调用方预期任何返回的字符串为 Unicode 字符串。</span><span class="sxs-lookup"><span data-stu-id="a7391-134">For these methods, callers can expect any returned strings to be Unicode strings.</span></span> <span data-ttu-id="a7391-135">从任何其他方法的 MAPI 实现返回的字符串将是 ANSI 字符串。</span><span class="sxs-lookup"><span data-stu-id="a7391-135">Character strings returned from MAPI implementations of any other method will be ANSI character strings.</span></span>
  

