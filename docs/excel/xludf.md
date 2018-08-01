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
ms.openlocfilehash: 8f45f800ca50d2a46792e7cf5e00ac25bd099e8c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773869"
---
# <a name="xludf"></a>xlUDF

**适用于** Excel 2013 | Office 2013 | Visual Studio 
  
调用用户定义函数 (UDF)。 此功能允许 DLL 调用 Visual Basic for Applications (VBA) 用户定义的函数、 XLM 宏语言函数和注册其他加载项中包含的函数。
  
```cs
Excel12(xlUDF, LPXLOPER12 pxRes, int iCount, LPXLOPER12 pxFnRef,
LPXLOPER12 pxArg1, ...);
```

## <a name="parameters"></a>参数

_pxFnRef_（**xltypeRef**、 **xltypeSRef**、 **xltypeStr**或**xltypeNum**）
  
要调用的函数的引用。 这可以是宏工作表单元格引用，作为字符串函数的已注册名称或注册 ID 的函数。 对于 XLL 加载项函数注册使用提供的参数_pxFunctionText_ **xlfRegister**或**注册**，可以通过使用**xlfEvaluate**查找名称获得 ID。 
  
_pxArg1..._
  
零个或多个用户定义函数的参数。 时要调用此函数中版本早于 Excel 2007，可以传递的其他参数的最大数量为 29，这是 30 包括_pxFnRef_。 从 Excel 2007 开始，此限制增加到 254，这是 255 包括_pxFnRef_。
  
## <a name="return-value"></a>返回值

返回任何值返回的用户定义函数。
  
## <a name="example"></a>示例

下面的示例表 Macro1 BOOK1 中运行**TestMacro** 。XLS。 请确保为宏名为 Macro1 工作表上。 
  
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

