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
ms.openlocfilehash: 5d62be7ebef71547de3a903db4c1a030984b8640
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32303869"
---
# <a name="xlsheetnm"></a>xlSheetNm

**适用于** Excel 2013 | Office 2013 | Visual Studio 
  
返回包含在外部引用中的工作表或宏表的内部表 ID 中的名称, 或当前工作表的名称 (如果传递了内部引用)。
  
```cs
Excel12(xlSheetNm, LPXLOPER12 pxRes, 1, LPXLOPER12 pxExtref);
```

## <a name="parameters"></a>参数

_pxExtref_(**xltypeRef**或**xltypeSRef**)
  
对需要其名称的工作表的引用。
  
如果要传递外部引用 (**xltypeRef**), 它只需要包含工作表的 ID。 对工作表上的单元格进行描述的数据结构将被忽略且无需提供。 如果将 ID 设置为零, **xlSheetNm**将返回当前工作表的名称。 
  
如果传递的是内部引用 (**xltypeSef**), 则**xlSheetNm**将返回当前工作表的名称。 
  
## <a name="property-valuereturn-value"></a>属性值/返回值

返回窗体`[Book1]Sheet1`中的工作表名称 (**xltypeStr**)。
  
## <a name="example"></a>示例

下面的示例显示从中调用函数的工作表的名称。 只有在执行 XLM 命令宏时从宏表中调用时, 函数才能正常运行。 这是因为它调用**xlcAlert**, 这只是命令可以执行的操作, 而需要从工作表 (而不是对话框、菜单或命令栏) 中调用, 以便**xlfCaller**返回引用。 
  
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

