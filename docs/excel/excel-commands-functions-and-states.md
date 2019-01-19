---
title: Excel 命令、函数和状态
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
keywords:
- 状态 [excel 2007], 命令 [Excel 2007], 工作表函数 [Excel 2007], 宏工作表函数 [Excel 2007], Excel 状态
ms.assetid: 20f19aa4-f184-47be-bcdd-7ded78778974
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
localization_priority: Priority
ms.openlocfilehash: c941ba7445f1f0598bf044b5f177ad576df0137c
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28716234"
---
# <a name="excel-commands-functions-and-states"></a><span data-ttu-id="eba8d-104">Excel 命令、函数和状态</span><span class="sxs-lookup"><span data-stu-id="eba8d-104">Excel Commands, Functions, and States</span></span>

 <span data-ttu-id="eba8d-105">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="eba8d-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="eba8d-106">Microsoft Excel 可识别两种非常不同的新增功能类型：命令和函数。</span><span class="sxs-lookup"><span data-stu-id="eba8d-106">Microsoft Excel recognizes two very different types of added functionality: commands and functions.</span></span>
  
## <a name="commands"></a><span data-ttu-id="eba8d-107">命令</span><span class="sxs-lookup"><span data-stu-id="eba8d-107">Commands</span></span>

<span data-ttu-id="eba8d-108">在 Excel中，命令具有以下特征：</span><span class="sxs-lookup"><span data-stu-id="eba8d-108">In Excel, commands have the following characteristics:</span></span>
  
- <span data-ttu-id="eba8d-109">它们执行操作的方式与用户相同。</span><span class="sxs-lookup"><span data-stu-id="eba8d-109">They perform actions in the same way that users do.</span></span>
    
- <span data-ttu-id="eba8d-110">它们可以完成用户可执行的任何任务（受所使用的接口限制），例如更改 Excel 设置，打开、关闭和编辑文档，启动重新计算等。</span><span class="sxs-lookup"><span data-stu-id="eba8d-110">They can do anything a user can do (subject to the limits of the interface used), such as altering Excel settings, opening, closing, and editing documents, initiating recalculations, and so on.</span></span>
    
- <span data-ttu-id="eba8d-111">可以将它们设置为在发生某些捕获到的事件时对其进行调用。</span><span class="sxs-lookup"><span data-stu-id="eba8d-111">They can be set up to be called when certain trapped events occur.</span></span>
    
- <span data-ttu-id="eba8d-112">它们可显示对话框并与用户交互。</span><span class="sxs-lookup"><span data-stu-id="eba8d-112">They can display dialog boxes and interact with the user.</span></span>
    
- <span data-ttu-id="eba8d-113">可将它们链接以控制对象，以便在该对象上采取某些操作（如左键单击）时对其进行调用。</span><span class="sxs-lookup"><span data-stu-id="eba8d-113">They can be linked to control objects so that they are called when some action is taken on that object, such as left-clicking.</span></span>
    
- <span data-ttu-id="eba8d-114">Excel 在重新计算期间从不调用它们。</span><span class="sxs-lookup"><span data-stu-id="eba8d-114">They are never called by Excel during a recalculation.</span></span>
    
- <span data-ttu-id="eba8d-115">任何函数在重新计算期间都不能调用它们。</span><span class="sxs-lookup"><span data-stu-id="eba8d-115">They cannot be called by functions during a recalculation.</span></span>
    
## <a name="functions"></a><span data-ttu-id="eba8d-116">函数</span><span class="sxs-lookup"><span data-stu-id="eba8d-116">Functions</span></span>

<span data-ttu-id="eba8d-117">Excel 中的函数执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="eba8d-117">Functions in Excel do the following:</span></span>
  
- <span data-ttu-id="eba8d-118">它们通常采用参数并且始终返回一个结果。</span><span class="sxs-lookup"><span data-stu-id="eba8d-118">They usually take arguments and always return a result.</span></span>
    
