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
# <a name="accessing-xll-code-in-excel"></a><span data-ttu-id="c86f6-104">在 Excel 中访问 XLL 代码</span><span class="sxs-lookup"><span data-stu-id="c86f6-104">Accessing XLL code in Excel</span></span>

<span data-ttu-id="c86f6-105">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="c86f6-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="c86f6-106">要在 Microsoft Excel 中可供访问，XLL 包含的函数和命令需满足以下条件：</span><span class="sxs-lookup"><span data-stu-id="c86f6-106">To be accessible in Microsoft Excel, the functions and commands that an XLL contains:</span></span>
  
- <span data-ttu-id="c86f6-107">必须通过 XLL 导出。</span><span class="sxs-lookup"><span data-stu-id="c86f6-107">Must be exported by the XLL.</span></span>
    
- <span data-ttu-id="c86f6-108">必须使用 Excel 进行注册。</span><span class="sxs-lookup"><span data-stu-id="c86f6-108">Must be registered with Excel.</span></span>
    
## <a name="registering-functions-and-commands-with-excel"></a><span data-ttu-id="c86f6-109">使用 Excel 注册函数和命令</span><span class="sxs-lookup"><span data-stu-id="c86f6-109">Registering functions and commands with Excel</span></span>

<span data-ttu-id="c86f6-110">注册会指示 Excel 以下关于 DLL 入口点的信息：</span><span class="sxs-lookup"><span data-stu-id="c86f6-110">Registration tells Excel the following about a DLL entry point:</span></span>
  
- <span data-ttu-id="c86f6-111">它是否隐藏，或者如果是函数，是否在“函数向导”中可见。</span><span class="sxs-lookup"><span data-stu-id="c86f6-111">Whether it is hidden or, if a function, whether it is visible in the Function Wizard.</span></span>
    
- <span data-ttu-id="c86f6-112">是只能从 XLM 宏表调用它，还是同样可以从工作表调用。</span><span class="sxs-lookup"><span data-stu-id="c86f6-112">Whether it is callable only from an XLM macro sheet, or also from a worksheet.</span></span>
    
- <span data-ttu-id="c86f6-113">如果是命令，那么它是工作表函数还是宏表等效函数。</span><span class="sxs-lookup"><span data-stu-id="c86f6-113">If a command, whether it is a worksheet function or a macro sheet equivalent function.</span></span>
    
- <span data-ttu-id="c86f6-114">它的 XLL/DLL 导出名是什么，以及你希望 Excel 使用什么名称。</span><span class="sxs-lookup"><span data-stu-id="c86f6-114">What its XLL/DLL export name is, and what name you want Excel to use.</span></span>
    
- <span data-ttu-id="c86f6-115">如果它是一个函数：</span><span class="sxs-lookup"><span data-stu-id="c86f6-115">If it is a function:</span></span>
    
  - <span data-ttu-id="c86f6-116">它返回并将其作为参数的数据类型。</span><span class="sxs-lookup"><span data-stu-id="c86f6-116">What data types it returns and takes as arguments.</span></span>
    
  - <span data-ttu-id="c86f6-117">它是否通过修改相应的参数返回结果。</span><span class="sxs-lookup"><span data-stu-id="c86f6-117">Whether it returns its result by modifying an argument in place.</span></span>
    
  - <span data-ttu-id="c86f6-118">它是否易变。</span><span class="sxs-lookup"><span data-stu-id="c86f6-118">Whether it is volatile.</span></span>
    
  - <span data-ttu-id="c86f6-119">它是否为线程安全函数（在 Excel 2007 中开始受支持）。</span><span class="sxs-lookup"><span data-stu-id="c86f6-119">Whether it is thread safe (supported starting in Excel 2007).</span></span>
    
  - <span data-ttu-id="c86f6-120">“粘贴函数向导”和“自动完成”编辑器应显示什么文本来帮助调用函数。</span><span class="sxs-lookup"><span data-stu-id="c86f6-120">What text the Paste Function Wizard and AutoComplete editor should display to help with calling the function.</span></span>
    
  - <span data-ttu-id="c86f6-121">它应列在哪个函数类别下。</span><span class="sxs-lookup"><span data-stu-id="c86f6-121">Which function category it should be listed under.</span></span>
    
