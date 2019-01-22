---
title: Excel 重新计算
manager: kelbow
ms.date: 08/22/2018
ms.audience: Developer
ms.topic: overview
keywords:
- 强制计算 [excel 2007],选择性重新计算 [Excel 2007],函数 [Excel 2007],可变,计算模式,重新计算的单元格 [Excel 2007],相关性 [Excel 2007],指定工作表计算 [Excel 2007],重新计算 [Excel 2007],工作簿树重建 [Excel 2007],范围计算 [Excel 2007],Excel 重新计算,可变函数 [Excel 2007],函数 [Excel 2007],非可变,活动工作表计算 [Excel 2007],脏单元格 [Excel 2007],非可变函数 [Excel 2007],强制重新计算 [Excel 2007]
ms.assetid: b4c38442-42e6-4fd2-a1b0-97cfa3300379
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
localization_priority: Priority
ms.openlocfilehash: 07deec5ad104c59074567725d6abf9b66711e351
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28703347"
---
# <a name="excel-recalculation"></a>Excel 重新计算

**适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
用户可以通过以下几种方法在 Microsoft Excel 中触发重新计算，例如：
  
- 输入新数据（如果 Excel 处于自动重新计算模式，本主题稍后将对此进行介绍）。
    
- 显式指示 Excel 重新计算所有或一部分工作簿。
    
- 删除或插入行或列。
    
- 设置“保存前重新计算”**** 选项时保存工作簿。 
    
- 执行某些自动筛选操作。
    
- 双击行分隔符或列分隔符（在自动计算模式下）。
    
- 添加、编辑或删除已定义的名称。
    
- 重命名工作表。
    
- 更改某个工作表相对于其他工作表的位置。
    
- 隐藏或取消隐藏行，而非列。
    
> [!NOTE]
> 本主题不区分用户直接按下按键或单击鼠标，以及通过命令或宏完成的任务。 用户运行命令或执行某个操作使命令运行，以便仍将其视为用户操作。 因此，短语“用户”也意味着“用户，或由用户启动的命令或进程”。 
  
## <a name="dependence-dirty-cells-and-recalculated-cells"></a>相关性、脏单元格和重新计算的单元格

Excel 中工作表的计算可视为包含三个阶段的过程：
  
1. 构造依赖关系树
    
2. 构造计算链
    
3. 重新计算单元格
    
依赖关系树通知 Excel，哪些单元格依赖于哪些其他单元格，或者说，哪些单元格是其他单元格的引用单元格。 Excel 从此树中构造计算链。 计算链按计算的顺序列出包含公式的所有单元格。 在重新计算过程中，如果此链遇到依赖于尚未计算的单元格的公式，Excel 会对其进行修改。 在这种情况下，正在计算的单元格及其依赖项会移动到该链下。 因此，通常会在前几个计算周期中刚刚打开的工作表中增加计算次数。
  
对工作簿进行结构更改后（例如，输入新公式后），Excel 会重新构造依赖关系树和计算链。 输入新数据或新公式后，Excel 会将依赖于该新数据的所有单元格标记为需要重新计算。 通过这种方式标记的单元格称为*脏*单元格。 所有直接依赖项和间接依赖项都标记为脏依赖项，因此，如果 B1 依赖于 A1，且 C1 依赖于 B1，那么如果更改 A1，B1 和 C1 都将标记为脏单元格。 
  
如果某个单元格直接或间接依赖于其自身，Excel 将检测到循环引用并提醒用户。 这通常是用户必须解决的问题，并且 Excel 提供了非常有用的图形和导航工具来帮助用户查找循环依赖关系的来源。 在某些情况下，用户可能会有意希望存在此情况。 例如，用户可能想要运行迭代计算，其中下一次迭代的起始点是上一次迭代的结果。 Excel 支持通过计算选项对话框控制迭代计算。
  
将单元格标记为脏单元格后，如果再进行重新计算，Excel 会按计算链指定的顺序重新计算每个脏单元格的内容。 在先前提供的示例中，这意味着 B1 是第一个，其次是 C1。 如果重新计算模式为自动，则在 Excel 将单元格标记为脏单元格后，将立即进行此重新计算；否则将稍后执行。
  
从 Microsoft Excel 2002 开始，Microsoft Visual Basic for Applications (VBA) 中的 **Range** 对象支持 **Range.Dirty** 方法，该方法可将单元格标记为“需要计算”。 如果将该方法与 **Range.Calculate** 方法结合使用（请参阅下一部分），会强制重新计算给定区域内的单元格。 在宏期间执行有限计算时（其中计算模式设置为手动），此做法非常有用，可以避免因计算与宏函数无关的单元格而产生开销。 C API 不提供区域计算方法。 
  
