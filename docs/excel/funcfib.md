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
description: ���÷�Χ�� Excel 2013?| Office 2013?| Visual Studio
ms.openlocfilehash: 8d1c97ea57e968aaedffca6b37ded3d875e87413
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773747"
---
# <a name="funcfib"></a><span data-ttu-id="6f5f7-104">FuncFib</span><span class="sxs-lookup"><span data-stu-id="6f5f7-104">FuncFib</span></span>

 <span data-ttu-id="6f5f7-105">**适用于**： Excel 2013 |Office 2013 |Visual Studio</span><span class="sxs-lookup"><span data-stu-id="6f5f7-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="6f5f7-106">示例计算第 n 个 Fibonacci 数的用户定义的工作表函数。</span><span class="sxs-lookup"><span data-stu-id="6f5f7-106">Example user-defined worksheet function that computes the Nth Fibonacci number.</span></span> <span data-ttu-id="6f5f7-107">加载 GENERIC.xll 时，以便它可以调用从工作表中注册此函数。</span><span class="sxs-lookup"><span data-stu-id="6f5f7-107">When GENERIC.xll is loaded, it registers this function so that it can be called from the worksheet.</span></span>
  
```cs
LPXLOPER12 WINAPI FuncFib (LPXLOPER12 pxN);
```

## <a name="parameters"></a><span data-ttu-id="6f5f7-108">参数</span><span class="sxs-lookup"><span data-stu-id="6f5f7-108">Parameters</span></span>

 <span data-ttu-id="6f5f7-109">_pxN_(**LPXLOPER12**)</span><span class="sxs-lookup"><span data-stu-id="6f5f7-109">_pxN_ (**LPXLOPER12**)</span></span>
  
<span data-ttu-id="6f5f7-110">N 需要第 n 个 Fibonacci 数的值。</span><span class="sxs-lookup"><span data-stu-id="6f5f7-110">The value of N for which the Nth Fibonacci number is required.</span></span>
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="6f5f7-111">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="6f5f7-111">Property value/Return value</span></span>

<span data-ttu-id="6f5f7-112">（**xltypeNum LPXLOPER12**如果成功或**xltypeErr**否则为）</span><span class="sxs-lookup"><span data-stu-id="6f5f7-112">(**xltypeNum LPXLOPER12** if successful or **xltypeErr** otherwise)</span></span> 
  
<span data-ttu-id="6f5f7-113">第 n 个 Fibonacci 数。</span><span class="sxs-lookup"><span data-stu-id="6f5f7-113">The Nth Fibonacci number.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="6f5f7-114">备注</span><span class="sxs-lookup"><span data-stu-id="6f5f7-114">Remarks</span></span>

<span data-ttu-id="6f5f7-115">该函数使用的函数块内定义为**XLOPER12**的返回值的静态变量。</span><span class="sxs-lookup"><span data-stu-id="6f5f7-115">The function uses a static variable defined within the function block as the return value **XLOPER12**.</span></span> <span data-ttu-id="6f5f7-116">这不是线程安全的，因此此函数中，并使用此策略对返回**XLOPER**s 或**XLOPER12**s 进行任何工作表函数不应注册为安全启动 Excel 2007 中的线程。</span><span class="sxs-lookup"><span data-stu-id="6f5f7-116">This is not thread safe, and so this function, and any worksheet function that uses this strategy for returning **XLOPER**s or **XLOPER12**s, should not be registered as thread safe starting in Excel 2007.</span></span>
  
### <a name="example"></a><span data-ttu-id="6f5f7-117">示例</span><span class="sxs-lookup"><span data-stu-id="6f5f7-117">Example</span></span>

<span data-ttu-id="6f5f7-118">请参阅`\SAMPLES\GENERIC\GENERIC.C`的此函数的源代码。</span><span class="sxs-lookup"><span data-stu-id="6f5f7-118">See  `\SAMPLES\GENERIC\GENERIC.C` for the source code for this function.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="6f5f7-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6f5f7-119">See also</span></span>



[<span data-ttu-id="6f5f7-120">泛型 DLL 中的函数</span><span class="sxs-lookup"><span data-stu-id="6f5f7-120">Functions in the Generic DLL</span></span>](functions-in-the-generic-dll.md)

