---
title: FuncSum
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- FuncSum
keywords:
- funcsum 函数 [excel 2007]
localization_priority: Normal
ms.assetid: 934192ef-8a89-4dbb-bd37-01e92ba24256
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 14db5812165812161cf7031f75338a981251dfd2
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32304058"
---
# <a name="funcsum"></a><span data-ttu-id="52dcc-104">FuncSum</span><span class="sxs-lookup"><span data-stu-id="52dcc-104">FuncSum</span></span>

 <span data-ttu-id="52dcc-105">**适用于** Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="52dcc-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="52dcc-106">示例用户定义的工作表函数, 它需要1到29个参数并计算它们的和。</span><span class="sxs-lookup"><span data-stu-id="52dcc-106">Example user-defined worksheet function that takes 1 to 29 arguments and computes their sum.</span></span> <span data-ttu-id="52dcc-107">每个参数都可以是单个数字、一个区域或一个数组。</span><span class="sxs-lookup"><span data-stu-id="52dcc-107">Each argument can be a single number, a range, or an array.</span></span> <span data-ttu-id="52dcc-108">当加载了 GENERIC xll 时, 它将注册此函数, 以便可以从工作表中调用它。</span><span class="sxs-lookup"><span data-stu-id="52dcc-108">When GENERIC.xll is loaded, it registers this function so that it can be called from the worksheet.</span></span> 
  
```cs
LPXLOPER12 WINAPI FuncSum(LPXLOPER12 px1, LPXLOPER12 px2, LPXLOPER12 px3,LPXLOPER12 px4, LPXLOPER12 px5, LPXLOPER12 px6, LPXLOPER12 px7,LPXLOPER12 px8, LPXLOPER12 px9, LPXLOPER12 px10, LPXLOPER12 px11,LPXLOPER12 px12, LPXLOPER12 px13, LPXLOPER12 px14, LPXLOPER12 px15,LPXLOPER12 px16, LPXLOPER12 px17, LPXLOPER12 px18, LPXLOPER12 px19,LPXLOPER12 px20, LPXLOPER12 px21, LPXLOPER12 px22, LPXLOPER12 px23,LPXLOPER12 px24, LPXLOPER12 px25, LPXLOPER12 px26, LPXLOPER12 px27,LPXLOPER12 px28, LPXLOPER12 px29);
```

## <a name="parameters"></a><span data-ttu-id="52dcc-109">参数</span><span class="sxs-lookup"><span data-stu-id="52dcc-109">Parameters</span></span>

 <span data-ttu-id="52dcc-110">_px1-px29_(**LPXLOPER12**)</span><span class="sxs-lookup"><span data-stu-id="52dcc-110">_px1-px29_ (**LPXLOPER12**)</span></span>
  
<span data-ttu-id="52dcc-111">指向**XLOPER12**参数的指针。</span><span class="sxs-lookup"><span data-stu-id="52dcc-111">Pointers to **XLOPER12** arguments.</span></span> <span data-ttu-id="52dcc-112">函数接受任何类型的输入类型, 但只对数字、数字数组和仅包含数字或空白单元格的区域进行编码。</span><span class="sxs-lookup"><span data-stu-id="52dcc-112">The function accepts any kind of input type but is coded only to operate on numbers, literal arrays of numbers, and ranges containing only numbers or blank cells.</span></span> <span data-ttu-id="52dcc-113">如果提供的参数少于29个, 则会将其余参数作为**xltypeMissing**提供。</span><span class="sxs-lookup"><span data-stu-id="52dcc-113">If fewer than 29 arguments are supplied, the remaining arguments are supplied as **xltypeMissing**.</span></span>
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="52dcc-114">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="52dcc-114">Property value/Return value</span></span>

<span data-ttu-id="52dcc-115">(**LPXLOPER12 xltypeNum**或**xltypeErr**)</span><span class="sxs-lookup"><span data-stu-id="52dcc-115">(**LPXLOPER12 xltypeNum** or **xltypeErr**)</span></span>
  
<span data-ttu-id="52dcc-116">参数或 #VALUE 的总和!</span><span class="sxs-lookup"><span data-stu-id="52dcc-116">The sum of the arguments or #VALUE!</span></span> <span data-ttu-id="52dcc-117">如果在提供的参数列表中或数组中区域或元素中的单元格中有非数值型。</span><span class="sxs-lookup"><span data-stu-id="52dcc-117">if there are non-numerics in the supplied argument list or in a cell in a range or element in an array.</span></span>
  
### <a name="example"></a><span data-ttu-id="52dcc-118">示例</span><span class="sxs-lookup"><span data-stu-id="52dcc-118">Example</span></span>

<span data-ttu-id="52dcc-119">有关`\SAMPLES\GENERIC\GENERIC.C`此函数的源代码, 请参阅。</span><span class="sxs-lookup"><span data-stu-id="52dcc-119">See  `\SAMPLES\GENERIC\GENERIC.C` for the source code for this function.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="52dcc-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="52dcc-120">See also</span></span>



[<span data-ttu-id="52dcc-121">通用 DLL 中的函数</span><span class="sxs-lookup"><span data-stu-id="52dcc-121">Functions in the Generic DLL</span></span>](functions-in-the-generic-dll.md)

