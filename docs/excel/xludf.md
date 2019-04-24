---
title: xlUDF
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- xlUDF
keywords:
- xludf 函数 [excel 2007]
localization_priority: Normal
ms.assetid: b608b356-ca5c-47bb-9de8-9b7e2b3924dd
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 569334847c7612b86f6ddc967f159e2ef425cbbb
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32303813"
---
# <a name="xludf"></a>xlUDF

**适用于** Excel 2013 | Office 2013 | Visual Studio 
  
调用用户定义的函数 (UDF)。 此函数允许 DLL 调用 Visual Basic for Applications (VBA) 用户定义的函数、XLM 宏语言函数和其他加载项中包含的已注册函数。
  
```cs
Excel12(xlUDF, LPXLOPER12 pxRes, int iCount, LPXLOPER12 pxFnRef,
LPXLOPER12 pxArg1, ...);
```

## <a name="parameters"></a>参数

_pxFnRef_(**xltypeRef**、 **xltypeSRef**、 **xltypeStr**或**xltypeNum**)
  
要调用的函数的引用。 它可以是宏工作表单元格引用、作为字符串的函数的注册名称或函数的 register ID。 对于使用**xlfRegister**注册的 XLL 加载项函数或在提供参数_pxFunctionText_的情况下**注册**时, 可以使用**xlfEvaluate**来查找该名称, 从而获取 ID。 
  
_pxArg1 .。。_
  
对用户定义函数的零个或多个参数。 在 Excel 2007 之前的版本中调用此函数时, 可以传递的其他参数的最大数目为 29, 即 30 (包括_pxFnRef_)。 从 Excel 2007 开始, 此限制将提升到 254, 其中为 255, 其中包括_pxFnRef_。
  
## <a name="return-value"></a>返回值

返回用户定义的函数返回的任何值。
  
## <a name="example"></a>示例

下面的示例在 book1.xls 中的 sheet Macro1 上运行**TestMacro** 。.xls. 请确保该宏位于名为 Macro1 的工作表上。 
  
`\SAMPLES\EXAMPLE\EXAMPLE.C`
  
```cs
short WINAPI xlUDFExample(void)
{       
   XLOPER12 xMacroName, xMacroRef, xRes;
   xMacroName.xltype = xltypeStr;
   xMacroName.val.str = L"\044[BOOK1.XLSX]Macro1!TestMacro";
   Excel12(xlfEvaluate, &xMacroRef, 1, (LPXLOPER12)&xMacroName);
   Excel12(xlUDF, &xRes, 1, (LPXLOPER12)&xMacroRef);
   return 1;
}
```

## <a name="see-also"></a>另请参阅

- [只能从 DLL 或 XLL 调用的 C API 函数](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)

