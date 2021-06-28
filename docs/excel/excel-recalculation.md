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
ms.openlocfilehash: c4b6dbad7a31b7155d1bec3a5c867b6c74d0ff42
ms.sourcegitcommit: 35b723efe168ae4bad461bd16b26f9a2412656f2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/25/2021
ms.locfileid: "53139091"
---
# <a name="excel-recalculation"></a><span data-ttu-id="60bba-104">Excel 重新计算</span><span class="sxs-lookup"><span data-stu-id="60bba-104">Excel Recalculation</span></span>

<span data-ttu-id="60bba-105">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="60bba-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="60bba-106">用户可以通过以下几种方法在 Microsoft Excel 中触发重新计算，例如：</span><span class="sxs-lookup"><span data-stu-id="60bba-106">The user can trigger recalculation in Microsoft Excel in several ways, for example:</span></span>
  
- <span data-ttu-id="60bba-107">输入新数据（如果 Excel 处于自动重新计算模式，本主题稍后将对此进行介绍）。</span><span class="sxs-lookup"><span data-stu-id="60bba-107">Entering new data (if Excel is in Automatic recalculation mode, described later in this topic).</span></span>
    
- <span data-ttu-id="60bba-108">显式指示 Excel 重新计算所有或一部分工作簿。</span><span class="sxs-lookup"><span data-stu-id="60bba-108">Explicitly instructing Excel to recalculate all or part of a workbook.</span></span>
    
- <span data-ttu-id="60bba-109">删除或插入行或列。</span><span class="sxs-lookup"><span data-stu-id="60bba-109">Deleting or inserting a row or column.</span></span>
    
- <span data-ttu-id="60bba-110">设置“保存前重新计算”选项时保存工作簿。</span><span class="sxs-lookup"><span data-stu-id="60bba-110">Saving a workbook while the **Recalculate before save** option is set.</span></span> 
    
- <span data-ttu-id="60bba-111">执行某些自动筛选操作。</span><span class="sxs-lookup"><span data-stu-id="60bba-111">Performing certain Autofilter actions.</span></span>
    
- <span data-ttu-id="60bba-112">双击行分隔符或列分隔符（在自动计算模式下）。</span><span class="sxs-lookup"><span data-stu-id="60bba-112">Double-clicking a row or column divider (in Automatic calculation mode).</span></span>
    
- <span data-ttu-id="60bba-113">添加、编辑或删除已定义的名称。</span><span class="sxs-lookup"><span data-stu-id="60bba-113">Adding, editing, or deleting a defined name.</span></span>
    
- <span data-ttu-id="60bba-114">重命名工作表。</span><span class="sxs-lookup"><span data-stu-id="60bba-114">Renaming a worksheet.</span></span>
    
- <span data-ttu-id="60bba-115">更改某个工作表相对于其他工作表的位置。</span><span class="sxs-lookup"><span data-stu-id="60bba-115">Changing the position of a worksheet in relation to other worksheets.</span></span>
    
- <span data-ttu-id="60bba-116">隐藏或取消隐藏行，而非列。</span><span class="sxs-lookup"><span data-stu-id="60bba-116">Hiding or unhiding rows, but not columns.</span></span>
    
> [!NOTE]
> <span data-ttu-id="60bba-117">本主题不区分用户直接按下按键或单击鼠标，以及通过命令或宏完成的任务。</span><span class="sxs-lookup"><span data-stu-id="60bba-117">This topic does not distinguish between the user directly pressing a key or clicking the mouse, and those tasks being done by a command or macro.</span></span> <span data-ttu-id="60bba-118">用户运行命令或执行某个操作使命令运行，以便仍将其视为用户操作。</span><span class="sxs-lookup"><span data-stu-id="60bba-118">The user runs the command, or does something to cause the command to run so that it is still considered a user action.</span></span> <span data-ttu-id="60bba-119">因此，短语“用户”也意味着“用户，或由用户启动的命令或进程”。</span><span class="sxs-lookup"><span data-stu-id="60bba-119">Therefore the phrase "the user" also means "the user, or a command or process started by the user."</span></span> 
  
## <a name="dependence-dirty-cells-and-recalculated-cells"></a><span data-ttu-id="60bba-120">相关性、脏单元格和重新计算的单元格</span><span class="sxs-lookup"><span data-stu-id="60bba-120">Dependence, Dirty Cells, and Recalculated Cells</span></span>

<span data-ttu-id="60bba-121">Excel 中工作表的计算可视为包含三个阶段的过程：</span><span class="sxs-lookup"><span data-stu-id="60bba-121">The calculation of worksheets in Excel can be viewed as a three-stage process:</span></span>
  
1. <span data-ttu-id="60bba-122">构造依赖关系树</span><span class="sxs-lookup"><span data-stu-id="60bba-122">Construction of a dependency tree</span></span>
    
2. <span data-ttu-id="60bba-123">构造计算链</span><span class="sxs-lookup"><span data-stu-id="60bba-123">Construction of a calculation chain</span></span>
    
3. <span data-ttu-id="60bba-124">重新计算单元格</span><span class="sxs-lookup"><span data-stu-id="60bba-124">Recalculation of cells</span></span>
    
