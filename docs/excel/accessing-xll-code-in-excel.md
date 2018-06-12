---
title: 在 Excel 中访问 XLL 代码
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
keywords:
- 中访问 xll 代码 [excel 2007]，Xll [Excel 2007]，访问代码、 命令 [Excel 2007]、 注册、 函数 [Excel 2007]、 注册，从 Excel 调用 xll （英文）、 注册命令 [Excel 2007]，注册函数 [Excel 2007]
localization_priority: Normal
ms.assetid: 6e4bf1f3-8eca-4be5-9632-75355ac31d61
description: ���÷�Χ�� Excel 2013?| Office 2013?| Visual Studio
ms.openlocfilehash: 1523f9e8213cb955f1bfd995c42f921b001299fe
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773637"
---
# <a name="accessing-xll-code-in-excel"></a>在 Excel 中访问 XLL 代码

**适用于**： Excel 2013 |Office 2013 |Visual Studio 
  
可在 Microsoft Excel、 函数和 XLL 包含的命令：
  
- 必须通过 XLL 导出。
    
- 必须使用 Excel 注册。
    
## <a name="registering-functions-and-commands-with-excel"></a>使用 Excel 中注册的函数和命令

注册告诉 Excel 以下关于 DLL 入口点：
  
- 它隐藏还是，如果一个函数，它可见在函数向导。
    
- 是否为仅从 XLM 宏工作表或还从工作表，可调用。
    
- 如果一个命令，它工作表函数或宏表等效功能。
    
- 其 XLL 或动态链接库导出名称是什么，并且想要使用的 Excel 什么名称。
    
- 如果它是一个函数：
    
  - 哪些数据类型它返回，并采用作为参数。
    
  - 是否通过修改就地参数返回其结果。
    
  - 是否是可变。
    
  - 它是否线程安全 （支持从 Excel 2007）。
    
  - 应显示哪些文本粘贴函数向导和记忆式键入编辑器以帮助实现调用的函数。
    
  - 该函数也会列在的类别。
    
这是所有实现使用 C API 函数[xlfRegister](xlfregister-form-1.md)，等价于**注册**XLM 函数。
  
## <a name="calling-xll-functions-directly-from-excel"></a>直接从 Excel 调用 XLL 函数

它们注册后，可以从任何位置可从调用内置函数调用 XLL 工作表和宏工作表函数：
  
- 单个单元格或阵列的工作表上的公式。
    
- 单个单元格或阵列的宏工作表上的公式。
    
- 定义名称的定义。
    
- 一个条件格式对话框中的条件和限制字段。
    
- 从另一个加载项通过 C API 函数[xlUDF](xludf.md)。
    
- 从 Visual Basic for Applications (VBA) 通过**Application.Run**方法。 
    
使用 C API 函数**xlfCaller**您函数中，可以获取对调用单元格或单元格区域的引用。 如果单元格的条件格式表达式中调用该函数，则仍会返回对关联的单元格的单元格的引用，因此您无法假定单元格的公式包含 XLL 函数。 如果您的函数调用从 VBA 用户定义函数 (UDF)， **xlfCaller**再次返回调用 VBA 函数的单元格的地址。 有关详细信息，请参阅[xlfCaller](xlfcaller.md)。
  
> [!NOTE]
> Excel**粘贴函数向导**和**替换**对话框还调用 XLL 函数代码。 您可能需要限制您的代码正常运行的**粘贴函数参数**对话框中，尤其是其中函数可以需要很长时间，以执行情况。 若要检测如果从这些对话框任一调用您函数时，您必须循环访问所有打开的窗口以确定是否前端窗口是下列对话框之一，如果是这样，您项目中实现一些代码哪一个。 
  
## <a name="calling-xll-commands-directly-from-excel"></a>直接从 Excel 调用 XLL 命令

它们注册后，可在所有其他用户定义的宏，可以调用的方法调用 XLL 命令：
  
- 通过与 control 对象相关联嵌入工作表上。
    
- 从运行宏对话框。
    
- 从 VBA 用户定义的宏使用**Application.Run**方法。 
    
- 从自定义的菜单项或工具栏中。
    
- 使用快捷方式键击设置，当注册命令。
    
- 捕获是为指定的事件时运行命令。
    
> [!NOTE]
> 因为它们不出现在列表中的 Excel 对话框中可用的宏，XLL 命令已被隐藏。 但是，可以输入到宏名称字段的手动。 Excel 预计这些对话框，而不是 DLL 导出名称中的注册为名称。 
  
使用 Excel 中注册的所有 XLL 命令都假定 Excel 的以下形式：
  
```cs
short WINAPI xll_cmd_name(void)
{
// Function code...
    return 1;
}

```

除非调用从 XLM 宏工作表，在其中案例的返回值转换为**TRUE**或**FALSE**，则 Excel 会忽略返回值。 如果它失败或已被用户取消，因此应返回 1 如果您的命令执行成功和 0。
  
您可以获得信息有关您的命令的调用方式使用 C API 函数**xlfCaller**。 有关详细信息，请参阅[xlfCaller](xlfcaller.md)。
  
在 Excel 2007 用户界面中启动很大差异从早期版本。 在大多数情况下仍然支持允许添加和删除自定义菜单栏、 菜单、 子菜单、 菜单项、 自定义工具栏和工具栏按钮的 C API 函数。 但是，他们不始终会使所添加的项可用用户熟悉的方式。 您应该仔细检查任何新增的功能仍可访问，或实现的特定于版本的自定义项。 启动 Excel 2007 中的用户界面使用的托管的代码模块，然后可以 XLL 命令紧密耦合的最佳自定义。
  
## <a name="see-also"></a>另请参阅

- [创建 xll （英文）](creating-xlls.md)
- [从函数向导或替换对话框呼叫 XLL 函数](how-to-call-xll-functions-from-the-function-wizard-or-replace-dialog-boxes.md)
- [加载项管理器和 XLL 接口函数](add-in-manager-and-xll-interface-functions.md)
- [Developing Excel XLLs](developing-excel-xlls.md)



