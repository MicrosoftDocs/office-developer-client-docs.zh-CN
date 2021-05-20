---
title: xlSheetNm
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- xlSheetNm
keywords:
- xlsheetnm 函数 [excel 2007]
localization_priority: Normal
ms.assetid: bcb16207-5499-4474-b006-51ccde1002d7
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 5d62be7ebef71547de3a903db4c1a030984b8640
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33437411"
---
# <a name="xlsheetnm"></a>xlSheetNm

**适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
从外部引用中包含的工作表或宏表的内部工作表 ID 中返回工作表或宏表的名称，如果传递了内部引用，则返回当前工作表的名称。
  
```cs
Excel12(xlSheetNm, LPXLOPER12 pxRes, 1, LPXLOPER12 pxExtref);
```

## <a name="parameters"></a>参数

_pxExtref_ (**xltypeRef** 或 **xltypeSRef**) 
  
对需要其名称的工作表的引用。
  
如果要向 **xltypeRef** (外部引用) 只需包含工作表的 ID。 工作表上描述单元格的数据结构将被忽略，并且不需要提供。 如果 ID 设置为零， **则 xlSheetNm** 将返回当前工作表的名称。 
  
如果要向 **xltypeSef** (内部引用) ， **则 xlSheetNm** 将返回当前工作表的名称。 
  
## <a name="property-valuereturn-value"></a>属性值/返回值

以 形式返回 **xltypeStr ()** 的名称  `[Book1]Sheet1` 。
  
## <a name="example"></a>示例

下面的示例显示从中调用函数的工作表的名称。 函数只有在执行 XLM 命令宏时从宏工作表调用时才能正常工作。 这是因为它调用 **xlcAlert**，只有命令才能执行，并且需要从工作表而不是对话框、菜单或命令栏调用它，以便 **xlfCaller** 返回引用。 
  
`\SAMPLES\EXAMPLE\EXAMPLE.C`
  
```cs
short WINAPI xlSheetNmExample(void)
{
   XLOPER12 xRes, xSheetName;
   Excel12(xlfCaller, &xRes, 0);
   Excel12(xlSheetNm, &xSheetName, 1, (LPXLOPER12)&xRes);
   Excel12(xlcAlert, 0, 1, (LPXLOPER12)&xSheetName);
   Excel12(xlFree, 0, 1, (LPXLOPER12)&xSheetName);
   return 1;
}
```

## <a name="see-also"></a>另请参阅

- [xlSheetId](xlsheetid.md)
- [只能从 DLL 或 XLL 调用的 C API 函数](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)