<span data-ttu-id="60bba-125">依赖关系树通知 Excel，哪些单元格依赖于哪些其他单元格，或者说，哪些单元格是其他单元格的引用单元格。</span><span class="sxs-lookup"><span data-stu-id="60bba-125">The dependency tree informs Excel about which cells depend on which others, or equivalently, which cells are precedents for which others.</span></span> <span data-ttu-id="60bba-126">Excel 从此树中构造计算链。</span><span class="sxs-lookup"><span data-stu-id="60bba-126">From this tree, Excel constructs a calculation chain.</span></span> <span data-ttu-id="60bba-127">计算链按计算的顺序列出包含公式的所有单元格。</span><span class="sxs-lookup"><span data-stu-id="60bba-127">The calculation chain lists all the cells that contain formulas in the order in which they should be calculated.</span></span> <span data-ttu-id="60bba-128">在重新计算过程中，如果此链遇到依赖于尚未计算的单元格的公式，Excel 会对其进行修改。</span><span class="sxs-lookup"><span data-stu-id="60bba-128">During recalculation, Excel revises this chain if it comes across a formula that depends on a cell that has not yet been calculated.</span></span> <span data-ttu-id="60bba-129">在这种情况下，正在计算的单元格及其依赖项会移动到该链下。</span><span class="sxs-lookup"><span data-stu-id="60bba-129">In this case, the cell that is being calculated and its dependents are moved down the chain.</span></span> <span data-ttu-id="60bba-130">因此，通常会在前几个计算周期中刚刚打开的工作表中增加计算次数。</span><span class="sxs-lookup"><span data-stu-id="60bba-130">For this reason, calculation times can often improve in a worksheet that has just been opened in the first few calculation cycles.</span></span>
  
<span data-ttu-id="60bba-131">对工作簿进行结构更改后（例如，输入新公式后），Excel 会重新构造依赖关系树和计算链。</span><span class="sxs-lookup"><span data-stu-id="60bba-131">When a structural change is made to a workbook, for example, when a new formula is entered, Excel reconstructs the dependency tree and calculation chain.</span></span> <span data-ttu-id="60bba-132">输入新数据或新公式后，Excel 会将依赖于该新数据的所有单元格标记为需要重新计算。</span><span class="sxs-lookup"><span data-stu-id="60bba-132">When new data or new formulas are entered, Excel marks all the cells that depend on that new data as needing recalculation.</span></span> <span data-ttu-id="60bba-133">通过这种方式标记的单元格称为 *脏* 单元格。</span><span class="sxs-lookup"><span data-stu-id="60bba-133">Cells that are marked in this way are known as  *dirty*  .</span></span> <span data-ttu-id="60bba-134">所有直接依赖项和间接依赖项都标记为脏依赖项，因此，如果 B1 依赖于 A1，且 C1 依赖于 B1，那么如果更改 A1，B1 和 C1 都将标记为脏单元格。</span><span class="sxs-lookup"><span data-stu-id="60bba-134">All direct and indirect dependents are marked as dirty so that if B1 depends on A1, and C1 depends on B1, when A1 is changed, both B1 and C1 are marked as dirty.</span></span> 
  
<span data-ttu-id="60bba-135">如果某个单元格直接或间接依赖于其自身，Excel 将检测到循环引用并提醒用户。</span><span class="sxs-lookup"><span data-stu-id="60bba-135">If a cell depends, directly or indirectly, on itself, Excel detects the circular reference and warns the user.</span></span> <span data-ttu-id="60bba-136">这通常是用户必须解决的问题，并且 Excel 提供了非常有用的图形和导航工具来帮助用户查找循环依赖关系的来源。</span><span class="sxs-lookup"><span data-stu-id="60bba-136">This is usually an error condition that the user must fix, and Excel provides very helpful graphical and navigational tools to help the user to find the source of the circular dependency.</span></span> <span data-ttu-id="60bba-137">在某些情况下，用户可能会有意希望存在此情况。</span><span class="sxs-lookup"><span data-stu-id="60bba-137">In some cases, you might deliberately want this condition to exist.</span></span> <span data-ttu-id="60bba-138">例如，用户可能想要运行迭代计算，其中下一次迭代的起始点是上一次迭代的结果。</span><span class="sxs-lookup"><span data-stu-id="60bba-138">For example, you might want to run an iterative calculation where the starting point for the next iteration is the result of the previous iteration.</span></span> <span data-ttu-id="60bba-139">Excel 支持通过计算选项对话框控制迭代计算。</span><span class="sxs-lookup"><span data-stu-id="60bba-139">Excel supports control of iterative calculations through the calculation options dialog box.</span></span>
  
