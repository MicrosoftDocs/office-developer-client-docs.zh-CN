---
title: 显示对话框从 DLL 或 XLL 中
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
keywords:
- xll [excel 2007]，显示对话框中，对话框 [Excel 2007]，显示从 DLL 或 XLL，显示对话框从 Dll [Excel 2007]
localization_priority: Normal
ms.assetid: e77ac555-331d-41c8-a000-7b178959754d
description: ���÷�Χ�� Excel 2013?| Office 2013?| Visual Studio
ms.openlocfilehash: afb21125bc54a2607a997c7b2f7c73ef2f528f28
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773651"
---
# <a name="displaying-dialog-boxes-from-within-a-dll-or-xll"></a>显示对话框从 DLL 或 XLL 中

 **适用于**： Excel 2013 |Office 2013 |Visual Studio 
  
若要显示 Win32 对话框中使用，例如 Windows SDK 函数**DialogBox**，首先必须适用于 Excel 获取完整的 32 位实例和主窗口句柄。 有关详细信息，请参阅[访问 Excel 实例，主窗口句柄](how-to-access-excel-instance-and-main-window-handles.md)。 
  
假定您的项目包含对话框资源，必须执行以下几个步骤以设置为的新显示的对话框中的消息处理例程并恢复 Excel 邮件处理例程时关闭对话框。 通用项目中的示例命令[fShowDialog](fshowdialog.md)演示了 Windows 函数以正确执行此操作。 
  
您还可以显示对话框，而无需使用 Windows SDK 函数中使用 C API。 但是，C API 的对话框框功能是非常有限与 Windows、 Visual Basic for Applications (VBA) 或 Microsoft 基础类 (MFC) 的比较。 （例如，C API 对话框始终是有模式）。
  
## <a name="see-also"></a>另请参阅



[创建 xll （英文）](creating-xlls.md)
  
[开发 Dll](developing-dlls.md)
  
[访问 Excel 实例和主窗口句柄](how-to-access-excel-instance-and-main-window-handles.md)
  
[只能从 DLL 或 XLL 调用的 C API 函数](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)

