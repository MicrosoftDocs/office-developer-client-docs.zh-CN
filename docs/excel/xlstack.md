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
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 55ceed93407b1d99e05bc20fb6ce0b22459de7df
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32310155"
---
# <a name="xlstack"></a><span data-ttu-id="99da6-104">xlStack</span><span class="sxs-lookup"><span data-stu-id="99da6-104">xlStack</span></span>

<span data-ttu-id="99da6-105">**适用于** Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="99da6-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="99da6-106">检查堆栈中剩余的空间量。</span><span class="sxs-lookup"><span data-stu-id="99da6-106">Checks the amount of space left on the stack.</span></span>
  
```cs
Excel12(xlStack, LPXLOPER12 pxRes, 0);
```

## <a name="parameters"></a><span data-ttu-id="99da6-107">参数</span><span class="sxs-lookup"><span data-stu-id="99da6-107">Parameters</span></span>

<span data-ttu-id="99da6-108">此函数无需使用任何参数。</span><span class="sxs-lookup"><span data-stu-id="99da6-108">This function takes no arguments.</span></span>
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="99da6-109">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="99da6-109">Property value/Return value</span></span>

<span data-ttu-id="99da6-110">返回堆栈中剩余的字节数 (**xltypeInt**)。</span><span class="sxs-lookup"><span data-stu-id="99da6-110">Returns the number of bytes (**xltypeInt**) remaining on the stack.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="99da6-111">注解</span><span class="sxs-lookup"><span data-stu-id="99da6-111">Remarks</span></span>

<span data-ttu-id="99da6-112">最新版本的可用堆栈空间量溢出**XLOPER**的16位带符号整数。</span><span class="sxs-lookup"><span data-stu-id="99da6-112">The amount of available stack space of recent versions overflows the 16-bit signed integer of the **XLOPER**.</span></span> <span data-ttu-id="99da6-113">这意味着, 当使用**XLOPER**s 和**Excel4**或**Excel4v**调用时, **xlStack**可以返回介于-32767 和32768之间的值。</span><span class="sxs-lookup"><span data-stu-id="99da6-113">This means that **xlStack** can return a value between -32767 and 32768 when called using **XLOPER**s and **Excel4** or **Excel4v**.</span></span> <span data-ttu-id="99da6-114">若要在这种情况下获取正确的值, 必须将返回的值转换为无符号的短整型值。</span><span class="sxs-lookup"><span data-stu-id="99da6-114">To obtain the correct value in this case, you must cast the returned value to an unsigned short.</span></span>
  
<span data-ttu-id="99da6-115">从 Excel 2007 开始, 应使用**XLOPER12**s 和**Excel12**或**Excel12v**调用此函数, 在这种情况下, 返回的值是可用的堆栈空间量或 64 KB (以较低者为准)。</span><span class="sxs-lookup"><span data-stu-id="99da6-115">Starting in Excel 2007, you should call this function using **XLOPER12**s and **Excel12** or **Excel12v**, in which case the returned value is amount of stack space available or 64 KB, whichever is the lesser.</span></span>
  
<span data-ttu-id="99da6-116">Excel 在堆栈上的空间量有限, 应注意不要使此空间溢出。</span><span class="sxs-lookup"><span data-stu-id="99da6-116">Excel has a limited amount of space on the stack, and you should take care not to overrun this space.</span></span> <span data-ttu-id="99da6-117">永远不要将非常大的数据结构放在堆栈上, 并将任意多个局部变量作为可能的静态变量。</span><span class="sxs-lookup"><span data-stu-id="99da6-117">Never put very large data structures on the stack, and make as many local variables as possible static.</span></span> <span data-ttu-id="99da6-118">避免以递归方式调用函数, 因为这将迅速填满堆栈。</span><span class="sxs-lookup"><span data-stu-id="99da6-118">Avoid calling functions recursively, because that will quickly fill up the stack.</span></span>
  
<span data-ttu-id="99da6-119">如果您怀疑您正在 overrunning 堆栈, 请经常调用此函数以查看剩余的堆栈空间量。</span><span class="sxs-lookup"><span data-stu-id="99da6-119">If you suspect that you are overrunning the stack, call this function frequently to see how much stack space is left.</span></span>
  
## <a name="example"></a><span data-ttu-id="99da6-120">示例</span><span class="sxs-lookup"><span data-stu-id="99da6-120">Example</span></span>

<span data-ttu-id="99da6-121">第一个示例显示一条警告消息, 其中包含剩余的堆栈空间量, 包含`\SAMPLES\EXAMPLE\EXAMPLE.C`在中。</span><span class="sxs-lookup"><span data-stu-id="99da6-121">The first example displays an alert message containing the amount of stack space left and is contained in  `\SAMPLES\EXAMPLE\EXAMPLE.C`.</span></span> <span data-ttu-id="99da6-122">第二个示例执行相同的操作, 使用**XLOPER**s 且不包含在 SDK 示例代码中。</span><span class="sxs-lookup"><span data-stu-id="99da6-122">The second example does the same thing, working with **XLOPER**s and is not contained in the SDK example code.</span></span>
  
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

## <a name="see-also"></a><span data-ttu-id="99da6-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="99da6-123">See also</span></span>

- [<span data-ttu-id="99da6-124">只能从 DLL 或 XLL 调用的 C API 函数</span><span class="sxs-lookup"><span data-stu-id="99da6-124">C API Functions That Can Be Called Only from a DLL or XLL</span></span>](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)

