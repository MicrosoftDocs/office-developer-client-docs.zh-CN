---
title: Excel 命令、函数和状态
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
keywords:
- '[excel 2007] 的状态、 命令 [Excel 2007]、 工作表函数 [Excel 2007]、 宏工作表函数 [Excel 2007]、 Excel 状态'
localization_priority: Normal
ms.assetid: 20f19aa4-f184-47be-bcdd-7ded78778974
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 60977216663fb2492f425a9b7c855b77815f0e7b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773671"
---
# <a name="excel-commands-functions-and-states"></a><span data-ttu-id="2c595-104">Excel 命令、函数和状态</span><span class="sxs-lookup"><span data-stu-id="2c595-104">Excel Commands, Functions, and States</span></span>

 <span data-ttu-id="2c595-105">**适用于** Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="2c595-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="2c595-106">Microsoft Excel 能识别两种非常不同类型的新增功能： 命令和函数。</span><span class="sxs-lookup"><span data-stu-id="2c595-106">Microsoft Excel recognizes two very different types of added functionality: commands and functions.</span></span>
  
## <a name="commands"></a><span data-ttu-id="2c595-107">命令</span><span class="sxs-lookup"><span data-stu-id="2c595-107">Commands</span></span>

<span data-ttu-id="2c595-108">在 Excel 中，命令具有以下特征：</span><span class="sxs-lookup"><span data-stu-id="2c595-108">In Excel, commands have the following characteristics:</span></span>
  
- <span data-ttu-id="2c595-109">他们在用户执行的相同方式执行操作。</span><span class="sxs-lookup"><span data-stu-id="2c595-109">They perform actions in the same way that users do.</span></span>
    
- <span data-ttu-id="2c595-110">它们可以执行任何操作的用户可以执行 (使用的接口的限制到的 subject) 更改 Excel 设置、 打开、 关闭和编辑文档，如启动重新计算，等等。</span><span class="sxs-lookup"><span data-stu-id="2c595-110">They can do anything a user can do (subject to the limits of the interface used), such as altering Excel settings, opening, closing, and editing documents, initiating recalculations, and so on.</span></span>
    
- <span data-ttu-id="2c595-111">他们可以设置某些发生了已捕获的事件发生时调用。</span><span class="sxs-lookup"><span data-stu-id="2c595-111">They can be set up to be called when certain trapped events occur.</span></span>
    
- <span data-ttu-id="2c595-112">他们可以显示对话框，并与用户交互。</span><span class="sxs-lookup"><span data-stu-id="2c595-112">They can display dialog boxes and interact with the user.</span></span>
    
- <span data-ttu-id="2c595-113">它们可以链接来控制对象，以便他们对该对象，例如单击鼠标左键执行某些操作时调用。</span><span class="sxs-lookup"><span data-stu-id="2c595-113">They can be linked to control objects so that they are called when some action is taken on that object, such as left-clicking.</span></span>
    
- <span data-ttu-id="2c595-114">会永远不会调用 Excel 重新计算过程中。</span><span class="sxs-lookup"><span data-stu-id="2c595-114">They are never called by Excel during a recalculation.</span></span>
    
- <span data-ttu-id="2c595-115">他们不能调用函数过程中重新计算。</span><span class="sxs-lookup"><span data-stu-id="2c595-115">They cannot be called by functions during a recalculation.</span></span>
    
## <a name="functions"></a><span data-ttu-id="2c595-116">函数</span><span class="sxs-lookup"><span data-stu-id="2c595-116">Functions</span></span>

<span data-ttu-id="2c595-117">在 Excel 中的功能执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="2c595-117">Functions in Excel do the following:</span></span>
  
- <span data-ttu-id="2c595-118">他们通常采用参数并始终返回结果。</span><span class="sxs-lookup"><span data-stu-id="2c595-118">They usually take arguments and always return a result.</span></span>
    
