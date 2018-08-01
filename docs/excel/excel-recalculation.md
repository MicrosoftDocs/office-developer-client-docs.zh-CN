---
title: Excel 重新计算
manager: kelbow
ms.date: 03/09/2018
ms.audience: Developer
ms.topic: overview
keywords:
- 强制计算 [excel 2007，] 选择性重新计算 [Excel 2007，] 函数 [Excel 2007，] 可变，计算模式，重新计算的单元格 [Excel 2007]，依赖 [Excel 2007]，指定重新计算 [Excel 2007 工作表计算 [Excel 2007]]，工作簿树重建 [Excel 2007]，单元格区域计算 [Excel 2007]，Excel 重新计算，可变函数 [Excel 2007，] 函数 [Excel 2007]，稳定、 活动工作表计算 [Excel 2007]，dirty 非可变函数 [[Excel 2007]Excel 2007 中]，强制重新计算 [Excel 2007]
localization_priority: Normal
ms.assetid: b4c38442-42e6-4fd2-a1b0-97cfa3300379
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 9964f2c4282158e83891d82ba43fa19f23ab1eb6
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773713"
---
# <a name="excel-recalculation"></a>Excel 重新计算

 **适用于** Excel 2013 | Office 2013 | Visual Studio 
  
例如，用户可以触发多种方式，Microsoft Excel 中的重新计算：
  
- （如果 Excel 是在自动重新计算模式下，在本主题后面所述），请输入新数据。
    
- 明确指示 Excel 重新计算的全部或部分工作簿。
    
- 删除或插入行或列。
    
- 保存工作簿时**保存前的自动重算**设置选项。 
    
- 执行某些自动筛选操作。
    
- 双击 （在自动计算模式下） 的行或列分隔符。
    
- 添加、 编辑或删除已定义的名称。
    
- 重命名工作表。
    
- 更改相对于其他工作表的工作表的位置。
    
- 隐藏或不隐藏的行，但没有为列。
    
> [!NOTE]
> 本主题不区分用户直接按的键或单击鼠标，并且正在由命令或宏完成这些任务。 用户运行该命令，或者从事导致运行，以便仍认为是用户操作的命令。 因此短语"user"还意味着"用户或命令或由用户启动的过程。" 
  
## <a name="dependence-dirty-cells-and-recalculated-cells"></a>相关性和 Dirty 单元格，重新计算的单元格

在 Excel 中的工作表的计算可被视为三阶段过程：
  
1. 相关性树的构造
    
2. 计算链的构造
    
3. 重新计算的单元格
    
相关性树通知有关哪些单元格取决于哪些其他 Excel 或等效代码，哪些单元格的引用单元格的其他人。 此树中，从 Excel 构建计算链。 计算链列出的所有单元格包含公式应计算的顺序。 在重新计算，Excel 将修订此链碰到取决于尚未计算的单元格的公式。 在这种情况下，正在计算的单元格和其从属单元格移动链的下方。 因此，计算时间通常可以改善只是第一个几个计算周期内已打开的工作表中。
  
结构进行更改时到工作簿，例如，当输入一个新的公式时，Excel 重新构造的依赖项树和计算链。 当输入新的数据或新公式时，Excel 将标记取决于重新计算的新数据的所有单元格。 这种方式标记单元格一些已知为*带有脏数据*。 所有直接和间接从属单元格标记为已损坏，以便如果 B1 依赖 A1，并且 C1 取决于 B1，A1 发生更改时，B1 和 C1 标记为已损坏。 
  
如果单元格取决于，直接或间接本身，Excel 检测到循环引用，并将警告用户。 这通常是用户必须修复，错误条件和 Excel 提供了非常有帮助的图形和导航工具，可帮助用户查找循环依赖关系的源。 在某些情况下，您有意可能希望此条件会存在。 例如，您可能想要运行迭代计算其中下一次迭代的起始点是上一次迭代的结果。 Excel 支持通过计算选项对话框的迭代计算的控制权。
  
标记为带有脏数据的单元格之后完成重新计算后接下来，Excel 重新计算为由计算链的顺序每个 dirty 单元格的内容。 在示例中，这意味着 B1 首先，然后 C1 提供更早版本。 此重新计算后立即发生 Excel 完成标记为已损坏的重新计算模式是自动; 如果单元格否则，它发生更高版本。
  
