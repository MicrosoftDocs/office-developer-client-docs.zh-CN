---
title: TempStr
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- TempStr
keywords:
- tempstr 函数 [excel 2007]
localization_priority: Normal
ms.assetid: b21b4868-babe-4255-9093-503172efa045
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 4ccb6f3c764371c35bac12c8c78fede54234a7d6
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32310316"
---
# <a name="tempstr"></a><span data-ttu-id="7df0c-104">TempStr</span><span class="sxs-lookup"><span data-stu-id="7df0c-104">TempStr</span></span>

 <span data-ttu-id="7df0c-105">**适用于** Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="7df0c-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="7df0c-106">弃用的 Framework 库函数, 用于创建包含**xltypeStr**字节字符串的临时**XLOPER** 。</span><span class="sxs-lookup"><span data-stu-id="7df0c-106">Deprecated Framework library function that creates a temporary **XLOPER** containing an **xltypeStr** byte string.</span></span> <span data-ttu-id="7df0c-107">它采用以 null 结尾的源字符串作为输入。</span><span class="sxs-lookup"><span data-stu-id="7df0c-107">It takes a null-terminated source string as input.</span></span> <span data-ttu-id="7df0c-108">它尝试使用后面的字符串的长度覆盖所提供的字符串的第一个字符。</span><span class="sxs-lookup"><span data-stu-id="7df0c-108">It tries to overwrite the first character of the supplied string with the subsequent string's length.</span></span> <span data-ttu-id="7df0c-109">但这并不总是安全的事情: 如果传递只读字符串, Microsoft Excel 可能会崩溃。</span><span class="sxs-lookup"><span data-stu-id="7df0c-109">This is not always a safe thing to do: Microsoft Excel might crash if passed a read-only string.</span></span> 
  
```cs
LPXLOPER TempStr(LPSTR str);
```

## <a name="parameters"></a><span data-ttu-id="7df0c-110">参数</span><span class="sxs-lookup"><span data-stu-id="7df0c-110">Parameters</span></span>

 <span data-ttu-id="7df0c-111">_str_</span><span class="sxs-lookup"><span data-stu-id="7df0c-111">_str_</span></span>
  
<span data-ttu-id="7df0c-112">指向以 null 结尾的源字符串的指针。</span><span class="sxs-lookup"><span data-stu-id="7df0c-112">A pointer to the null-terminated source string.</span></span> <span data-ttu-id="7df0c-113">**TempStr**截断超过255字节的字符串。</span><span class="sxs-lookup"><span data-stu-id="7df0c-113">**TempStr** truncates strings that are longer than 255 bytes.</span></span> 
  
## <a name="return-value"></a><span data-ttu-id="7df0c-114">返回值</span><span class="sxs-lookup"><span data-stu-id="7df0c-114">Return value</span></span>

<span data-ttu-id="7df0c-115">返回一个**xltypeStr**字符串, 该字符串包含指向传入的字符串缓冲区的指针。</span><span class="sxs-lookup"><span data-stu-id="7df0c-115">Returns an **xltypeStr** string containing a pointer to the passed-in string buffer.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="7df0c-116">注解</span><span class="sxs-lookup"><span data-stu-id="7df0c-116">Remarks</span></span>

<span data-ttu-id="7df0c-117">这种创建临时字符串的方法现在已被弃用, 取而代之的是[TempStrConst 和 TempStr12](tempstrconst-tempstr12.md)的工作方式。</span><span class="sxs-lookup"><span data-stu-id="7df0c-117">This way of creating temporary strings is now deprecated in favor of the way in which both [TempStrConst and TempStr12](tempstrconst-tempstr12.md) work.</span></span> <span data-ttu-id="7df0c-118">这些函数分配一个新的内存缓冲区, 并将传入的字符串复制到该缓冲区中。</span><span class="sxs-lookup"><span data-stu-id="7df0c-118">These functions allocate a new memory buffer and copy the passed-in string into it.</span></span> <span data-ttu-id="7df0c-119">**TempStrConst**和**TempStr12**的输入字符串不会发生更改, 因此声明为**const**。</span><span class="sxs-lookup"><span data-stu-id="7df0c-119">The input strings for **TempStrConst** and **TempStr12** are not altered and so are declared as **const**.</span></span> <span data-ttu-id="7df0c-120">相比之下, **TempStr**的输入字符串已更改, 因此不能声明为**const**。</span><span class="sxs-lookup"><span data-stu-id="7df0c-120">In contrast, the input string to **TempStr** is altered and so cannot be declared as **const**.</span></span> <span data-ttu-id="7df0c-121">输入字符串的第一个字符被视为长度字符的空格, 并被此函数覆盖。</span><span class="sxs-lookup"><span data-stu-id="7df0c-121">The first character of the input string is treated as space for a length character and is overwritten by this function.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7df0c-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7df0c-122">See also</span></span>



[<span data-ttu-id="7df0c-123">框架库中的函数</span><span class="sxs-lookup"><span data-stu-id="7df0c-123">Functions in the Framework Library</span></span>](functions-in-the-framework-library.md)

