---
title: HookExcelWindow
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- HookExcelWindow
keywords:
- hookexcelwindow 函数 [excel 2007]
localization_priority: Normal
ms.assetid: 13f0ae5e-9951-4e89-a245-7cf68c6f6724
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 8965cc6b1e3d24001c42744f2ee7d447aa4c79b5
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773760"
---
# <a name="hookexcelwindow"></a>HookExcelWindow

 **适用于** Excel 2013 | Office 2013 | Visual Studio 
  
安装**ExcelCursorProc** ，以便在 Microsoft Excel 主**WndProc**之前调用。
  
```cs
extern void FAR PASCAL HookExcelWindow(HANDLE hWndExcel);
```

## <a name="parameters"></a>参数

 _hWndExcel_（**处理**）
  
Excel 主窗口的句柄。
  
## <a name="property-valuereturn-value"></a>属性值/返回值

该函数不返回值。
  
## <a name="remarks"></a>说明

该函数获取 Excel **WndProc** **GetWindowLong()** 使用的地址。 它将此值存储在全局可用于调用默认**WndProc**和还将其还原。 最后，它会替换此地址**ExcelCursorProc**使用**SetWindowLong()** 的地址。
  
### <a name="example"></a>示例

请参阅`\SAMPLES\GENERIC\GENERIC.C`的此函数的源代码。 
  
## <a name="see-also"></a>另请参阅



[通用 DLL 中的函数](functions-in-the-generic-dll.md)

