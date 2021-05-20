---
title: xlStack
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- xlStack
keywords:
- xlstack 函数 [excel 2007]
localization_priority: Normal
ms.assetid: f9f030e8-1ec9-4cbf-92e1-360526260916
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 55ceed93407b1d99e05bc20fb6ce0b22459de7df
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33429977"
---
# <a name="xlstack"></a><span data-ttu-id="d37d9-104">xlStack</span><span class="sxs-lookup"><span data-stu-id="d37d9-104">xlStack</span></span>

<span data-ttu-id="d37d9-105">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="d37d9-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="d37d9-106">检查堆栈上留下的空间量。</span><span class="sxs-lookup"><span data-stu-id="d37d9-106">Checks the amount of space left on the stack.</span></span>
  
```cs
Excel12(xlStack, LPXLOPER12 pxRes, 0);
```

## <a name="parameters"></a><span data-ttu-id="d37d9-107">参数</span><span class="sxs-lookup"><span data-stu-id="d37d9-107">Parameters</span></span>

<span data-ttu-id="d37d9-108">此函数无需使用任何参数。</span><span class="sxs-lookup"><span data-stu-id="d37d9-108">This function takes no arguments.</span></span>
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="d37d9-109">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="d37d9-109">Property value/Return value</span></span>

<span data-ttu-id="d37d9-110">返回堆栈上 (**xltypeInt)** 字节数。</span><span class="sxs-lookup"><span data-stu-id="d37d9-110">Returns the number of bytes (**xltypeInt**) remaining on the stack.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="d37d9-111">备注</span><span class="sxs-lookup"><span data-stu-id="d37d9-111">Remarks</span></span>

<span data-ttu-id="d37d9-112">最新版本的可用堆栈空间量会溢出 **XLOPER** 的 16 位有符号整数。</span><span class="sxs-lookup"><span data-stu-id="d37d9-112">The amount of available stack space of recent versions overflows the 16-bit signed integer of the **XLOPER**.</span></span> <span data-ttu-id="d37d9-113">这意味着在使用 **XLOPER** s 和 Excel4 或 **Excel4v** 调用 **xlStack** 时，可能会返回 -32767 和 32768 **之间的值**。</span><span class="sxs-lookup"><span data-stu-id="d37d9-113">This means that **xlStack** can return a value between -32767 and 32768 when called using **XLOPER** s and **Excel4** or **Excel4v**.</span></span> <span data-ttu-id="d37d9-114">若要在这种情况下获取正确的值，必须将返回的值强制转换到无符号短整。</span><span class="sxs-lookup"><span data-stu-id="d37d9-114">To obtain the correct value in this case, you must cast the returned value to an unsigned short.</span></span>
  
<span data-ttu-id="d37d9-115">从 Excel 2007 开始，您应使用 **XLOPER12** s 和 **Excel12** 或 **Excel12v** 调用此函数，在这种情况下，返回的值是可用的堆栈空间量或 64 KB（以较小者为准）。</span><span class="sxs-lookup"><span data-stu-id="d37d9-115">Starting in Excel 2007, you should call this function using **XLOPER12** s and **Excel12** or **Excel12v**, in which case the returned value is amount of stack space available or 64 KB, whichever is the lesser.</span></span>
  
<span data-ttu-id="d37d9-116">Excel堆栈上的空间有限，你应该注意不要溢出此空间。</span><span class="sxs-lookup"><span data-stu-id="d37d9-116">Excel has a limited amount of space on the stack, and you should take care not to overrun this space.</span></span> <span data-ttu-id="d37d9-117">切勿在堆栈上放入非常大的数据结构，并且使尽可能多的本地变量静态。</span><span class="sxs-lookup"><span data-stu-id="d37d9-117">Never put very large data structures on the stack, and make as many local variables as possible static.</span></span> <span data-ttu-id="d37d9-118">避免以递归式调用函数，因为这会迅速填满堆栈。</span><span class="sxs-lookup"><span data-stu-id="d37d9-118">Avoid calling functions recursively, because that will quickly fill up the stack.</span></span>
  
<span data-ttu-id="d37d9-119">如果您怀疑您溢出堆栈，请经常调用此函数以查看所剩的堆栈空间。</span><span class="sxs-lookup"><span data-stu-id="d37d9-119">If you suspect that you are overrunning the stack, call this function frequently to see how much stack space is left.</span></span>
  
## <a name="example"></a><span data-ttu-id="d37d9-120">示例</span><span class="sxs-lookup"><span data-stu-id="d37d9-120">Example</span></span>

<span data-ttu-id="d37d9-121">第一个示例显示一条警报消息，其中包含左侧堆栈空间量，并包含在 中  `\SAMPLES\EXAMPLE\EXAMPLE.C` 。</span><span class="sxs-lookup"><span data-stu-id="d37d9-121">The first example displays an alert message containing the amount of stack space left and is contained in  `\SAMPLES\EXAMPLE\EXAMPLE.C`.</span></span> <span data-ttu-id="d37d9-122">第二个示例执行相同的工作，即使用 **XLOPER，** 并且不包含在 SDK 示例代码中。</span><span class="sxs-lookup"><span data-stu-id="d37d9-122">The second example does the same thing, working with **XLOPER** s and is not contained in the SDK example code.</span></span>
  
```cs
short WINAPI xlStackExample(void)
{
   XLOPER12 xRes;
   Excel12(xlStack, &xRes, 0);
   Excel12(xlcAlert, 0, 1, (LPXLOPER12)&xRes);
   return 1;
} 
short int WINAPI xlStackExample_XLOPER(void)
{
    XLOPER xRes;
    Excel4(xlStack, (LPXLOPER)&xRes, 0);
    xRes.xltype = xltypeNum; // Change the type to double
    // Cast to an unsigned short to get rid of the overflow problem
    xRes.val.num = (double)(unsigned short) xRes.val.w;
    Excel4(xlcAlert, 0, 1, (LPXLOPER)& xRes);
    return 1;
}
```

## <a name="see-also"></a><span data-ttu-id="d37d9-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d37d9-123">See also</span></span>

- [<span data-ttu-id="d37d9-124">只能从 DLL 或 XLL 调用的 C API 函数</span><span class="sxs-lookup"><span data-stu-id="d37d9-124">C API Functions That Can Be Called Only from a DLL or XLL</span></span>](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)

