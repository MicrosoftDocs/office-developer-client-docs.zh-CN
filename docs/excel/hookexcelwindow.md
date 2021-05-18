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
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 4103bf3a95388d20efeb74fcd736aeb5520d0845
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33413505"
---
# <a name="hookexcelwindow"></a>HookExcelWindow

 **适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
安装 **ExcelCursorProc，** 以便它先于主 **WndProc** Microsoft Excel调用。
  
```cs
extern void FAR PASCAL HookExcelWindow(HANDLE hWndExcel);
```

## <a name="parameters"></a>参数

 _hWndExcel_ (**HANDLE**) 
  
主Excel句柄Windows句柄。
  
## <a name="property-valuereturn-value"></a>属性值/返回值

函数不返回值。
  
## <a name="remarks"></a>备注

该函数使用 **GetWindowLong** Excel获取 **WndProc** () 。 它将此值存储在全局中，可用于调用默认 **WndProc** 并还原它。 最后，它将此地址替换为使用 **SetWindowLong** () 的 **ExcelCursorProc** 地址。
  
### <a name="example"></a>示例

有关  `\SAMPLES\GENERIC\GENERIC.C` 此函数的源代码，请参阅 。 
  
## <a name="see-also"></a>另请参阅



[通用 DLL 中的函数](functions-in-the-generic-dll.md)