从 Microsoft Excel 2002 开始， **Range**对象在 Microsoft Visual Basic for Applications (VBA) 支持的方法， **Range.Dirty**，其标记为需要计算的单元格。 **Range.Calculate**方法一起使用时 （请参阅下一节），使强制重新计算给定范围中的单元格。 执行期间宏有限的计算设置为手动，以避免计算单元格与宏函数不相关的开销计算模式的位置时，这很有用。 范围的计算方法不可用通过 C API。 
  
在 Excel 2002 和早期版本，Excel 构建每个打开的工作簿中的每个工作表的计算链。 这将导致一些方式工作表之间的链接处理，并需要注意一下，以确保高效的重新计算的复杂性。 具体而言，在 Excel 2000 中，您应最小化跨工作表依赖项和字母顺序中的名称工作表以便取决于其他工作表的表按字母顺序晚它们依赖于工作表。
  
在 Excel 2007 中，已经过改进逻辑要启用多个线程上的重新计算，以便的计算链部分不是相互依赖，而可以同时计算。 您可以配置 Excel 多处理器或多核计算机上使用多个线程单处理器的计算机上或单个线程。 
  
## <a name="asynchronous-user-defined-functions-udfs"></a>异步的用户定义函数 (Udf)

当计算遇到异步 UDF 时，保存当前的公式的状态、 启动 UDF 和继续评估单元格的其余部分。 当计算完成评估 Excel 等待完成如果没有运行仍异步函数的异步函数的单元格。 为每个异步函数的报告结果，Excel 完成公式，，，然后运行新的计算传递，以重新计算的单元格的引用的异步函数中使用单元格。
  
## <a name="volatile-and-non-volatile-functions"></a>可变和非可变函数

Excel 支持将可变函数，即，一个不假定其值为从到下一个矩相同，即使没有其参数 （如果计任何） 已更改的概念。 Excel 重新计算每次重新计算使其包含可变函数，以及所有从属单元格。 因此，太多依赖可变函数可以进行重新计算时间慢。 尽量少用。
  
下面的 Excel 函数是可变：
  
- **立即**
    
- **今天**
    
- **RANDBETWEEN**
    
- **偏移**
    
- **间接**
    
- **信息**（具体取决于其参数） 
    
- **单元格**（具体取决于其参数） 
    
- **SUMIF**（具体取决于其参数） 
    
VBA 和 C API 支持通知 Excel，应为可变处理用户定义函数 (UDF) 的方法。 使用 VBA，UDF 声明为可变，如下所示。
  
```vb
Function MyUDF(MakeMeVolatile As Boolean) As Double
   ' Good practice to call this on the first line.
   Application.Volatile (MakeMeVolatile)
   MyUDF = Now
End Function

```

默认情况下，Excel 假定不可变 VBA Udf。 Excel 仅了解到 UDF 可变时首先调用它。 可变 UDF 可以更改回稳定，如下例所示。
  
使用 C API，您可以为其第一次调用之前的可变注册 XLL 函数。 它还可以打开和关闭的工作表函数的可变状态。
  
默认情况下，Excel 处理 XLL Udf 的范围参数并作为为可变宏表等效的声明。 您可以关闭此默认状态首次调用 UDF 时使用**xlfVolatile**函数。 
  
## <a name="calculation-modes-commands-selective-recalculation-and-data-tables"></a>计算模式、 命令、 选择性重新计算，和模拟运算表

Excel 有三种计算模式：
  
- 自动
    
- 除表的自动
    
- 手动
    
当计算设置为自动时，重新计算发生每个数据输入之后和之后如前一节中提供的示例某些事件。 对于非常大的工作簿，计算的时间可能会很长时间，用户必须限制时发生这种情况，即，在需要时仅重新计算。 若要启用此功能，Excel 支持手动模式。 用户可以选择通过 Excel 菜单系统，或以编程方式使用 VBA、 COM 或 C API 的模式。
  
模拟运算表是工作表中的特殊结构。 首先，用户设置的工作表上的结果计算。 这取决于一个或两个关键可更改输入和其他参数。 用户然后可以为一个或两个关键输入创建一组值的结果的表格。 使用**数据表向导**创建表。 表设置后，Excel 输入一个地插入计算，并将结果值复制到表。 可以使用一个或两个输入，模拟运算表可以是一个-或二维。 
  
重新计算的模拟运算表处理略有不同：
  
- 重新计算为常规工作簿重新计算，以便大表可能需要更长时间重新计算工作簿的 rest 比异步处理。
    
