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
# <a name="excel-recalculation"></a><span data-ttu-id="2d9cd-104">Excel 重新计算</span><span class="sxs-lookup"><span data-stu-id="2d9cd-104">Excel Recalculation</span></span>

 <span data-ttu-id="2d9cd-105">**适用于** Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="2d9cd-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="2d9cd-106">例如，用户可以触发多种方式，Microsoft Excel 中的重新计算：</span><span class="sxs-lookup"><span data-stu-id="2d9cd-106">The user can trigger recalculation in Microsoft Excel in several ways, for example:</span></span>
  
- <span data-ttu-id="2d9cd-107">（如果 Excel 是在自动重新计算模式下，在本主题后面所述），请输入新数据。</span><span class="sxs-lookup"><span data-stu-id="2d9cd-107">Entering new data (if Excel is in Automatic recalculation mode, described later in this topic).</span></span>
    
- <span data-ttu-id="2d9cd-108">明确指示 Excel 重新计算的全部或部分工作簿。</span><span class="sxs-lookup"><span data-stu-id="2d9cd-108">Explicitly instructing Excel to recalculate all or part of a workbook.</span></span>
    
- <span data-ttu-id="2d9cd-109">删除或插入行或列。</span><span class="sxs-lookup"><span data-stu-id="2d9cd-109">Deleting or inserting a row or column.</span></span>
    
- <span data-ttu-id="2d9cd-110">保存工作簿时**保存前的自动重算**设置选项。</span><span class="sxs-lookup"><span data-stu-id="2d9cd-110">Saving a workbook while the **Recalculate before save** option is set.</span></span> 
    
- <span data-ttu-id="2d9cd-111">执行某些自动筛选操作。</span><span class="sxs-lookup"><span data-stu-id="2d9cd-111">Performing certain Autofilter actions.</span></span>
    
- <span data-ttu-id="2d9cd-112">双击 （在自动计算模式下） 的行或列分隔符。</span><span class="sxs-lookup"><span data-stu-id="2d9cd-112">Double-clicking a row or column divider (in Automatic calculation mode).</span></span>
    
- <span data-ttu-id="2d9cd-113">添加、 编辑或删除已定义的名称。</span><span class="sxs-lookup"><span data-stu-id="2d9cd-113">Adding, editing, or deleting a defined name.</span></span>
    
- <span data-ttu-id="2d9cd-114">重命名工作表。</span><span class="sxs-lookup"><span data-stu-id="2d9cd-114">Renaming a worksheet.</span></span>
    
- <span data-ttu-id="2d9cd-115">更改相对于其他工作表的工作表的位置。</span><span class="sxs-lookup"><span data-stu-id="2d9cd-115">Changing the position of a worksheet in relation to other worksheets.</span></span>
    
- <span data-ttu-id="2d9cd-116">隐藏或不隐藏的行，但没有为列。</span><span class="sxs-lookup"><span data-stu-id="2d9cd-116">Hiding or unhiding rows, but not columns.</span></span>
    
> [!NOTE]
> <span data-ttu-id="2d9cd-117">本主题不区分用户直接按的键或单击鼠标，并且正在由命令或宏完成这些任务。</span><span class="sxs-lookup"><span data-stu-id="2d9cd-117">This topic does not distinguish between the user directly pressing a key or clicking the mouse, and those tasks being done by a command or macro.</span></span> <span data-ttu-id="2d9cd-118">用户运行该命令，或者从事导致运行，以便仍认为是用户操作的命令。</span><span class="sxs-lookup"><span data-stu-id="2d9cd-118">The user runs the command, or does something to cause the command to run so that it is still considered a user action.</span></span> <span data-ttu-id="2d9cd-119">因此短语"user"还意味着"用户或命令或由用户启动的过程。"</span><span class="sxs-lookup"><span data-stu-id="2d9cd-119">Therefore the phrase "the user" also means "the user, or a command or process started by the user."</span></span> 
  
## <a name="dependence-dirty-cells-and-recalculated-cells"></a><span data-ttu-id="2d9cd-120">相关性和 Dirty 单元格，重新计算的单元格</span><span class="sxs-lookup"><span data-stu-id="2d9cd-120">Dependence, Dirty Cells, and Recalculated Cells</span></span>

<span data-ttu-id="2d9cd-121">在 Excel 中的工作表的计算可被视为三阶段过程：</span><span class="sxs-lookup"><span data-stu-id="2d9cd-121">The calculation of worksheets in Excel can be viewed as a three-stage process:</span></span>
  
1. <span data-ttu-id="2d9cd-122">相关性树的构造</span><span class="sxs-lookup"><span data-stu-id="2d9cd-122">Construction of a dependency tree</span></span>
    
2. <span data-ttu-id="2d9cd-123">计算链的构造</span><span class="sxs-lookup"><span data-stu-id="2d9cd-123">Construction of a calculation chain</span></span>
    
3. <span data-ttu-id="2d9cd-124">重新计算的单元格</span><span class="sxs-lookup"><span data-stu-id="2d9cd-124">Recalculation of cells</span></span>
    
