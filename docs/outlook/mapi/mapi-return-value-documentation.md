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
ms.openlocfilehash: f2b8f87987f93ec152d4986131a6b7990273c28d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776318"
---
# <a name="mapi-return-value-documentation"></a><span data-ttu-id="aad25-103">MAPI 返回值文档</span><span class="sxs-lookup"><span data-stu-id="aad25-103">MAPI Return Value Documentation</span></span>

  
  
<span data-ttu-id="aad25-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="aad25-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="aad25-105">本参考中的引用条目文档仅这些客户端应用程序需要一些处理的返回值。</span><span class="sxs-lookup"><span data-stu-id="aad25-105">The reference entries in this Reference document only those return values that require some handling by client applications.</span></span> <span data-ttu-id="aad25-106">返回值指示常见错误条件，可以通过检查失败推导不包含文档中。</span><span class="sxs-lookup"><span data-stu-id="aad25-106">Return values that indicate common error conditions and can be deduced by checking for failure are not included in the documentation.</span></span> <span data-ttu-id="aad25-107">例如，很多接口方法可以返回 MAPI_E_INVALID_PARAMETER，如果呼叫者指定输入参数的错误值。</span><span class="sxs-lookup"><span data-stu-id="aad25-107">For example, many interface methods can return MAPI_E_INVALID_PARAMETER if a caller specifies the wrong value for an input parameter.</span></span> <span data-ttu-id="aad25-108">此值未通常列出集中预期的返回值的原因是存在不需要专门为 MAPI_E_INVALID_PARAMETER 查找和无需从任何其他错误处理也不同。</span><span class="sxs-lookup"><span data-stu-id="aad25-108">This value is typically not listed in the set of expected return values because there is no need to look specifically for MAPI_E_INVALID_PARAMETER and no need to process it differently from any other error.</span></span> <span data-ttu-id="aad25-109">另一方面，某些服务提供程序不支持事件通知，并将所做的客户端通过**IMAPISession** **Advise**方法返回 MAPI_E_NO_SUPPORT。</span><span class="sxs-lookup"><span data-stu-id="aad25-109">On the other hand, some service providers do not support event notification and will return MAPI_E_NO_SUPPORT to the **Advise** method made by clients through **IMAPISession**.</span></span> <span data-ttu-id="aad25-110">由于客户端需要显式检查此值，并提供用于处理它所表示的条件的代码应发生此错误，MAPI_E_NO_SUPPORT 纳入[IMAPISession::Advise](imapisession-advise.md)返回值的列表。</span><span class="sxs-lookup"><span data-stu-id="aad25-110">Because clients need to explicitly check for this value and provide code for handling the condition that it represents should it occur, MAPI_E_NO_SUPPORT is included in the list of return values for [IMAPISession::Advise](imapisession-advise.md).</span></span>
  
<span data-ttu-id="aad25-111">下表描述通常会返回从方法和函数，并且需要进行客户端或服务提供程序需要显式处理的错误值。</span><span class="sxs-lookup"><span data-stu-id="aad25-111">The following table describes error values that are commonly returned from methods and functions and require explicit handling on the part of a client or service provider.</span></span> <span data-ttu-id="aad25-112">这些值分为四个类别： 表示无效输入的数据、 指示资源问题值、 指示字符集不兼容，值和指示来源未知失败的值。</span><span class="sxs-lookup"><span data-stu-id="aad25-112">These values fall into four categories: values that indicate invalid input data, values that indicate resource problems, values that indicate character set incompatibility, and values that indicate failure of an unknown origin.</span></span>
  
