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
- tempstr12 函数 [excel 2007，] TempStrConst 函数 [Excel 2007]
localization_priority: Normal
ms.assetid: faf4ee4e-8d33-4cb3-ae16-5648a837ee4f
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 321c41aa87a3bfa0edc1d77ecc8fbe4b6a6a4730
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773827"
---
# <a name="tempstrconsttempstr12"></a><span data-ttu-id="2ec59-104">TempStrConst/TempStr12</span><span class="sxs-lookup"><span data-stu-id="2ec59-104">TempStrConst/TempStr12</span></span>

 <span data-ttu-id="2ec59-105">**适用于** Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="2ec59-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="2ec59-106">创建临时**XLOPER/XLOPER12**的框架库函数包含**xltypeStr**字符串，将作为输入 null 结尾的源字符串。</span><span class="sxs-lookup"><span data-stu-id="2ec59-106">Framework library function that creates a temporary **XLOPER/XLOPER12** that contains an **xltypeStr** string, taking a null-terminated source string as input.</span></span> <span data-ttu-id="2ec59-107">该函数分配新内存缓冲区，并向其复制传入的字符串。</span><span class="sxs-lookup"><span data-stu-id="2ec59-107">The function allocates a new memory buffer and copies the passed-in string into it.</span></span> <span data-ttu-id="2ec59-108">输入的字符串不会改动，并因此声明为**常量**。</span><span class="sxs-lookup"><span data-stu-id="2ec59-108">The input string is not altered and so is declared as **const**.</span></span>
  
```cs
LPXLOPER TempStrConst(const LPSTR str);
LPXLOPER12 TempStr12(const XCHAR* lpstr);
```

## <a name="parameters"></a><span data-ttu-id="2ec59-109">参数</span><span class="sxs-lookup"><span data-stu-id="2ec59-109">Parameters</span></span>

 <span data-ttu-id="2ec59-110">_str_</span><span class="sxs-lookup"><span data-stu-id="2ec59-110">_str_</span></span>
  
<span data-ttu-id="2ec59-111">一个指向 null 结尾的源字符串。</span><span class="sxs-lookup"><span data-stu-id="2ec59-111">A pointer to the null-terminated source string.</span></span> <span data-ttu-id="2ec59-112">对于**XLOPER**的 TempStrConst 截断字符串的长度超过 255 个字节。</span><span class="sxs-lookup"><span data-stu-id="2ec59-112">In the case of **XLOPER**s, TempStrConst truncates strings that are longer than 255 bytes.</span></span> <span data-ttu-id="2ec59-113">对于**XLOPER12**的 TempStr12Const 截断长度大于 32,767 Unicode 字符的字符串。</span><span class="sxs-lookup"><span data-stu-id="2ec59-113">In the case of **XLOPER12**s, TempStr12Const truncates strings that are longer than 32,767 Unicode characters.</span></span>
  
## <a name="return-value"></a><span data-ttu-id="2ec59-114">返回值</span><span class="sxs-lookup"><span data-stu-id="2ec59-114">Return value</span></span>

<span data-ttu-id="2ec59-115">返回包含字符串中传递缓冲区的副本**xltypeStr**字符串。</span><span class="sxs-lookup"><span data-stu-id="2ec59-115">Returns an **xltypeStr** string containing a copy of the passed-in string buffer.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="2ec59-116">说明</span><span class="sxs-lookup"><span data-stu-id="2ec59-116">Remarks</span></span>

<span data-ttu-id="2ec59-117">请注意**XLOPER**字符串框架函数， **TempStr**，会有所不同，并尝试使用后面的字符串长度覆盖所提供的字符串的第一个字符。</span><span class="sxs-lookup"><span data-stu-id="2ec59-117">Note that the **XLOPER** string Framework function, **TempStr**, behaves differently and tries to overwrite the first character of the supplied string with the subsequent string's length.</span></span> <span data-ttu-id="2ec59-118">这并不总是安全的做法： 如果传递的只读的字符串，Microsoft Excel 可能崩溃。</span><span class="sxs-lookup"><span data-stu-id="2ec59-118">This is not always a safe thing to do: Microsoft Excel might crash if passed a read-only string.</span></span> <span data-ttu-id="2ec59-119">创建临时字符串的这种方式以哪些**TempStrConst**和**TempStr12**工作方式应用现已被否决。</span><span class="sxs-lookup"><span data-stu-id="2ec59-119">This way of creating temporary strings is now deprecated in favor of the way in which both **TempStrConst** and **TempStr12** work.</span></span> <span data-ttu-id="2ec59-120">因此输入字符串的第一个字符被视为字符串的开头，即不作为长度字符或空格长度字符。</span><span class="sxs-lookup"><span data-stu-id="2ec59-120">Therefore the first character of the input string is treated as the start of the string, that is, not as a length character or as a space for a length character.</span></span> <span data-ttu-id="2ec59-121">不应将传递已长度字符编码开头，如下后果可能不可预测的字符串。</span><span class="sxs-lookup"><span data-stu-id="2ec59-121">You should not pass strings that have a length character encoded at the start, as the consequences could be unpredictable.</span></span> 
  
## <a name="example"></a><span data-ttu-id="2ec59-122">示例</span><span class="sxs-lookup"><span data-stu-id="2ec59-122">Example</span></span>

<span data-ttu-id="2ec59-123">本示例使用**TempStr12**函数创建一个消息框的字符串。</span><span class="sxs-lookup"><span data-stu-id="2ec59-123">This example uses the **TempStr12** function to create a string for a message box.</span></span> 
  
 `\SAMPLES\EXAMPLE\EXAMPLE.C`
  
```cs
short WINAPI TempStrExample(void)
{
   Excel12f(xlcAlert, 0, 1, TempStr12Const(L"Made it!"));
   return 1;
}
```

## <a name="see-also"></a><span data-ttu-id="2ec59-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2ec59-124">See also</span></span>



[<span data-ttu-id="2ec59-125">框架库中的函数</span><span class="sxs-lookup"><span data-stu-id="2ec59-125">Functions in the Framework Library</span></span>](functions-in-the-framework-library.md)