- <span data-ttu-id="2c595-119">它们可以输入到一个或多个单元格中 Excel 公式的一部分。</span><span class="sxs-lookup"><span data-stu-id="2c595-119">They can be entered into one or more cells as part of an Excel formula.</span></span>
    
- <span data-ttu-id="2c595-120">它们可在定义的名称定义。</span><span class="sxs-lookup"><span data-stu-id="2c595-120">They can be used in defined name definitions.</span></span>
    
- <span data-ttu-id="2c595-121">它们可在条件格式限制和阈值表达式。</span><span class="sxs-lookup"><span data-stu-id="2c595-121">They can be used in conditional formatting limit and threshold expressions.</span></span>
    
- <span data-ttu-id="2c595-122">它们可通过命令调用。</span><span class="sxs-lookup"><span data-stu-id="2c595-122">They can be called by commands.</span></span>
    
- <span data-ttu-id="2c595-123">他们不能调用命令。</span><span class="sxs-lookup"><span data-stu-id="2c595-123">They cannot call commands.</span></span>
    
<span data-ttu-id="2c595-124">Excel 将用户定义的工作表函数和旨在配合使用宏工作表上的用户定义函数进一步区别。</span><span class="sxs-lookup"><span data-stu-id="2c595-124">Excel makes a further distinction between user-defined worksheet functions and user-defined functions that are designed to work on macro sheets.</span></span> <span data-ttu-id="2c595-125">Excel 不会限制仅对宏工作表上使用的用户定义的宏工作表函数： 这些功能可以使用任意位置可正常工作表函数。</span><span class="sxs-lookup"><span data-stu-id="2c595-125">Excel does not limit user-defined macro sheet functions only to being used on macro sheets: these functions can be used anywhere a normal worksheet function can be used.</span></span>
  
### <a name="worksheet-functions"></a><span data-ttu-id="2c595-126">工作表函数</span><span class="sxs-lookup"><span data-stu-id="2c595-126">Worksheet Functions</span></span>

<span data-ttu-id="2c595-127">以下是 true 的 Excel 工作表函数：</span><span class="sxs-lookup"><span data-stu-id="2c595-127">The following is true of Excel worksheet functions:</span></span>
  
- <span data-ttu-id="2c595-128">他们无法访问宏工作表信息函数。</span><span class="sxs-lookup"><span data-stu-id="2c595-128">They cannot access macro sheet information functions.</span></span>
    
- <span data-ttu-id="2c595-129">他们无法获取未计算的单元格的值。</span><span class="sxs-lookup"><span data-stu-id="2c595-129">They cannot obtain the values of uncalculated cells.</span></span>
    
- <span data-ttu-id="2c595-130">他们可以编写并注册为 Excel 2007 中的线程安全启动。</span><span class="sxs-lookup"><span data-stu-id="2c595-130">They can be written and registered as thread-safe starting in Excel 2007.</span></span>
    
### <a name="macro-sheet-functions"></a><span data-ttu-id="2c595-131">宏工作表函数</span><span class="sxs-lookup"><span data-stu-id="2c595-131">Macro-Sheet Functions</span></span>

<span data-ttu-id="2c595-132">以下是 true 的 Excel 宏工作表函数：</span><span class="sxs-lookup"><span data-stu-id="2c595-132">The following is true of Excel macro-sheet functions:</span></span>
  
- <span data-ttu-id="2c595-133">他们可以访问宏工作表信息函数。</span><span class="sxs-lookup"><span data-stu-id="2c595-133">They can access macro sheet information functions.</span></span>
    
- <span data-ttu-id="2c595-134">它们可以获取包括调用单元格的值的未计算单元格的值。</span><span class="sxs-lookup"><span data-stu-id="2c595-134">They can obtain the values of uncalculated cells including the values of the calling cells.</span></span>
    