<span data-ttu-id="60bba-140">将单元格标记为脏单元格后，如果再进行重新计算，Excel 会按计算链指定的顺序重新计算每个脏单元格的内容。</span><span class="sxs-lookup"><span data-stu-id="60bba-140">After marking cells as dirty, when a recalculation is next done, Excel reevaluates the contents of each dirty cell in the order dictated by the calculation chain.</span></span> <span data-ttu-id="60bba-141">在先前提供的示例中，这意味着 B1 是第一个，其次是 C1。</span><span class="sxs-lookup"><span data-stu-id="60bba-141">In the example given earlier, this means B1 is first, and then C1.</span></span> <span data-ttu-id="60bba-142">如果重新计算模式为自动，则在 Excel 将单元格标记为脏单元格后，将立即进行此重新计算；否则将稍后执行。</span><span class="sxs-lookup"><span data-stu-id="60bba-142">This recalculation occurs immediately after Excel finishes marking cells as dirty if the recalculation mode is automatic; otherwise, it occurs later.</span></span>
  
<span data-ttu-id="60bba-143">从 Microsoft Excel 2002 开始，Microsoft Visual Basic for Applications (VBA) 中的 **Range** 对象支持 **Range.Dirty** 方法，该方法可将单元格标记为“需要计算”。</span><span class="sxs-lookup"><span data-stu-id="60bba-143">Starting in Microsoft Excel 2002, the **Range** object in Microsoft Visual Basic for Applications (VBA) supports a method, **Range.Dirty**, which marks cells as needing calculation.</span></span> <span data-ttu-id="60bba-144">如果将该方法与 **Range.Calculate** 方法结合使用（请参阅下一部分），会强制重新计算给定区域内的单元格。</span><span class="sxs-lookup"><span data-stu-id="60bba-144">When it is used together with the **Range.Calculate** method (see next section), it enables forced recalculation of cells in a given range.</span></span> <span data-ttu-id="60bba-145">在宏期间执行有限计算时（其中计算模式设置为手动），此做法非常有用，可以避免因计算与宏函数无关的单元格而产生开销。</span><span class="sxs-lookup"><span data-stu-id="60bba-145">This is useful when you are performing a limited calculation during a macro, where the calculation mode is set to manual, to avoid the overhead of calculating cells unrelated to the macro function.</span></span> <span data-ttu-id="60bba-146">C API 不提供区域计算方法。</span><span class="sxs-lookup"><span data-stu-id="60bba-146">Range calculation methods are not available through the C API.</span></span> 
  
<span data-ttu-id="60bba-147">在 Excel 2002 和更早版本中，Excel 为每个打开的工作簿中的每个工作表构建一个计算链。</span><span class="sxs-lookup"><span data-stu-id="60bba-147">In Excel 2002 and earlier versions, Excel built a calculation chain for each worksheet in each open workbook.</span></span> <span data-ttu-id="60bba-148">这导致处理工作表之间的链接的方式有些复杂，并且需要小心谨慎以确保有效的重新计算。</span><span class="sxs-lookup"><span data-stu-id="60bba-148">This resulted in some complexity in the way links between worksheets were handled, and required some care to ensure efficient recalculation.</span></span> <span data-ttu-id="60bba-149">特别是，在 Excel 2000 中，应尽量减少跨工作表的依赖关系并按字母顺序命名工作表，以便依赖于其他工作表的工作表按字母顺序排在它们所依赖的工作表之后。</span><span class="sxs-lookup"><span data-stu-id="60bba-149">In particular, in Excel 2000, you should minimize cross-worksheet dependencies and name worksheets in alphabetical order so that sheets that depend on other sheets come alphabetically after the sheets they depend on.</span></span>
  
<span data-ttu-id="60bba-150">Excel 2007 中的逻辑得以改进，允许在多个线程上重新计算，这样计算链的各个部分就不再相互依赖，并且可以同时计算。</span><span class="sxs-lookup"><span data-stu-id="60bba-150">In Excel 2007, the logic was improved to enable recalculation on multiple threads so that sections of the calculation chain are not interdependent and can be calculated at the same time.</span></span> <span data-ttu-id="60bba-151">可以将 Excel 配置为在单个处理器计算机上使用多个线程，或者在多处理器或多核计算机上使用单个线程。</span><span class="sxs-lookup"><span data-stu-id="60bba-151">You can configure Excel to use multiple threads on a single processor computer, or a single thread on a multi-processor or multi-core computer.</span></span> 
  
## <a name="asynchronous-user-defined-functions-udfs"></a><span data-ttu-id="60bba-152">用户定义的异步函数 (UDF)</span><span class="sxs-lookup"><span data-stu-id="60bba-152">Asynchronous User Defined Functions (UDFs)</span></span>

<span data-ttu-id="60bba-153">当计算遇到异步 UDF 时，它会保存当前公式的状态，启动 UDF 并继续计算其余单元格。</span><span class="sxs-lookup"><span data-stu-id="60bba-153">When a calculation encounters an asynchronous UDF, it saves the state of the current formula, starts the UDF and continues evaluating the rest of the cells.</span></span> <span data-ttu-id="60bba-154">当计算完成单元格的计算时，Excel 将等待异步函数完成（如果仍然有异步函数在运行）。</span><span class="sxs-lookup"><span data-stu-id="60bba-154">When the calculation finishes evaluating the cells Excel waits for the asynchronous functions to complete if there are still asynchronous functions running.</span></span> <span data-ttu-id="60bba-155">每个异步函数报告结果时，Excel 将完成公式，然后运行新的计算通道，以便重新计算使用引用异步函数的单元格的单元格。</span><span class="sxs-lookup"><span data-stu-id="60bba-155">As each asynchronous function reports results, Excel finishes the formula, and then runs a new calculation pass to re-compute cells that use the cell with the reference to the asynchronous function.</span></span>
  
