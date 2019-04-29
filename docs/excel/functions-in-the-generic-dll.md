---
title: 通用 DLL 中的函数
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
keywords:
- 泛型 dll [excel 2007], 函数, 函数 [excel 2007], 泛型 dll
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
  
该文件夹`\EXAMPLES\GENERIC\`包含用于编译示例 DLL 的示例常规 xll 的 Microsoft Visual Studio 项目文件和源代码文件。 您可以将此项目用作模板, 以编写自己的 Microsoft Excel xll。 此项目中的源代码演示了 Excel C API 的许多功能。 
  
加载 GENERIC 时, 它将创建一个具有四个命令的新的**通用**菜单: 
  
- **对话框**-显示 "Microsoft Excel" 对话框。 
    
- **Dance** -在周围移动所选内容, 直到按**ESC**键。 
    
- "**本机对话框**"-显示 Windows 对话框。 
    
- **退出**-卸载 generic 并删除**通用**菜单。 
    
generic 还提供了三个工作表函数、Func1、FuncSum 和 FuncFib, 可以在加载 GENERIC xll 时使用这些函数。 可以使用加载项管理器加载常规 xll, 如果它在最后一个 Excel 会话的正常结束时处于活动状态, 则会加载。
  
此项目使用框架库 (FRMWRK32)。
  
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