<span data-ttu-id="2d9cd-125">相关性树通知有关哪些单元格取决于哪些其他 Excel 或等效代码，哪些单元格的引用单元格的其他人。</span><span class="sxs-lookup"><span data-stu-id="2d9cd-125">The dependency tree informs Excel about which cells depend on which others, or equivalently, which cells are precedents for which others.</span></span> <span data-ttu-id="2d9cd-126">此树中，从 Excel 构建计算链。</span><span class="sxs-lookup"><span data-stu-id="2d9cd-126">From this tree, Excel constructs a calculation chain.</span></span> <span data-ttu-id="2d9cd-127">计算链列出的所有单元格包含公式应计算的顺序。</span><span class="sxs-lookup"><span data-stu-id="2d9cd-127">The calculation chain lists all the cells that contain formulas in the order in which they should be calculated.</span></span> <span data-ttu-id="2d9cd-128">在重新计算，Excel 将修订此链碰到取决于尚未计算的单元格的公式。</span><span class="sxs-lookup"><span data-stu-id="2d9cd-128">During recalculation, Excel revises this chain if it comes across a formula that depends on a cell that has not yet been calculated.</span></span> <span data-ttu-id="2d9cd-129">在这种情况下，正在计算的单元格和其从属单元格移动链的下方。</span><span class="sxs-lookup"><span data-stu-id="2d9cd-129">In this case, the cell that is being calculated and its dependents are moved down the chain.</span></span> <span data-ttu-id="2d9cd-130">因此，计算时间通常可以改善只是第一个几个计算周期内已打开的工作表中。</span><span class="sxs-lookup"><span data-stu-id="2d9cd-130">For this reason, calculation times can often improve in a worksheet that has just been opened in the first few calculation cycles.</span></span>
  
<span data-ttu-id="2d9cd-131">结构进行更改时到工作簿，例如，当输入一个新的公式时，Excel 重新构造的依赖项树和计算链。</span><span class="sxs-lookup"><span data-stu-id="2d9cd-131">When a structural change is made to a workbook, for example, when a new formula is entered, Excel reconstructs the dependency tree and calculation chain.</span></span> <span data-ttu-id="2d9cd-132">当输入新的数据或新公式时，Excel 将标记取决于重新计算的新数据的所有单元格。</span><span class="sxs-lookup"><span data-stu-id="2d9cd-132">When new data or new formulas are entered, Excel marks all the cells that depend on that new data as needing recalculation.</span></span> <span data-ttu-id="2d9cd-133">这种方式标记单元格一些已知为*带有脏数据*。</span><span class="sxs-lookup"><span data-stu-id="2d9cd-133">Cells that are marked in this way are known as  *dirty*  .</span></span> <span data-ttu-id="2d9cd-134">所有直接和间接从属单元格标记为已损坏，以便如果 B1 依赖 A1，并且 C1 取决于 B1，A1 发生更改时，B1 和 C1 标记为已损坏。</span><span class="sxs-lookup"><span data-stu-id="2d9cd-134">All direct and indirect dependents are marked as dirty so that if B1 depends on A1, and C1 depends on B1, when A1 is changed, both B1 and C1 are marked as dirty.</span></span> 
  
<span data-ttu-id="2d9cd-135">如果单元格取决于，直接或间接本身，Excel 检测到循环引用，并将警告用户。</span><span class="sxs-lookup"><span data-stu-id="2d9cd-135">If a cell depends, directly or indirectly, on itself, Excel detects the circular reference and warns the user.</span></span> <span data-ttu-id="2d9cd-136">这通常是用户必须修复，错误条件和 Excel 提供了非常有帮助的图形和导航工具，可帮助用户查找循环依赖关系的源。</span><span class="sxs-lookup"><span data-stu-id="2d9cd-136">This is usually an error condition that the user must fix, and Excel provides very helpful graphical and navigational tools to help the user to find the source of the circular dependency.</span></span> <span data-ttu-id="2d9cd-137">在某些情况下，您有意可能希望此条件会存在。</span><span class="sxs-lookup"><span data-stu-id="2d9cd-137">In some cases, you might deliberately want this condition to exist.</span></span> <span data-ttu-id="2d9cd-138">例如，您可能想要运行迭代计算其中下一次迭代的起始点是上一次迭代的结果。</span><span class="sxs-lookup"><span data-stu-id="2d9cd-138">For example, you might want to run an iterative calculation where the starting point for the next iteration is the result of the previous iteration.</span></span> <span data-ttu-id="2d9cd-139">Excel 支持通过计算选项对话框的迭代计算的控制权。</span><span class="sxs-lookup"><span data-stu-id="2d9cd-139">Excel supports control of iterative calculations through the calculation options dialog box.</span></span>
  
<span data-ttu-id="2d9cd-140">标记为带有脏数据的单元格之后完成重新计算后接下来，Excel 重新计算为由计算链的顺序每个 dirty 单元格的内容。</span><span class="sxs-lookup"><span data-stu-id="2d9cd-140">After marking cells as dirty, when a recalculation is next done, Excel reevaluates the contents of each dirty cell in the order dictated by the calculation chain.</span></span> <span data-ttu-id="2d9cd-141">在示例中，这意味着 B1 首先，然后 C1 提供更早版本。</span><span class="sxs-lookup"><span data-stu-id="2d9cd-141">In the example given earlier, this means B1 is first, and then C1.</span></span> <span data-ttu-id="2d9cd-142">此重新计算后立即发生 Excel 完成标记为已损坏的重新计算模式是自动; 如果单元格否则，它发生更高版本。</span><span class="sxs-lookup"><span data-stu-id="2d9cd-142">This recalculation occurs immediately after Excel finishes marking cells as dirty if the recalculation mode is automatic; otherwise, it occurs later.</span></span>
  
