---
title: 评估名称和其他工作表的公式表达式
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
keywords:
- 表达式求值 [excel 2007]，工作表 [Excel 2007]，名称评估，计算表达式 [Excel 2007，] 评估工作表名称 [Excel 2007]，[Excel 2007]，表达式评估，名称 [Excel 2007，] 评估，命名为评估 [Excel 2007]将转换为值、 xlfEvaluate 函数 [Excel 2007]、 工作表 [Excel 2007]、 表达式求值的字符串 [Excel 2007]
localization_priority: Normal
ms.assetid: 2b23c75e-2a95-4f26-8714-2a73f5e326a7
description: ���÷�Χ�� Excel 2013?| Office 2013?| Visual Studio
ms.openlocfilehash: 9d726d89c859e2f7428b459971d5d13586f144e9
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773665"
---
# <a name="evaluating-names-and-other-worksheet-formula-expressions"></a><span data-ttu-id="5b1bb-104">评估名称和其他工作表的公式表达式</span><span class="sxs-lookup"><span data-stu-id="5b1bb-104">Evaluating names and other worksheet formula expressions</span></span>

<span data-ttu-id="5b1bb-105">**适用于**： Excel 2013 |Office 2013 |Visual Studio</span><span class="sxs-lookup"><span data-stu-id="5b1bb-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="5b1bb-106">Excel 公开通过 C API 的最重要功能之一是能够将转换任何字符串公式合法可输入工作表插入到一个值或值的数组。</span><span class="sxs-lookup"><span data-stu-id="5b1bb-106">One of the most important features that Excel exposes through the C API is the ability to convert any string formula that can legally be entered into a worksheet to a value, or array of values.</span></span> <span data-ttu-id="5b1bb-107">这是非常重要的 XLL 函数和必须读取内容的已定义名称，例如的命令。</span><span class="sxs-lookup"><span data-stu-id="5b1bb-107">This is essential for XLL functions and commands that must read the contents of defined names, for example.</span></span> <span data-ttu-id="5b1bb-108">此功能已公开[xlfEvaluate 函数](xlfevaluate.md)中，通过此例中所示。</span><span class="sxs-lookup"><span data-stu-id="5b1bb-108">This ability is exposed through the [xlfEvaluate function](xlfevaluate.md), as shown in this example.</span></span>
  
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

<span data-ttu-id="5b1bb-109">请注意时评估工作表名称，其自己上，也可以在公式中，, 您必须为名称前缀与 ！、 至少。</span><span class="sxs-lookup"><span data-stu-id="5b1bb-109">Note that when you are evaluating a worksheet name, either on its own or in a formula, you must prefix the name with '!', at least.</span></span> <span data-ttu-id="5b1bb-110">否则，Excel 将尝试查找中隐藏的命名空间名称保留为 Dll。</span><span class="sxs-lookup"><span data-stu-id="5b1bb-110">Otherwise, Excel tries to find the name in a hidden namespace reserved for DLLs.</span></span> <span data-ttu-id="5b1bb-111">您可以创建和删除使用[xlfSetName 函数](xlfsetname.md)的隐藏的 DLL 名称。</span><span class="sxs-lookup"><span data-stu-id="5b1bb-111">You can create and delete hidden DLL names using the [xlfSetName function](xlfsetname.md).</span></span> <span data-ttu-id="5b1bb-112">您可以获取任何已定义的名称，的定义是否隐藏的 DLL 名称或工作表名称，使用**xlfGetDef**函数。</span><span class="sxs-lookup"><span data-stu-id="5b1bb-112">You can get the definition of any defined name, whether it is a hidden DLL name or a worksheet name, using the **xlfGetDef** function.</span></span> 
  
<span data-ttu-id="5b1bb-113">工作表名称的完整规范采用以下形式：</span><span class="sxs-lookup"><span data-stu-id="5b1bb-113">The full specification for a worksheet name takes the following form:</span></span>
  
`='C:\example folder\[Book1.xls]Sheet1'!Name`
  
<span data-ttu-id="5b1bb-114">请注意 Excel 2007 中引入的新的文件扩展名的数量。</span><span class="sxs-lookup"><span data-stu-id="5b1bb-114">Note that Excel 2007 introduced a number of new file extensions.</span></span> <span data-ttu-id="5b1bb-115">可以省略路径、 工作簿和工作表名称如果此 Excel 会话中没有打开的工作簿之间没有歧义。</span><span class="sxs-lookup"><span data-stu-id="5b1bb-115">You can omit the path, the workbook name, and the sheet name where there is no ambiguity among the open workbooks in this Excel session.</span></span> 
  