在 Excel 2002 和更早版本中，Excel 为每个打开的工作簿中的每个工作表构建一个计算链。 这导致处理工作表之间的链接的方式有些复杂，并且需要小心谨慎以确保有效的重新计算。 特别是，在 Excel 2000 中，应尽量减少跨工作表的依赖关系并按字母顺序命名工作表，以便依赖于其他工作表的工作表按字母顺序排在它们所依赖的工作表之后。
  
Excel 2007 中的逻辑得以改进，允许在多个线程上重新计算，这样计算链的各个部分就不再相互依赖，并且可以同时计算。 可以将 Excel 配置为在单个处理器计算机上使用多个线程，或者在多处理器或多核计算机上使用单个线程。 
  
## <a name="asynchronous-user-defined-functions-udfs"></a>用户定义的异步函数 (UDF)

当计算遇到异步 UDF 时，它会保存当前公式的状态，启动 UDF 并继续计算其余单元格。 当计算完成单元格的计算时，Excel 将等待异步函数完成（如果仍然有异步函数在运行）。 每个异步函数报告结果时，Excel 将完成公式，然后运行新的计算通道，以便重新计算使用引用异步函数的单元格的单元格。
  
## <a name="volatile-and-non-volatile-functions"></a>可变函数和非可变函数

Excel 支持可变函数的概念，也就是说，即使它的参数（如果有的话）没有任何变化，也不能假定该函数的值在不同时刻都是相同的。 Excel 在每次重新计算时，都会重新计算包含可变函数和所有依赖项的单元格。 因此，过于依赖可变函数会使重新计算时间变慢。 请谨慎使用。
  
以下是可变的 Excel 函数：
  
- **NOW**
    
- **TODAY**
    
- **RANDBETWEEN**
    
- **OFFSET**
    
- **INDIRECT**
    
- **INFO**（具体取决于其参数） 
    
- **CELL**（具体取决于其参数） 
    
- **SUMIF**（具体取决于其参数） 
    
VBA 和 C API 都支持通知 Excel 用户定义函数 (UDF) 应作为可变函数处理的方法。 通过使用 VBA，UDF 被声明为可变，如下所示。
  
```vb
Function MyUDF(MakeMeVolatile As Boolean) As Double
   ' Good practice to call this on the first line.
   Application.Volatile (MakeMeVolatile)
   MyUDF = Now
End Function

```

默认情况下，Excel 假定 VBA UDF 不可变。 Excel 只知道 UDF 在第一次调用时是可变的。 可变的 UDF 可以像本例中那样更改回非可变 UDF。
  
使用 C API，可以在第一次调用 XLL 函数之前将其注册为可变。 用户还可以使用它启用和禁用工作表函数的可变状态。
  
默认情况下，Excel 处理可接受区域参数、并且被声明为作为可变函数的宏表等效项的 XLL UDF。 在首次调用 UDF 时，可以使用 **xlfVolatile** 函数禁用此默认状态。 
  
## <a name="calculation-modes-commands-selective-recalculation-and-data-tables"></a>计算模式、命令、选择性重新计算和数据表

Excel 有三种计算模式：
  
- 自动
    
- 自动（表除外）
    
- 手动
    
如果计算设置为自动，将在每次数据输入之后以及在某些事件（如前一节中给出的示例）之后重新计算。 对于非常大的工作簿，重新计算时间可能太长，以至于用户必须限制何时发生这种情况，即只在需要时重新计算。 为此，Excel 支持手动模式。 用户可以通过 Excel 菜单系统选择模式，也可以使用 VBA、COM 或 C API 以编程方式选择模式。
  
数据表是工作表中的特殊结构。 首先，用户在工作表上设置结果计算。 这取决于一两个关键的可变输入和其他参数。 然后，用户可以为一两个关键输入的一组值创建结果表。 该表是使用“数据表向导”**** 创建的。 表设置完成后，Excel 将输入逐个插入到计算中，并将结果值复制到表中。 由于可以使用一个或两个输入，因此，数据表可以是一维或二维的。 
  
对重新计算数据表的处理略有不同：
  
- 相比常规工作簿重新计算，此类重新计算是以异步方式进行的，因此大型表重新计算可能要比工作簿的其余部分花费更长时间。
    