## <a name="volatile-and-non-volatile-functions"></a><span data-ttu-id="60bba-156">可变函数和非可变函数</span><span class="sxs-lookup"><span data-stu-id="60bba-156">Volatile and Non-Volatile Functions</span></span>

<span data-ttu-id="60bba-157">Excel 支持可变函数的概念，也就是说，即使它的参数（如果有的话）没有任何变化，也不能假定该函数的值在不同时刻都是相同的。</span><span class="sxs-lookup"><span data-stu-id="60bba-157">Excel supports the concept of a volatile function, that is, one whose value cannot be assumed to be the same from one moment to the next even if none of its arguments (if it takes any) has changed.</span></span> <span data-ttu-id="60bba-158">Excel 在每次重新计算时，都会重新计算包含可变函数和所有依赖项的单元格。</span><span class="sxs-lookup"><span data-stu-id="60bba-158">Excel reevaluates cells that contain volatile functions, together with all dependents, every time that it recalculates.</span></span> <span data-ttu-id="60bba-159">因此，过于依赖可变函数会使重新计算时间变慢。</span><span class="sxs-lookup"><span data-stu-id="60bba-159">For this reason, too much reliance on volatile functions can make recalculation times slow.</span></span> <span data-ttu-id="60bba-160">请谨慎使用。</span><span class="sxs-lookup"><span data-stu-id="60bba-160">Use them sparingly.</span></span>
  
<span data-ttu-id="60bba-161">以下是可变的 Excel 函数：</span><span class="sxs-lookup"><span data-stu-id="60bba-161">The following Excel functions are volatile:</span></span>
  
- <span data-ttu-id="60bba-162">**NOW**</span><span class="sxs-lookup"><span data-stu-id="60bba-162">**NOW**</span></span>
    
- <span data-ttu-id="60bba-163">**TODAY**</span><span class="sxs-lookup"><span data-stu-id="60bba-163">**TODAY**</span></span>
    
- <span data-ttu-id="60bba-164">**RANDBETWEEN**</span><span class="sxs-lookup"><span data-stu-id="60bba-164">**RANDBETWEEN**</span></span>
    
- <span data-ttu-id="60bba-165">**OFFSET**</span><span class="sxs-lookup"><span data-stu-id="60bba-165">**OFFSET**</span></span>
    
- <span data-ttu-id="60bba-166">**INDIRECT**</span><span class="sxs-lookup"><span data-stu-id="60bba-166">**INDIRECT**</span></span>
    
- <span data-ttu-id="60bba-167">**INFO**（具体取决于其参数）</span><span class="sxs-lookup"><span data-stu-id="60bba-167">**INFO** (depending on its arguments)</span></span> 
    
- <span data-ttu-id="60bba-168">**CELL**（具体取决于其参数）</span><span class="sxs-lookup"><span data-stu-id="60bba-168">**CELL** (depending on its arguments)</span></span> 
    
- <span data-ttu-id="60bba-169">**SUMIF**（具体取决于其参数）</span><span class="sxs-lookup"><span data-stu-id="60bba-169">**SUMIF** (depending on its arguments)</span></span> 
    
<span data-ttu-id="60bba-170">VBA 和 C API 都支持通知 Excel 用户定义函数 (UDF) 应作为可变函数处理的方法。</span><span class="sxs-lookup"><span data-stu-id="60bba-170">Both the VBA and C API support ways to inform Excel that a user-defined function (UDF) should be handled as volatile.</span></span> <span data-ttu-id="60bba-171">通过使用 VBA，UDF 被声明为可变，如下所示。</span><span class="sxs-lookup"><span data-stu-id="60bba-171">By using VBA, the UDF is declared as volatile as follows.</span></span>
  
```vba
Function MyUDF(MakeMeVolatile As Boolean) As Double
   ' Good practice to call this on the first line.
   Application.Volatile MakeMeVolatile
   MyUDF = Now
End Function

```

<span data-ttu-id="60bba-172">默认情况下，Excel 假定 VBA UDF 不可变。</span><span class="sxs-lookup"><span data-stu-id="60bba-172">By default, Excel assumes that VBA UDFs are not volatile.</span></span> <span data-ttu-id="60bba-173">Excel 只知道 UDF 在第一次调用时是可变的。</span><span class="sxs-lookup"><span data-stu-id="60bba-173">Excel only learns that a UDF is volatile when it first calls it.</span></span> <span data-ttu-id="60bba-174">可变的 UDF 可以像本例中那样更改回非可变 UDF。</span><span class="sxs-lookup"><span data-stu-id="60bba-174">A volatile UDF can be changed back to non-volatile as in this example.</span></span>
  
<span data-ttu-id="60bba-175">使用 C API，可以在第一次调用 XLL 函数之前将其注册为可变。</span><span class="sxs-lookup"><span data-stu-id="60bba-175">Using the C API, you can register an XLL function as volatile before its first call.</span></span> <span data-ttu-id="60bba-176">用户还可以使用它启用和禁用工作表函数的可变状态。</span><span class="sxs-lookup"><span data-stu-id="60bba-176">It also enables you to switch on and off the volatile status of a worksheet function.</span></span>
  