- <span data-ttu-id="eba8d-119">可以将它们作为 Excel 公式的一部分输入到一个或多个单元格中。</span><span class="sxs-lookup"><span data-stu-id="eba8d-119">They can be entered into one or more cells as part of an Excel formula.</span></span>
    
- <span data-ttu-id="eba8d-120">它们可用于定义的名称定义中。</span><span class="sxs-lookup"><span data-stu-id="eba8d-120">They can be used in defined name definitions.</span></span>
    
- <span data-ttu-id="eba8d-121">它们可用于条件格式限制和阈值表达式中。</span><span class="sxs-lookup"><span data-stu-id="eba8d-121">They can be used in conditional formatting limit and threshold expressions.</span></span>
    
- <span data-ttu-id="eba8d-122">它们不能被命令调用。</span><span class="sxs-lookup"><span data-stu-id="eba8d-122">They can be called by commands.</span></span>
    
- <span data-ttu-id="eba8d-123">它们不能调用命令。</span><span class="sxs-lookup"><span data-stu-id="eba8d-123">They cannot call commands.</span></span>
    
<span data-ttu-id="eba8d-124">Excel 可以进一步分区用户定义的工作表函数和用户定义的用于宏工作表的函数。</span><span class="sxs-lookup"><span data-stu-id="eba8d-124">Excel makes a further distinction between user-defined worksheet functions and user-defined functions that are designed to work on macro sheets.</span></span> <span data-ttu-id="eba8d-125">Excel 并没有将用户定义的宏工作表函数限制为仅可在宏工作表上使用：这些函数可以在正常工作表函数可使用的任何位置使用。</span><span class="sxs-lookup"><span data-stu-id="eba8d-125">Excel does not limit user-defined macro sheet functions only to being used on macro sheets: these functions can be used anywhere a normal worksheet function can be used.</span></span>
  
### <a name="worksheet-functions"></a><span data-ttu-id="eba8d-126">工作表函数</span><span class="sxs-lookup"><span data-stu-id="eba8d-126">Worksheet Functions</span></span>

<span data-ttu-id="eba8d-127">以下适用于 Excel 工作表函数：</span><span class="sxs-lookup"><span data-stu-id="eba8d-127">The following is true of Excel worksheet functions:</span></span>
  
- <span data-ttu-id="eba8d-128">它们无法访问宏工作表信息函数。</span><span class="sxs-lookup"><span data-stu-id="eba8d-128">They cannot access macro sheet information functions.</span></span>
    
- <span data-ttu-id="eba8d-129">它们无法获得未计算单元格的值。</span><span class="sxs-lookup"><span data-stu-id="eba8d-129">They cannot obtain the values of uncalculated cells.</span></span>
    
- <span data-ttu-id="eba8d-130">从 Excel 2007 起，它们可被编写和注册为线程安全对象。</span><span class="sxs-lookup"><span data-stu-id="eba8d-130">They can be written and registered as thread-safe starting in Excel 2007.</span></span>
    
### <a name="macro-sheet-functions"></a><span data-ttu-id="eba8d-131">宏工作表函数</span><span class="sxs-lookup"><span data-stu-id="eba8d-131">Macro-Sheet Functions</span></span>

<span data-ttu-id="eba8d-132">以下适用于 Excel 宏工作表函数：</span><span class="sxs-lookup"><span data-stu-id="eba8d-132">The following is true of Excel macro-sheet functions:</span></span>
  
- <span data-ttu-id="eba8d-133">它们可以访问宏工作表信息函数。</span><span class="sxs-lookup"><span data-stu-id="eba8d-133">They can access macro sheet information functions.</span></span>
    
- <span data-ttu-id="eba8d-134">它们可以获得未计算单元格的值，包括调用单元格的值。</span><span class="sxs-lookup"><span data-stu-id="eba8d-134">They can obtain the values of uncalculated cells including the values of the calling cells.</span></span>
    
- <span data-ttu-id="eba8d-135">从 Excel 2007 起，它们不能被视为线程安全对象。</span><span class="sxs-lookup"><span data-stu-id="eba8d-135">They are not considered thread safe starting in Excel 2007.</span></span>
    
