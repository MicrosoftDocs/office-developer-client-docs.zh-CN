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
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: aef2734aeb4d9cf5df33e3d012cef309e8a1eb6e
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33409445"
---
# <a name="unhookexcelwindow"></a>UnhookExcelWindow

 **适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
删除以前由 **HookExcelWindow** 安装的 **ExcelCursorProc。** 这应该已经完成，以便 **ExcelCursorProc** 在主 **WndProc Microsoft Excel之前调用**。
  
```cs
extern void FAR PASCAL UnhookExcelWindow(HANDLE hWndExcel);
```

## <a name="parameters"></a>参数

 _hWndExcel_ (**HANDLE**) 
  
主Excel句柄Windows句柄。
  
## <a name="property-valuereturn-value"></a>属性值/返回值

函数不返回值。
  
## <a name="remarks"></a>备注

此函数使用 **SetWindowLong** Excel还原默认 **WndProc** () 以还原 **由 HookExcelWindow** () 保存的地址。
  
### <a name="example"></a>示例

有关  `\SAMPLES\GENERIC\GENERIC.C` 此函数的源代码，请参阅 。 
  
## <a name="see-also"></a>另请参阅



[通用 DLL 中的函数](functions-in-the-generic-dll.md)