<span data-ttu-id="2d9cd-143">从 Microsoft Excel 2002 开始， **Range**对象在 Microsoft Visual Basic for Applications (VBA) 支持的方法， **Range.Dirty**，其标记为需要计算的单元格。</span><span class="sxs-lookup"><span data-stu-id="2d9cd-143">Starting in Microsoft Excel 2002, the **Range** object in Microsoft Visual Basic for Applications (VBA) supports a method, **Range.Dirty**, which marks cells as needing calculation.</span></span> <span data-ttu-id="2d9cd-144">**Range.Calculate**方法一起使用时 （请参阅下一节），使强制重新计算给定范围中的单元格。</span><span class="sxs-lookup"><span data-stu-id="2d9cd-144">When it is used together with the **Range.Calculate** method (see next section), it enables forced recalculation of cells in a given range.</span></span> <span data-ttu-id="2d9cd-145">执行期间宏有限的计算设置为手动，以避免计算单元格与宏函数不相关的开销计算模式的位置时，这很有用。</span><span class="sxs-lookup"><span data-stu-id="2d9cd-145">This is useful when you are performing a limited calculation during a macro, where the calculation mode is set to manual, to avoid the overhead of calculating cells unrelated to the macro function.</span></span> <span data-ttu-id="2d9cd-146">范围的计算方法不可用通过 C API。</span><span class="sxs-lookup"><span data-stu-id="2d9cd-146">Range calculation methods are not available through the C API.</span></span> 
  
<span data-ttu-id="2d9cd-147">在 Excel 2002 和早期版本，Excel 构建每个打开的工作簿中的每个工作表的计算链。</span><span class="sxs-lookup"><span data-stu-id="2d9cd-147">In Excel 2002 and earlier versions, Excel built a calculation chain for each worksheet in each open workbook.</span></span> <span data-ttu-id="2d9cd-148">这将导致一些方式工作表之间的链接处理，并需要注意一下，以确保高效的重新计算的复杂性。</span><span class="sxs-lookup"><span data-stu-id="2d9cd-148">This resulted in some complexity in the way links between worksheets were handled, and required some care to ensure efficient recalculation.</span></span> <span data-ttu-id="2d9cd-149">具体而言，在 Excel 2000 中，您应最小化跨工作表依赖项和字母顺序中的名称工作表以便取决于其他工作表的表按字母顺序晚它们依赖于工作表。</span><span class="sxs-lookup"><span data-stu-id="2d9cd-149">In particular, in Excel 2000, you should minimize cross-worksheet dependencies and name worksheets in alphabetical order so that sheets that depend on other sheets come alphabetically after the sheets they depend on.</span></span>
  
<span data-ttu-id="2d9cd-150">在 Excel 2007 中，已经过改进逻辑要启用多个线程上的重新计算，以便的计算链部分不是相互依赖，而可以同时计算。</span><span class="sxs-lookup"><span data-stu-id="2d9cd-150">In Excel 2007, the logic was improved to enable recalculation on multiple threads so that sections of the calculation chain are not interdependent and can be calculated at the same time.</span></span> <span data-ttu-id="2d9cd-151">您可以配置 Excel 多处理器或多核计算机上使用多个线程单处理器的计算机上或单个线程。</span><span class="sxs-lookup"><span data-stu-id="2d9cd-151">You can configure Excel to use multiple threads on a single processor computer, or a single thread on a multi-processor or multi-core computer.</span></span> 
  
## <a name="asynchronous-user-defined-functions-udfs"></a><span data-ttu-id="2d9cd-152">异步的用户定义函数 (Udf)</span><span class="sxs-lookup"><span data-stu-id="2d9cd-152">Asynchronous User Defined Functions (UDFs)</span></span>

<span data-ttu-id="2d9cd-153">当计算遇到异步 UDF 时，保存当前的公式的状态、 启动 UDF 和继续评估单元格的其余部分。</span><span class="sxs-lookup"><span data-stu-id="2d9cd-153">When a calculation encounters an asynchronous UDF, it saves the state of the current formula, starts the UDF and continues evaluating the rest of the cells.</span></span> <span data-ttu-id="2d9cd-154">当计算完成评估 Excel 等待完成如果没有运行仍异步函数的异步函数的单元格。</span><span class="sxs-lookup"><span data-stu-id="2d9cd-154">When the calculation finishes evaluating the cells Excel waits for the asynchronous functions to complete if there are still asynchronous functions running.</span></span> <span data-ttu-id="2d9cd-155">为每个异步函数的报告结果，Excel 完成公式，，，然后运行新的计算传递，以重新计算的单元格的引用的异步函数中使用单元格。</span><span class="sxs-lookup"><span data-stu-id="2d9cd-155">As each asynchronous function reports results, Excel finishes the formula, and then runs a new calculation pass to re-compute cells that use the cell with the reference to the asynchronous function.</span></span>
  
