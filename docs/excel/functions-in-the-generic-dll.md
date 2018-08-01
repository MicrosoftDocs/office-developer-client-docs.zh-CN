---
title: 通用 DLL 中的函数
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
keywords:
- 泛型 dll [excel 2007，] 函数，函数 [Excel 2007，] 泛型 DLL
localization_priority: Normal
ms.assetid: 80ce2247-d69d-45b0-b5e2-4ff0d7078a2c
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: e78f276e58ca1c98786e28ed5167762cf0bfdf7f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773767"
---
# <a name="functions-in-the-generic-dll"></a>通用 DLL 中的函数

 **适用于** Excel 2013 | Office 2013 | Visual Studio 
  
文件夹`\EXAMPLES\GENERIC\`包含 Microsoft Visual Studio 项目文件和所需编译该示例 DLL GENERIC.xll 源代码文件。 编写您自己的 Microsoft Excel Xll 可作为模板用于此项目。 此项目中的源代码演示了许多 Excel C API 的功能。 
  
当加载 GENERIC.xll 时，它使用四个命令创建一个新的**泛型**菜单： 
  
- **对话框**-显示 Microsoft Excel 对话框。 
    
- **舞**-移动所选内容，直到您按**ESC**键。 
    
- **本机对话框**-显示 Windows 对话框。 
    
- **退出**-卸载 GENERIC.xll 并删除**通用**菜单。 
    
GENERIC.xll 还提供了三个工作表函数、 Func1、 FuncSum 和 FuncFib，每当加载 GENERIC.xll 可以使用它。 可使用的加载项管理器中，加载 GENERIC.xll 或加载如果在正常的最后一个 Excel 会话结束处于活动状态。
  
此项目使用 framework 库 (FRMWRK32.lib)。
  
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

