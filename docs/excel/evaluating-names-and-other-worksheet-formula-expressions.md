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
# <a name="evaluating-names-and-other-worksheet-formula-expressions"></a>评估名称和其他工作表公式表达式

**适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
Excel 通过 C API 公开最重要的功能之一是能够将可合法输入到工作表的任何字符串公式转换为值或值数组。 例如，对于必须读取已定义名称内容的 XLL 函数和命令，这一点至关重要。 此功能通过 [xlfEvaluate 函数](xlfevaluate.md)公开，如本例所示。
  
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

请注意，在自己或公式中计算工作表名称时，必须至少在名称前面添加"！"前缀。 否则，Excel 会尝试在为 DLL 保留的隐藏命名空间中查找名称。 可以使用 [xlfSetName](xlfsetname.md)函数创建和删除隐藏的 DLL 名称。 您可以使用 **xlfGetDef** 函数获取任何已定义名称的定义，无论它是隐藏的 DLL 名称还是工作表名称。 
  
工作表名称的完整规范采用以下形式：
  
`='C:\example folder\[Book1.xls]Sheet1'!Name`
  
请注意，Excel 2007 引入了许多新的文件扩展名。 可以省略路径、工作簿名称和工作表名称，在此 Excel 会话中打开的工作簿之间没有歧义。 
  
下一个示例对活动  `COUNT(A1:IV65536)` 工作表的公式进行计算并显示结果。 请注意，需要在范围地址前面添加"！"前缀，这符合 XLM 宏表上的范围引用约定。 C API XLM 遵循此约定： 
  
- `=A1` 对当前宏工作表上单元格 A1 的引用。  (未为 XLL 定义) 。 
  
- `=!A1` 对活动工作表上单元格 A1 的引用 (可以是工作表或宏工作表)  
  
- `=Sheet1!A1` 对指定工作表中单元格 A1 的引用，本例中为 Sheet1。 
  
- `=[Book1.xls]Sheet1!A1` 对指定工作簿中指定工作表上单元格 A1 的引用。 
  
在 XLL 中，没有前导感叹号 (！) **无法** 转换为值。 它没有任何意义，因为没有当前的宏表。 请注意，前导等号 () **=** 可选，并且下一个示例将省略它。
  
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

您还可以使用 **xlfEvaluate** 函数从 XLL 函数的注册名称中检索其注册 ID，然后可使用该名称使用 [xlUDF](xludf.md)函数调用该函数。
  
> [!NOTE]
> 注册的名称可以直接传递给 **xlUDF** 函数。 这意味着，在调用 **xlUDF** 之前，无需评估名称以获取 ID。 但是，如果要多次调用 函数，则使用注册 ID 调用它速度更快。 
  
## <a name="see-also"></a>另请参阅

- [Excel 工作表和表达式计算](excel-worksheet-and-expression-evaluation.md)
- [允许用户中断冗长操作](permitting-user-breaks-in-lengthy-operations.md)
- [Getting Started with the Excel XLL SDK](getting-started-with-the-excel-xll-sdk.md)

