---
title: 评估名称和其他工作表公式表达式
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
keywords:
- 表达式求值 [excel 2007], 工作表 [excel 2007], 名称求值, 计算表达式 [excel 2007], 计算工作表名称 [excel 2007], 表达式 [excel 2007], 评估, 名称 [excel 2007], 评估, 名称求值 [excel 2007], 字符串 [excel 2007], 转换为值, xlfEvaluate 函数 [Excel 2007], 工作表 [excel 2007], 表达式求值
localization_priority: Normal
ms.assetid: 2b23c75e-2a95-4f26-8714-2a73f5e326a7
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 97328cbc57a9144a133524774e3be10a84a96bf4
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32311114"
---
# <a name="evaluating-names-and-other-worksheet-formula-expressions"></a>评估名称和其他工作表公式表达式

**适用于** Excel 2013 | Office 2013 | Visual Studio 
  
Excel 通过 C API 公开的最重要功能之一是能够将任何可合法输入到工作表中的字符串公式转换为值或值数组。 对于必须读取已定义名称的内容的 XLL 函数和命令而言, 这是必不可少的。 此功能通过[xlfEvaluate 函数](xlfevaluate.md)公开, 如以下示例中所示。
  
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

请注意, 在计算工作表名称时或在公式中, 必须至少为名称加上 "!" 前缀。 否则, Excel 将尝试在为 dll 保留的隐藏命名空间中查找该名称。 您可以使用[xlfSetName 函数](xlfsetname.md)创建和删除隐藏的 DLL 名称。 您可以使用**xlfGetDef**函数来获取任何已定义名称的定义, 无论它是隐藏的 DLL 名称还是工作表名称。 
  
工作表名称的完整规范采用以下形式:
  
`='C:\example folder\[Book1.xls]Sheet1'!Name`
  
请注意, Excel 2007 引入了许多新的文件扩展名。 您可以在此 Excel 会话中的打开的工作簿之间省略不明确出现的路径、工作簿名称和工作表名称。 
  
下一个示例对活动工作`COUNT(A1:IV65536)`表的公式求值并显示结果。 请注意, 必须在范围地址前加上前缀 "!", 这与 XLM 宏工作表上的区域引用约定一致。 C API XLM 遵循以下约定: 
  
- `=A1`对当前宏工作表上单元格 A1 的引用。 (没有为 xll 定义)。 
  
- `=!A1`对活动工作表上单元格 A1 的引用 (可以是工作表或宏工作表) 
  
- `=Sheet1!A1`对指定工作表上单元格 A1 的引用, 在此示例中为 Sheet1。 
  
- `=[Book1.xls]Sheet1!A1`对指定工作簿中指定工作表上的单元格 A1 的引用。 
  
在 XLL 中, 不能将不带前导感叹号 (**!**) 的引用转换为值。 它没有任何意义, 因为没有当前的宏工作表。 请注意, 在下一个示例**=** 中, 前导等号 () 是可选的, 并将被省略。
  
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

您还可以使用**xlfEvaluate**函数从其注册的名称检索 XLL 函数的注册 ID, 然后可以使用[xlUDF 函数](xludf.md)调用该函数。
  
> [!NOTE]
> 注册的名称可以直接传递给**xlUDF**函数。 这意味着, 您可以避免在调用**xlUDF**之前评估名称以获取 ID。 但是, 如果多次调用该函数, 则使用注册 ID 调用它的速度会更快。 
  
## <a name="see-also"></a>另请参阅

- [Excel 工作表和表达式计算](excel-worksheet-and-expression-evaluation.md)
- [允许用户中断冗长操作](permitting-user-breaks-in-lengthy-operations.md)
- [Getting Started with the Excel XLL SDK](getting-started-with-the-excel-xll-sdk.md)

