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
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 9d726d89c859e2f7428b459971d5d13586f144e9
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773665"
---
# <a name="evaluating-names-and-other-worksheet-formula-expressions"></a>评估名称和其他工作表的公式表达式

**适用于** Excel 2013 | Office 2013 | Visual Studio 
  
Excel 公开通过 C API 的最重要功能之一是能够将转换任何字符串公式合法可输入工作表插入到一个值或值的数组。 这是非常重要的 XLL 函数和必须读取内容的已定义名称，例如的命令。 此功能已公开[xlfEvaluate 函数](xlfevaluate.md)中，通过此例中所示。
  
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

请注意时评估工作表名称，其自己上，也可以在公式中，, 您必须为名称前缀与 ！、 至少。 否则，Excel 将尝试查找中隐藏的命名空间名称保留为 Dll。 您可以创建和删除使用[xlfSetName 函数](xlfsetname.md)的隐藏的 DLL 名称。 您可以获取任何已定义的名称，的定义是否隐藏的 DLL 名称或工作表名称，使用**xlfGetDef**函数。 
  
工作表名称的完整规范采用以下形式：
  
`='C:\example folder\[Book1.xls]Sheet1'!Name`
  
请注意 Excel 2007 中引入的新的文件扩展名的数量。 可以省略路径、 工作簿和工作表名称如果此 Excel 会话中没有打开的工作簿之间没有歧义。 
  
下一个示例计算公式`COUNT(A1:IV65536)`活动工作表，并显示结果。 请注意需要前缀与区域地址 ！，这是与 XLM 宏工作表上的区域引用约定保持一致。 C API XLM 遵循以下约定： 
  
- `=A1`对当前的宏工作表上 A1 单元格的引用。 （没有为 Xll 定义）。 
  
- `=!A1`对活动工作表 （这可能是表或宏表） 的 A1 单元格的引用 
  
- `=Sheet1!A1`一个单元格 A1 上的指定工作表 Sheet1 上时，将在这种情况下的引用。 
  
- `=[Book1.xls]Sheet1!A1`对指定工作簿中的指定工作表上 A1 单元格的引用。 
  
在 XLL 中，不带前导感叹号 （**！**） 的引用不能转换为值。 它任何意义，因为没有任何当前的宏工作表。 注意前导等号 (**=**) 是可选的在下一个示例中省略。
  
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

您可以使用**xlfEvaluate**函数从其注册名称，然后可用于调用该函数使用[xlUDF 函数](xludf.md)检索 XLL 函数的注册 ID。
  
> [!NOTE]
> 可以直接向**xlUDF**函数传递已注册的名称。 这意味着，您可以避免评估调用**xlUDF**之前获取 ID 的名称。 但是，如果函数调用多次，则调用使用 ID 是更快的注册。 
  
## <a name="see-also"></a>另请参阅

- [Excel 工作表和表达式计算](excel-worksheet-and-expression-evaluation.md)
- [在长时间的操作中允许用户中断](permitting-user-breaks-in-lengthy-operations.md)
- [Excel XLL SDK 入门](getting-started-with-the-excel-xll-sdk.md)