<span data-ttu-id="5b1bb-116">下一个示例计算公式`COUNT(A1:IV65536)`活动工作表，并显示结果。</span><span class="sxs-lookup"><span data-stu-id="5b1bb-116">The next example evaluates the formula  `COUNT(A1:IV65536)` for the active worksheet and displays the result.</span></span> <span data-ttu-id="5b1bb-117">请注意需要前缀与区域地址 ！，这是与 XLM 宏工作表上的区域引用约定保持一致。</span><span class="sxs-lookup"><span data-stu-id="5b1bb-117">Note the need to prefix the range address with '!', which is consistent with the range reference convention on XLM macro sheets.</span></span> <span data-ttu-id="5b1bb-118">C API XLM 遵循以下约定：</span><span class="sxs-lookup"><span data-stu-id="5b1bb-118">The C API XLM follows this convention:</span></span> 
  
- <span data-ttu-id="5b1bb-119">`=A1`对当前的宏工作表上 A1 单元格的引用。</span><span class="sxs-lookup"><span data-stu-id="5b1bb-119">`=A1` A reference to cell A1 on the current macro sheet.</span></span> <span data-ttu-id="5b1bb-120">（没有为 Xll 定义）。</span><span class="sxs-lookup"><span data-stu-id="5b1bb-120">(Not defined for XLLs).</span></span> 
  
- <span data-ttu-id="5b1bb-121">`=!A1`对活动工作表 （这可能是表或宏表） 的 A1 单元格的引用</span><span class="sxs-lookup"><span data-stu-id="5b1bb-121">`=!A1` A reference to cell A1 on the active sheet (which could be a worksheet or macro sheet)</span></span> 
  
- <span data-ttu-id="5b1bb-122">`=Sheet1!A1`一个单元格 A1 上的指定工作表 Sheet1 上时，将在这种情况下的引用。</span><span class="sxs-lookup"><span data-stu-id="5b1bb-122">`=Sheet1!A1` A reference to cell A1 on the specified sheet, Sheet1 in this case.</span></span> 
  
- <span data-ttu-id="5b1bb-123">`=[Book1.xls]Sheet1!A1`对指定工作簿中的指定工作表上 A1 单元格的引用。</span><span class="sxs-lookup"><span data-stu-id="5b1bb-123">`=[Book1.xls]Sheet1!A1` A reference to cell A1 on the specified sheet in the specified workbook.</span></span> 
  
<span data-ttu-id="5b1bb-124">在 XLL 中，不带前导感叹号 （**！**） 的引用不能转换为值。</span><span class="sxs-lookup"><span data-stu-id="5b1bb-124">In an XLL, a reference without a leading exclamation point (**!**) cannot be converted to a value.</span></span> <span data-ttu-id="5b1bb-125">它任何意义，因为没有任何当前的宏工作表。</span><span class="sxs-lookup"><span data-stu-id="5b1bb-125">It has no meaning because there is no current macro sheet.</span></span> <span data-ttu-id="5b1bb-126">注意前导等号 (**=**) 是可选的在下一个示例中省略。</span><span class="sxs-lookup"><span data-stu-id="5b1bb-126">Note that a leading equals sign (**=**) is optional and is omitted in the next example.</span></span>
  
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

<span data-ttu-id="5b1bb-127">您可以使用**xlfEvaluate**函数从其注册名称，然后可用于调用该函数使用[xlUDF 函数](xludf.md)检索 XLL 函数的注册 ID。</span><span class="sxs-lookup"><span data-stu-id="5b1bb-127">You can also use the **xlfEvaluate** function to retrieve the registration ID of an XLL function from its registered name, which can then be used to call that function using the [xlUDF function](xludf.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="5b1bb-128">可以直接向**xlUDF**函数传递已注册的名称。</span><span class="sxs-lookup"><span data-stu-id="5b1bb-128">The registered name can be passed directly to the **xlUDF** function.</span></span> <span data-ttu-id="5b1bb-129">这意味着，您可以避免评估调用**xlUDF**之前获取 ID 的名称。</span><span class="sxs-lookup"><span data-stu-id="5b1bb-129">This means that you can avoid having to evaluate the name to get the ID before calling **xlUDF**.</span></span> <span data-ttu-id="5b1bb-130">但是，如果函数调用多次，则调用使用 ID 是更快的注册。</span><span class="sxs-lookup"><span data-stu-id="5b1bb-130">However, if the function is to be called many times, calling it by using the registration ID is faster.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="5b1bb-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5b1bb-131">See also</span></span>

- [<span data-ttu-id="5b1bb-132">Excel 工作表和表达式评估</span><span class="sxs-lookup"><span data-stu-id="5b1bb-132">Excel Worksheet and Expression Evaluation</span></span>](excel-worksheet-and-expression-evaluation.md)
- [<span data-ttu-id="5b1bb-133">允许用户在冗长操作中中断</span><span class="sxs-lookup"><span data-stu-id="5b1bb-133">Permitting User Breaks in Lengthy Operations</span></span>](permitting-user-breaks-in-lengthy-operations.md)
- [<span data-ttu-id="5b1bb-134">Getting Started with the Excel XLL SDK</span><span class="sxs-lookup"><span data-stu-id="5b1bb-134">Getting Started with the Excel XLL SDK</span></span>](getting-started-with-the-excel-xll-sdk.md)

