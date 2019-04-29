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
# <a name="xlfevaluate"></a>xlfEvaluate

 **适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
使用 Microsoft Excel 分析器和函数计算器计算可在工作表单元格中输入的任何表达式。
  
```cs
Excel12(xlfEvaluate, LPXLOPER12 pxRes, 1, LPXLOPER12 pxFormulaText);
```

## <a name="parameters"></a>参数

 _pxFormulaText (xltypeStr)_
  
要计算的字符串。 前导等号 (=) 是可选的。 该字符串可以是可在工作表或宏工作表单元格中合法输入的任何文本。
  
## <a name="property-valuereturn-value"></a>属性值/返回值

返回计算字符串的结果, 可以是**xltypeNum**、 **xltypeStr**、 **xltypeBool**、 **xltypeErr**、 **xltypeNil**、 **xltypeMulti**的任意类型。
  
## <a name="remarks"></a>说明

该字符串只能包含函数, 而不能包含命令等效项。 它等效于在编辑栏上按**F9** 。 如果从已注册为线程安全的 XLL 工作表函数调用**xlfEvaluate** , 则该表达式必须只包含线程安全函数。 
  
**xlfEvaluate**函数的主要用途是允许 dll 查找分配给已定义名称的值, 该名称在工作表上或在 DLL 内定义的隐藏名称上。 请注意, 在 dll/XLL 中, 工作表名称必须至少带有感叹号 (!) 前缀, 以确保它被解释为 DLL 的外部名称。 有关详细信息, 请参阅[评估名称和其他工作表公式表达式](evaluating-names-and-other-worksheet-formula-expressions.md)。
  
 **xlfEvaluate**不能用于计算对未打开的外部工作表的引用。 
  
## <a name="example"></a>示例

此示例使用**xlfEvaluate**来强制文本 "!B38 "到单元格 B38 的内容。 
  
 `\SAMPLES\EXAMPLE\EXAMPLE.C`. 此函数调用命令宏 (**xlcAlert**), 并且只有在宏工作表或宏命令调用时才能正常运行。
  
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

## <a name="see-also"></a>另请参阅

- [实用的基本 C API XLM 函数](essential-and-useful-c-api-xlm-functions.md)

