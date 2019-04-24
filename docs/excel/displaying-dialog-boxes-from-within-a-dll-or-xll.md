---
title: 在 DLL 或 XLL 中显示对话框
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
keywords:
- xll [excel 2007], 显示对话框 from、对话框 [excel 2007]、从 DLL 或 XLL 显示对话框、dll [excel 2007]、显示对话框
localization_priority: Normal
ms.assetid: e77ac555-331d-41c8-a000-7b178959754d
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 7b00430b047fe792afef701d210ccde06dd16216
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32310933"
---
# <a name="displaying-dialog-boxes-from-within-a-dll-or-xll"></a>在 DLL 或 XLL 中显示对话框

 **适用于** Excel 2013 | Office 2013 | Visual Studio 
  
若要显示 Win32 对话框 (例如, 使用 Windows SDK 函数**video.dialogbox.html**), 必须首先获取 Excel 的完整32位实例和主窗口句柄。 有关详细信息, 请参阅[Access Excel 实例和主窗口句柄](how-to-access-excel-instance-and-main-window-handles.md)。 
  
假定您的项目包含对话框资源, 则必须执行几个步骤, 将消息处理例程设置为新显示的对话框, 并在关闭该对话框时还原 Excel 消息处理例程。 通用项目中的示例命令[fShowDialog](fshowdialog.md)演示如何使用 Windows 函数来正确执行此操作。 
  
您还可以使用 C API 显示对话框, 而无需使用 Windows SDK 函数。 但是, 与 Windows、Visual Basic for Applications (VBA) 或 Microsoft 基础类 (MFC) 相比, C API 的对话框功能非常有限。 (例如, C API 对话框始终是模式的)。
  
## <a name="see-also"></a>另请参阅



[创建 XLL](creating-xlls.md)
  
[开发 DLL](developing-dlls.md)
  
[访问 Excel 实例和主窗口句柄](how-to-access-excel-instance-and-main-window-handles.md)
  
[只能从 DLL 或 XLL 调用的 C API 函数](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)

