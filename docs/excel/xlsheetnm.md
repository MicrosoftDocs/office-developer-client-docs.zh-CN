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
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 815565d886b1aea203f6b3b9774325d6b534abd2
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773868"
---
# <a name="xlsheetnm"></a>xlSheetNm

**适用于** Excel 2013 | Office 2013 | Visual Studio 
  
从包含内外部的引用，或者当前工作表的名称，如果传递内部参考其内部工作表 ID 返回工作表或宏表的名称。
  
```cs
Excel12(xlSheetNm, LPXLOPER12 pxRes, 1, LPXLOPER12 pxExtref);
```

## <a name="parameters"></a>参数

_pxExtref_（**xltypeRef**或**xltypeSRef**）
  
对工作表名称所需的引用。
  
如果将传递外部引用 (**xltypeRef**) 它只需包含的工作表的 ID。 介绍在工作表单元格的数据结构将被忽略，无需提供。 如果 ID 设置为零，则**xlSheetNm**返回当前工作表的名称。 
  
如果将传递内部引用 (**xltypeSef**)， **xlSheetNm**返回当前工作表的名称。 
  
## <a name="property-valuereturn-value"></a>属性值/返回值

返回窗体中的工作表 (**xltypeStr**) 的名称`[Book1]Sheet1`。
  
## <a name="example"></a>示例

下面的示例显示从中调用该函数的工作表的名称。 仅当从宏表执行 XLM 命令宏时调用，该函数可以正常工作。 这是因为它调用**xlcAlert**，其中仅命令可执行的操作，则需要从工作表而不是对话框中，菜单上或**xlfCaller**返回的引用的顺序中的命令栏调用。 
  
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

