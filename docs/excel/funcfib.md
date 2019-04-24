---
title: FuncFib
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- FuncFib
keywords:
- funcfib 函数 [excel 2007]
localization_priority: Normal
ms.assetid: 6a719f04-b2d1-4f87-a227-be561cbd3e49
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: fb8f0c12c27fb2c95007eb5006c1d8b90970f3ad
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32310834"
---
# <a name="funcfib"></a><span data-ttu-id="a1916-104">FuncFib</span><span class="sxs-lookup"><span data-stu-id="a1916-104">FuncFib</span></span>

 <span data-ttu-id="a1916-105">**适用于** Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="a1916-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="a1916-106">用于计算第 n 个斐波纳契数的用户定义的工作表函数示例。</span><span class="sxs-lookup"><span data-stu-id="a1916-106">Example user-defined worksheet function that computes the Nth Fibonacci number.</span></span> <span data-ttu-id="a1916-107">当加载了 GENERIC xll 时, 它将注册此函数, 以便可以从工作表中调用它。</span><span class="sxs-lookup"><span data-stu-id="a1916-107">When GENERIC.xll is loaded, it registers this function so that it can be called from the worksheet.</span></span>
  
```cs
LPXLOPER12 WINAPI FuncFib (LPXLOPER12 pxN);
```

## <a name="parameters"></a><span data-ttu-id="a1916-108">参数</span><span class="sxs-lookup"><span data-stu-id="a1916-108">Parameters</span></span>

 <span data-ttu-id="a1916-109">_pxN_(**LPXLOPER12**)</span><span class="sxs-lookup"><span data-stu-id="a1916-109">_pxN_ (**LPXLOPER12**)</span></span>
  
<span data-ttu-id="a1916-110">n 的值为 n, 其中必须有第 n 个斐波纳契数。</span><span class="sxs-lookup"><span data-stu-id="a1916-110">The value of N for which the Nth Fibonacci number is required.</span></span>
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="a1916-111">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="a1916-111">Property value/Return value</span></span>

<span data-ttu-id="a1916-112">(如果成功, 则为**xltypeNum LPXLOPER12** , 否则为**xltypeErr** )</span><span class="sxs-lookup"><span data-stu-id="a1916-112">(**xltypeNum LPXLOPER12** if successful or **xltypeErr** otherwise)</span></span> 
  
<span data-ttu-id="a1916-113">第 n 个斐波纳契号码。</span><span class="sxs-lookup"><span data-stu-id="a1916-113">The Nth Fibonacci number.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="a1916-114">注解</span><span class="sxs-lookup"><span data-stu-id="a1916-114">Remarks</span></span>

<span data-ttu-id="a1916-115">函数使用在函数块中定义的静态变量作为返回值**XLOPER12**。</span><span class="sxs-lookup"><span data-stu-id="a1916-115">The function uses a static variable defined within the function block as the return value **XLOPER12**.</span></span> <span data-ttu-id="a1916-116">这不是线程安全的, 因此此函数以及使用此策略以返回**XLOPER**s 或**XLOPER12**s 的任何工作表函数都不应注册为 Excel 2007 中的线程安全。</span><span class="sxs-lookup"><span data-stu-id="a1916-116">This is not thread safe, and so this function, and any worksheet function that uses this strategy for returning **XLOPER**s or **XLOPER12**s, should not be registered as thread safe starting in Excel 2007.</span></span>
  
### <a name="example"></a><span data-ttu-id="a1916-117">示例</span><span class="sxs-lookup"><span data-stu-id="a1916-117">Example</span></span>

<span data-ttu-id="a1916-118">有关`\SAMPLES\GENERIC\GENERIC.C`此函数的源代码, 请参阅。</span><span class="sxs-lookup"><span data-stu-id="a1916-118">See  `\SAMPLES\GENERIC\GENERIC.C` for the source code for this function.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="a1916-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a1916-119">See also</span></span>



[<span data-ttu-id="a1916-120">通用 DLL 中的函数</span><span class="sxs-lookup"><span data-stu-id="a1916-120">Functions in the Generic DLL</span></span>](functions-in-the-generic-dll.md)