- 容许循环引用。 如果用于获取结果计算依赖的模拟运算表中的一个或多个值，Excel 不返回错误的循环依赖关系。 
    
Excel 给定 Excel 处理重新计算的模拟运算表和取决于复杂或较长的计算的大型表花费很长时间才能计算事实的不同方式，允许您禁用自动计算的模拟运算表。 若要执行此操作，设置为自动 （数据表除外） 的计算模式。 在此模式中计算后，用户将通过按 F9 或某个等效的编程操作重新计算模拟运算表。
  
Excel 公开的方法，您可以通过其更改的重新计算模式和控制重新计算。 这些方法进行了改进从版本到版本，以允许更精细的控制。 C API 的功能在这方面反映的 Excel 版本 5、 中可用，并因此并不允许您已在较新版本中使用 VBA 的相同控件。 
  
最常用于手动计算模式 Excel 时，这些方法允许选择性计算工作簿、 工作表和区域，完整的重新计算所有打开的工作簿，并甚至完全重建的依赖项树和计算链。
  
### <a name="range-calculation"></a>区域计算

键击： 无
  
VBA: （在 Excel 2000 中，更改 Excel 2007 中引入） **Range.Calculate**和**Range.CalculateRowMajorOrder** （引入 Excel 2007 中） 
  
C API： 不支持
  
- **手动模式**
    
    将来重新计算刚刚而不考虑它们是否给定范围中的单元格 dirty 或不。 在 Excel 2007 中; 更改**Range.Calculate**方法的行为但是，仍然**Range.CalculateRowMajorOrder**方法支持的旧的行为。 
    
- **自动或自动除表模式**
    
    重新计算工作簿，但不会强制重新计算的范围或范围中的任何单元格。
    
### <a name="active-worksheet-calculation"></a>活动工作表计算

键击： SHIFT + F9
  
VBA: **ActiveSheet.Calculate**
  
C API: **xlcCalculateDocument**
  
- **所有模式**
    
    重新计算标记为活动工作表中计算的单元格。
    
### <a name="specified-worksheet-calculation"></a>指定工作表计算

键击： 无
  
VBA:**工作表 (****引用)。计算**
  
C API： 不支持
  
- **所有模式**
    
    重新计算的 dirty 单元格并指定工作表中的其从属单元格。 引用是为一个字符串或相关的工作簿中的索引号的工作表的名称。
    
    Excel 2000 和更高版本公开一个**布尔值**的工作表属性， **EnableCalculation**属性。 设置为**True**从**False**弄脏指定工作表中的所有单元格。 在自动模式下，这还将触发整个工作簿重新计算。 
    
    在手动模式下，下面的代码使活动工作表重新计算。
    
  ```vb
  With ActiveSheet
    .EnableCalculation = False
    .EnableCalculation = True
    .Calculate
  End With
  
  ```

### <a name="workbook-tree-rebuild-and-forced-recalculation"></a>工作簿树重新生成并强制重新计算

键击： CTRL + ALT + SHIFT + F9 （引入 Excel 2002 中）
  
VBA:**工作簿 (****引用)。ForceFullCalculation** （引入 Excel 2007 中） 
  
C API： 不支持
  
- **所有模式**
    
    使 Excel 重建相关性树和给定的工作簿的计算链并强制重新计算包含公式的所有单元格。
    
### <a name="all-open-workbooks"></a>所有打开的工作簿

键击： F9
  
VBA: **Application.Calculate**
  
C API: **xlcCalculateNow**
  
- **所有模式**
    
    重新计算的所有单元格的 Excel 已标记为已损坏，即，从属单元格的可变或更改的数据，并以编程方式标记为已损坏的单元格。 如果计算模式是自动除表，这会计算需要更新这些表还所有可变函数和其从属单元格。
    
### <a name="all-open-workbooks-tree-rebuild-and-forced-calculation"></a>所有打开的工作簿树重新生成并强制计算

键击： CTRL + ALT + F9
  
VBA: **Application.CalculateFull**
  
C API： 不支持
  
- **所有模式**
    
    重新计算所有打开的工作簿中所有单元格。 如果计算模式是自动除表，它会强制重新计算的表格。
    
## <a name="see-also"></a>另请参阅



[Excel 中的多线程重新计算](multithreaded-recalculation-in-excel.md)
  
[Excel 使用的数据类型](data-types-used-by-excel.md)
  
[Excel 中的内存管理](memory-management-in-excel.md)
  
[Excel Programming Concepts](excel-programming-concepts.md)