## <a name="volatile-and-non-volatile-functions"></a><span data-ttu-id="2d9cd-156">可变和非可变函数</span><span class="sxs-lookup"><span data-stu-id="2d9cd-156">Volatile and Non-Volatile Functions</span></span>

<span data-ttu-id="2d9cd-157">Excel 支持将可变函数，即，一个不假定其值为从到下一个矩相同，即使没有其参数 （如果计任何） 已更改的概念。</span><span class="sxs-lookup"><span data-stu-id="2d9cd-157">Excel supports the concept of a volatile function, that is, one whose value cannot be assumed to be the same from one moment to the next even if none of its arguments (if it takes any) has changed.</span></span> <span data-ttu-id="2d9cd-158">Excel 重新计算每次重新计算使其包含可变函数，以及所有从属单元格。</span><span class="sxs-lookup"><span data-stu-id="2d9cd-158">Excel reevaluates cells that contain volatile functions, together with all dependents, every time that it recalculates.</span></span> <span data-ttu-id="2d9cd-159">因此，太多依赖可变函数可以进行重新计算时间慢。</span><span class="sxs-lookup"><span data-stu-id="2d9cd-159">For this reason, too much reliance on volatile functions can make recalculation times slow.</span></span> <span data-ttu-id="2d9cd-160">尽量少用。</span><span class="sxs-lookup"><span data-stu-id="2d9cd-160">Use them sparingly.</span></span>
  
<span data-ttu-id="2d9cd-161">下面的 Excel 函数是可变：</span><span class="sxs-lookup"><span data-stu-id="2d9cd-161">The following Excel functions are volatile:</span></span>
  
- <span data-ttu-id="2d9cd-162">**立即**</span><span class="sxs-lookup"><span data-stu-id="2d9cd-162">**NOW**</span></span>
    
- <span data-ttu-id="2d9cd-163">**今天**</span><span class="sxs-lookup"><span data-stu-id="2d9cd-163">**TODAY**</span></span>
    
- <span data-ttu-id="2d9cd-164">**RANDBETWEEN**</span><span class="sxs-lookup"><span data-stu-id="2d9cd-164">**RANDBETWEEN**</span></span>
    
- <span data-ttu-id="2d9cd-165">**偏移**</span><span class="sxs-lookup"><span data-stu-id="2d9cd-165">**OFFSET**</span></span>
    
- <span data-ttu-id="2d9cd-166">**间接**</span><span class="sxs-lookup"><span data-stu-id="2d9cd-166">**INDIRECT**</span></span>
    
- <span data-ttu-id="2d9cd-167">**信息**（具体取决于其参数）</span><span class="sxs-lookup"><span data-stu-id="2d9cd-167">**INFO** (depending on its arguments)</span></span> 
    
- <span data-ttu-id="2d9cd-168">**单元格**（具体取决于其参数）</span><span class="sxs-lookup"><span data-stu-id="2d9cd-168">**CELL** (depending on its arguments)</span></span> 
    
- <span data-ttu-id="2d9cd-169">**SUMIF**（具体取决于其参数）</span><span class="sxs-lookup"><span data-stu-id="2d9cd-169">**SUMIF** (depending on its arguments)</span></span> 
    
<span data-ttu-id="2d9cd-170">VBA 和 C API 支持通知 Excel，应为可变处理用户定义函数 (UDF) 的方法。</span><span class="sxs-lookup"><span data-stu-id="2d9cd-170">Both the VBA and C API support ways to inform Excel that a user-defined function (UDF) should be handled as volatile.</span></span> <span data-ttu-id="2d9cd-171">使用 VBA，UDF 声明为可变，如下所示。</span><span class="sxs-lookup"><span data-stu-id="2d9cd-171">By using VBA, the UDF is declared as volatile as follows.</span></span>
  
```vb
Function MyUDF(MakeMeVolatile As Boolean) As Double
   ' Good practice to call this on the first line.
   Application.Volatile (MakeMeVolatile)
   MyUDF = Now
End Function

```

<span data-ttu-id="2d9cd-172">默认情况下，Excel 假定不可变 VBA Udf。</span><span class="sxs-lookup"><span data-stu-id="2d9cd-172">By default, Excel assumes that VBA UDFs are not volatile.</span></span> <span data-ttu-id="2d9cd-173">Excel 仅了解到 UDF 可变时首先调用它。</span><span class="sxs-lookup"><span data-stu-id="2d9cd-173">Excel only learns that a UDF is volatile when it first calls it.</span></span> <span data-ttu-id="2d9cd-174">可变 UDF 可以更改回稳定，如下例所示。</span><span class="sxs-lookup"><span data-stu-id="2d9cd-174">A volatile UDF can be changed back to non-volatile as in this example.</span></span>
  
<span data-ttu-id="2d9cd-175">使用 C API，您可以为其第一次调用之前的可变注册 XLL 函数。</span><span class="sxs-lookup"><span data-stu-id="2d9cd-175">Using the C API, you can register an XLL function as volatile before its first call.</span></span> <span data-ttu-id="2d9cd-176">它还可以打开和关闭的工作表函数的可变状态。</span><span class="sxs-lookup"><span data-stu-id="2d9cd-176">It also enables you to switch on and off the volatile status of a worksheet function.</span></span>
  
