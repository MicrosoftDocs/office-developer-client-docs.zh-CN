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
ms.openlocfilehash: fcd073f7d2b97e84743d01c498435f186277e345
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773859"
---
# <a name="xlstack"></a><span data-ttu-id="68a29-104">xlStack</span><span class="sxs-lookup"><span data-stu-id="68a29-104">xlStack</span></span>

<span data-ttu-id="68a29-105">**适用于** Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="68a29-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="68a29-106">检查堆栈中的剩余空间量。</span><span class="sxs-lookup"><span data-stu-id="68a29-106">Checks the amount of space left on the stack.</span></span>
  
```cs
Excel12(xlStack, LPXLOPER12 pxRes, 0);
```

## <a name="parameters"></a><span data-ttu-id="68a29-107">参数</span><span class="sxs-lookup"><span data-stu-id="68a29-107">Parameters</span></span>

<span data-ttu-id="68a29-108">此函数无需使用任何参数。</span><span class="sxs-lookup"><span data-stu-id="68a29-108">This function takes no arguments.</span></span>
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="68a29-109">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="68a29-109">Property value/Return value</span></span>

<span data-ttu-id="68a29-110">返回的字节数 (**xltypeInt**) 保持堆栈。</span><span class="sxs-lookup"><span data-stu-id="68a29-110">Returns the number of bytes (**xltypeInt**) remaining on the stack.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="68a29-111">说明</span><span class="sxs-lookup"><span data-stu-id="68a29-111">Remarks</span></span>

<span data-ttu-id="68a29-112">最新版本的可用堆栈空间量溢出**XLOPER**16 位有符号的整数。</span><span class="sxs-lookup"><span data-stu-id="68a29-112">The amount of available stack space of recent versions overflows the 16-bit signed integer of the **XLOPER**.</span></span> <span data-ttu-id="68a29-113">这意味着该**xlStack**可-32767 之间 32768 调用使用**XLOPER**s 和**Excel4**或**Excel4v**时返回的值。</span><span class="sxs-lookup"><span data-stu-id="68a29-113">This means that **xlStack** can return a value between -32767 and 32768 when called using **XLOPER**s and **Excel4** or **Excel4v**.</span></span> <span data-ttu-id="68a29-114">若要在这种情况下获取正确的值，必须转换为无符号短返回的值。</span><span class="sxs-lookup"><span data-stu-id="68a29-114">To obtain the correct value in this case, you must cast the returned value to an unsigned short.</span></span>
  
<span data-ttu-id="68a29-115">在 Excel 2007 中，您应调用此函数使用**XLOPER12**s 和**Excel12**或**Excel12v**，在其中 case 返回的值是可用的堆栈空间量或 64 KB，无论哪个都有启动。</span><span class="sxs-lookup"><span data-stu-id="68a29-115">Starting in Excel 2007, you should call this function using **XLOPER12**s and **Excel12** or **Excel12v**, in which case the returned value is amount of stack space available or 64 KB, whichever is the lesser.</span></span>
  
<span data-ttu-id="68a29-116">Excel 在堆栈，限制的空间量，您应注意不要溢出此空间。</span><span class="sxs-lookup"><span data-stu-id="68a29-116">Excel has a limited amount of space on the stack, and you should take care not to overrun this space.</span></span> <span data-ttu-id="68a29-117">从不将非常大的数据结构置于堆栈，并尽可能静态使任意数量的本地变量。</span><span class="sxs-lookup"><span data-stu-id="68a29-117">Never put very large data structures on the stack, and make as many local variables as possible static.</span></span> <span data-ttu-id="68a29-118">避免调用函数以递归方式，因为它会迅速填满堆栈。</span><span class="sxs-lookup"><span data-stu-id="68a29-118">Avoid calling functions recursively, because that will quickly fill up the stack.</span></span>
  
<span data-ttu-id="68a29-119">如果您怀疑您致使溢出堆栈，调用此函数经常可看到剩余堆栈空间。</span><span class="sxs-lookup"><span data-stu-id="68a29-119">If you suspect that you are overrunning the stack, call this function frequently to see how much stack space is left.</span></span>
  
## <a name="example"></a><span data-ttu-id="68a29-120">示例</span><span class="sxs-lookup"><span data-stu-id="68a29-120">Example</span></span>

<span data-ttu-id="68a29-121">第一个示例显示包含堆栈空间剩余的一条警告消息，并包含在`\SAMPLES\EXAMPLE\EXAMPLE.C`。</span><span class="sxs-lookup"><span data-stu-id="68a29-121">The first example displays an alert message containing the amount of stack space left and is contained in  `\SAMPLES\EXAMPLE\EXAMPLE.C`.</span></span> <span data-ttu-id="68a29-122">第二个示例执行同样的任务，使用**XLOPER**s，并且未包含在 SDK 示例代码。</span><span class="sxs-lookup"><span data-stu-id="68a29-122">The second example does the same thing, working with **XLOPER**s and is not contained in the SDK example code.</span></span>
  
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

## <a name="see-also"></a><span data-ttu-id="68a29-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="68a29-123">See also</span></span>

- [<span data-ttu-id="68a29-124">只能从 DLL 或 XLL 调用的 C API 函数</span><span class="sxs-lookup"><span data-stu-id="68a29-124">C API Functions That Can Be Called Only from a DLL or XLL</span></span>](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)