<span data-ttu-id="c86f6-122">可通过使用 C API 函数 [xlfRegister](xlfregister-form-1.md)（相当于 XLM 函数 **REGISTER**）来实现。</span><span class="sxs-lookup"><span data-stu-id="c86f6-122">This is all achieved using the C API function [xlfRegister](xlfregister-form-1.md), equivalent to the XLM function **REGISTER**.</span></span>
  
## <a name="calling-xll-functions-directly-from-excel"></a><span data-ttu-id="c86f6-123">直接从 Excel 调用 XLL 函数</span><span class="sxs-lookup"><span data-stu-id="c86f6-123">Calling XLL functions directly from Excel</span></span>

<span data-ttu-id="c86f6-124">注册后，可以从调用内置函数的任何位置调用 XLL 工作表和宏表函数：</span><span class="sxs-lookup"><span data-stu-id="c86f6-124">Once they are registered, XLL worksheet and macro sheet functions can be called from anywhere a built-in function can be called from:</span></span>
  
- <span data-ttu-id="c86f6-125">工作表上的单个单元格或数组公式。</span><span class="sxs-lookup"><span data-stu-id="c86f6-125">A single-cell or array formula on a worksheet.</span></span>
    
- <span data-ttu-id="c86f6-126">宏表上的单个单元格或数组公式。</span><span class="sxs-lookup"><span data-stu-id="c86f6-126">A single-cell or array formula on a macro sheet.</span></span>
    
- <span data-ttu-id="c86f6-127">已定义名称的定义。</span><span class="sxs-lookup"><span data-stu-id="c86f6-127">The definition of a defined name.</span></span>
    
- <span data-ttu-id="c86f6-128">条件格式对话框中的条件和限制字段。</span><span class="sxs-lookup"><span data-stu-id="c86f6-128">The condition and limit fields in a conditional format dialog box.</span></span>
    
- <span data-ttu-id="c86f6-129">在另一个加载项中通过 C API 函数 [xlUDF](xludf.md) 实现。</span><span class="sxs-lookup"><span data-stu-id="c86f6-129">From another add-in via the C API function [xlUDF](xludf.md).</span></span>
    
- <span data-ttu-id="c86f6-130">在 Visual Basic for Applications (VBA) 中通过 **Application.Run** 方法实现。</span><span class="sxs-lookup"><span data-stu-id="c86f6-130">From Visual Basic for Applications (VBA) via the **Application.Run** method.</span></span> 
    