<span data-ttu-id="2d9cd-177">默认情况下，Excel 处理 XLL Udf 的范围参数并作为为可变宏表等效的声明。</span><span class="sxs-lookup"><span data-stu-id="2d9cd-177">By default, Excel handles XLL UDFs that take range arguments and that are declared as macro-sheet equivalents as volatile.</span></span> <span data-ttu-id="2d9cd-178">您可以关闭此默认状态首次调用 UDF 时使用**xlfVolatile**函数。</span><span class="sxs-lookup"><span data-stu-id="2d9cd-178">You can turn this default state off using the **xlfVolatile** function when the UDF is first called.</span></span> 
  
## <a name="calculation-modes-commands-selective-recalculation-and-data-tables"></a><span data-ttu-id="2d9cd-179">计算模式、 命令、 选择性重新计算，和模拟运算表</span><span class="sxs-lookup"><span data-stu-id="2d9cd-179">Calculation Modes, Commands, Selective Recalculation, and Data Tables</span></span>

<span data-ttu-id="2d9cd-180">Excel 有三种计算模式：</span><span class="sxs-lookup"><span data-stu-id="2d9cd-180">Excel has three calculation modes:</span></span>
  
- <span data-ttu-id="2d9cd-181">自动</span><span class="sxs-lookup"><span data-stu-id="2d9cd-181">Automatic</span></span>
    
- <span data-ttu-id="2d9cd-182">除表的自动</span><span class="sxs-lookup"><span data-stu-id="2d9cd-182">Automatic Except Tables</span></span>
    
- <span data-ttu-id="2d9cd-183">手动</span><span class="sxs-lookup"><span data-stu-id="2d9cd-183">Manual</span></span>
    
<span data-ttu-id="2d9cd-184">当计算设置为自动时，重新计算发生每个数据输入之后和之后如前一节中提供的示例某些事件。</span><span class="sxs-lookup"><span data-stu-id="2d9cd-184">When calculation is set to automatic, recalculation occurs after every data input and after certain events such as the examples given in the previous section.</span></span> <span data-ttu-id="2d9cd-185">对于非常大的工作簿，计算的时间可能会很长时间，用户必须限制时发生这种情况，即，在需要时仅重新计算。</span><span class="sxs-lookup"><span data-stu-id="2d9cd-185">For very large workbooks, recalculation time might be so long that users must limit when this happens, that is, only recalculating when they need to.</span></span> <span data-ttu-id="2d9cd-186">若要启用此功能，Excel 支持手动模式。</span><span class="sxs-lookup"><span data-stu-id="2d9cd-186">To enable this, Excel supports the manual mode.</span></span> <span data-ttu-id="2d9cd-187">用户可以选择通过 Excel 菜单系统，或以编程方式使用 VBA、 COM 或 C API 的模式。</span><span class="sxs-lookup"><span data-stu-id="2d9cd-187">The user can select the mode through the Excel menu system, or programmatically using VBA, COM, or the C API.</span></span>
  
<span data-ttu-id="2d9cd-188">模拟运算表是工作表中的特殊结构。</span><span class="sxs-lookup"><span data-stu-id="2d9cd-188">Data tables are special structures in a worksheet.</span></span> <span data-ttu-id="2d9cd-189">首先，用户设置的工作表上的结果计算。</span><span class="sxs-lookup"><span data-stu-id="2d9cd-189">First, the user sets up the calculation of a result on a worksheet.</span></span> <span data-ttu-id="2d9cd-190">这取决于一个或两个关键可更改输入和其他参数。</span><span class="sxs-lookup"><span data-stu-id="2d9cd-190">This depends on one or two key changeable inputs and other parameters.</span></span> <span data-ttu-id="2d9cd-191">用户然后可以为一个或两个关键输入创建一组值的结果的表格。</span><span class="sxs-lookup"><span data-stu-id="2d9cd-191">The user can then create a table of results for a set of values for one or both of the key inputs.</span></span> <span data-ttu-id="2d9cd-192">使用**数据表向导**创建表。</span><span class="sxs-lookup"><span data-stu-id="2d9cd-192">The table is created by using the **Data Table Wizard**.</span></span> <span data-ttu-id="2d9cd-193">表设置后，Excel 输入一个地插入计算，并将结果值复制到表。</span><span class="sxs-lookup"><span data-stu-id="2d9cd-193">After the table is set up, Excel plugs the inputs one-by-one into the calculation and copies the resulting value into the table.</span></span> <span data-ttu-id="2d9cd-194">可以使用一个或两个输入，模拟运算表可以是一个-或二维。</span><span class="sxs-lookup"><span data-stu-id="2d9cd-194">As one or two inputs can be used, data tables can be one- or two-dimensional.</span></span> 
  
<span data-ttu-id="2d9cd-195">重新计算的模拟运算表处理略有不同：</span><span class="sxs-lookup"><span data-stu-id="2d9cd-195">Recalculation of data tables is handled slightly differently:</span></span>
  
- <span data-ttu-id="2d9cd-196">重新计算为常规工作簿重新计算，以便大表可能需要更长时间重新计算工作簿的 rest 比异步处理。</span><span class="sxs-lookup"><span data-stu-id="2d9cd-196">Recalculation is handled asynchronously to regular workbook recalculation so that large tables might take longer to recalculate than the rest of the workbook.</span></span>
    
