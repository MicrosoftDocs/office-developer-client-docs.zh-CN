---
title: MAPI 返回值文档
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: c32ee53c-b063-4a00-a6bf-75ce5e07f56a
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 5bbafe9fda479d951bb20175ab904dc6e241226a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32329713"
---
# <a name="mapi-return-value-documentation"></a><span data-ttu-id="27abb-103">MAPI 返回值文档</span><span class="sxs-lookup"><span data-stu-id="27abb-103">MAPI Return Value Documentation</span></span>

  
  
<span data-ttu-id="27abb-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="27abb-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="27abb-105">此参考中的引用条目只记录那些需要由客户端应用程序处理的返回值。</span><span class="sxs-lookup"><span data-stu-id="27abb-105">The reference entries in this Reference document only those return values that require some handling by client applications.</span></span> <span data-ttu-id="27abb-106">返回指示常见错误条件的值, 并且可以通过检查是否有故障来推断, 而不包括在文档中。</span><span class="sxs-lookup"><span data-stu-id="27abb-106">Return values that indicate common error conditions and can be deduced by checking for failure are not included in the documentation.</span></span> <span data-ttu-id="27abb-107">例如, 如果调用方为输入参数指定了错误的值, 则许多接口方法可以返回 MAPI_E_INVALID_PARAMETER。</span><span class="sxs-lookup"><span data-stu-id="27abb-107">For example, many interface methods can return MAPI_E_INVALID_PARAMETER if a caller specifies the wrong value for an input parameter.</span></span> <span data-ttu-id="27abb-108">此值通常不会在预期的返回值集中列出, 因为无需专门查找 MAPI_E_INVALID_PARAMETER, 也无需与任何其他错误那样进行处理。</span><span class="sxs-lookup"><span data-stu-id="27abb-108">This value is typically not listed in the set of expected return values because there is no need to look specifically for MAPI_E_INVALID_PARAMETER and no need to process it differently from any other error.</span></span> <span data-ttu-id="27abb-109">另一方面, 某些服务提供商不支持事件通知, 并将 MAPI_E_NO_SUPPORT 返回到由客户端通过**IMAPISession**发出的**Advise**方法。</span><span class="sxs-lookup"><span data-stu-id="27abb-109">On the other hand, some service providers do not support event notification and will return MAPI_E_NO_SUPPORT to the **Advise** method made by clients through **IMAPISession**.</span></span> <span data-ttu-id="27abb-110">由于客户端需要显式检查此值并提供用于处理它所代表的条件的代码, 因此, MAPI_E_NO_SUPPORT 将包含在[IMAPISession:: 建议](imapisession-advise.md)的返回值列表中。</span><span class="sxs-lookup"><span data-stu-id="27abb-110">Because clients need to explicitly check for this value and provide code for handling the condition that it represents should it occur, MAPI_E_NO_SUPPORT is included in the list of return values for [IMAPISession::Advise](imapisession-advise.md).</span></span>
  
<span data-ttu-id="27abb-111">下表介绍了通常从方法和函数返回的错误值, 并要求对客户端或服务提供程序的部分进行显式处理。</span><span class="sxs-lookup"><span data-stu-id="27abb-111">The following table describes error values that are commonly returned from methods and functions and require explicit handling on the part of a client or service provider.</span></span> <span data-ttu-id="27abb-112">这些值分为四个类别: 指示无效输入数据的值、指示资源问题的值、指示字符集不兼容的值以及指示未知源失败的值。</span><span class="sxs-lookup"><span data-stu-id="27abb-112">These values fall into four categories: values that indicate invalid input data, values that indicate resource problems, values that indicate character set incompatibility, and values that indicate failure of an unknown origin.</span></span>
  
