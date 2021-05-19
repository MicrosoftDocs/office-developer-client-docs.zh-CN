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
  
当模式对话框显示在活动窗口Microsoft Excel时，光标是活动窗口上的繁忙Excel光标。 此 **WndProc** 捕获WM_SETCURSOR类型Windows消息，将光标更改回正常箭头。 
  
```cs
LRESULT CALLBACK ExcelCursorProc(HWND hwnd, UINT wMsg, WPARAM wParam, LPARAM lParam);
```

## <a name="parameters"></a>参数

 _hWndDlg_ (**HWND**) 
  
包含对话框Windows HWND 对象句柄。
  
 _message_ (**UINT**) 
  
要响应的邮件。
  
 _wParam_ (**WPARAM**) 
  
 _lParam_ (**LPARAM**) 
  
由 Windows。
  
## <a name="property-valuereturn-value"></a>属性值/返回值

LRESULT： 0 如果邮件已处理，否则由默认 **WndProc 返回的结果**。
  
### <a name="example"></a>示例

有关  `\SAMPLES\GENERIC\GENERIC.C` 此函数的源代码，请参阅 。 
  
## <a name="see-also"></a>另请参阅



[通用 DLL 中的函数](functions-in-the-generic-dll.md)

