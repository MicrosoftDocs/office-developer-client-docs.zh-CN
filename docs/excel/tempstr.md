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
ms.openlocfilehash: ce9399168d5b94d10481d2d0b5b69dd2e1d1d2e9
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773824"
---
# <a name="tempstr"></a><span data-ttu-id="e6344-104">TempStr</span><span class="sxs-lookup"><span data-stu-id="e6344-104">TempStr</span></span>

 <span data-ttu-id="e6344-105">**适用于** Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e6344-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="e6344-106">创建包含**xltypeStr**字节字符串临时**XLOPER**的弃用的 Framework 库函数。</span><span class="sxs-lookup"><span data-stu-id="e6344-106">Deprecated Framework library function that creates a temporary **XLOPER** containing an **xltypeStr** byte string.</span></span> <span data-ttu-id="e6344-107">它将 null 结尾的源字符串作为输入。</span><span class="sxs-lookup"><span data-stu-id="e6344-107">It takes a null-terminated source string as input.</span></span> <span data-ttu-id="e6344-108">它会尝试使用后面的字符串长度覆盖所提供的字符串的第一个字符。</span><span class="sxs-lookup"><span data-stu-id="e6344-108">It tries to overwrite the first character of the supplied string with the subsequent string's length.</span></span> <span data-ttu-id="e6344-109">这并不总是安全的做法： 如果传递的只读的字符串，Microsoft Excel 可能崩溃。</span><span class="sxs-lookup"><span data-stu-id="e6344-109">This is not always a safe thing to do: Microsoft Excel might crash if passed a read-only string.</span></span> 
  
```cs
LPXLOPER TempStr(LPSTR str);
```

## <a name="parameters"></a><span data-ttu-id="e6344-110">参数</span><span class="sxs-lookup"><span data-stu-id="e6344-110">Parameters</span></span>

 <span data-ttu-id="e6344-111">_str_</span><span class="sxs-lookup"><span data-stu-id="e6344-111">_str_</span></span>
  
<span data-ttu-id="e6344-112">一个指向 null 结尾的源字符串。</span><span class="sxs-lookup"><span data-stu-id="e6344-112">A pointer to the null-terminated source string.</span></span> <span data-ttu-id="e6344-113">**TempStr**截断字符串的长度超过 255 个字节。</span><span class="sxs-lookup"><span data-stu-id="e6344-113">**TempStr** truncates strings that are longer than 255 bytes.</span></span> 
  
## <a name="return-value"></a><span data-ttu-id="e6344-114">返回值</span><span class="sxs-lookup"><span data-stu-id="e6344-114">Return value</span></span>

<span data-ttu-id="e6344-115">返回包含一个指向传入的字符串缓冲区**xltypeStr**字符串。</span><span class="sxs-lookup"><span data-stu-id="e6344-115">Returns an **xltypeStr** string containing a pointer to the passed-in string buffer.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="e6344-116">说明</span><span class="sxs-lookup"><span data-stu-id="e6344-116">Remarks</span></span>

<span data-ttu-id="e6344-117">创建临时字符串的这种方式以的两个[TempStrConst 和 TempStr12](tempstrconst-tempstr12.md)工作方式应用现已被否决。</span><span class="sxs-lookup"><span data-stu-id="e6344-117">This way of creating temporary strings is now deprecated in favor of the way in which both [TempStrConst and TempStr12](tempstrconst-tempstr12.md) work.</span></span> <span data-ttu-id="e6344-118">这些函数分配新内存缓冲区，并复制到它的传入的字符串。</span><span class="sxs-lookup"><span data-stu-id="e6344-118">These functions allocate a new memory buffer and copy the passed-in string into it.</span></span> <span data-ttu-id="e6344-119">**TempStrConst**和**TempStr12**的输入的字符串不会改动，并因此声明为**常量**。</span><span class="sxs-lookup"><span data-stu-id="e6344-119">The input strings for **TempStrConst** and **TempStr12** are not altered and so are declared as **const**.</span></span> <span data-ttu-id="e6344-120">相比之下， **TempStr**的输入的字符串更改，因此不能声明为**const**。</span><span class="sxs-lookup"><span data-stu-id="e6344-120">In contrast, the input string to **TempStr** is altered and so cannot be declared as **const**.</span></span> <span data-ttu-id="e6344-121">输入字符串的第一个字符视为长度字符的空间，并覆盖此函数。</span><span class="sxs-lookup"><span data-stu-id="e6344-121">The first character of the input string is treated as space for a length character and is overwritten by this function.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e6344-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e6344-122">See also</span></span>



[<span data-ttu-id="e6344-123">框架库中的函数</span><span class="sxs-lookup"><span data-stu-id="e6344-123">Functions in the Framework Library</span></span>](functions-in-the-framework-library.md)

