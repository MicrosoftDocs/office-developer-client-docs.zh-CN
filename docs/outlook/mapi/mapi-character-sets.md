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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32319073"
---
# <a name="mapi-character-sets"></a><span data-ttu-id="76018-103">MAPI 字符集</span><span class="sxs-lookup"><span data-stu-id="76018-103">MAPI Character Sets</span></span>

  
  
<span data-ttu-id="76018-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="76018-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="76018-105">符合 MAPI 的客户端应用程序和服务提供程序可以使用 ANSI 字符 (单字节) 或 Unicode 字符 (双字节)。</span><span class="sxs-lookup"><span data-stu-id="76018-105">MAPI-compliant client applications and service providers can use ANSI characters (single byte) or Unicode characters (double byte).</span></span> <span data-ttu-id="76018-106">OEM 字符集不受支持。</span><span class="sxs-lookup"><span data-stu-id="76018-106">OEM character sets are not supported.</span></span> <span data-ttu-id="76018-107">传递给 MAPI 方法或函数的 OEM 字符串将导致该方法或函数失败。</span><span class="sxs-lookup"><span data-stu-id="76018-107">An OEM string passed to a MAPI method or function will cause that method or function to fail.</span></span> <span data-ttu-id="76018-108">使用 OEM 字符集中的文件名的客户端应用程序必须在将它们传递给 MAPI 方法或函数之前, 将其转换为 ANSI。</span><span class="sxs-lookup"><span data-stu-id="76018-108">Client applications that work with filenames in the OEM character set must be careful to convert them to ANSI before passing them to a MAPI method or function.</span></span>
  
<span data-ttu-id="76018-109">对于客户端和服务提供程序, 支持 Unicode 字符集是可选的。</span><span class="sxs-lookup"><span data-stu-id="76018-109">Supporting the Unicode character set is optional, both for clients and service providers.</span></span> <span data-ttu-id="76018-110">所有服务提供程序都应编写自己的代码, 以便无论它们是否支持 Unicode, 都可以编译它们。</span><span class="sxs-lookup"><span data-stu-id="76018-110">All service providers should write their code so that they can compile regardless of whether or not they support Unicode.</span></span> <span data-ttu-id="76018-111">客户端根据其支持级别进行了条件编译, 但服务提供商不会这样做。</span><span class="sxs-lookup"><span data-stu-id="76018-111">Clients compile conditionally, depending on their level of support, but service providers do not.</span></span> <span data-ttu-id="76018-112">在字符集发生更改时, 不必重新编译这些设置。</span><span class="sxs-lookup"><span data-stu-id="76018-112">They should not have to be recompiled when the character set changes.</span></span> <span data-ttu-id="76018-113">服务提供程序代码中的任何内容都不应有条件。</span><span class="sxs-lookup"><span data-stu-id="76018-113">Nothing in service provider code should be conditional.</span></span> 
  
<span data-ttu-id="76018-114">当支持 Unicode 的客户端或服务提供程序发出的方法调用包含作为输入或输出参数的字符串时, 它们将设置 MAPI_UNICODE 标志。</span><span class="sxs-lookup"><span data-stu-id="76018-114">When clients or service providers that support Unicode make a method call that includes character strings as input or output parameters, they set the MAPI_UNICODE flag.</span></span> <span data-ttu-id="76018-115">设置此标志指示所有传入字符串均为 Unicode 字符串的实现。</span><span class="sxs-lookup"><span data-stu-id="76018-115">Setting this flag indicates to the implementation that all incoming strings are Unicode strings.</span></span> <span data-ttu-id="76018-116">在输出时, 设置此标志将请求从实现传递回来的所有字符串都应为 Unicode 字符串 (如果可能)。</span><span class="sxs-lookup"><span data-stu-id="76018-116">On output, setting this flag requests that all strings passed back from the implementation should be Unicode strings if possible.</span></span> <span data-ttu-id="76018-117">支持 Unicode 的方法实施者将符合请求;不提供 Unicode 支持的方法实施者将不符合这些要求。</span><span class="sxs-lookup"><span data-stu-id="76018-117">Method implementers that support Unicode will comply with the request; method implementers that do not provide Unicode support will not comply.</span></span> <span data-ttu-id="76018-118">不是 Unicode 格式的字符串属性的类型为 PT_STRING8。</span><span class="sxs-lookup"><span data-stu-id="76018-118">String properties that are not in Unicode format are of type PT_STRING8.</span></span>
  
