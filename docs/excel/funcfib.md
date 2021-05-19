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
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: fb8f0c12c27fb2c95007eb5006c1d8b90970f3ad
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33423669"
---
# <a name="funcfib"></a><span data-ttu-id="0bffb-104">FuncFib</span><span class="sxs-lookup"><span data-stu-id="0bffb-104">FuncFib</span></span>

 <span data-ttu-id="0bffb-105">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="0bffb-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="0bffb-106">计算第 N 个 Fi一号的用户定义的工作表函数示例。</span><span class="sxs-lookup"><span data-stu-id="0bffb-106">Example user-defined worksheet function that computes the Nth Fibonacci number.</span></span> <span data-ttu-id="0bffb-107">当加载 GENERIC.xll 时，它会注册此函数，以便可以从工作表中调用它。</span><span class="sxs-lookup"><span data-stu-id="0bffb-107">When GENERIC.xll is loaded, it registers this function so that it can be called from the worksheet.</span></span>
  
```cs
LPXLOPER12 WINAPI FuncFib (LPXLOPER12 pxN);
```

## <a name="parameters"></a><span data-ttu-id="0bffb-108">参数</span><span class="sxs-lookup"><span data-stu-id="0bffb-108">Parameters</span></span>

 <span data-ttu-id="0bffb-109">_pxN_ (**LPXLOPER12**) </span><span class="sxs-lookup"><span data-stu-id="0bffb-109">_pxN_ (**LPXLOPER12**)</span></span>
  
<span data-ttu-id="0bffb-110">N 的值，其第 N 个 Fi一线数字是必需的。</span><span class="sxs-lookup"><span data-stu-id="0bffb-110">The value of N for which the Nth Fibonacci number is required.</span></span>
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="0bffb-111">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="0bffb-111">Property value/Return value</span></span>

<span data-ttu-id="0bffb-112"> (**为 xltypeNum LPXLOPER12，** 否则为 **xltypeErr**) </span><span class="sxs-lookup"><span data-stu-id="0bffb-112">(**xltypeNum LPXLOPER12** if successful or **xltypeErr** otherwise)</span></span> 
  
<span data-ttu-id="0bffb-113">第 N 个 Fi一号。</span><span class="sxs-lookup"><span data-stu-id="0bffb-113">The Nth Fibonacci number.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="0bffb-114">备注</span><span class="sxs-lookup"><span data-stu-id="0bffb-114">Remarks</span></span>

<span data-ttu-id="0bffb-115">函数使用函数块中定义的静态变量作为返回值 **XLOPER12**。</span><span class="sxs-lookup"><span data-stu-id="0bffb-115">The function uses a static variable defined within the function block as the return value **XLOPER12**.</span></span> <span data-ttu-id="0bffb-116">这不是线程安全函数，因此，此函数以及使用此策略返回 **XLOPER 或 XLOPER12** 的任何工作表函数不应从 Excel 2007 开始注册为线程安全。 </span><span class="sxs-lookup"><span data-stu-id="0bffb-116">This is not thread safe, and so this function, and any worksheet function that uses this strategy for returning **XLOPER** s or **XLOPER12** s, should not be registered as thread safe starting in Excel 2007.</span></span>
  
### <a name="example"></a><span data-ttu-id="0bffb-117">示例</span><span class="sxs-lookup"><span data-stu-id="0bffb-117">Example</span></span>

<span data-ttu-id="0bffb-118">有关  `\SAMPLES\GENERIC\GENERIC.C` 此函数的源代码，请参阅 。</span><span class="sxs-lookup"><span data-stu-id="0bffb-118">See  `\SAMPLES\GENERIC\GENERIC.C` for the source code for this function.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="0bffb-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0bffb-119">See also</span></span>



[<span data-ttu-id="0bffb-120">通用 DLL 中的函数</span><span class="sxs-lookup"><span data-stu-id="0bffb-120">Functions in the Generic DLL</span></span>](functions-in-the-generic-dll.md)