<span data-ttu-id="60bba-177">默认情况下，Excel 处理可接受区域参数、并且被声明为作为可变函数的宏表等效项的 XLL UDF。</span><span class="sxs-lookup"><span data-stu-id="60bba-177">By default, Excel handles XLL UDFs that take range arguments and that are declared as macro-sheet equivalents as volatile.</span></span> <span data-ttu-id="60bba-178">在首次调用 UDF 时，可以使用 **xlfVolatile** 函数禁用此默认状态。</span><span class="sxs-lookup"><span data-stu-id="60bba-178">You can turn this default state off using the **xlfVolatile** function when the UDF is first called.</span></span> 
  
## <a name="calculation-modes-commands-selective-recalculation-and-data-tables"></a><span data-ttu-id="60bba-179">计算模式、命令、选择性重新计算和数据表</span><span class="sxs-lookup"><span data-stu-id="60bba-179">Calculation Modes, Commands, Selective Recalculation, and Data Tables</span></span>

<span data-ttu-id="60bba-180">Excel 有三种计算模式：</span><span class="sxs-lookup"><span data-stu-id="60bba-180">Excel has three calculation modes:</span></span>
  
- <span data-ttu-id="60bba-181">自动</span><span class="sxs-lookup"><span data-stu-id="60bba-181">Automatic</span></span>
    
- <span data-ttu-id="60bba-182">自动（表除外）</span><span class="sxs-lookup"><span data-stu-id="60bba-182">Automatic Except Tables</span></span>
    
- <span data-ttu-id="60bba-183">手动</span><span class="sxs-lookup"><span data-stu-id="60bba-183">Manual</span></span>
    
<span data-ttu-id="60bba-184">如果计算设置为自动，将在每次数据输入之后以及在某些事件（如前一节中给出的示例）之后重新计算。</span><span class="sxs-lookup"><span data-stu-id="60bba-184">When calculation is set to automatic, recalculation occurs after every data input and after certain events such as the examples given in the previous section.</span></span> <span data-ttu-id="60bba-185">对于非常大的工作簿，重新计算时间可能太长，以至于用户必须限制何时发生这种情况，即只在需要时重新计算。</span><span class="sxs-lookup"><span data-stu-id="60bba-185">For very large workbooks, recalculation time might be so long that users must limit when this happens, that is, only recalculating when they need to.</span></span> <span data-ttu-id="60bba-186">为此，Excel 支持手动模式。</span><span class="sxs-lookup"><span data-stu-id="60bba-186">To enable this, Excel supports the manual mode.</span></span> <span data-ttu-id="60bba-187">用户可以通过 Excel 菜单系统选择模式，也可以使用 VBA、COM 或 C API 以编程方式选择模式。</span><span class="sxs-lookup"><span data-stu-id="60bba-187">The user can select the mode through the Excel menu system, or programmatically using VBA, COM, or the C API.</span></span>
  
<span data-ttu-id="60bba-188">数据表是工作表中的特殊结构。</span><span class="sxs-lookup"><span data-stu-id="60bba-188">Data tables are special structures in a worksheet.</span></span> <span data-ttu-id="60bba-189">首先，用户在工作表上设置结果计算。</span><span class="sxs-lookup"><span data-stu-id="60bba-189">First, the user sets up the calculation of a result on a worksheet.</span></span> <span data-ttu-id="60bba-190">这取决于一两个关键的可变输入和其他参数。</span><span class="sxs-lookup"><span data-stu-id="60bba-190">This depends on one or two key changeable inputs and other parameters.</span></span> <span data-ttu-id="60bba-191">然后，用户可以为一两个关键输入的一组值创建结果表。</span><span class="sxs-lookup"><span data-stu-id="60bba-191">The user can then create a table of results for a set of values for one or both of the key inputs.</span></span> <span data-ttu-id="60bba-192">该表是使用“数据表向导”创建的。</span><span class="sxs-lookup"><span data-stu-id="60bba-192">The table is created by using the **Data Table Wizard**.</span></span> <span data-ttu-id="60bba-193">表设置完成后，Excel 将输入逐个插入到计算中，并将结果值复制到表中。</span><span class="sxs-lookup"><span data-stu-id="60bba-193">After the table is set up, Excel plugs the inputs one-by-one into the calculation and copies the resulting value into the table.</span></span> <span data-ttu-id="60bba-194">由于可以使用一个或两个输入，因此，数据表可以是一维或二维的。</span><span class="sxs-lookup"><span data-stu-id="60bba-194">As one or two inputs can be used, data tables can be one- or two-dimensional.</span></span> 
  
<span data-ttu-id="60bba-195">对重新计算数据表的处理略有不同：</span><span class="sxs-lookup"><span data-stu-id="60bba-195">Recalculation of data tables is handled slightly differently:</span></span>
  