- 允许循环引用。 如果用于获取结果的计算取决于数据表中的一个或多个值，Excel 将不会返回循环依赖项错误。 

- 数据表不使用多线程计算。
    
鉴于 Excel 处理数据表重新计算的方式不同，以及依赖于复杂或冗长计算的大型表可能需要很长时间才能计算，Excel 允许禁用数据表的自动计算。 为此，将计算模式设置为“自动(数据表除外)”。 当计算处于此模式时，用户通过按 F9 或一些等效编程操作可以重新计算数据表。
  
Excel 公开了一些方法，用户可以通过这些方法更改重新计算模式并控制重新计算。 这些方法已在各版本中得以改进，从而实现更精细的控制。 C API 在此方面的功能反映了 Excel 版本 5 中可用的功能，因此不提供与在更新版本中使用 VBA 的相同控件。 
  
当 Excel 处于手动计算模式时，这些方法使用最为频繁，它们允许对工作簿、工作表以及区域进行选择性计算，完成对所有打开的工作簿的重新计算，甚至完成依赖关系树和计算链的重建。
  
### <a name="range-calculation"></a>区域计算

击键：无
  
VBA：**Range.Calculate**（在 Excel 2000 中引入，在 Excel 2007 中更改）和 **Range.CalculateRowMajorOrder**（在 Excel 2007 中引入） 
  
C API：不支持
  
- **手动模式**
    
    只重新计算给定区域内的单元格（无论它们是否为脏单元格）。 **Range.Calculate** 方法的行为在 Excel 2007 中进行了更改；但 **Range.CalculateRowMajorOrder** 方法仍支持旧行为。 
    
- **自动模式或自动（表除外）模式**
    
    重新计算工作簿，但不强制重新计算区域或区域中的任何单元格。
    
### <a name="active-worksheet-calculation"></a>活动工作表计算

击键：SHIFT+F9
  
VBA：**ActiveSheet.Calculate**
  
C API：**xlcCalculateDocument**
  
- **所有模式**
    
    仅重新计算活动工作表中标记为计算的单元格。
    
### <a name="specified-worksheet-calculation"></a>指定工作表计算

击键：无
  
VBA：**Worksheets(** reference **).Calculate**
  
C API：不支持
  
- **所有模式**
    
    仅在指定工作表中重新计算脏单元格及其依赖项。 引用是作为字符串的工作表的名称或相关工作簿中的索引号。
    
    Excel 2000 及更高版本版本公开了一个**布尔**工作表属性，即 **EnableCalculation** 属性。 将此属性从 **False** 设置为 **True** 将使指定工作表的全部单元格变为脏单元格。 在自动模式下，这还会触发整个工作簿的重新计算。 
    
    在手动模式下，以下代码只会导致重新计算活动表。
    
  ```vb
  With ActiveSheet
    .EnableCalculation = False
    .EnableCalculation = True
    .Calculate
  End With
  
  ```

### <a name="workbook-tree-rebuild-and-forced-recalculation"></a>工作簿树重建和强制重新计算

击键：CTRL+ALT+SHIFT+F9（在 Excel 2002 中引入）
  
VBA：**Workbooks(** reference **).ForceFullCalculation**（在 Excel 2007 中引入） 
  
C API：不支持
  
- **所有模式**
    
    使 Excel 重建给定工作簿的依赖关系树和计算链，并强制重新计算包含公式的所有单元格。
    
### <a name="all-open-workbooks"></a>所有打开的工作簿

击键：F9
  
VBA：**Application.Calculate**
  
C API：**xlcCalculateNow**
  
- **所有模式**
    
    重新计算 Excel 已标记为脏的所有单元格（即可变或已更改的数据的从属单元格），以及以编程方式标记为脏的单元格。 如果计算模式是“自动(表除外)”，则计算那些需要更新的表以及所有可变函数及其依赖项。
    
### <a name="all-open-workbooks-tree-rebuild-and-forced-calculation"></a>所有打开的工作簿树重建和强制计算

击键：CTRL+ALT+F9
  
VBA：**Application.CalculateFull**
  
C API：不支持
  
- **所有模式**
    
    重新计算所有已打开工作簿中的全部单元格。 如果计算模式是“自动(表除外)”，则强制重新计算表。
    
## <a name="see-also"></a>另请参阅



[Excel 中的多线程重新计算](multithreaded-recalculation-in-excel.md)
  
[Excel 使用的数据类型](data-types-used-by-excel.md)
  
[Excel 中的内存管理](memory-management-in-excel.md)
  
[Excel 编程概念](excel-programming-concepts.md)