<span data-ttu-id="c86f6-131">可以使用 C API 函数 **xlfCaller** 获取对函数中的调用单元格或单元格区域的引用。</span><span class="sxs-lookup"><span data-stu-id="c86f6-131">You can obtain a reference to the calling cell or range of cells within your function using the C API function **xlfCaller**.</span></span> <span data-ttu-id="c86f6-132">如果从单元格的条件格式表达式调用该函数，则仍然会返回对一个或多个相关单元格的引用，因此不能假定单元格的公式包含 XLL 函数。</span><span class="sxs-lookup"><span data-stu-id="c86f6-132">If the function was called from the cell's conditional format expression, you are still returned a reference to the associated cell or cells, so you cannot assume that the cell's formula contains the XLL function.</span></span> <span data-ttu-id="c86f6-133">如果函数是从 VBA 用户定义函数 (UDF) 调用的，**xlfCaller** 将再次返回调用了 VBA 函数的单元格的地址。</span><span class="sxs-lookup"><span data-stu-id="c86f6-133">If your function was called from a VBA user-defined function (UDF), **xlfCaller** again returns the address of the cells that called the VBA function.</span></span> <span data-ttu-id="c86f6-134">有关详细信息，请参阅 [xlfCaller](xlfcaller.md)。</span><span class="sxs-lookup"><span data-stu-id="c86f6-134">For more information, see [](xlfcaller.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="c86f6-135">Excel 还从“粘贴函数向导”\*\*\*\* 和“替换”\*\*\*\* 对话框中调用 XLL 函数代码。</span><span class="sxs-lookup"><span data-stu-id="c86f6-135">Excel also calls XLL function code from the **Paste Function Wizard** and **Replace** dialog boxes.</span></span> <span data-ttu-id="c86f6-136">在“粘贴函数参数”\*\*\*\* 对话框中，可能需要限制代码的正常运行，特别是在函数执行时间很长的情况下。</span><span class="sxs-lookup"><span data-stu-id="c86f6-136">You might need to restrict your code's normal running in the case of the **Paste Function Arguments** dialog box, especially where your function can take a long time to execute.</span></span> <span data-ttu-id="c86f6-137">要检测是否从这些对话框中调用函数，必须在项目中实现一些代码，这些代码遍历所有打开的窗口，确定前窗口是否是这些对话框之一，如果是，则确定是哪个对话框。</span><span class="sxs-lookup"><span data-stu-id="c86f6-137">To detect if your function is being called from either of these dialog boxes, you must implement some code in your project that iterates through all the open windows to determine if the front window is one of these dialog boxes, and, if so, which one.</span></span> 
  
## <a name="calling-xll-commands-directly-from-excel"></a><span data-ttu-id="c86f6-138">直接从 Excel 调用 XLL 命令</span><span class="sxs-lookup"><span data-stu-id="c86f6-138">Calling XLL commands directly from Excel</span></span>

<span data-ttu-id="c86f6-139">注册后，就可以像调用其他用户定义的宏一样调用 XLL 命令了，具体方法如下：</span><span class="sxs-lookup"><span data-stu-id="c86f6-139">Once they are registered, XLL commands can be called in all the ways that other user-defined macros can be called:</span></span>
  
- <span data-ttu-id="c86f6-140">通过与嵌入工作表中的控件对象相关联。</span><span class="sxs-lookup"><span data-stu-id="c86f6-140">By being associated with a control object embedded on a worksheet.</span></span>
    
- <span data-ttu-id="c86f6-141">从“运行宏”对话框执行操作。</span><span class="sxs-lookup"><span data-stu-id="c86f6-141">From the Run Macro dialog box.</span></span>
    
- <span data-ttu-id="c86f6-142">通过使用 **Application.Run** 方法的 VBA 用户定义的宏。</span><span class="sxs-lookup"><span data-stu-id="c86f6-142">From a VBA user-defined macro using the **Application.Run** method.</span></span> 
    
- <span data-ttu-id="c86f6-143">从自定义菜单项或工具栏执行操作。</span><span class="sxs-lookup"><span data-stu-id="c86f6-143">From a customized menu item or toolbar.</span></span>
    
- <span data-ttu-id="c86f6-144">使用注册命令时设置的快捷键。</span><span class="sxs-lookup"><span data-stu-id="c86f6-144">Using a shortcut keystroke set up when registering the command.</span></span>
    
- <span data-ttu-id="c86f6-145">作为捕获指定事件时要运行的命令。</span><span class="sxs-lookup"><span data-stu-id="c86f6-145">As the command to be run when a specified event is trapped.</span></span>
    
> [!NOTE]
> <span data-ttu-id="c86f6-146">XLL 命令处于隐藏状态，它们不会出现在 Excel 对话框的可用宏列表中。</span><span class="sxs-lookup"><span data-stu-id="c86f6-146">XLL commands are hidden in that they do not appear on the list of available macros in Excel dialog boxes.</span></span> <span data-ttu-id="c86f6-147">但是可以手动将它们输入到宏名称字段中。</span><span class="sxs-lookup"><span data-stu-id="c86f6-147">But they can be entered manually into the macro name field.</span></span> <span data-ttu-id="c86f6-148">Excel 希望这些对话框中显示像是注册过的名称，而不是 DLL 导出名称。</span><span class="sxs-lookup"><span data-stu-id="c86f6-148">Excel expects the registered-as name in these dialog boxes, not the DLL export name.</span></span> 
  
<span data-ttu-id="c86f6-149">Excel 假定使用 Excel 注册的所有 XLL 命令采用以下形式：</span><span class="sxs-lookup"><span data-stu-id="c86f6-149">All XLL commands registered with Excel are assumed by Excel to be of the following form:</span></span>
  
```cs
short WINAPI xll_cmd_name(void)
{
// Function code...
    return 1;
}

```

<span data-ttu-id="c86f6-150">Excel 将忽略返回值，除非是通过 XLM 宏工作表调用该值，在此情况下，返回值将转换为 **TRUE** 或 **FALSE**。</span><span class="sxs-lookup"><span data-stu-id="c86f6-150">Excel ignores the return value unless it is called from an XLM macro sheet, in which case the return value is converted to **TRUE** or **FALSE**.</span></span> <span data-ttu-id="c86f6-151">因此，如果命令执行成功，应返回 1，如果失败或者被用户取消，则返回 0。</span><span class="sxs-lookup"><span data-stu-id="c86f6-151">You should therefore return 1 if your command executed successfully, and 0 if it failed or was canceled by the user.</span></span>
  
<span data-ttu-id="c86f6-152">可以获取有关如何使用 C API函数 **xlfCaller** 调用命令的信息。</span><span class="sxs-lookup"><span data-stu-id="c86f6-152">You can obtain information about how your command was invoked using the C API function **xlfCaller**.</span></span> <span data-ttu-id="c86f6-153">有关详细信息，请参阅 [xlfCaller](xlfcaller.md)。</span><span class="sxs-lookup"><span data-stu-id="c86f6-153">For more information, see [](xlfcaller.md).</span></span>
  
<span data-ttu-id="c86f6-154">从 Excel 2007 开始，用户界面与早期版本不不相同。</span><span class="sxs-lookup"><span data-stu-id="c86f6-154">Starting in Excel 2007 user interface is very different from earlier versions.</span></span> <span data-ttu-id="c86f6-155">大多数情况下仍然支持允许添加和删除自定义菜单栏、菜单、子菜单、菜单项、自定义工具栏和工具栏按钮的 C API 函数。</span><span class="sxs-lookup"><span data-stu-id="c86f6-155">The C API functions that permit the addition and deletion of custom menu bars, menus, submenus, menu items, custom toolbars and toolbar buttons are still supported in most cases.</span></span> <span data-ttu-id="c86f6-156">但是，它们可能并不总是以用户熟悉的方式提供添加的项。</span><span class="sxs-lookup"><span data-stu-id="c86f6-156">However, they may not always make the added item available in a way that your users are familiar with.</span></span> <span data-ttu-id="c86f6-157">应仔细检查任何添加的功能是否仍然可访问，或实现特定于版本的自定义项。</span><span class="sxs-lookup"><span data-stu-id="c86f6-157">You should carefully check that any added functionality is still accessible, or implement a version-specific customization.</span></span> <span data-ttu-id="c86f6-158">从 Excel 2007 开始，用户界面最好使用托管代码模块进行自定义，该模块随后可与 XLL 命令紧密结合。</span><span class="sxs-lookup"><span data-stu-id="c86f6-158">Starting in Excel 2007 the user interface is best customized by using a managed code module that can then be tightly coupled to your XLL commands.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c86f6-159">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c86f6-159">See also</span></span>

- [<span data-ttu-id="c86f6-160">创建 XLL</span><span class="sxs-lookup"><span data-stu-id="c86f6-160">Creating XLLs</span></span>](creating-xlls.md)
- [<span data-ttu-id="c86f6-161">从“函数向导”或“替换”对话框调用 XLL 函数</span><span class="sxs-lookup"><span data-stu-id="c86f6-161">Call XLL functions from the Function Wizard or Replace dialog boxes</span></span>](how-to-call-xll-functions-from-the-function-wizard-or-replace-dialog-boxes.md)
- [<span data-ttu-id="c86f6-162">加载项管理器和 XLL 接口函数</span><span class="sxs-lookup"><span data-stu-id="c86f6-162">Add-in Manager and XLL Interface Functions</span></span>](add-in-manager-and-xll-interface-functions.md)
- [<span data-ttu-id="c86f6-163">开发 Excel XLL</span><span class="sxs-lookup"><span data-stu-id="c86f6-163">Developing Excel XLLs</span></span>](developing-excel-xlls.md)