- <span data-ttu-id="60bba-196">相比常规工作簿重新计算，此类重新计算是以异步方式进行的，因此大型表重新计算可能要比工作簿的其余部分花费更长时间。</span><span class="sxs-lookup"><span data-stu-id="60bba-196">Recalculation is handled asynchronously to regular workbook recalculation so that large tables might take longer to recalculate than the rest of the workbook.</span></span>
    
- <span data-ttu-id="60bba-p117">允许循环引用。如果用于获取结果的计算取决于数据表中的一个或多个值，则 Excel 不会返回循环依赖项错误。</span><span class="sxs-lookup"><span data-stu-id="60bba-p117">Circular references are tolerated. If the calculation that is used to get the result depends on one or more values from the data table, Excel does not return an error for the circular dependency.</span></span> 

- <span data-ttu-id="60bba-199">数据表不使用多线程计算。</span><span class="sxs-lookup"><span data-stu-id="60bba-199">Data tables do not use multi-threaded calculation.</span></span>
    
<span data-ttu-id="60bba-200">鉴于 Excel 处理数据表重新计算的方式不同，以及依赖于复杂或冗长计算的大型表可能需要很长时间才能计算，Excel 允许禁用数据表的自动计算。</span><span class="sxs-lookup"><span data-stu-id="60bba-200">Given the different way that Excel handles recalculation of data tables, and the fact that large tables that depend on complex or lengthy calculations can take a long time to calculate, Excel lets you disable the automatic calculation of data tables.</span></span> <span data-ttu-id="60bba-201">为此，将计算模式设置为“自动(数据表除外)”。</span><span class="sxs-lookup"><span data-stu-id="60bba-201">To do this, set the calculation mode to Automatic except Data Tables.</span></span> <span data-ttu-id="60bba-202">当计算处于此模式时，用户通过按 F9 或一些等效编程操作可以重新计算数据表。</span><span class="sxs-lookup"><span data-stu-id="60bba-202">When calculation is in this mode, the user recalculates the data tables by pressing F9 or some equivalent programmatic operation.</span></span>
  
<span data-ttu-id="60bba-203">Excel 公开了一些方法，用户可以通过这些方法更改重新计算模式并控制重新计算。</span><span class="sxs-lookup"><span data-stu-id="60bba-203">Excel exposes methods through which you can alter the recalculation mode and control recalculation.</span></span> <span data-ttu-id="60bba-204">这些方法已在各版本中得以改进，从而实现更精细的控制。</span><span class="sxs-lookup"><span data-stu-id="60bba-204">These methods have been improved from version to version to allow for finer control.</span></span> <span data-ttu-id="60bba-205">C API 在此方面的功能反映了 Excel 版本 5 中可用的功能，因此不提供与在更新版本中使用 VBA 的相同控件。</span><span class="sxs-lookup"><span data-stu-id="60bba-205">The capabilities of the C API in this regard reflect those that were available in Excel version 5, and so do not give you the same control that you have using VBA in more recent versions.</span></span> 
  
<span data-ttu-id="60bba-206">当 Excel 处于手动计算模式时，这些方法使用最为频繁，它们允许对工作簿、工作表以及区域进行选择性计算，完成对所有打开的工作簿的重新计算，甚至完成依赖关系树和计算链的重建。</span><span class="sxs-lookup"><span data-stu-id="60bba-206">Most frequently used when Excel is in manual calculation mode, these methods allow selective calculation of workbooks, worksheets, and ranges, complete recalculation of all open workbooks, and even complete rebuild of the dependency tree and calculation chain.</span></span>
  
### <a name="range-calculation"></a><span data-ttu-id="60bba-207">区域计算</span><span class="sxs-lookup"><span data-stu-id="60bba-207">Range Calculation</span></span>

<span data-ttu-id="60bba-208">击键：无</span><span class="sxs-lookup"><span data-stu-id="60bba-208">Keystroke: None</span></span>
  
<span data-ttu-id="60bba-209">VBA：**Range.Calculate**（在 Excel 2000 中引入，在 Excel 2007 中更改）和 **Range.CalculateRowMajorOrder**（在 Excel 2007 中引入）</span><span class="sxs-lookup"><span data-stu-id="60bba-209">VBA: **Range.Calculate** (introduced in Excel 2000, changed in Excel 2007) and **Range.CalculateRowMajorOrder** (introduced in Excel 2007)</span></span> 
  
<span data-ttu-id="60bba-210">C API：不支持</span><span class="sxs-lookup"><span data-stu-id="60bba-210">C API: Not supported</span></span>
  
- <span data-ttu-id="60bba-211">**手动模式**</span><span class="sxs-lookup"><span data-stu-id="60bba-211">**Manual mode**</span></span>
    
    <span data-ttu-id="60bba-212">只重新计算给定区域内的单元格（无论它们是否为脏单元格）。</span><span class="sxs-lookup"><span data-stu-id="60bba-212">Recalculates just the cells in the given range regardless of whether they are dirty or not.</span></span> <span data-ttu-id="60bba-213">**Range.Calculate** 方法的行为在 Excel 2007 中进行了更改；但 **Range.CalculateRowMajorOrder** 方法仍支持旧行为。</span><span class="sxs-lookup"><span data-stu-id="60bba-213">Behavior of the **Range.Calculate** method changed in Excel 2007; however, the old behavior is still supported by the **Range.CalculateRowMajorOrder** method.</span></span> 
    
