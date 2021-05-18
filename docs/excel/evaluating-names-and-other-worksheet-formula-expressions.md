---
title: 评估名称和其他工作表公式表达式
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
keywords:
- expression evaluation [excel 2007]，worksheets [Excel 2007]， name evaluation，evaluating expressions [Excel 2007]，evaluating worksheet names [Excel 2007]，expressions [Excel 2007]， evaluating，names [Excel 2007]， evaluating，name evaluation [Excel 2007]，strings [Excel 2007]， converting to values，xlfEvaluate function [Excel 2007]，worksheets [Excel 2007]， expression evaluation
localization_priority: Normal
ms.assetid: 2b23c75e-2a95-4f26-8714-2a73f5e326a7
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 97328cbc57a9144a133524774e3be10a84a96bf4
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33406862"
---
# <a name="evaluating-names-and-other-worksheet-formula-expressions"></a><span data-ttu-id="551f0-104">评估名称和其他工作表公式表达式</span><span class="sxs-lookup"><span data-stu-id="551f0-104">Evaluating names and other worksheet formula expressions</span></span>

<span data-ttu-id="551f0-105">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="551f0-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="551f0-106">Excel 通过 C API 公开最重要的功能之一是能够将可合法输入到工作表的任何字符串公式转换为值或值数组。</span><span class="sxs-lookup"><span data-stu-id="551f0-106">One of the most important features that Excel exposes through the C API is the ability to convert any string formula that can legally be entered into a worksheet to a value, or array of values.</span></span> <span data-ttu-id="551f0-107">例如，对于必须读取已定义名称内容的 XLL 函数和命令，这一点至关重要。</span><span class="sxs-lookup"><span data-stu-id="551f0-107">This is essential for XLL functions and commands that must read the contents of defined names, for example.</span></span> <span data-ttu-id="551f0-108">此功能通过 [xlfEvaluate 函数](xlfevaluate.md)公开，如本例所示。</span><span class="sxs-lookup"><span data-stu-id="551f0-108">This ability is exposed through the [xlfEvaluate function](xlfevaluate.md), as shown in this example.</span></span>
  
```C
int WINAPI evaluate_name_example(void)
{
  wchar_t *expression = L"\016!MyDefinedName";
  XLOPER12 xNameText, xNameValue;
  xNameText.xltype = xltypeStr;
  xNameText.val.str = expression;
// Try to evaluate the name. Will fail with a #NAME? error
// if MyDefinedName is not defined in the active workbook.
  Excel12(xlfEvaluate, &xNameValue, 1, &xNameText);
// Attempt to convert the value to a string and display it in
// an alert dialog. This fails if xNameValue is an error value.
  Excel12(xlcAlert, 0, 1, &xNameValue);
// Must free xNameValue in case MyDefinedName evaluated to a string
  Excel12(xlFree, 0, 1, &xNameValue);
  return 1;
}
```

<span data-ttu-id="551f0-109">请注意，在自己或公式中计算工作表名称时，必须至少在名称前面添加"！"前缀。</span><span class="sxs-lookup"><span data-stu-id="551f0-109">Note that when you are evaluating a worksheet name, either on its own or in a formula, you must prefix the name with '!', at least.</span></span> <span data-ttu-id="551f0-110">否则，Excel 会尝试在为 DLL 保留的隐藏命名空间中查找名称。</span><span class="sxs-lookup"><span data-stu-id="551f0-110">Otherwise, Excel tries to find the name in a hidden namespace reserved for DLLs.</span></span> <span data-ttu-id="551f0-111">可以使用 [xlfSetName](xlfsetname.md)函数创建和删除隐藏的 DLL 名称。</span><span class="sxs-lookup"><span data-stu-id="551f0-111">You can create and delete hidden DLL names using the [xlfSetName function](xlfsetname.md).</span></span> <span data-ttu-id="551f0-112">您可以使用 **xlfGetDef** 函数获取任何已定义名称的定义，无论它是隐藏的 DLL 名称还是工作表名称。</span><span class="sxs-lookup"><span data-stu-id="551f0-112">You can get the definition of any defined name, whether it is a hidden DLL name or a worksheet name, using the **xlfGetDef** function.</span></span> 
  
<span data-ttu-id="551f0-113">工作表名称的完整规范采用以下形式：</span><span class="sxs-lookup"><span data-stu-id="551f0-113">The full specification for a worksheet name takes the following form:</span></span>
  
`='C:\example folder\[Book1.xls]Sheet1'!Name`
  
<span data-ttu-id="551f0-114">请注意，Excel 2007 引入了许多新的文件扩展名。</span><span class="sxs-lookup"><span data-stu-id="551f0-114">Note that Excel 2007 introduced a number of new file extensions.</span></span> <span data-ttu-id="551f0-115">可以省略路径、工作簿名称和工作表名称，在此 Excel 会话中打开的工作簿之间没有歧义。</span><span class="sxs-lookup"><span data-stu-id="551f0-115">You can omit the path, the workbook name, and the sheet name where there is no ambiguity among the open workbooks in this Excel session.</span></span> 
  
