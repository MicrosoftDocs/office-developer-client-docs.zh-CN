---
title: DIALOGMsgProc
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- DIALOGMsgProc
keywords:
- dialogmsgproc 函数 [excel 2007]
localization_priority: Normal
ms.assetid: 9a538e83-ba34-4806-bb8c-7cda3beb6b66
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 3a69d192babbcf0419850e203f51d8cfd81cdef6
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773642"
---
# <a name="dialogmsgproc"></a>DIALOGMsgProc

**适用于** Excel 2013 | Office 2013 | Visual Studio 
  
此过程相关联的[fShowDialog](fshowdialog.md)本机 Windows 对话框显示。 它提供了 Windows 用户运行对话框的按钮，输入字段或控件之一时，会发生的事件 （邮件） 调用服务例程。 
  
```cs
BOOL CALLBACK DIALOGMsgProc(HWND hWndDlg, UINT message, WPARAM wParam, LPARAM lParam);
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

 **TRUE**如果消息处理， **FALSE**如果不需要。 
  
### <a name="example"></a>示例

请参阅`\SAMPLES\GENERIC\GENERIC.C`的此函数的源代码。 
  
## <a name="see-also"></a>另请参阅



[通用 DLL 中的函数](functions-in-the-generic-dll.md)