- <span data-ttu-id="2d9cd-197">容许循环引用。</span><span class="sxs-lookup"><span data-stu-id="2d9cd-197">Circular references are tolerated.</span></span> <span data-ttu-id="2d9cd-198">如果用于获取结果计算依赖的模拟运算表中的一个或多个值，Excel 不返回错误的循环依赖关系。</span><span class="sxs-lookup"><span data-stu-id="2d9cd-198">If the calculation that is used to get the result depends on one or more values from the data table, Excel does not return an error for the circular dependency.</span></span> 
    
<span data-ttu-id="2d9cd-199">Excel 给定 Excel 处理重新计算的模拟运算表和取决于复杂或较长的计算的大型表花费很长时间才能计算事实的不同方式，允许您禁用自动计算的模拟运算表。</span><span class="sxs-lookup"><span data-stu-id="2d9cd-199">Given the different way that Excel handles recalculation of data tables, and the fact that large tables that depend on complex or lengthy calculations can take a long time to calculate, Excel lets you disable the automatic calculation of data tables.</span></span> <span data-ttu-id="2d9cd-200">若要执行此操作，设置为自动 （数据表除外） 的计算模式。</span><span class="sxs-lookup"><span data-stu-id="2d9cd-200">To do this, set the calculation mode to Automatic except Data Tables.</span></span> <span data-ttu-id="2d9cd-201">在此模式中计算后，用户将通过按 F9 或某个等效的编程操作重新计算模拟运算表。</span><span class="sxs-lookup"><span data-stu-id="2d9cd-201">When calculation is in this mode, the user recalculates the data tables by pressing F9 or some equivalent programmatic operation.</span></span>
  
<span data-ttu-id="2d9cd-202">Excel 公开的方法，您可以通过其更改的重新计算模式和控制重新计算。</span><span class="sxs-lookup"><span data-stu-id="2d9cd-202">Excel exposes methods through which you can alter the recalculation mode and control recalculation.</span></span> <span data-ttu-id="2d9cd-203">这些方法进行了改进从版本到版本，以允许更精细的控制。</span><span class="sxs-lookup"><span data-stu-id="2d9cd-203">These methods have been improved from version to version to allow for finer control.</span></span> <span data-ttu-id="2d9cd-204">C API 的功能在这方面反映的 Excel 版本 5、 中可用，并因此并不允许您已在较新版本中使用 VBA 的相同控件。</span><span class="sxs-lookup"><span data-stu-id="2d9cd-204">The capabilities of the C API in this regard reflect those that were available in Excel version 5, and so do not give you the same control that you have using VBA in more recent versions.</span></span> 
  
<span data-ttu-id="2d9cd-205">最常用于手动计算模式 Excel 时，这些方法允许选择性计算工作簿、 工作表和区域，完整的重新计算所有打开的工作簿，并甚至完全重建的依赖项树和计算链。</span><span class="sxs-lookup"><span data-stu-id="2d9cd-205">Most frequently used when Excel is in manual calculation mode, these methods allow selective calculation of workbooks, worksheets, and ranges, complete recalculation of all open workbooks, and even complete rebuild of the dependency tree and calculation chain.</span></span>
  
### <a name="range-calculation"></a><span data-ttu-id="2d9cd-206">区域计算</span><span class="sxs-lookup"><span data-stu-id="2d9cd-206">Range Calculation</span></span>

<span data-ttu-id="2d9cd-207">键击： 无</span><span class="sxs-lookup"><span data-stu-id="2d9cd-207">Keystroke: None</span></span>
  
<span data-ttu-id="2d9cd-208">VBA: （在 Excel 2000 中，更改 Excel 2007 中引入） **Range.Calculate**和**Range.CalculateRowMajorOrder** （引入 Excel 2007 中）</span><span class="sxs-lookup"><span data-stu-id="2d9cd-208">VBA: **Range.Calculate** (introduced in Excel 2000, changed in Excel 2007) and **Range.CalculateRowMajorOrder** (introduced in Excel 2007)</span></span> 
  
<span data-ttu-id="2d9cd-209">C API： 不支持</span><span class="sxs-lookup"><span data-stu-id="2d9cd-209">C API: Not supported</span></span>
  
- <span data-ttu-id="2d9cd-210">**手动模式**</span><span class="sxs-lookup"><span data-stu-id="2d9cd-210">**Manual mode**</span></span>
    
    <span data-ttu-id="2d9cd-211">将来重新计算刚刚而不考虑它们是否给定范围中的单元格 dirty 或不。</span><span class="sxs-lookup"><span data-stu-id="2d9cd-211">Recalculates just the cells in the given range regardless of whether they are dirty or not.</span></span> <span data-ttu-id="2d9cd-212">在 Excel 2007 中; 更改**Range.Calculate**方法的行为但是，仍然**Range.CalculateRowMajorOrder**方法支持的旧的行为。</span><span class="sxs-lookup"><span data-stu-id="2d9cd-212">Behavior of the **Range.Calculate** method changed in Excel 2007; however, the old behavior is still supported by the **Range.CalculateRowMajorOrder** method.</span></span> 
    
