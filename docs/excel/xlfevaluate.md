---
title: xlfEvaluate
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- xlfEvaluate
keywords:
- xlfevaluate 函数 [excel 2007]
localization_priority: Normal
ms.assetid: deea3ee6-2a32-47ef-bfa4-914891538633
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: e468dc18b8f78f56acaa67c2f23dd53254088ad0
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773839"
---
# <a name="xlfevaluate"></a><span data-ttu-id="68293-104">xlfEvaluate</span><span class="sxs-lookup"><span data-stu-id="68293-104">xlfEvaluate</span></span>

 <span data-ttu-id="68293-105">**适用于** Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="68293-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="68293-106">使用 Microsoft Excel 分析程序和函数计算器无法在工作表单元格中输入任何表达式进行求值。</span><span class="sxs-lookup"><span data-stu-id="68293-106">Uses the Microsoft Excel parser and function evaluator to evaluate any expression that could be entered in a worksheet cell.</span></span>
  
```cs
Excel12(xlfEvaluate, LPXLOPER12 pxRes, 1, LPXLOPER12 pxFormulaText);
```

## <a name="parameters"></a><span data-ttu-id="68293-107">参数</span><span class="sxs-lookup"><span data-stu-id="68293-107">Parameters</span></span>

 <span data-ttu-id="68293-108">_pxFormulaText (xltypeStr)_</span><span class="sxs-lookup"><span data-stu-id="68293-108">_pxFormulaText (xltypeStr)_</span></span>
  
<span data-ttu-id="68293-109">要进行求值的字符串。</span><span class="sxs-lookup"><span data-stu-id="68293-109">The string to be evaluated.</span></span> <span data-ttu-id="68293-110">可选前导等号 （=）。</span><span class="sxs-lookup"><span data-stu-id="68293-110">A leading equal sign (=) is optional.</span></span> <span data-ttu-id="68293-111">字符串可以是任何合法可插入工作表或宏表单元格输入的文本。</span><span class="sxs-lookup"><span data-stu-id="68293-111">The string can be any text that can legally be entered into a worksheet or macro sheet cell.</span></span>
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="68293-112">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="68293-112">Property value/Return value</span></span>

<span data-ttu-id="68293-113">返回的计算的字符串可以是任何类型**xltypeNum**、 **xltypeStr**、 **xltypeBool**、 **xltypeErr**、 **xltypeNil**、 **xltypeMulti**结果。</span><span class="sxs-lookup"><span data-stu-id="68293-113">Returns the result of evaluating the string which can be any of the types **xltypeNum**, **xltypeStr**, **xltypeBool**, **xltypeErr**, **xltypeNil**, **xltypeMulti**.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="68293-114">说明</span><span class="sxs-lookup"><span data-stu-id="68293-114">Remarks</span></span>

<span data-ttu-id="68293-115">字符串可以包含仅函数，不命令等效。</span><span class="sxs-lookup"><span data-stu-id="68293-115">The string can contain only functions, not command equivalents.</span></span> <span data-ttu-id="68293-116">它等效于按**F9**公式栏中。</span><span class="sxs-lookup"><span data-stu-id="68293-116">It is equivalent to pressing **F9** from the formula bar.</span></span> <span data-ttu-id="68293-117">如果从已注册为线程安全的 XLL 工作表函数调用**xlfEvaluate** ，则表达式必须只包含线程安全功能。</span><span class="sxs-lookup"><span data-stu-id="68293-117">If **xlfEvaluate** is called from an XLL worksheet function that has been registered as thread safe, the expression must only contain thread-safe functions.</span></span> 
  
<span data-ttu-id="68293-118">**XlfEvaluate**函数的主要用途是允许 Dll 以找出分配给工作表是已定义名称的值或隐藏的名称 DLL 中定义。</span><span class="sxs-lookup"><span data-stu-id="68293-118">The primary use of the **xlfEvaluate** function is to allow DLLs to find out the value assigned to a defined name that is either on a sheet or a hidden name defined within the DLL.</span></span> <span data-ttu-id="68293-119">请注意，在 DLL/XLL，工作表名称必须附上前缀至少感叹号 （！） 以确保它被解释为外部的 dll。</span><span class="sxs-lookup"><span data-stu-id="68293-119">Note that within a DLL/XLL, a worksheet name must be prefixed with at least an exclamation mark (!) to ensure that it is interpreted as external to the DLL.</span></span> <span data-ttu-id="68293-120">有关详细信息，请参阅[评估名称和其他工作表公式表达式](evaluating-names-and-other-worksheet-formula-expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="68293-120">For more information, see [Evaluating Names and Other Worksheet Formula Expressions](evaluating-names-and-other-worksheet-formula-expressions.md).</span></span>
  
 <span data-ttu-id="68293-121">**xlfEvaluate**不能用于评估对未打开外部表的引用。</span><span class="sxs-lookup"><span data-stu-id="68293-121">**xlfEvaluate** cannot be used to evaluate references to an external sheet that is not open.</span></span> 
  
## <a name="example"></a><span data-ttu-id="68293-122">示例</span><span class="sxs-lookup"><span data-stu-id="68293-122">Example</span></span>

<span data-ttu-id="68293-123">此示例使用**xlfEvaluate**强制文本"！B38"B38 单元格的内容。</span><span class="sxs-lookup"><span data-stu-id="68293-123">This example uses **xlfEvaluate** to coerce the text "!B38" to the contents of cell B38.</span></span> 
  
 <span data-ttu-id="68293-124">`\SAMPLES\EXAMPLE\EXAMPLE.C`.</span><span class="sxs-lookup"><span data-stu-id="68293-124"></span></span> <span data-ttu-id="68293-125">此函数调用命令宏 (**xlcAlert**)，并将正常工作，仅当调用从宏工作表或宏命令。</span><span class="sxs-lookup"><span data-stu-id="68293-125">This function calls a command macro (**xlcAlert**) and will work correctly only when called from a macro sheet or as a macro command.</span></span>
  
```cs
short WINAPI EvaluateExample(void)
{
    XLOPER12 xFormulaText, xRes, xRes2, xInt;
    xFormulaText.xltype = xltypeStr;
    xFormulaText.val.str = L"\004!B38";
    Excel12(xlfEvaluate, &xRes, 1, (LPXLOPER12)&xFormulaText);
    xInt.xltype = xltypeInt;
    xInt.val.w = 2;
    Excel12(xlcAlert, &xRes2, 2, (LPXLOPER12)&xRes, (LPXLOPER12)&xInt);
    Excel12(xlFree, 0, 1, (LPXLOPER12)&xRes);
    Excel12(xlFree, 0, 1, (LPXLOPER12)&xRes2);
    return 1;
}
```

## <a name="see-also"></a><span data-ttu-id="68293-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="68293-126">See also</span></span>

- [<span data-ttu-id="68293-127">基本的有用 C API XLM 函数</span><span class="sxs-lookup"><span data-stu-id="68293-127">Essential and Useful C API XLM Functions</span></span>](essential-and-useful-c-api-xlm-functions.md)