- <span data-ttu-id="60bba-214">**自动模式或自动（表除外）模式**</span><span class="sxs-lookup"><span data-stu-id="60bba-214">**Automatic or Automatic Except Tables modes**</span></span>
    
    <span data-ttu-id="60bba-215">重新计算工作簿，但不强制重新计算区域或区域中的任何单元格。</span><span class="sxs-lookup"><span data-stu-id="60bba-215">Recalculates the workbook but does not force recalculation of the range or any cells in the range.</span></span>
    
### <a name="active-worksheet-calculation"></a><span data-ttu-id="60bba-216">活动工作表计算</span><span class="sxs-lookup"><span data-stu-id="60bba-216">Active Worksheet Calculation</span></span>

<span data-ttu-id="60bba-217">击键：SHIFT+F9</span><span class="sxs-lookup"><span data-stu-id="60bba-217">Keystroke: SHIFT+F9</span></span>
  
<span data-ttu-id="60bba-218">VBA：**ActiveSheet.Calculate**</span><span class="sxs-lookup"><span data-stu-id="60bba-218">VBA: **ActiveSheet.Calculate**</span></span>
  
<span data-ttu-id="60bba-219">C API：**xlcCalculateDocument**</span><span class="sxs-lookup"><span data-stu-id="60bba-219">C API: **xlcCalculateDocument**</span></span>
  
- <span data-ttu-id="60bba-220">**所有模式**</span><span class="sxs-lookup"><span data-stu-id="60bba-220">**All modes**</span></span>
    
    <span data-ttu-id="60bba-221">仅重新计算活动工作表中标记为计算的单元格。</span><span class="sxs-lookup"><span data-stu-id="60bba-221">Recalculates the cells marked for calculation in the active worksheet only.</span></span>
    
### <a name="specified-worksheet-calculation"></a><span data-ttu-id="60bba-222">指定工作表计算</span><span class="sxs-lookup"><span data-stu-id="60bba-222">Specified Worksheet Calculation</span></span>

<span data-ttu-id="60bba-223">击键：无</span><span class="sxs-lookup"><span data-stu-id="60bba-223">Keystroke: None</span></span>
  
<span data-ttu-id="60bba-224">VBA：**Worksheets(** reference **).Calculate**</span><span class="sxs-lookup"><span data-stu-id="60bba-224">VBA: **Worksheets(** reference **).Calculate**</span></span>
  
<span data-ttu-id="60bba-225">C API：不支持</span><span class="sxs-lookup"><span data-stu-id="60bba-225">C API: Not supported</span></span>
  
- <span data-ttu-id="60bba-226">**所有模式**</span><span class="sxs-lookup"><span data-stu-id="60bba-226">**All modes**</span></span>
    
    <span data-ttu-id="60bba-227">仅在指定工作表中重新计算脏单元格及其依赖项。</span><span class="sxs-lookup"><span data-stu-id="60bba-227">Recalculates the dirty cells and their dependents within the specified worksheet only.</span></span> <span data-ttu-id="60bba-228">引用是作为字符串的工作表的名称或相关工作簿中的索引号。</span><span class="sxs-lookup"><span data-stu-id="60bba-228">Reference is the name of the worksheet as a string or the index number in the relevant workbook.</span></span>
    
    <span data-ttu-id="60bba-229">Excel 2000 及更高版本版本公开了一个 **布尔** 工作表属性，即 **EnableCalculation** 属性。</span><span class="sxs-lookup"><span data-stu-id="60bba-229">Excel 2000 and later versions expose a **Boolean** worksheet property, the **EnableCalculation** property.</span></span> <span data-ttu-id="60bba-230">将此属性从 **False** 设置为 **True** 将使指定工作表的全部单元格变为脏单元格。</span><span class="sxs-lookup"><span data-stu-id="60bba-230">Setting this to **True** from **False** dirties all cells in the specified worksheet.</span></span> <span data-ttu-id="60bba-231">在自动模式下，这还会触发整个工作簿的重新计算。</span><span class="sxs-lookup"><span data-stu-id="60bba-231">In automatic modes, this also triggers a recalculation of the whole workbook.</span></span> 
    
    <span data-ttu-id="60bba-232">在手动模式下，以下代码只会导致重新计算活动表。</span><span class="sxs-lookup"><span data-stu-id="60bba-232">In manual mode, the following code causes recalculation of the active sheet only.</span></span>
    
  ```vb
  With ActiveSheet
    .EnableCalculation = False
    .EnableCalculation = True
    .Calculate
  End With
  
  ```

### <a name="workbook-tree-rebuild-and-forced-recalculation"></a><span data-ttu-id="60bba-233">工作簿树重建和强制重新计算</span><span class="sxs-lookup"><span data-stu-id="60bba-233">Workbook Tree Rebuild and Forced Recalculation</span></span>

<span data-ttu-id="60bba-234">击键：CTRL+ALT+SHIFT+F9（在 Excel 2002 中引入）</span><span class="sxs-lookup"><span data-stu-id="60bba-234">Keystroke: CTRL+ALT+SHIFT+F9 (introduced in Excel 2002)</span></span>
  