- <span data-ttu-id="2c595-135">它们不被视为线程安全 Excel 2007 中启动。</span><span class="sxs-lookup"><span data-stu-id="2c595-135">They are not considered thread safe starting in Excel 2007.</span></span>
    
<span data-ttu-id="2c595-136">Excel 如何处理用户定义函数 (UDF)，它还允许函数执行，并重新计算的方式，注册功能时，是所有确定该函数。</span><span class="sxs-lookup"><span data-stu-id="2c595-136">How Excel treats a user-defined function (UDF), what it permits the function to do, and how it recalculates the function are all determined when you register the function.</span></span> <span data-ttu-id="2c595-137">如果函数注册为工作表函数，但试图执行一些只有宏工作表函数可以执行操作，则操作将失败。</span><span class="sxs-lookup"><span data-stu-id="2c595-137">If a function is registered as a worksheet function but tries to do something that only a macro-sheet function can do, the operation fails.</span></span> <span data-ttu-id="2c595-138">从 Excel 2007 中，如果尝试调用宏工作表函数注册为线程安全的工作表函数，同样，则操作将失败。</span><span class="sxs-lookup"><span data-stu-id="2c595-138">Starting in Excel 2007, if a worksheet function registered as thread safe tries to call a macro sheet function, again, the operation fails.</span></span>
  
<span data-ttu-id="2c595-139">Excel 视为 Microsoft Visual Basic for Applications (VBA) Udf 宏工作表的等价函数，他们可以访问工作区信息和未计算的单元格的值，并且它们不会考虑如线程在 Excel 2007 中的安全启动。</span><span class="sxs-lookup"><span data-stu-id="2c595-139">Excel treats Microsoft Visual Basic for Applications (VBA) UDFs as macro sheet-equivalent functions, in that they can access workspace information and the value of uncalculated cells, and they are not considered as thread safe starting in Excel 2007.</span></span>
  
## <a name="excel-states"></a><span data-ttu-id="2c595-140">Excel 状态</span><span class="sxs-lookup"><span data-stu-id="2c595-140">Excel States</span></span>

<span data-ttu-id="2c595-141">Excel 中可以许多状态之一在任何给定时间，具体取决于用户、 外部进程、 发生了已捕获的事件运行宏或如**自动保存**定时的 Excel 内部管理事件的操作。</span><span class="sxs-lookup"><span data-stu-id="2c595-141">Excel can be in one of a number of states at any given time depending on the actions of the user, an external process, a trapped event running a macro, or a timed Excel housekeeping event such as **Autosave**.</span></span>
  
<span data-ttu-id="2c595-142">用户体验的状态如下所示：</span><span class="sxs-lookup"><span data-stu-id="2c595-142">The states that the user experiences are as follows:</span></span>
  
- <span data-ttu-id="2c595-143">**准备状态：** 正在运行任何命令或宏。</span><span class="sxs-lookup"><span data-stu-id="2c595-143">**Ready state:** No commands or macros are being run.</span></span> <span data-ttu-id="2c595-144">要不显示的任何对话框。</span><span class="sxs-lookup"><span data-stu-id="2c595-144">No dialog boxes are being displayed.</span></span> <span data-ttu-id="2c595-145">正在编辑没有单元格，并且用户不剪切/复制和粘贴操作过程。</span><span class="sxs-lookup"><span data-stu-id="2c595-145">No cells are being edited and the user is not in the middle of a cut/copy and paste operation.</span></span> <span data-ttu-id="2c595-146">没有嵌入的对象具有焦点。</span><span class="sxs-lookup"><span data-stu-id="2c595-146">No embedded object has focus.</span></span> 
    
- <span data-ttu-id="2c595-147">**编辑模式：** 用户开始输入的有效字符单元格中键入未锁定或未受保护，或者已对一个或多个未锁定或未受保护的单元格按**F2** 。</span><span class="sxs-lookup"><span data-stu-id="2c595-147">**Edit mode:** The user has started to type valid input characters into an unlocked or unprotected cell, or has pressed **F2** on one or more unlocked or unprotected cells.</span></span> 
    
