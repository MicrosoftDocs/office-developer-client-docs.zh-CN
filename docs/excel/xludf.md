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
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 569334847c7612b86f6ddc967f159e2ef425cbbb
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33430642"
---
# <a name="xludf"></a>xlUDF

**适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
使用 UDF 函数 (用户) 。 此函数允许 DLL 调用 Visual Basic for Applications (VBA) 用户定义函数、XLM 宏语言函数和其他加载项中包含的已注册函数。
  
```cs
Excel12(xlUDF, LPXLOPER12 pxRes, int iCount, LPXLOPER12 pxFnRef,
LPXLOPER12 pxArg1, ...);
```

## <a name="parameters"></a>参数

_pxFnRef_ (xltypeRef、xltypeSRef、xltypeStr 或 **xltypeNum**)   
  
要调用的函数的引用。 它可以是宏工作表单元格引用、字符串形式函数的注册名称或函数的注册 ID。 对于使用 **xlfRegister 或** **REGISTER（** 提供的参数  _pxFunctionText）_ 注册的 XLL 加载项函数，可以通过使用 **xlfEvaluate** 查找名称来获取 ID。 
  
_pxArg1， ..._
  
用户定义的函数的零个或多个参数。 在 Excel 2007 以前的版本中调用此函数时，可以传递的其他参数的最大数量为 29，即 30（包括 _pxFnRef）。_ 从 2007 Excel，此限制将提升至 254，即 255（包括 _pxFnRef）。_
  
## <a name="return-value"></a>返回值

返回用户定义函数返回的任何值。
  
## <a name="example"></a>示例

下面的示例在工作表 **Macro1** 上的 BOOK1.XLS。 确保宏位于名为 Macro1 的工作表上。 
  
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

