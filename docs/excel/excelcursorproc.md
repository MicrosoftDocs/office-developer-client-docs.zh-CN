---
title: ExcelCursorProc
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- ExcelCursorProc
keywords:
- excelcursorproc 函数 [excel 2007]
localization_priority: Normal
ms.assetid: 43759617-998d-4030-a17d-c4bbe35ffaf9
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: d3cc41487f0cae31e110249fe148f5370319a39a
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33432490"
---
# <a name="excelcursorproc"></a>ExcelCursorProc

 **适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
当在 Microsoft Excel 窗口上显示模式对话框时, 光标在 Excel 窗口上是一个繁忙的光标。 此**WndProc**陷阱 WM_SETCURSOR 键入 Windows 消息, 并将光标更改回正常箭头。 
  
```cs
LRESULT CALLBACK ExcelCursorProc(HWND hwnd, UINT wMsg, WPARAM wParam, LPARAM lParam);
```

## <a name="parameters"></a>参数

 _hWndDlg_(**HWND**)
  
包含对话框的 HWND 窗口句柄。
  
 _邮件_(**UINT**)
  
要响应的邮件。
  
 _wParam_(**WPARAM**)
  
 _lParam_(**LPARAM**)
  
由 Windows 传递的参数。
  
## <a name="property-valuereturn-value"></a>属性值/返回值

LRESULT: 0 如果已处理邮件, 否则由默认**WndProc**返回的结果。
  
### <a name="example"></a>示例

有关`\SAMPLES\GENERIC\GENERIC.C`此函数的源代码, 请参阅。 
  
## <a name="see-also"></a>另请参阅



[通用 DLL 中的函数](functions-in-the-generic-dll.md)

