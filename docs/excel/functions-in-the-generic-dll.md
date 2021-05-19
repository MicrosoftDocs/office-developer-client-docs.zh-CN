---
title: 通用 DLL 中的函数
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
keywords:
- generic dll [excel 2007]， functions，functions [Excel 2007]， Generic DLL
localization_priority: Normal
ms.assetid: 80ce2247-d69d-45b0-b5e2-4ff0d7078a2c
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 3064e1a09ad8850e121da678f3702a6236574599
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33420596"
---
# <a name="functions-in-the-generic-dll"></a>通用 DLL 中的函数

 **适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
该文件夹 `\EXAMPLES\GENERIC\` 包含Microsoft Visual Studio DLL GENERIC.xll 示例所需的项目文件和源代码文件。 您可以将此项目用作编写您自己的 XLL Microsoft Excel模板。 此项目中的源代码演示了 C API Excel功能。 
  
加载 GENERIC.xll 时，它会创建一个包含四个命令的新 **"通用** "菜单： 
  
- **对话框**- 显示Microsoft Excel对话框。 
    
- **当** 按下 Esc 键之前，将所选内容 **四处** 移动。 
    
- **本机对话框**- 显示Windows对话框。 
    
- **Exit** - 卸载 GENERIC.xll 并删除 **"泛型"** 菜单。 
    
GENERIC.xll 还提供了三个工作表函数 Func1、FuncSum 和 FuncFib，每次加载 GENERIC.xll 时都可以使用。 可以使用外接程序管理器加载 GENERIC.xll，或者，如果它在上一个加载项会话的普通末尾处于活动状态，Excel加载。
  
此项目使用 FRMWRK32.lib (框架库) 。
  
## <a name="in-this-section"></a>本节内容

[DIALOGMsgProc](dialogmsgproc.md)
  
[ExcelCursorProc](excelcursorproc.md)
  
[HookExcelWindow](hookexcelwindow.md)
  
[UnhookExcelWindow](unhookexcelwindow.md)
  
[fShowDialog](fshowdialog.md)
  
[fDance](fdance.md)
  
[fDialog/fDialog12](fdialog-fdialog12.md)
  
[fExit](fexit.md)
  
[Func1](func1.md)
  
[FuncSum](funcsum.md)
  
[FuncFib](funcfib.md)
  
## <a name="see-also"></a>另请参阅



[框架库中的函数](functions-in-the-framework-library.md)

