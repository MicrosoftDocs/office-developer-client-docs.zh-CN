---
title: 显示 DLL 或 XLL 中的对话框
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
keywords:
- xlls [excel 2007]， displaying dialog boxes from，dialog boxes [Excel 2007]， displaying from a DLL or XLL，DLL [Excel 2007]， displaying dialog boxes from
localization_priority: Normal
ms.assetid: e77ac555-331d-41c8-a000-7b178959754d
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 7b00430b047fe792afef701d210ccde06dd16216
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33417866"
---
# <a name="displaying-dialog-boxes-from-within-a-dll-or-xll"></a>显示 DLL 或 XLL 中的对话框

 **适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
若要使用例如 Windows SDK 函数 **DialogBox** 显示 Win32 对话框，必须先获取 Excel 的完整 32 位实例和主窗口句柄。 有关详细信息，请参阅访问 [Excel 实例和主窗口句柄](how-to-access-excel-instance-and-main-window-handles.md)。 
  
假定您的项目包含对话框资源，则必须执行几个步骤，将消息处理例程设置为新显示的对话框的例程，以及当对话框关闭时还原 Excel 邮件处理例程。 Generic 项目中 [的示例命令 fShowDialog](fshowdialog.md) 演示了如何使用 Windows 函数正确完成此操作。 
  
您还可以使用 C API 显示对话框，而无需使用 Windows SDK 函数。 但是，与 Windows、Visual Basic for Applications (VBA) 或 Microsoft Foundation Classes (MFC) 相比，C API 的对话框功能非常有限。  (例如，C API 对话框始终是模式) 。
  
## <a name="see-also"></a>另请参阅



[创建 XLL](creating-xlls.md)
  
[开发 DLL](developing-dlls.md)
  
[访问 Excel 实例和主窗口句柄](how-to-access-excel-instance-and-main-window-handles.md)
  
[只能从 DLL 或 XLL 调用的 C API 函数](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)

