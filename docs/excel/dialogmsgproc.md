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
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 1de1b73f5672067f07518ef3367d77349395a1c3
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33406512"
---
# <a name="dialogmsgproc"></a>DIALOGMsgProc

**适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
此过程与[fShowDialog](fshowdialog.md)显示的本机Windows对话框相关联。 它提供由 Windows 调用的服务例程， (用户) 按钮、输入字段或控件之一时发生的) 消息。 
  
```cs
BOOL CALLBACK DIALOGMsgProc(HWND hWndDlg, UINT message, WPARAM wParam, LPARAM lParam);
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

 如果邮件已处理，则其为 **TRUE;** 如果未处理，则为 **FALSE。** 
  
### <a name="example"></a>示例

有关  `\SAMPLES\GENERIC\GENERIC.C` 此函数的源代码，请参阅 。 
  
## <a name="see-also"></a>另请参阅



[通用 DLL 中的函数](functions-in-the-generic-dll.md)

