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
description: ���÷�Χ�� Excel 2013?| Office 2013?| Visual Studio
ms.openlocfilehash: e468dc18b8f78f56acaa67c2f23dd53254088ad0
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773839"
---
# <a name="xlfevaluate"></a>xlfEvaluate

 **适用于**： Excel 2013 |Office 2013 |Visual Studio 
  
使用 Microsoft Excel 分析程序和函数计算器无法在工作表单元格中输入任何表达式进行求值。
  
```cs
Excel12(xlfEvaluate, LPXLOPER12 pxRes, 1, LPXLOPER12 pxFormulaText);
```

## <a name="parameters"></a>参数

 _pxFormulaText (xltypeStr)_
  
要进行求值的字符串。 可选前导等号 （=）。 字符串可以是任何合法可插入工作表或宏表单元格输入的文本。
  
## <a name="property-valuereturn-value"></a>属性值/返回值

返回的计算的字符串可以是任何类型**xltypeNum**、 **xltypeStr**、 **xltypeBool**、 **xltypeErr**、 **xltypeNil**、 **xltypeMulti**结果。
  
## <a name="remarks"></a>备注

字符串可以包含仅函数，不命令等效。 它等效于按**F9**公式栏中。 如果从已注册为线程安全的 XLL 工作表函数调用**xlfEvaluate** ，则表达式必须只包含线程安全功能。 
  
**XlfEvaluate**函数的主要用途是允许 Dll 以找出分配给工作表是已定义名称的值或隐藏的名称 DLL 中定义。 请注意，在 DLL/XLL，工作表名称必须附上前缀至少感叹号 （！） 以确保它被解释为外部的 dll。 有关详细信息，请参阅[评估名称和其他工作表公式表达式](evaluating-names-and-other-worksheet-formula-expressions.md)。
  
 **xlfEvaluate**不能用于评估对未打开外部表的引用。 
  
## <a name="example"></a>示例

此示例使用**xlfEvaluate**强制文本"！B38"B38 单元格的内容。 
  
 `\SAMPLES\EXAMPLE\EXAMPLE.C`. 此函数调用命令宏 (**xlcAlert**)，并将正常工作，仅当调用从宏工作表或宏命令。
  
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

- [关键及有用的 C API XLM 函数](essential-and-useful-c-api-xlm-functions.md)