<span data-ttu-id="eba8d-136">Excel 如何对待用户定义的函数 (UDF)、其允许函数执行的操作以及如何重新计算函数均在注册函数时决定。</span><span class="sxs-lookup"><span data-stu-id="eba8d-136">How Excel treats a user-defined function (UDF), what it permits the function to do, and how it recalculates the function are all determined when you register the function.</span></span> <span data-ttu-id="eba8d-137">如果函数被注册为工作表函数，但却尝试执行只有宏工作表函数才能完成的操作，则操作将会失败。</span><span class="sxs-lookup"><span data-stu-id="eba8d-137">If a function is registered as a worksheet function but tries to do something that only a macro-sheet function can do, the operation fails.</span></span> <span data-ttu-id="eba8d-138">从 Excel 2007 起，如果注册为线程安全对象的工作表函数尝试调用宏工作表函数，则操作也会失败。</span><span class="sxs-lookup"><span data-stu-id="eba8d-138">Starting in Excel 2007, if a worksheet function registered as thread safe tries to call a macro sheet function, again, the operation fails.</span></span>
  
<span data-ttu-id="eba8d-139">Excel 将 Microsoft Visual Basic for Applications (VBA) UDF 处理为宏工作表等效函数，因为它们可以访问工作区信息和未计算单元格的值，并且从 Exel 2007 起，它们不能被视为线程安全对象。</span><span class="sxs-lookup"><span data-stu-id="eba8d-139">Excel treats Microsoft Visual Basic for Applications (VBA) UDFs as macro sheet-equivalent functions, in that they can access workspace information and the value of uncalculated cells, and they are not considered as thread safe starting in Excel 2007.</span></span>
  
## <a name="excel-states"></a><span data-ttu-id="eba8d-140">Excel 状态</span><span class="sxs-lookup"><span data-stu-id="eba8d-140">Excel States</span></span>

<span data-ttu-id="eba8d-141">Excel 在任何给定时间处于多种状态之一，具体取决于用户操作、外部进程、捕获到的运行宏的事件或计时 Excel 维护管理事件（如**自动保存**）。</span><span class="sxs-lookup"><span data-stu-id="eba8d-141">Excel can be in one of a number of states at any given time depending on the actions of the user, an external process, a trapped event running a macro, or a timed Excel housekeeping event such as **Autosave**.</span></span>
  
<span data-ttu-id="eba8d-142">用户可遇到的状态如下所示：</span><span class="sxs-lookup"><span data-stu-id="eba8d-142">The states that the user experiences are as follows:</span></span>
  
- <span data-ttu-id="eba8d-143">**就绪状态：** 未开始运行任何命令或宏。</span><span class="sxs-lookup"><span data-stu-id="eba8d-143">**Ready state:** No commands or macros are being run.</span></span> <span data-ttu-id="eba8d-144">不会显示任何对话框。</span><span class="sxs-lookup"><span data-stu-id="eba8d-144">No dialog boxes are being displayed.</span></span> <span data-ttu-id="eba8d-145">不会编辑任何单元格，并且用户未处在剪切/复制与粘贴操作中间。</span><span class="sxs-lookup"><span data-stu-id="eba8d-145">No cells are being edited and the user is not in the middle of a cut/copy and paste operation.</span></span> <span data-ttu-id="eba8d-146">没有嵌入对象具有焦点。</span><span class="sxs-lookup"><span data-stu-id="eba8d-146">No embedded object has focus.</span></span> 
    
- <span data-ttu-id="eba8d-147">**编辑模式：** 用户已开始将有效的输入字符键入到已解锁或未保护的单元格，或者在一个或多个已解锁或未保护的单元格上按 **F2**。</span><span class="sxs-lookup"><span data-stu-id="eba8d-147">**Edit mode:** The user has started to type valid input characters into an unlocked or unprotected cell, or has pressed **F2** on one or more unlocked or unprotected cells.</span></span> 
    
