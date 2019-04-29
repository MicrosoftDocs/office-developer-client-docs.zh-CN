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
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 527f7e932a41103c374e327a1bd0dd4c7d8e92a0
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439182"
---
# <a name="xlfevaluate"></a><span data-ttu-id="98b76-104">xlfEvaluate</span><span class="sxs-lookup"><span data-stu-id="98b76-104">xlfEvaluate</span></span>

 <span data-ttu-id="98b76-105">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="98b76-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="98b76-106">使用 Microsoft Excel 分析器和函数计算器计算可在工作表单元格中输入的任何表达式。</span><span class="sxs-lookup"><span data-stu-id="98b76-106">Uses the Microsoft Excel parser and function evaluator to evaluate any expression that could be entered in a worksheet cell.</span></span>
  
```cs
Excel12(xlfEvaluate, LPXLOPER12 pxRes, 1, LPXLOPER12 pxFormulaText);
```

## <a name="parameters"></a><span data-ttu-id="98b76-107">参数</span><span class="sxs-lookup"><span data-stu-id="98b76-107">Parameters</span></span>

 <span data-ttu-id="98b76-108">_pxFormulaText (xltypeStr)_</span><span class="sxs-lookup"><span data-stu-id="98b76-108">_pxFormulaText (xltypeStr)_</span></span>
  
<span data-ttu-id="98b76-109">要计算的字符串。</span><span class="sxs-lookup"><span data-stu-id="98b76-109">The string to be evaluated.</span></span> <span data-ttu-id="98b76-110">前导等号 (=) 是可选的。</span><span class="sxs-lookup"><span data-stu-id="98b76-110">A leading equal sign (=) is optional.</span></span> <span data-ttu-id="98b76-111">该字符串可以是可在工作表或宏工作表单元格中合法输入的任何文本。</span><span class="sxs-lookup"><span data-stu-id="98b76-111">The string can be any text that can legally be entered into a worksheet or macro sheet cell.</span></span>
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="98b76-112">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="98b76-112">Property value/Return value</span></span>

<span data-ttu-id="98b76-113">返回计算字符串的结果, 可以是**xltypeNum**、 **xltypeStr**、 **xltypeBool**、 **xltypeErr**、 **xltypeNil**、 **xltypeMulti**的任意类型。</span><span class="sxs-lookup"><span data-stu-id="98b76-113">Returns the result of evaluating the string which can be any of the types **xltypeNum**, **xltypeStr**, **xltypeBool**, **xltypeErr**, **xltypeNil**, **xltypeMulti**.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="98b76-114">说明</span><span class="sxs-lookup"><span data-stu-id="98b76-114">Remarks</span></span>

<span data-ttu-id="98b76-115">该字符串只能包含函数, 而不能包含命令等效项。</span><span class="sxs-lookup"><span data-stu-id="98b76-115">The string can contain only functions, not command equivalents.</span></span> <span data-ttu-id="98b76-116">它等效于在编辑栏上按**F9** 。</span><span class="sxs-lookup"><span data-stu-id="98b76-116">It is equivalent to pressing **F9** from the formula bar.</span></span> <span data-ttu-id="98b76-117">如果从已注册为线程安全的 XLL 工作表函数调用**xlfEvaluate** , 则该表达式必须只包含线程安全函数。</span><span class="sxs-lookup"><span data-stu-id="98b76-117">If **xlfEvaluate** is called from an XLL worksheet function that has been registered as thread safe, the expression must only contain thread-safe functions.</span></span> 
  
<span data-ttu-id="98b76-118">**xlfEvaluate**函数的主要用途是允许 dll 查找分配给已定义名称的值, 该名称在工作表上或在 DLL 内定义的隐藏名称上。</span><span class="sxs-lookup"><span data-stu-id="98b76-118">The primary use of the **xlfEvaluate** function is to allow DLLs to find out the value assigned to a defined name that is either on a sheet or a hidden name defined within the DLL.</span></span> <span data-ttu-id="98b76-119">请注意, 在 dll/XLL 中, 工作表名称必须至少带有感叹号 (!) 前缀, 以确保它被解释为 DLL 的外部名称。</span><span class="sxs-lookup"><span data-stu-id="98b76-119">Note that within a DLL/XLL, a worksheet name must be prefixed with at least an exclamation mark (!) to ensure that it is interpreted as external to the DLL.</span></span> <span data-ttu-id="98b76-120">有关详细信息, 请参阅[评估名称和其他工作表公式表达式](evaluating-names-and-other-worksheet-formula-expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="98b76-120">For more information, see [Evaluating Names and Other Worksheet Formula Expressions](evaluating-names-and-other-worksheet-formula-expressions.md).</span></span>
  
 <span data-ttu-id="98b76-121">**xlfEvaluate**不能用于计算对未打开的外部工作表的引用。</span><span class="sxs-lookup"><span data-stu-id="98b76-121">**xlfEvaluate** cannot be used to evaluate references to an external sheet that is not open.</span></span> 
  
## <a name="example"></a><span data-ttu-id="98b76-122">示例</span><span class="sxs-lookup"><span data-stu-id="98b76-122">Example</span></span>

<span data-ttu-id="98b76-123">此示例使用**xlfEvaluate**来强制文本 "!B38 "到单元格 B38 的内容。</span><span class="sxs-lookup"><span data-stu-id="98b76-123">This example uses **xlfEvaluate** to coerce the text "!B38" to the contents of cell B38.</span></span> 
  
 <span data-ttu-id="98b76-124">`\SAMPLES\EXAMPLE\EXAMPLE.C`.</span><span class="sxs-lookup"><span data-stu-id="98b76-124"></span></span> <span data-ttu-id="98b76-125">此函数调用命令宏 (**xlcAlert**), 并且只有在宏工作表或宏命令调用时才能正常运行。</span><span class="sxs-lookup"><span data-stu-id="98b76-125">This function calls a command macro (**xlcAlert**) and will work correctly only when called from a macro sheet or as a macro command.</span></span>
  
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

## <a name="see-also"></a><span data-ttu-id="98b76-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="98b76-126">See also</span></span>

- [<span data-ttu-id="98b76-127">实用的基本 C API XLM 函数</span><span class="sxs-lookup"><span data-stu-id="98b76-127">Essential and Useful C API XLM Functions</span></span>](essential-and-useful-c-api-xlm-functions.md)

