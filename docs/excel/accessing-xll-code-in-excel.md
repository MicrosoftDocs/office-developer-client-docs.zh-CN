---
title: 在 Excel 中访问 XLL 代码
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
keywords:
- 访问 xll 代码 [excel 2007],XLL [Excel 2007],访问代码,命令 [Excel 2007],注册,函数 [Excel 2007],注册,从 Excel 调用 XLL,注册命令 [Excel 2007],注册函数 [Excel 2007]
ms.assetid: 6e4bf1f3-8eca-4be5-9632-75355ac31d61
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
localization_priority: Priority
ms.openlocfilehash: d1332b0dffc052404c75c4ec51d94879457c3da0
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28705279"
---
# <a name="accessing-xll-code-in-excel"></a>在 Excel 中访问 XLL 代码

**适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
要在 Microsoft Excel 中可供访问，XLL 包含的函数和命令需满足以下条件：
  
- 必须通过 XLL 导出。
    
- 必须使用 Excel 进行注册。
    
## <a name="registering-functions-and-commands-with-excel"></a>使用 Excel 注册函数和命令

注册会指示 Excel 以下关于 DLL 入口点的信息：
  
- 它是否隐藏，或者如果是函数，是否在“函数向导”中可见。
    
- 是只能从 XLM 宏表调用它，还是同样可以从工作表调用。
    
- 如果是命令，那么它是工作表函数还是宏表等效函数。
    
- 它的 XLL/DLL 导出名是什么，以及你希望 Excel 使用什么名称。
    
- 如果它是一个函数：
    
  - 它返回并将其作为参数的数据类型。
    
  - 它是否通过修改相应的参数返回结果。
    
  - 它是否易变。
    
  - 它是否为线程安全函数（在 Excel 2007 中开始受支持）。
    
  - “粘贴函数向导”和“自动完成”编辑器应显示什么文本来帮助调用函数。
    
  - 它应列在哪个函数类别下。
    
可通过使用 C API 函数 [xlfRegister](xlfregister-form-1.md)（相当于 XLM 函数 **REGISTER**）来实现。
  
## <a name="calling-xll-functions-directly-from-excel"></a>直接从 Excel 调用 XLL 函数

注册后，可以从调用内置函数的任何位置调用 XLL 工作表和宏表函数：
  
- 工作表上的单个单元格或数组公式。
    
- 宏表上的单个单元格或数组公式。
    
- 已定义名称的定义。
    
- 条件格式对话框中的条件和限制字段。
    
- 在另一个加载项中通过 C API 函数 [xlUDF](xludf.md) 实现。
    
- 在 Visual Basic for Applications (VBA) 中通过 **Application.Run** 方法实现。 
    
可以使用 C API 函数 **xlfCaller** 获取对函数中的调用单元格或单元格区域的引用。 如果从单元格的条件格式表达式调用该函数，则仍然会返回对一个或多个相关单元格的引用，因此不能假定单元格的公式包含 XLL 函数。 如果函数是从 VBA 用户定义函数 (UDF) 调用的，**xlfCaller** 将再次返回调用了 VBA 函数的单元格的地址。 有关详细信息，请参阅 [xlfCaller](xlfcaller.md)。
  
> [!NOTE]
> Excel 还从“粘贴函数向导”**** 和“替换”**** 对话框中调用 XLL 函数代码。 在“粘贴函数参数”**** 对话框中，可能需要限制代码的正常运行，特别是在函数执行时间很长的情况下。 要检测是否从这些对话框中调用函数，必须在项目中实现一些代码，这些代码遍历所有打开的窗口，确定前窗口是否是这些对话框之一，如果是，则确定是哪个对话框。 
  
## <a name="calling-xll-commands-directly-from-excel"></a>直接从 Excel 调用 XLL 命令

注册后，就可以像调用其他用户定义的宏一样调用 XLL 命令了，具体方法如下：
  
- 通过与嵌入工作表中的控件对象相关联。
    
- 从“运行宏”对话框执行操作。
    
- 通过使用 **Application.Run** 方法的 VBA 用户定义的宏。 
    
- 从自定义菜单项或工具栏执行操作。
    
- 使用注册命令时设置的快捷键。
    
- 作为捕获指定事件时要运行的命令。
    
> [!NOTE]
> XLL 命令处于隐藏状态，它们不会出现在 Excel 对话框的可用宏列表中。 但是可以手动将它们输入到宏名称字段中。 Excel 希望这些对话框中显示像是注册过的名称，而不是 DLL 导出名称。 
  
Excel 假定使用 Excel 注册的所有 XLL 命令采用以下形式：
  
```cs
short WINAPI xll_cmd_name(void)
{
// Function code...
    return 1;
}

```

Excel 将忽略返回值，除非是通过 XLM 宏工作表调用该值，在此情况下，返回值将转换为 **TRUE** 或 **FALSE**。 因此，如果命令执行成功，应返回 1，如果失败或者被用户取消，则返回 0。
  
可以获取有关如何使用 C API函数 **xlfCaller** 调用命令的信息。 有关详细信息，请参阅 [xlfCaller](xlfcaller.md)。
  
从 Excel 2007 开始，用户界面与早期版本不不相同。 大多数情况下仍然支持允许添加和删除自定义菜单栏、菜单、子菜单、菜单项、自定义工具栏和工具栏按钮的 C API 函数。 但是，它们可能并不总是以用户熟悉的方式提供添加的项。 应仔细检查任何添加的功能是否仍然可访问，或实现特定于版本的自定义项。 从 Excel 2007 开始，用户界面最好使用托管代码模块进行自定义，该模块随后可与 XLL 命令紧密结合。
  
## <a name="see-also"></a>另请参阅

- [创建 XLL](creating-xlls.md)
- [从“函数向导”或“替换”对话框调用 XLL 函数](how-to-call-xll-functions-from-the-function-wizard-or-replace-dialog-boxes.md)
- [加载项管理器和 XLL 接口函数](add-in-manager-and-xll-interface-functions.md)
- [开发 Excel XLL](developing-excel-xlls.md)