<span data-ttu-id="60bba-235">VBA：**Workbooks(** reference **).ForceFullCalculation**（在 Excel 2007 中引入）</span><span class="sxs-lookup"><span data-stu-id="60bba-235">VBA: **Workbooks(** reference **).ForceFullCalculation** (introduced in Excel 2007)</span></span> 
  
<span data-ttu-id="60bba-236">C API：不支持</span><span class="sxs-lookup"><span data-stu-id="60bba-236">C API: Not supported</span></span>
  
- <span data-ttu-id="60bba-237">**所有模式**</span><span class="sxs-lookup"><span data-stu-id="60bba-237">**All modes**</span></span>
    
    <span data-ttu-id="60bba-238">使 Excel 重建给定工作簿的依赖关系树和计算链，并强制重新计算包含公式的所有单元格。</span><span class="sxs-lookup"><span data-stu-id="60bba-238">Causes Excel to rebuild the dependency tree and the calculation chain for a given workbook and forces a recalculation of all cells that contain formulas.</span></span>
    
### <a name="all-open-workbooks"></a><span data-ttu-id="60bba-239">所有打开的工作簿</span><span class="sxs-lookup"><span data-stu-id="60bba-239">All Open Workbooks</span></span>

<span data-ttu-id="60bba-240">击键：F9</span><span class="sxs-lookup"><span data-stu-id="60bba-240">Keystroke: F9</span></span>
  
<span data-ttu-id="60bba-241">VBA：**Application.Calculate**</span><span class="sxs-lookup"><span data-stu-id="60bba-241">VBA: **Application.Calculate**</span></span>
  
<span data-ttu-id="60bba-242">C API：**xlcCalculateNow**</span><span class="sxs-lookup"><span data-stu-id="60bba-242">C API: **xlcCalculateNow**</span></span>
  
- <span data-ttu-id="60bba-243">**所有模式**</span><span class="sxs-lookup"><span data-stu-id="60bba-243">**All modes**</span></span>
    
    <span data-ttu-id="60bba-244">重新计算 Excel 已标记为脏的所有单元格（即可变或已更改的数据的从属单元格），以及以编程方式标记为脏的单元格。</span><span class="sxs-lookup"><span data-stu-id="60bba-244">Recalculates all cells that Excel has marked as dirty, that is, dependents of volatile or changed data, and cells programmatically marked as dirty.</span></span> <span data-ttu-id="60bba-245">如果计算模式是“自动(表除外)”，则计算那些需要更新的表以及所有可变函数及其依赖项。</span><span class="sxs-lookup"><span data-stu-id="60bba-245">If the calculation mode is Automatic Except Tables, this calculates those tables that require updating and also all volatile functions and their dependents.</span></span>
    
### <a name="all-open-workbooks-tree-rebuild-and-forced-calculation"></a><span data-ttu-id="60bba-246">所有打开的工作簿树重建和强制计算</span><span class="sxs-lookup"><span data-stu-id="60bba-246">All Open Workbooks Tree Rebuild and Forced Calculation</span></span>

<span data-ttu-id="60bba-247">击键：CTRL+ALT+F9</span><span class="sxs-lookup"><span data-stu-id="60bba-247">Keystroke: CTRL+ALT+F9</span></span>
  
<span data-ttu-id="60bba-248">VBA：**Application.CalculateFull**</span><span class="sxs-lookup"><span data-stu-id="60bba-248">VBA: **Application.CalculateFull**</span></span>
  
<span data-ttu-id="60bba-249">C API：不支持</span><span class="sxs-lookup"><span data-stu-id="60bba-249">C API: Not supported</span></span>
  
- <span data-ttu-id="60bba-250">**所有模式**</span><span class="sxs-lookup"><span data-stu-id="60bba-250">**All modes**</span></span>
    
    <span data-ttu-id="60bba-p124">重新计算所有打开的工作簿中的所有单元格。如果计算模式为除表格外自动，则强制重新计算表。</span><span class="sxs-lookup"><span data-stu-id="60bba-p124">Recalculates all cells in all open workbooks. If the calculation mode is Automatic Except Tables, it forces the tables to be recalculated.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="60bba-253">另请参阅</span><span class="sxs-lookup"><span data-stu-id="60bba-253">See also</span></span>



[<span data-ttu-id="60bba-254">Excel 中的多线程重新计算</span><span class="sxs-lookup"><span data-stu-id="60bba-254">Multithreaded Recalculation in Excel</span></span>](multithreaded-recalculation-in-excel.md)
  
[<span data-ttu-id="60bba-255">Excel 使用的数据类型</span><span class="sxs-lookup"><span data-stu-id="60bba-255">Data Types Used by Excel</span></span>](data-types-used-by-excel.md)
  
[<span data-ttu-id="60bba-256">Excel 中的内存管理</span><span class="sxs-lookup"><span data-stu-id="60bba-256">Memory Management in Excel</span></span>](memory-management-in-excel.md)
  
[<span data-ttu-id="60bba-257">Excel 编程概念</span><span class="sxs-lookup"><span data-stu-id="60bba-257">Excel Programming Concepts</span></span>](excel-programming-concepts.md)

