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
- tempstr12 函数 [excel 2007]，TempStrConst 函数 [Excel 2007]
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
# <a name="tempstrconsttempstr12"></a><span data-ttu-id="ec470-104">TempStrConst/TempStr12</span><span class="sxs-lookup"><span data-stu-id="ec470-104">TempStrConst/TempStr12</span></span>

 <span data-ttu-id="ec470-105">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ec470-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="ec470-106">创建包含 **xltypeStr** 字符串的临时 **XLOPER/XLOPER12** 的框架库函数，以以 null 结尾的源字符串作为输入。</span><span class="sxs-lookup"><span data-stu-id="ec470-106">Framework library function that creates a temporary **XLOPER/XLOPER12** that contains an **xltypeStr** string, taking a null-terminated source string as input.</span></span> <span data-ttu-id="ec470-107">函数分配新的内存缓冲区，将传入的字符串复制到该缓冲区中。</span><span class="sxs-lookup"><span data-stu-id="ec470-107">The function allocates a new memory buffer and copies the passed-in string into it.</span></span> <span data-ttu-id="ec470-108">输入字符串不会更改，因此声明为 **const**。</span><span class="sxs-lookup"><span data-stu-id="ec470-108">The input string is not altered and so is declared as **const**.</span></span>
  
```cs
LPXLOPER TempStrConst(const LPSTR str);
LPXLOPER12 TempStr12(const XCHAR* lpstr);
```

## <a name="parameters"></a><span data-ttu-id="ec470-109">参数</span><span class="sxs-lookup"><span data-stu-id="ec470-109">Parameters</span></span>

 <span data-ttu-id="ec470-110">_str_</span><span class="sxs-lookup"><span data-stu-id="ec470-110">_str_</span></span>
  
<span data-ttu-id="ec470-111">指向以 null 结尾的源字符串的指针。</span><span class="sxs-lookup"><span data-stu-id="ec470-111">A pointer to the null-terminated source string.</span></span> <span data-ttu-id="ec470-112">对于 **XLOPER，TempStrConst** 将截断长度超过 255 字节的字符串。</span><span class="sxs-lookup"><span data-stu-id="ec470-112">In the case of **XLOPER** s, TempStrConst truncates strings that are longer than 255 bytes.</span></span> <span data-ttu-id="ec470-113">对于 **XLOPER12，TempStr12Const** 将截断长度超过 32，767 Unicode 字符的字符串。</span><span class="sxs-lookup"><span data-stu-id="ec470-113">In the case of **XLOPER12** s, TempStr12Const truncates strings that are longer than 32,767 Unicode characters.</span></span>
  
## <a name="return-value"></a><span data-ttu-id="ec470-114">返回值</span><span class="sxs-lookup"><span data-stu-id="ec470-114">Return value</span></span>

<span data-ttu-id="ec470-115">返回一 **个 xltypeStr** 字符串，其中包含传入字符串缓冲区的副本。</span><span class="sxs-lookup"><span data-stu-id="ec470-115">Returns an **xltypeStr** string containing a copy of the passed-in string buffer.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="ec470-116">备注</span><span class="sxs-lookup"><span data-stu-id="ec470-116">Remarks</span></span>

<span data-ttu-id="ec470-117">请注意 **，XLOPER** 字符串 Framework 函数 **TempStr** 的行为不同，并尝试使用后续字符串的长度覆盖所提供字符串的第一个字符。</span><span class="sxs-lookup"><span data-stu-id="ec470-117">Note that the **XLOPER** string Framework function, **TempStr**, behaves differently and tries to overwrite the first character of the supplied string with the subsequent string's length.</span></span> <span data-ttu-id="ec470-118">这并不总是一个安全的方法：如果传递了只读字符串，Microsoft Excel 可能会崩溃。</span><span class="sxs-lookup"><span data-stu-id="ec470-118">This is not always a safe thing to do: Microsoft Excel might crash if passed a read-only string.</span></span> <span data-ttu-id="ec470-119">这种创建临时字符串的方法现已弃用，支持 **TempStrConst** 和 **TempStr12 的** 正常工作方式。</span><span class="sxs-lookup"><span data-stu-id="ec470-119">This way of creating temporary strings is now deprecated in favor of the way in which both **TempStrConst** and **TempStr12** work.</span></span> <span data-ttu-id="ec470-120">因此，输入字符串的第一个字符被视为字符串的开头，即不作为长度字符或长度字符的空格。</span><span class="sxs-lookup"><span data-stu-id="ec470-120">Therefore the first character of the input string is treated as the start of the string, that is, not as a length character or as a space for a length character.</span></span> <span data-ttu-id="ec470-121">不应传递在开始时编码有长度字符的字符串，因为后果可能是不可预知的。</span><span class="sxs-lookup"><span data-stu-id="ec470-121">You should not pass strings that have a length character encoded at the start, as the consequences could be unpredictable.</span></span> 
  
## <a name="example"></a><span data-ttu-id="ec470-122">示例</span><span class="sxs-lookup"><span data-stu-id="ec470-122">Example</span></span>

<span data-ttu-id="ec470-123">此示例使用 **TempStr12** 函数为消息框创建字符串。</span><span class="sxs-lookup"><span data-stu-id="ec470-123">This example uses the **TempStr12** function to create a string for a message box.</span></span> 
  
 `\SAMPLES\EXAMPLE\EXAMPLE.C`
  
```cs
short WINAPI TempStrExample(void)
{
   Excel12f(xlcAlert, 0, 1, TempStr12Const(L"Made it!"));
   return 1;
}
```

## <a name="see-also"></a><span data-ttu-id="ec470-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ec470-124">See also</span></span>



[<span data-ttu-id="ec470-125">框架库中的函数</span><span class="sxs-lookup"><span data-stu-id="ec470-125">Functions in the Framework Library</span></span>](functions-in-the-framework-library.md)

