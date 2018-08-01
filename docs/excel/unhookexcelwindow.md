---
title: UnhookExcelWindow
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- UnhookExcelWindow
keywords:
- unhookexcelwindow 函数
localization_priority: Normal
ms.assetid: 6508cb69-0c7c-4d8c-a466-dd79eb13e316
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 7b70bf4ed0ff45921df407605baa692c7621bca4
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773828"
---
# <a name="unhookexcelwindow"></a>UnhookExcelWindow

 **适用于** Excel 2013 | Office 2013 | Visual Studio 
  
删除以前安装的**HookExcelWindow** **ExcelCursorProc** 。 这将具有已完成，以便**ExcelCursorProc**已在 Microsoft Excel 主**WndProc**之前调用。
  
```cs
extern void FAR PASCAL UnhookExcelWindow(HANDLE hWndExcel);
```

## <a name="parameters"></a>参数

 _hWndExcel_（**处理**）
  
Excel 主窗口的句柄。
  
## <a name="property-valuereturn-value"></a>属性值/返回值

该函数不返回值。
  
## <a name="remarks"></a>说明

此函数将还原 Excel 默认**WndProc**使用**SetWindowLong()** 还原**HookExcelWindow()** 保存的地址。
  
### <a name="example"></a>示例

请参阅`\SAMPLES\GENERIC\GENERIC.C`的此函数的源代码。 
  
## <a name="see-also"></a>另请参阅



[通用 DLL 中的函数](functions-in-the-generic-dll.md)