<span data-ttu-id="76018-119">MAPI 在头文件 mapidefs.h 中定义**fMapiUnicode**常量。H 表示默认字符集。</span><span class="sxs-lookup"><span data-stu-id="76018-119">MAPI defines the **fMapiUnicode** constant in the header file MAPIDEFS.H to represent the default character set.</span></span> <span data-ttu-id="76018-120">如果客户端或服务提供程序支持 Unicode, 则**fMapiUnicode**设置为 MAPI_UNICODE。</span><span class="sxs-lookup"><span data-stu-id="76018-120">If a client or service provider supports Unicode, **fMapiUnicode** is set to MAPI_UNICODE.</span></span> <span data-ttu-id="76018-121">不支持 Unicode 的客户端和服务提供程序将**fMapiUnicode**设置为零。</span><span class="sxs-lookup"><span data-stu-id="76018-121">Clients and service providers that do not support Unicode set **fMapiUnicode** to zero.</span></span> 
  
<span data-ttu-id="76018-122">不支持 Unicode 的服务提供程序应执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="76018-122">Service providers that do not support Unicode should:</span></span>
  
- <span data-ttu-id="76018-123">拒绝在字符集之间执行转换。</span><span class="sxs-lookup"><span data-stu-id="76018-123">Refuse to perform conversions between character sets.</span></span>
    
- <span data-ttu-id="76018-124">从不在方法调用中传递 MAPI_UNICODE 标志。</span><span class="sxs-lookup"><span data-stu-id="76018-124">Never pass the MAPI_UNICODE flag in method calls.</span></span>
    
- <span data-ttu-id="76018-125">在传入 MAPI_UNICODE 标志时返回 MAPI_E_BAD_CHARWIDTH。</span><span class="sxs-lookup"><span data-stu-id="76018-125">Return MAPI_E_BAD_CHARWIDTH when the MAPI_UNICODE flag is passed in.</span></span>
    
- <span data-ttu-id="76018-126">显式声明 ANSI 字符串属性。</span><span class="sxs-lookup"><span data-stu-id="76018-126">Declare ANSI string properties explicitly.</span></span> 
    
<span data-ttu-id="76018-127">如果服务提供程序仅支持 Unicode, 并且客户端未传递 MAPI_UNICODE 标志, 则服务提供程序也可以返回 MAPI_E_BAD_CHARWIDTH。</span><span class="sxs-lookup"><span data-stu-id="76018-127">Service providers can also return MAPI_E_BAD_CHARWIDTH when they only support Unicode and clients do not pass the MAPI_UNICODE flag.</span></span> 
  
 <span data-ttu-id="76018-128">当前版本的 MAPI 在以下方法中支持 Unicode:</span><span class="sxs-lookup"><span data-stu-id="76018-128">The current version of MAPI supports Unicode in the following methods:</span></span> 
  
[<span data-ttu-id="76018-129">IAddrBook::Address</span><span class="sxs-lookup"><span data-stu-id="76018-129">IAddrBook::Address</span></span>](iaddrbook-address.md)
  
[<span data-ttu-id="76018-130">IAddrBook::CreateOneOff</span><span class="sxs-lookup"><span data-stu-id="76018-130">IAddrBook::CreateOneOff</span></span>](iaddrbook-createoneoff.md)
  
[<span data-ttu-id="76018-131">IAddrBook::Details</span><span class="sxs-lookup"><span data-stu-id="76018-131">IAddrBook::Details</span></span>](iaddrbook-details.md)
  
[<span data-ttu-id="76018-132">IAddrBook::ResolveName</span><span class="sxs-lookup"><span data-stu-id="76018-132">IAddrBook::ResolveName</span></span>](iaddrbook-resolvename.md)
  
<span data-ttu-id="76018-133">[IMAPIProp:: GetLastError](imapiprop-getlasterror.md)(仅限**IAddrBook**实现)</span><span class="sxs-lookup"><span data-stu-id="76018-133">[IMAPIProp::GetLastError](imapiprop-getlasterror.md) (**IAddrBook** implementation only)</span></span> 
  
<span data-ttu-id="76018-134">对于这些方法, 调用方可以预期任何返回的字符串为 Unicode 字符串。</span><span class="sxs-lookup"><span data-stu-id="76018-134">For these methods, callers can expect any returned strings to be Unicode strings.</span></span> <span data-ttu-id="76018-135">从任何其他方法的 MAPI 实现返回的字符串将是 ANSI 字符字符串。</span><span class="sxs-lookup"><span data-stu-id="76018-135">Character strings returned from MAPI implementations of any other method will be ANSI character strings.</span></span>
  