- <span data-ttu-id="2d9cd-213">**自动或自动除表模式**</span><span class="sxs-lookup"><span data-stu-id="2d9cd-213">**Automatic or Automatic Except Tables modes**</span></span>
    
    <span data-ttu-id="2d9cd-214">重新计算工作簿，但不会强制重新计算的范围或范围中的任何单元格。</span><span class="sxs-lookup"><span data-stu-id="2d9cd-214">Recalculates the workbook but does not force recalculation of the range or any cells in the range.</span></span>
    
### <a name="active-worksheet-calculation"></a><span data-ttu-id="2d9cd-215">活动工作表计算</span><span class="sxs-lookup"><span data-stu-id="2d9cd-215">Active Worksheet Calculation</span></span>

<span data-ttu-id="2d9cd-216">键击： SHIFT + F9</span><span class="sxs-lookup"><span data-stu-id="2d9cd-216">Keystroke: SHIFT+F9</span></span>
  
<span data-ttu-id="2d9cd-217">VBA: **ActiveSheet.Calculate**</span><span class="sxs-lookup"><span data-stu-id="2d9cd-217">VBA: **ActiveSheet.Calculate**</span></span>
  
<span data-ttu-id="2d9cd-218">C API: **xlcCalculateDocument**</span><span class="sxs-lookup"><span data-stu-id="2d9cd-218">C API: **xlcCalculateDocument**</span></span>
  
- <span data-ttu-id="2d9cd-219">**所有模式**</span><span class="sxs-lookup"><span data-stu-id="2d9cd-219">**All modes**</span></span>
    
    <span data-ttu-id="2d9cd-220">重新计算标记为活动工作表中计算的单元格。</span><span class="sxs-lookup"><span data-stu-id="2d9cd-220">Recalculates the cells marked for calculation in the active worksheet only.</span></span>
    
### <a name="specified-worksheet-calculation"></a><span data-ttu-id="2d9cd-221">指定工作表计算</span><span class="sxs-lookup"><span data-stu-id="2d9cd-221">Specified Worksheet Calculation</span></span>

<span data-ttu-id="2d9cd-222">键击： 无</span><span class="sxs-lookup"><span data-stu-id="2d9cd-222">Keystroke: None</span></span>
  
<span data-ttu-id="2d9cd-223">VBA:**工作表 (****引用)。计算**</span><span class="sxs-lookup"><span data-stu-id="2d9cd-223">VBA: **Worksheets(** reference **).Calculate**</span></span>
  
<span data-ttu-id="2d9cd-224">C API： 不支持</span><span class="sxs-lookup"><span data-stu-id="2d9cd-224">C API: Not supported</span></span>
  
- <span data-ttu-id="2d9cd-225">**所有模式**</span><span class="sxs-lookup"><span data-stu-id="2d9cd-225">**All modes**</span></span>
    
    <span data-ttu-id="2d9cd-226">重新计算的 dirty 单元格并指定工作表中的其从属单元格。</span><span class="sxs-lookup"><span data-stu-id="2d9cd-226">Recalculates the dirty cells and their dependents within the specified worksheet only.</span></span> <span data-ttu-id="2d9cd-227">引用是为一个字符串或相关的工作簿中的索引号的工作表的名称。</span><span class="sxs-lookup"><span data-stu-id="2d9cd-227">Reference is the name of the worksheet as a string or the index number in the relevant workbook.</span></span>
    
    <span data-ttu-id="2d9cd-228">Excel 2000 和更高版本公开一个**布尔值**的工作表属性， **EnableCalculation**属性。</span><span class="sxs-lookup"><span data-stu-id="2d9cd-228">Excel 2000 and later versions expose a **Boolean** worksheet property, the **EnableCalculation** property.</span></span> <span data-ttu-id="2d9cd-229">设置为**True**从**False**弄脏指定工作表中的所有单元格。</span><span class="sxs-lookup"><span data-stu-id="2d9cd-229">Setting this to **True** from **False** dirties all cells in the specified worksheet.</span></span> <span data-ttu-id="2d9cd-230">在自动模式下，这还将触发整个工作簿重新计算。</span><span class="sxs-lookup"><span data-stu-id="2d9cd-230">In automatic modes, this also triggers a recalculation of the whole workbook.</span></span> 
    
    <span data-ttu-id="2d9cd-231">在手动模式下，下面的代码使活动工作表重新计算。</span><span class="sxs-lookup"><span data-stu-id="2d9cd-231">In manual mode, the following code causes recalculation of the active sheet only.</span></span>
    
  ```vb
  With ActiveSheet
    .EnableCalculation = False
    .EnableCalculation = True
    .Calculate
  End With
  
  ```

### <a name="workbook-tree-rebuild-and-forced-recalculation"></a><span data-ttu-id="2d9cd-232">工作簿树重新生成并强制重新计算</span><span class="sxs-lookup"><span data-stu-id="2d9cd-232">Workbook Tree Rebuild and Forced Recalculation</span></span>

<span data-ttu-id="2d9cd-233">键击： CTRL + ALT + SHIFT + F9 （引入 Excel 2002 中）</span><span class="sxs-lookup"><span data-stu-id="2d9cd-233">Keystroke: CTRL+ALT+SHIFT+F9 (introduced in Excel 2002)</span></span>
  