|<span data-ttu-id="aad25-113">**返回值**</span><span class="sxs-lookup"><span data-stu-id="aad25-113">**Return value**</span></span>|<span data-ttu-id="aad25-114">**说明**</span><span class="sxs-lookup"><span data-stu-id="aad25-114">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="aad25-115">MAPI_E_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="aad25-115">MAPI_E_INVALID_PARAMETER</span></span>  <br/> |<span data-ttu-id="aad25-116">一个或多个参数传递到方法或函数不是有效。</span><span class="sxs-lookup"><span data-stu-id="aad25-116">One or more of the parameters passed into the method or functions were not valid.</span></span>  <br/> |
|<span data-ttu-id="aad25-117">MAPI_E_UNKNOWN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="aad25-117">MAPI_E_UNKNOWN_FLAGS</span></span>  <br/> |<span data-ttu-id="aad25-118">一个或多个 flags 参数值不是有效的。</span><span class="sxs-lookup"><span data-stu-id="aad25-118">One or more values for a flags parameter were not valid.</span></span>  <br/> |
|<span data-ttu-id="aad25-119">MAPI_E_DISK_ERROR</span><span class="sxs-lookup"><span data-stu-id="aad25-119">MAPI_E_DISK_ERROR</span></span>  <br/> |<span data-ttu-id="aad25-120">出现问题写入或从磁盘读取。</span><span class="sxs-lookup"><span data-stu-id="aad25-120">There was a problem writing to or reading from disk.</span></span>  <br/> |
|<span data-ttu-id="aad25-121">MAPI_E_NOT_ENOUGH_DISK</span><span class="sxs-lookup"><span data-stu-id="aad25-121">MAPI_E_NOT_ENOUGH_DISK</span></span>  <br/> |<span data-ttu-id="aad25-122">没有足够的磁盘空间时无法完成操作。</span><span class="sxs-lookup"><span data-stu-id="aad25-122">Not enough disk space was available to complete the operation.</span></span>  <br/> |
|<span data-ttu-id="aad25-123">MAPI_E_NOT_ENOUGH_MEMORY</span><span class="sxs-lookup"><span data-stu-id="aad25-123">MAPI_E_NOT_ENOUGH_MEMORY</span></span>  <br/> |<span data-ttu-id="aad25-124">没有足够的内存已无法完成操作。</span><span class="sxs-lookup"><span data-stu-id="aad25-124">Not enough memory was available to complete the operation.</span></span>  <br/> |
|<span data-ttu-id="aad25-125">MAPI_E_NOT_ENOUGH_RESOURCES</span><span class="sxs-lookup"><span data-stu-id="aad25-125">MAPI_E_NOT_ENOUGH_RESOURCES</span></span>  <br/> |<span data-ttu-id="aad25-126">没有足够的系统资源已无法完成操作。</span><span class="sxs-lookup"><span data-stu-id="aad25-126">Not enough system resources were available to complete the operation.</span></span>  <br/> |
|<span data-ttu-id="aad25-127">MAPI_E_BAD_CHARWIDTH</span><span class="sxs-lookup"><span data-stu-id="aad25-127">MAPI_E_BAD_CHARWIDTH</span></span>  <br/> |<span data-ttu-id="aad25-128">呼叫者和实现支持的字符集中存在不兼容。</span><span class="sxs-lookup"><span data-stu-id="aad25-128">An incompatibility exists in the character sets supported by the caller and the implementation.</span></span>  <br/> |
|<span data-ttu-id="aad25-129">MAPI_E_CALL_FAILED</span><span class="sxs-lookup"><span data-stu-id="aad25-129">MAPI_E_CALL_FAILED</span></span>  <br/> |<span data-ttu-id="aad25-130">出现意外的或未知的原点而言的错误。</span><span class="sxs-lookup"><span data-stu-id="aad25-130">An error of unexpected or unknown origin occurred.</span></span>  <br/> |
   
<span data-ttu-id="aad25-131">MAPICODE 列出了表示 MAPI 返回值的常量。H 头文件。</span><span class="sxs-lookup"><span data-stu-id="aad25-131">The constants that represent MAPI return values are listed in the MAPICODE.H header file.</span></span> <span data-ttu-id="aad25-132">部分常量将映射到 Win32 错误;在 Win32 标头文件中，WINERROR 找不到这些常量为数字值的映射。H。</span><span class="sxs-lookup"><span data-stu-id="aad25-132">Some of the constants map to Win32 errors; the mapping of these constants to numeric values can be found in the Win32 header file, WINERROR.H.</span></span>
  
<span data-ttu-id="aad25-133">可以通过任一参数验证 API 函数 MAPI 或一组的宏提供确定传入呼叫者的无效数据有关的错误。</span><span class="sxs-lookup"><span data-stu-id="aad25-133">Errors regarding invalid data passed in by a caller can be determined through either the parameter validation API functions provided by MAPI or a set of macros.</span></span> 
  
<span data-ttu-id="aad25-134">字符设置不兼容，则会发生发生以下情况之一：</span><span class="sxs-lookup"><span data-stu-id="aad25-134">Character set incompatibility arises when either of the following situations occurs:</span></span>
  
- <span data-ttu-id="aad25-135">客户端或服务提供程序设置的方法或函数调用 MAPI_UNICODE 标志和实现不支持 Unicode。</span><span class="sxs-lookup"><span data-stu-id="aad25-135">A client or service provider sets the MAPI_UNICODE flag on a method or function call and the implementation does not support Unicode.</span></span> <span data-ttu-id="aad25-136">设置 MAPI_UNICODE 指示作为输入中传递的字符串的 Unicode 字符串和字符串传递回作为输出会为 Unicode 字符串。</span><span class="sxs-lookup"><span data-stu-id="aad25-136">Setting MAPI_UNICODE indicates that character strings passed in as input are Unicode strings and that character strings passed back as output are expected to be Unicode strings.</span></span>
    
- <span data-ttu-id="aad25-137">客户端或服务提供程序的方法或函数调用未设置 MAPI_UNICODE 标志和实现仅支持 Unicode。</span><span class="sxs-lookup"><span data-stu-id="aad25-137">A client or service provider does not set the MAPI_UNICODE flag on a method or function call and the implementation only supports Unicode.</span></span>
    

