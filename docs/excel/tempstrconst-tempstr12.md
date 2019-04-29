---
title: TempStrConst/TempStr12
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- TempStr12
- TempStrConst
keywords:
- tempstr12 函数 [excel 2007], TempStrConst 函数 [excel 2007]
localization_priority: Normal
ms.assetid: faf4ee4e-8d33-4cb3-ae16-5648a837ee4f
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: d93f9de021c7ba325d9c11af2cede0245ffbbf6b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33407149"
---
# <a name="tempstrconsttempstr12"></a><span data-ttu-id="e7295-104">TempStrConst/TempStr12</span><span class="sxs-lookup"><span data-stu-id="e7295-104">TempStrConst/TempStr12</span></span>

 <span data-ttu-id="e7295-105">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e7295-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="e7295-106">Framework library 函数, 该函数创建一个包含**xltypeStr**字符串的临时**XLOPER/XLOPER12** , 并采用以 null 结尾的源字符串作为输入。</span><span class="sxs-lookup"><span data-stu-id="e7295-106">Framework library function that creates a temporary **XLOPER/XLOPER12** that contains an **xltypeStr** string, taking a null-terminated source string as input.</span></span> <span data-ttu-id="e7295-107">函数分配一个新的内存缓冲区, 并将传入的字符串复制到该缓冲区中。</span><span class="sxs-lookup"><span data-stu-id="e7295-107">The function allocates a new memory buffer and copies the passed-in string into it.</span></span> <span data-ttu-id="e7295-108">输入字符串不会发生更改, 因此声明为**const**。</span><span class="sxs-lookup"><span data-stu-id="e7295-108">The input string is not altered and so is declared as **const**.</span></span>
  
```cs
LPXLOPER TempStrConst(const LPSTR str);
LPXLOPER12 TempStr12(const XCHAR* lpstr);
```

## <a name="parameters"></a><span data-ttu-id="e7295-109">参数</span><span class="sxs-lookup"><span data-stu-id="e7295-109">Parameters</span></span>

 <span data-ttu-id="e7295-110">_str_</span><span class="sxs-lookup"><span data-stu-id="e7295-110">_str_</span></span>
  
<span data-ttu-id="e7295-111">指向以 null 结尾的源字符串的指针。</span><span class="sxs-lookup"><span data-stu-id="e7295-111">A pointer to the null-terminated source string.</span></span> <span data-ttu-id="e7295-112">在**XLOPER**s 的情况下, TempStrConst 截断长度超过255字节的字符串。</span><span class="sxs-lookup"><span data-stu-id="e7295-112">In the case of **XLOPER**s, TempStrConst truncates strings that are longer than 255 bytes.</span></span> <span data-ttu-id="e7295-113">在**XLOPER12**s 的情况下, TempStr12Const 截断长度超过32767个 Unicode 字符的字符串。</span><span class="sxs-lookup"><span data-stu-id="e7295-113">In the case of **XLOPER12**s, TempStr12Const truncates strings that are longer than 32,767 Unicode characters.</span></span>
  
## <a name="return-value"></a><span data-ttu-id="e7295-114">返回值</span><span class="sxs-lookup"><span data-stu-id="e7295-114">Return value</span></span>

<span data-ttu-id="e7295-115">返回一个**xltypeStr**字符串, 该字符串包含传入的字符串缓冲区的副本。</span><span class="sxs-lookup"><span data-stu-id="e7295-115">Returns an **xltypeStr** string containing a copy of the passed-in string buffer.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="e7295-116">说明</span><span class="sxs-lookup"><span data-stu-id="e7295-116">Remarks</span></span>

<span data-ttu-id="e7295-117">请注意, **XLOPER**字符串框架函数**TempStr**的行为有所不同, 并尝试使用后面的字符串的长度覆盖所提供的字符串的第一个字符。</span><span class="sxs-lookup"><span data-stu-id="e7295-117">Note that the **XLOPER** string Framework function, **TempStr**, behaves differently and tries to overwrite the first character of the supplied string with the subsequent string's length.</span></span> <span data-ttu-id="e7295-118">但这并不总是安全的事情: 如果传递只读字符串, Microsoft Excel 可能会崩溃。</span><span class="sxs-lookup"><span data-stu-id="e7295-118">This is not always a safe thing to do: Microsoft Excel might crash if passed a read-only string.</span></span> <span data-ttu-id="e7295-119">这种创建临时字符串的方法现在已被弃用, 取而代之的是**TempStrConst**和**TempStr12**的工作方式。</span><span class="sxs-lookup"><span data-stu-id="e7295-119">This way of creating temporary strings is now deprecated in favor of the way in which both **TempStrConst** and **TempStr12** work.</span></span> <span data-ttu-id="e7295-120">因此, 输入字符串的第一个字符被视为字符串的开头, 即不是长度字符或长度字符的空格。</span><span class="sxs-lookup"><span data-stu-id="e7295-120">Therefore the first character of the input string is treated as the start of the string, that is, not as a length character or as a space for a length character.</span></span> <span data-ttu-id="e7295-121">您不应在开始时传递具有已编码的长度字符的字符串, 因为结果可能是不可预知的。</span><span class="sxs-lookup"><span data-stu-id="e7295-121">You should not pass strings that have a length character encoded at the start, as the consequences could be unpredictable.</span></span> 
  
## <a name="example"></a><span data-ttu-id="e7295-122">示例</span><span class="sxs-lookup"><span data-stu-id="e7295-122">Example</span></span>

<span data-ttu-id="e7295-123">此示例使用**TempStr12**函数为消息框创建字符串。</span><span class="sxs-lookup"><span data-stu-id="e7295-123">This example uses the **TempStr12** function to create a string for a message box.</span></span> 
  
 `\SAMPLES\EXAMPLE\EXAMPLE.C`
  
```cs
short WINAPI TempStrExample(void)
{
   Excel12f(xlcAlert, 0, 1, TempStr12Const(L"Made it!"));
   return 1;
}
```

## <a name="see-also"></a><span data-ttu-id="e7295-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e7295-124">See also</span></span>



[<span data-ttu-id="e7295-125">框架库中的函数</span><span class="sxs-lookup"><span data-stu-id="e7295-125">Functions in the Framework Library</span></span>](functions-in-the-framework-library.md)