<span data-ttu-id="551f0-116">下一个示例对活动  `COUNT(A1:IV65536)` 工作表的公式进行计算并显示结果。</span><span class="sxs-lookup"><span data-stu-id="551f0-116">The next example evaluates the formula  `COUNT(A1:IV65536)` for the active worksheet and displays the result.</span></span> <span data-ttu-id="551f0-117">请注意，需要在范围地址前面添加"！"前缀，这符合 XLM 宏表上的范围引用约定。</span><span class="sxs-lookup"><span data-stu-id="551f0-117">Note the need to prefix the range address with '!', which is consistent with the range reference convention on XLM macro sheets.</span></span> <span data-ttu-id="551f0-118">C API XLM 遵循此约定：</span><span class="sxs-lookup"><span data-stu-id="551f0-118">The C API XLM follows this convention:</span></span> 
  
- <span data-ttu-id="551f0-119">`=A1` 对当前宏工作表上单元格 A1 的引用。</span><span class="sxs-lookup"><span data-stu-id="551f0-119">`=A1` A reference to cell A1 on the current macro sheet.</span></span> <span data-ttu-id="551f0-120"> (未为 XLL 定义) 。</span><span class="sxs-lookup"><span data-stu-id="551f0-120">(Not defined for XLLs).</span></span> 
  
- <span data-ttu-id="551f0-121">`=!A1` 对活动工作表上单元格 A1 的引用 (可以是工作表或宏工作表) </span><span class="sxs-lookup"><span data-stu-id="551f0-121">`=!A1` A reference to cell A1 on the active sheet (which could be a worksheet or macro sheet)</span></span> 
  
- <span data-ttu-id="551f0-122">`=Sheet1!A1` 对指定工作表中单元格 A1 的引用，本例中为 Sheet1。</span><span class="sxs-lookup"><span data-stu-id="551f0-122">`=Sheet1!A1` A reference to cell A1 on the specified sheet, Sheet1 in this case.</span></span> 
  
- <span data-ttu-id="551f0-123">`=[Book1.xls]Sheet1!A1` 对指定工作簿中指定工作表上单元格 A1 的引用。</span><span class="sxs-lookup"><span data-stu-id="551f0-123">`=[Book1.xls]Sheet1!A1` A reference to cell A1 on the specified sheet in the specified workbook.</span></span> 
  
<span data-ttu-id="551f0-124">在 XLL 中，没有前导感叹号 (！) **无法** 转换为值。</span><span class="sxs-lookup"><span data-stu-id="551f0-124">In an XLL, a reference without a leading exclamation point (**!**) cannot be converted to a value.</span></span> <span data-ttu-id="551f0-125">它没有任何意义，因为没有当前的宏表。</span><span class="sxs-lookup"><span data-stu-id="551f0-125">It has no meaning because there is no current macro sheet.</span></span> <span data-ttu-id="551f0-126">请注意，前导等号 () **=** 可选，并且下一个示例将省略它。</span><span class="sxs-lookup"><span data-stu-id="551f0-126">Note that a leading equals sign (**=**) is optional and is omitted in the next example.</span></span>
  
```C
int WINAPI evaluate_expression_example(void)
{
    wchar_t *expression = L"\022COUNT(!A1:IV65536)";
    XLOPER12 xExprText, xExprValue;
    xExprText.xltype = xltypeStr;
    xExprText.val.str = expression;
// Try to evaluate the formula.
    Excel12(xlfEvaluate, &xExprValue, 1, &xExprText);
// Attempt to convert the value to a string and display it in
// an alert dialog. Will fail if xExprValue is an error.
    Excel12(xlcAlert, 0, 1, &xExprValue);
// Not strictly necessary, as COUNT never returns a string
// but does no harm.
    Excel12(xlFree, 0, 1, &xExprValue);
    return 1;
}
```

<span data-ttu-id="551f0-127">您还可以使用 **xlfEvaluate** 函数从 XLL 函数的注册名称中检索其注册 ID，然后可使用该名称使用 [xlUDF](xludf.md)函数调用该函数。</span><span class="sxs-lookup"><span data-stu-id="551f0-127">You can also use the **xlfEvaluate** function to retrieve the registration ID of an XLL function from its registered name, which can then be used to call that function using the [xlUDF function](xludf.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="551f0-128">注册的名称可以直接传递给 **xlUDF** 函数。</span><span class="sxs-lookup"><span data-stu-id="551f0-128">The registered name can be passed directly to the **xlUDF** function.</span></span> <span data-ttu-id="551f0-129">这意味着，在调用 **xlUDF** 之前，无需评估名称以获取 ID。</span><span class="sxs-lookup"><span data-stu-id="551f0-129">This means that you can avoid having to evaluate the name to get the ID before calling **xlUDF**.</span></span> <span data-ttu-id="551f0-130">但是，如果要多次调用 函数，则使用注册 ID 调用它速度更快。</span><span class="sxs-lookup"><span data-stu-id="551f0-130">However, if the function is to be called many times, calling it by using the registration ID is faster.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="551f0-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="551f0-131">See also</span></span>

- [<span data-ttu-id="551f0-132">Excel 工作表和表达式计算</span><span class="sxs-lookup"><span data-stu-id="551f0-132">Excel Worksheet and Expression Evaluation</span></span>](excel-worksheet-and-expression-evaluation.md)
- [<span data-ttu-id="551f0-133">允许用户中断冗长操作</span><span class="sxs-lookup"><span data-stu-id="551f0-133">Permitting User Breaks in Lengthy Operations</span></span>](permitting-user-breaks-in-lengthy-operations.md)
- [<span data-ttu-id="551f0-134">Getting Started with the Excel XLL SDK</span><span class="sxs-lookup"><span data-stu-id="551f0-134">Getting Started with the Excel XLL SDK</span></span>](getting-started-with-the-excel-xll-sdk.md)