- <span data-ttu-id="2c595-148">**剪切/复制和粘贴模式：** 用户具有剪切或复制单元格区域和具有不尚未粘贴，或具有粘贴它们使用选择性粘贴对话框，允许多个粘贴操作。</span><span class="sxs-lookup"><span data-stu-id="2c595-148">**Cut/copy and paste mode:** The user has cut or copied a cell or range of cells and has not yet pasted them, or has pasted them using the paste-special dialog box, which enables multiple paste operations.</span></span> 
    
- <span data-ttu-id="2c595-149">**点模式：** 用户正在编辑公式，则选择其地址会添加到正在编辑的公式的单元格。</span><span class="sxs-lookup"><span data-stu-id="2c595-149">**Point mode:** The user is editing a formula and is selecting cells whose addresses are added to the formula being edited.</span></span> 
    
<span data-ttu-id="2c595-150">用户可以通过按**ESC**键，Excel 返回其准备状态清除编辑、 点和剪切/复制模式。</span><span class="sxs-lookup"><span data-stu-id="2c595-150">The user can clear the edit, point, and cut/copy modes by pressing the **ESC** key, which returns Excel to its ready state.</span></span> <span data-ttu-id="2c595-151">其他事件可以清除这些状态，如下所示：</span><span class="sxs-lookup"><span data-stu-id="2c595-151">Other events can clear these states, such as the following:</span></span> 
  
- <span data-ttu-id="2c595-152">用户打开一个内置对话框。</span><span class="sxs-lookup"><span data-stu-id="2c595-152">The user opens a built-in dialog box.</span></span>
    
- <span data-ttu-id="2c595-153">用户启动的重新计算。</span><span class="sxs-lookup"><span data-stu-id="2c595-153">The user initiates a recalculation.</span></span>
    
- <span data-ttu-id="2c595-154">用户运行命令。</span><span class="sxs-lookup"><span data-stu-id="2c595-154">The user runs a command.</span></span>
    
- <span data-ttu-id="2c595-155">Excel 执行**自动保存**操作。</span><span class="sxs-lookup"><span data-stu-id="2c595-155">Excel performs an **Autosave** operation.</span></span> 
    
- <span data-ttu-id="2c595-156">捕获 timer 事件。</span><span class="sxs-lookup"><span data-stu-id="2c595-156">A timer event is trapped.</span></span>
    
<span data-ttu-id="2c595-157">最后一个示例是重要性以外接程序的开发人员。</span><span class="sxs-lookup"><span data-stu-id="2c595-157">The last example is of importance to add-in developers.</span></span> <span data-ttu-id="2c595-158">您应考虑的常用的 timer 事件捕获其中的 Excel 的普通可用性影响被设置和执行。</span><span class="sxs-lookup"><span data-stu-id="2c595-158">You should consider the impact of the normal usability of Excel where frequent timer event traps are being set and executed.</span></span> <span data-ttu-id="2c595-159">这是外接程序的功能的重要组成部分，应将用户提供为挂起，以便他们可以剪切/复制并粘贴通常时需轻松访问方法。</span><span class="sxs-lookup"><span data-stu-id="2c595-159">When this is an important part of your add-in's functionality, you should provide users with an easily accessible way of suspending it, so that they can cut/copy and paste normally when they need to.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2c595-160">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2c595-160">See also</span></span>



[<span data-ttu-id="2c595-161">Excel Programming Concepts</span><span class="sxs-lookup"><span data-stu-id="2c595-161">Excel Programming Concepts</span></span>](excel-programming-concepts.md)
  
[<span data-ttu-id="2c595-162">在长时间的操作中允许用户中断</span><span class="sxs-lookup"><span data-stu-id="2c595-162">Permitting User Breaks in Lengthy Operations</span></span>](permitting-user-breaks-in-lengthy-operations.md)