|<span data-ttu-id="27abb-113">**返回值**</span><span class="sxs-lookup"><span data-stu-id="27abb-113">**Return value**</span></span>|<span data-ttu-id="27abb-114">**说明**</span><span class="sxs-lookup"><span data-stu-id="27abb-114">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="27abb-115">MAPI_E_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="27abb-115">MAPI_E_INVALID_PARAMETER</span></span>  <br/> |<span data-ttu-id="27abb-116">传递到方法或函数中的一个或多个参数无效。</span><span class="sxs-lookup"><span data-stu-id="27abb-116">One or more of the parameters passed into the method or functions were not valid.</span></span>  <br/> |
|<span data-ttu-id="27abb-117">MAPI_E_UNKNOWN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="27abb-117">MAPI_E_UNKNOWN_FLAGS</span></span>  <br/> |<span data-ttu-id="27abb-118">flags 参数的一个或多个值无效。</span><span class="sxs-lookup"><span data-stu-id="27abb-118">One or more values for a flags parameter were not valid.</span></span>  <br/> |
|<span data-ttu-id="27abb-119">MAPI_E_DISK_ERROR</span><span class="sxs-lookup"><span data-stu-id="27abb-119">MAPI_E_DISK_ERROR</span></span>  <br/> |<span data-ttu-id="27abb-120">写入或读取磁盘时出现问题。</span><span class="sxs-lookup"><span data-stu-id="27abb-120">There was a problem writing to or reading from disk.</span></span>  <br/> |
|<span data-ttu-id="27abb-121">MAPI_E_NOT_ENOUGH_DISK</span><span class="sxs-lookup"><span data-stu-id="27abb-121">MAPI_E_NOT_ENOUGH_DISK</span></span>  <br/> |<span data-ttu-id="27abb-122">可用磁盘空间不足, 无法完成此操作。</span><span class="sxs-lookup"><span data-stu-id="27abb-122">Not enough disk space was available to complete the operation.</span></span>  <br/> |
|<span data-ttu-id="27abb-123">MAPI_E_NOT_ENOUGH_MEMORY</span><span class="sxs-lookup"><span data-stu-id="27abb-123">MAPI_E_NOT_ENOUGH_MEMORY</span></span>  <br/> |<span data-ttu-id="27abb-124">可用内存不足, 无法完成操作。</span><span class="sxs-lookup"><span data-stu-id="27abb-124">Not enough memory was available to complete the operation.</span></span>  <br/> |
|<span data-ttu-id="27abb-125">MAPI_E_NOT_ENOUGH_RESOURCES</span><span class="sxs-lookup"><span data-stu-id="27abb-125">MAPI_E_NOT_ENOUGH_RESOURCES</span></span>  <br/> |<span data-ttu-id="27abb-126">可用的系统资源不足, 无法完成此操作。</span><span class="sxs-lookup"><span data-stu-id="27abb-126">Not enough system resources were available to complete the operation.</span></span>  <br/> |
|<span data-ttu-id="27abb-127">MAPI_E_BAD_CHARWIDTH</span><span class="sxs-lookup"><span data-stu-id="27abb-127">MAPI_E_BAD_CHARWIDTH</span></span>  <br/> |<span data-ttu-id="27abb-128">调用方和实现支持的字符集中存在不兼容性。</span><span class="sxs-lookup"><span data-stu-id="27abb-128">An incompatibility exists in the character sets supported by the caller and the implementation.</span></span>  <br/> |
|<span data-ttu-id="27abb-129">MAPI_E_CALL_FAILED</span><span class="sxs-lookup"><span data-stu-id="27abb-129">MAPI_E_CALL_FAILED</span></span>  <br/> |<span data-ttu-id="27abb-130">发生意外或未知源的错误。</span><span class="sxs-lookup"><span data-stu-id="27abb-130">An error of unexpected or unknown origin occurred.</span></span>  <br/> |
   
<span data-ttu-id="27abb-131">表示 MAPI 返回值的常量在 MAPICODE 中列出。H 头文件。</span><span class="sxs-lookup"><span data-stu-id="27abb-131">The constants that represent MAPI return values are listed in the MAPICODE.H header file.</span></span> <span data-ttu-id="27abb-132">某些常量映射到 Win32 错误;可以在 Win32 头文件 winerror.h 中找到这些常量到数字值的映射。水平.</span><span class="sxs-lookup"><span data-stu-id="27abb-132">Some of the constants map to Win32 errors; the mapping of these constants to numeric values can be found in the Win32 header file, WINERROR.H.</span></span>
  
<span data-ttu-id="27abb-133">可以通过 MAPI 提供的参数验证 API 函数或一组宏来确定有关由呼叫者传入的无效数据的错误。</span><span class="sxs-lookup"><span data-stu-id="27abb-133">Errors regarding invalid data passed in by a caller can be determined through either the parameter validation API functions provided by MAPI or a set of macros.</span></span> 
  
<span data-ttu-id="27abb-134">出现以下情况之一时, 将出现字符集不兼容情况:</span><span class="sxs-lookup"><span data-stu-id="27abb-134">Character set incompatibility arises when either of the following situations occurs:</span></span>
  
- <span data-ttu-id="27abb-135">客户端或服务提供程序在方法或函数调用上设置 MAPI_UNICODE 标志, 且实现不支持 UNICODE。</span><span class="sxs-lookup"><span data-stu-id="27abb-135">A client or service provider sets the MAPI_UNICODE flag on a method or function call and the implementation does not support Unicode.</span></span> <span data-ttu-id="27abb-136">设置 MAPI_UNICODE 指示作为输入传入的字符字符串是 unicode 字符串, 而传递回输出的字符串应为 unicode 字符串。</span><span class="sxs-lookup"><span data-stu-id="27abb-136">Setting MAPI_UNICODE indicates that character strings passed in as input are Unicode strings and that character strings passed back as output are expected to be Unicode strings.</span></span>
    
- <span data-ttu-id="27abb-137">客户端或服务提供程序不会在方法或函数调用上设置 MAPI_UNICODE 标志, 且实现仅支持 UNICODE。</span><span class="sxs-lookup"><span data-stu-id="27abb-137">A client or service provider does not set the MAPI_UNICODE flag on a method or function call and the implementation only supports Unicode.</span></span>
    

