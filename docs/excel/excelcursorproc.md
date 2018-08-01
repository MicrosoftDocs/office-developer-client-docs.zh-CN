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
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 07be8da4a07b988d5e848048a088859b58ea3a14
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773741"
---
# <a name="excelcursorproc"></a>ExcelCursorProc

 **适用于** Excel 2013 | Office 2013 | Visual Studio 
  
通过 Microsoft Excel 窗口显示一个模式对话框时，光标通过 Excel 窗口是忙游标。 此**WndProc**陷阱 WM_SETCURSOR 键入 Windows 消息和更改光标回正常的箭头。 
  
```cs
LRESULT CALLBACK ExcelCursorProc(HWND hwnd, UINT wMsg, WPARAM wParam, LPARAM lParam);
```

## <a name="parameters"></a>参数

 _hWndDlg_(**HWND**)
  
包含对话框的 HWND Windows 句柄。
  
 _消息_(**UINT**)
  
要回复的消息。
  
 _wParam_(**WPARAM**)
  
 _lParam_(**LPARAM**)
  
通过 Windows 传递的参数。
  
## <a name="property-valuereturn-value"></a>属性值/返回值

Lresult 替换： 如果消息处理 0，否则返回的结果由默认**WndProc**。
  
### <a name="example"></a>示例

请参阅`\SAMPLES\GENERIC\GENERIC.C`的此函数的源代码。 
  
## <a name="see-also"></a>另请参阅



[通用 DLL 中的函数](functions-in-the-generic-dll.md)