<span data-ttu-id="2d9cd-234">VBA:**工作簿 (****引用)。ForceFullCalculation** （引入 Excel 2007 中）</span><span class="sxs-lookup"><span data-stu-id="2d9cd-234">VBA: **Workbooks(** reference **).ForceFullCalculation** (introduced in Excel 2007)</span></span> 
  
<span data-ttu-id="2d9cd-235">C API： 不支持</span><span class="sxs-lookup"><span data-stu-id="2d9cd-235">C API: Not supported</span></span>
  
- <span data-ttu-id="2d9cd-236">**所有模式**</span><span class="sxs-lookup"><span data-stu-id="2d9cd-236">**All modes**</span></span>
    
    <span data-ttu-id="2d9cd-237">使 Excel 重建相关性树和给定的工作簿的计算链并强制重新计算包含公式的所有单元格。</span><span class="sxs-lookup"><span data-stu-id="2d9cd-237">Causes Excel to rebuild the dependency tree and the calculation chain for a given workbook and forces a recalculation of all cells that contain formulas.</span></span>
    
### <a name="all-open-workbooks"></a><span data-ttu-id="2d9cd-238">所有打开的工作簿</span><span class="sxs-lookup"><span data-stu-id="2d9cd-238">All Open Workbooks</span></span>

<span data-ttu-id="2d9cd-239">键击： F9</span><span class="sxs-lookup"><span data-stu-id="2d9cd-239">Keystroke: F9</span></span>
  
<span data-ttu-id="2d9cd-240">VBA: **Application.Calculate**</span><span class="sxs-lookup"><span data-stu-id="2d9cd-240">VBA: **Application.Calculate**</span></span>
  
<span data-ttu-id="2d9cd-241">C API: **xlcCalculateNow**</span><span class="sxs-lookup"><span data-stu-id="2d9cd-241">C API: **xlcCalculateNow**</span></span>
  
- <span data-ttu-id="2d9cd-242">**所有模式**</span><span class="sxs-lookup"><span data-stu-id="2d9cd-242">**All modes**</span></span>
    
    <span data-ttu-id="2d9cd-243">重新计算的所有单元格的 Excel 已标记为已损坏，即，从属单元格的可变或更改的数据，并以编程方式标记为已损坏的单元格。</span><span class="sxs-lookup"><span data-stu-id="2d9cd-243">Recalculates all cells that Excel has marked as dirty, that is, dependents of volatile or changed data, and cells programmatically marked as dirty.</span></span> <span data-ttu-id="2d9cd-244">如果计算模式是自动除表，这会计算需要更新这些表还所有可变函数和其从属单元格。</span><span class="sxs-lookup"><span data-stu-id="2d9cd-244">If the calculation mode is Automatic Except Tables, this calculates those tables that require updating and also all volatile functions and their dependents.</span></span>
    
### <a name="all-open-workbooks-tree-rebuild-and-forced-calculation"></a><span data-ttu-id="2d9cd-245">所有打开的工作簿树重新生成并强制计算</span><span class="sxs-lookup"><span data-stu-id="2d9cd-245">All Open Workbooks Tree Rebuild and Forced Calculation</span></span>

<span data-ttu-id="2d9cd-246">键击： CTRL + ALT + F9</span><span class="sxs-lookup"><span data-stu-id="2d9cd-246">Keystroke: CTRL+ALT+F9</span></span>
  
<span data-ttu-id="2d9cd-247">VBA: **Application.CalculateFull**</span><span class="sxs-lookup"><span data-stu-id="2d9cd-247">VBA: **Application.CalculateFull**</span></span>
  
<span data-ttu-id="2d9cd-248">C API： 不支持</span><span class="sxs-lookup"><span data-stu-id="2d9cd-248">C API: Not supported</span></span>
  
- <span data-ttu-id="2d9cd-249">**所有模式**</span><span class="sxs-lookup"><span data-stu-id="2d9cd-249">**All modes**</span></span>
    
    <span data-ttu-id="2d9cd-250">重新计算所有打开的工作簿中所有单元格。</span><span class="sxs-lookup"><span data-stu-id="2d9cd-250">Recalculates all cells in all open workbooks.</span></span> <span data-ttu-id="2d9cd-251">如果计算模式是自动除表，它会强制重新计算的表格。</span><span class="sxs-lookup"><span data-stu-id="2d9cd-251">If the calculation mode is Automatic Except Tables, it forces the tables to be recalculated.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="2d9cd-252">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2d9cd-252">See also</span></span>



[<span data-ttu-id="2d9cd-253">Excel 中的多线程重新计算</span><span class="sxs-lookup"><span data-stu-id="2d9cd-253">Multithreaded Recalculation in Excel</span></span>](multithreaded-recalculation-in-excel.md)
  
[<span data-ttu-id="2d9cd-254">Excel 使用的数据类型</span><span class="sxs-lookup"><span data-stu-id="2d9cd-254">Data Types Used by Excel</span></span>](data-types-used-by-excel.md)
  
[<span data-ttu-id="2d9cd-255">Excel 中的内存管理</span><span class="sxs-lookup"><span data-stu-id="2d9cd-255">Memory Management in Excel</span></span>](memory-management-in-excel.md)
  
[<span data-ttu-id="2d9cd-256">Excel Programming Concepts</span><span class="sxs-lookup"><span data-stu-id="2d9cd-256">Excel Programming Concepts</span></span>](excel-programming-concepts.md)