- <span data-ttu-id="eba8d-148">**剪切/复制和粘贴模式：** 用户已剪切或复制单元格或单元格区域但尚未粘贴，或者已使用支持多种粘贴操作的粘贴专用对话框进行了粘贴。</span><span class="sxs-lookup"><span data-stu-id="eba8d-148">**Cut/copy and paste mode:** The user has cut or copied a cell or range of cells and has not yet pasted them, or has pasted them using the paste-special dialog box, which enables multiple paste operations.</span></span> 
    
- <span data-ttu-id="eba8d-149">**数据点模式：** 用户将编辑公式，并且将选择地址已添加到所编辑的公式的单元格。</span><span class="sxs-lookup"><span data-stu-id="eba8d-149">**Point mode:** The user is editing a formula and is selecting cells whose addresses are added to the formula being edited.</span></span> 
    
<span data-ttu-id="eba8d-150">用户可以通过按 **ESC** 键清除编辑内容、数据点和剪切/复制模式，这会使 Excel 返回至其就绪状态。</span><span class="sxs-lookup"><span data-stu-id="eba8d-150">The user can clear the edit, point, and cut/copy modes by pressing the **ESC** key, which returns Excel to its ready state.</span></span> <span data-ttu-id="eba8d-151">其他事件可以清除这些状态，例如：</span><span class="sxs-lookup"><span data-stu-id="eba8d-151">Other events can clear these states, such as the following:</span></span> 
  
- <span data-ttu-id="eba8d-152">用户打开内置对话框。</span><span class="sxs-lookup"><span data-stu-id="eba8d-152">The user opens a built-in dialog box.</span></span>
    
- <span data-ttu-id="eba8d-153">用户启动重新计算。</span><span class="sxs-lookup"><span data-stu-id="eba8d-153">The user initiates sharing a Sway.</span></span>
    
- <span data-ttu-id="eba8d-154">用户运行命令。</span><span class="sxs-lookup"><span data-stu-id="eba8d-154">The user runs a command.</span></span>
    
- <span data-ttu-id="eba8d-155">Excel 执行**自动保存**操作。</span><span class="sxs-lookup"><span data-stu-id="eba8d-155">Excel performs an **Autosave** operation.</span></span> 
    
- <span data-ttu-id="eba8d-156">捕获到计时器事件。</span><span class="sxs-lookup"><span data-stu-id="eba8d-156">A timer event is trapped.</span></span>
    
<span data-ttu-id="eba8d-157">最后一个示例对于加载项开发人员来说非常重要。</span><span class="sxs-lookup"><span data-stu-id="eba8d-157">The last example is of importance to add-in developers.</span></span> <span data-ttu-id="eba8d-158">在设置和执行频繁计时器事件捕获时，应考虑正常使用 Excel 的影响。</span><span class="sxs-lookup"><span data-stu-id="eba8d-158">You should consider the impact of the normal usability of Excel where frequent timer event traps are being set and executed.</span></span> <span data-ttu-id="eba8d-159">如果这是加载项功能的重要组成部分，则应为用户提供一种能够轻松将其暂停的方式，以便它们在需要时能够正常完成剪切/复制和粘贴操作。</span><span class="sxs-lookup"><span data-stu-id="eba8d-159">When this is an important part of your add-in's functionality, you should provide users with an easily accessible way of suspending it, so that they can cut/copy and paste normally when they need to.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="eba8d-160">另请参阅</span><span class="sxs-lookup"><span data-stu-id="eba8d-160">See also</span></span>



[<span data-ttu-id="eba8d-161">Excel 编程概念</span><span class="sxs-lookup"><span data-stu-id="eba8d-161">Excel Programming Concepts</span></span>](excel-programming-concepts.md)
  
[<span data-ttu-id="eba8d-162">允许用户中断冗长操作</span><span class="sxs-lookup"><span data-stu-id="eba8d-162">Permitting user breaks in lengthy operations</span></span>](permitting-user-breaks-in-lengthy-operations.md)

