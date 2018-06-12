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
# <a name="accessing-xll-code-in-excel"></a><span data-ttu-id="29dd2-104">在 Excel 中访问 XLL 代码</span><span class="sxs-lookup"><span data-stu-id="29dd2-104">Accessing XLL code in Excel</span></span>

<span data-ttu-id="29dd2-105">**适用于**： Excel 2013 |Office 2013 |Visual Studio</span><span class="sxs-lookup"><span data-stu-id="29dd2-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="29dd2-106">可在 Microsoft Excel、 函数和 XLL 包含的命令：</span><span class="sxs-lookup"><span data-stu-id="29dd2-106">To be accessible in Microsoft Excel, the functions and commands that an XLL contains:</span></span>
  
- <span data-ttu-id="29dd2-107">必须通过 XLL 导出。</span><span class="sxs-lookup"><span data-stu-id="29dd2-107">Must be exported by the XLL.</span></span>
    
- <span data-ttu-id="29dd2-108">必须使用 Excel 注册。</span><span class="sxs-lookup"><span data-stu-id="29dd2-108">Must be registered with Excel.</span></span>
    
## <a name="registering-functions-and-commands-with-excel"></a><span data-ttu-id="29dd2-109">使用 Excel 中注册的函数和命令</span><span class="sxs-lookup"><span data-stu-id="29dd2-109">Registering functions and commands with Excel</span></span>

<span data-ttu-id="29dd2-110">注册告诉 Excel 以下关于 DLL 入口点：</span><span class="sxs-lookup"><span data-stu-id="29dd2-110">Registration tells Excel the following about a DLL entry point:</span></span>
  
- <span data-ttu-id="29dd2-111">它隐藏还是，如果一个函数，它可见在函数向导。</span><span class="sxs-lookup"><span data-stu-id="29dd2-111">Whether it is hidden or, if a function, whether it is visible in the Function Wizard.</span></span>
    
- <span data-ttu-id="29dd2-112">是否为仅从 XLM 宏工作表或还从工作表，可调用。</span><span class="sxs-lookup"><span data-stu-id="29dd2-112">Whether it is callable only from an XLM macro sheet, or also from a worksheet.</span></span>
    
- <span data-ttu-id="29dd2-113">如果一个命令，它工作表函数或宏表等效功能。</span><span class="sxs-lookup"><span data-stu-id="29dd2-113">If a command, whether it is a worksheet function or a macro sheet equivalent function.</span></span>
    
- <span data-ttu-id="29dd2-114">其 XLL 或动态链接库导出名称是什么，并且想要使用的 Excel 什么名称。</span><span class="sxs-lookup"><span data-stu-id="29dd2-114">What its XLL/DLL export name is, and what name you want Excel to use.</span></span>
    
- <span data-ttu-id="29dd2-115">如果它是一个函数：</span><span class="sxs-lookup"><span data-stu-id="29dd2-115">If it is a function:</span></span>
    
  - <span data-ttu-id="29dd2-116">哪些数据类型它返回，并采用作为参数。</span><span class="sxs-lookup"><span data-stu-id="29dd2-116">What data types it returns and takes as arguments.</span></span>
    
  - <span data-ttu-id="29dd2-117">是否通过修改就地参数返回其结果。</span><span class="sxs-lookup"><span data-stu-id="29dd2-117">Whether it returns its result by modifying an argument in place.</span></span>
    
  - <span data-ttu-id="29dd2-118">是否是可变。</span><span class="sxs-lookup"><span data-stu-id="29dd2-118">Whether it is volatile.</span></span>
    
  - <span data-ttu-id="29dd2-119">它是否线程安全 （支持从 Excel 2007）。</span><span class="sxs-lookup"><span data-stu-id="29dd2-119">Whether it is thread safe (supported starting in Excel 2007).</span></span>
    
  - <span data-ttu-id="29dd2-120">应显示哪些文本粘贴函数向导和记忆式键入编辑器以帮助实现调用的函数。</span><span class="sxs-lookup"><span data-stu-id="29dd2-120">What text the Paste Function Wizard and AutoComplete editor should display to help with calling the function.</span></span>
    
  - <span data-ttu-id="29dd2-121">该函数也会列在的类别。</span><span class="sxs-lookup"><span data-stu-id="29dd2-121">Which function category it should be listed under.</span></span>
    
<span data-ttu-id="29dd2-122">这是所有实现使用 C API 函数[xlfRegister](xlfregister-form-1.md)，等价于**注册**XLM 函数。</span><span class="sxs-lookup"><span data-stu-id="29dd2-122">This is all achieved using the C API function [xlfRegister](xlfregister-form-1.md), equivalent to the XLM function **REGISTER**.</span></span>
  
## <a name="calling-xll-functions-directly-from-excel"></a><span data-ttu-id="29dd2-123">直接从 Excel 调用 XLL 函数</span><span class="sxs-lookup"><span data-stu-id="29dd2-123">Calling XLL functions directly from Excel</span></span>

<span data-ttu-id="29dd2-124">它们注册后，可以从任何位置可从调用内置函数调用 XLL 工作表和宏工作表函数：</span><span class="sxs-lookup"><span data-stu-id="29dd2-124">Once they are registered, XLL worksheet and macro sheet functions can be called from anywhere a built-in function can be called from:</span></span>
  
- <span data-ttu-id="29dd2-125">单个单元格或阵列的工作表上的公式。</span><span class="sxs-lookup"><span data-stu-id="29dd2-125">A single-cell or array formula on a worksheet.</span></span>
    
- <span data-ttu-id="29dd2-126">单个单元格或阵列的宏工作表上的公式。</span><span class="sxs-lookup"><span data-stu-id="29dd2-126">A single-cell or array formula on a macro sheet.</span></span>
    
- <span data-ttu-id="29dd2-127">定义名称的定义。</span><span class="sxs-lookup"><span data-stu-id="29dd2-127">The definition of a defined name.</span></span>
    
- <span data-ttu-id="29dd2-128">一个条件格式对话框中的条件和限制字段。</span><span class="sxs-lookup"><span data-stu-id="29dd2-128">The condition and limit fields in a conditional format dialog box.</span></span>
    
- <span data-ttu-id="29dd2-129">从另一个加载项通过 C API 函数[xlUDF](xludf.md)。</span><span class="sxs-lookup"><span data-stu-id="29dd2-129">From another add-in via the C API function [xlUDF](xludf.md).</span></span>
    
- <span data-ttu-id="29dd2-130">从 Visual Basic for Applications (VBA) 通过**Application.Run**方法。</span><span class="sxs-lookup"><span data-stu-id="29dd2-130">From Visual Basic for Applications (VBA) via the **Application.Run** method.</span></span> 
    
<span data-ttu-id="29dd2-131">使用 C API 函数**xlfCaller**您函数中，可以获取对调用单元格或单元格区域的引用。</span><span class="sxs-lookup"><span data-stu-id="29dd2-131">You can obtain a reference to the calling cell or range of cells within your function using the C API function **xlfCaller**.</span></span> <span data-ttu-id="29dd2-132">如果单元格的条件格式表达式中调用该函数，则仍会返回对关联的单元格的单元格的引用，因此您无法假定单元格的公式包含 XLL 函数。</span><span class="sxs-lookup"><span data-stu-id="29dd2-132">If the function was called from the cell's conditional format expression, you are still returned a reference to the associated cell or cells, so you cannot assume that the cell's formula contains the XLL function.</span></span> <span data-ttu-id="29dd2-133">如果您的函数调用从 VBA 用户定义函数 (UDF)， **xlfCaller**再次返回调用 VBA 函数的单元格的地址。</span><span class="sxs-lookup"><span data-stu-id="29dd2-133">If your function was called from a VBA user-defined function (UDF), **xlfCaller** again returns the address of the cells that called the VBA function.</span></span> <span data-ttu-id="29dd2-134">有关详细信息，请参阅[xlfCaller](xlfcaller.md)。</span><span class="sxs-lookup"><span data-stu-id="29dd2-134">For more information, see [xlfCaller](xlfcaller.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="29dd2-135">Excel**粘贴函数向导**和**替换**对话框还调用 XLL 函数代码。</span><span class="sxs-lookup"><span data-stu-id="29dd2-135">Excel also calls XLL function code from the **Paste Function Wizard** and **Replace** dialog boxes.</span></span> <span data-ttu-id="29dd2-136">您可能需要限制您的代码正常运行的**粘贴函数参数**对话框中，尤其是其中函数可以需要很长时间，以执行情况。</span><span class="sxs-lookup"><span data-stu-id="29dd2-136">You might need to restrict your code's normal running in the case of the **Paste Function Arguments** dialog box, especially where your function can take a long time to execute.</span></span> <span data-ttu-id="29dd2-137">若要检测如果从这些对话框任一调用您函数时，您必须循环访问所有打开的窗口以确定是否前端窗口是下列对话框之一，如果是这样，您项目中实现一些代码哪一个。</span><span class="sxs-lookup"><span data-stu-id="29dd2-137">To detect if your function is being called from either of these dialog boxes, you must implement some code in your project that iterates through all the open windows to determine if the front window is one of these dialog boxes, and, if so, which one.</span></span> 
  
## <a name="calling-xll-commands-directly-from-excel"></a><span data-ttu-id="29dd2-138">直接从 Excel 调用 XLL 命令</span><span class="sxs-lookup"><span data-stu-id="29dd2-138">Calling XLL commands directly from Excel</span></span>

<span data-ttu-id="29dd2-139">它们注册后，可在所有其他用户定义的宏，可以调用的方法调用 XLL 命令：</span><span class="sxs-lookup"><span data-stu-id="29dd2-139">Once they are registered, XLL commands can be called in all the ways that other user-defined macros can be called:</span></span>
  
- <span data-ttu-id="29dd2-140">通过与 control 对象相关联嵌入工作表上。</span><span class="sxs-lookup"><span data-stu-id="29dd2-140">By being associated with a control object embedded on a worksheet.</span></span>
    
- <span data-ttu-id="29dd2-141">从运行宏对话框。</span><span class="sxs-lookup"><span data-stu-id="29dd2-141">From the Run Macro dialog box.</span></span>
    
- <span data-ttu-id="29dd2-142">从 VBA 用户定义的宏使用**Application.Run**方法。</span><span class="sxs-lookup"><span data-stu-id="29dd2-142">From a VBA user-defined macro using the **Application.Run** method.</span></span> 
    
- <span data-ttu-id="29dd2-143">从自定义的菜单项或工具栏中。</span><span class="sxs-lookup"><span data-stu-id="29dd2-143">From a customized menu item or toolbar.</span></span>
    
- <span data-ttu-id="29dd2-144">使用快捷方式键击设置，当注册命令。</span><span class="sxs-lookup"><span data-stu-id="29dd2-144">Using a shortcut keystroke set up when registering the command.</span></span>
    
- <span data-ttu-id="29dd2-145">捕获是为指定的事件时运行命令。</span><span class="sxs-lookup"><span data-stu-id="29dd2-145">As the command to be run when a specified event is trapped.</span></span>
    
> [!NOTE]
> <span data-ttu-id="29dd2-146">因为它们不出现在列表中的 Excel 对话框中可用的宏，XLL 命令已被隐藏。</span><span class="sxs-lookup"><span data-stu-id="29dd2-146">XLL commands are hidden in that they do not appear on the list of available macros in Excel dialog boxes.</span></span> <span data-ttu-id="29dd2-147">但是，可以输入到宏名称字段的手动。</span><span class="sxs-lookup"><span data-stu-id="29dd2-147">But they can be entered manually into the macro name field.</span></span> <span data-ttu-id="29dd2-148">Excel 预计这些对话框，而不是 DLL 导出名称中的注册为名称。</span><span class="sxs-lookup"><span data-stu-id="29dd2-148">Excel expects the registered-as name in these dialog boxes, not the DLL export name.</span></span> 
  
<span data-ttu-id="29dd2-149">使用 Excel 中注册的所有 XLL 命令都假定 Excel 的以下形式：</span><span class="sxs-lookup"><span data-stu-id="29dd2-149">All XLL commands registered with Excel are assumed by Excel to be of the following form:</span></span>
  
```cs
short WINAPI xll_cmd_name(void)
{
// Function code...
    return 1;
}

```

<span data-ttu-id="29dd2-150">除非调用从 XLM 宏工作表，在其中案例的返回值转换为**TRUE**或**FALSE**，则 Excel 会忽略返回值。</span><span class="sxs-lookup"><span data-stu-id="29dd2-150">Excel ignores the return value unless it is called from an XLM macro sheet, in which case the return value is converted to **TRUE** or **FALSE**.</span></span> <span data-ttu-id="29dd2-151">如果它失败或已被用户取消，因此应返回 1 如果您的命令执行成功和 0。</span><span class="sxs-lookup"><span data-stu-id="29dd2-151">You should therefore return 1 if your command executed successfully, and 0 if it failed or was canceled by the user.</span></span>
  
<span data-ttu-id="29dd2-152">您可以获得信息有关您的命令的调用方式使用 C API 函数**xlfCaller**。</span><span class="sxs-lookup"><span data-stu-id="29dd2-152">You can obtain information about how your command was invoked using the C API function **xlfCaller**.</span></span> <span data-ttu-id="29dd2-153">有关详细信息，请参阅[xlfCaller](xlfcaller.md)。</span><span class="sxs-lookup"><span data-stu-id="29dd2-153">For more information, see [xlfCaller](xlfcaller.md).</span></span>
  
<span data-ttu-id="29dd2-154">在 Excel 2007 用户界面中启动很大差异从早期版本。</span><span class="sxs-lookup"><span data-stu-id="29dd2-154">Starting in Excel 2007 user interface is very different from earlier versions.</span></span> <span data-ttu-id="29dd2-155">在大多数情况下仍然支持允许添加和删除自定义菜单栏、 菜单、 子菜单、 菜单项、 自定义工具栏和工具栏按钮的 C API 函数。</span><span class="sxs-lookup"><span data-stu-id="29dd2-155">The C API functions that permit the addition and deletion of custom menu bars, menus, submenus, menu items, custom toolbars and toolbar buttons are still supported in most cases.</span></span> <span data-ttu-id="29dd2-156">但是，他们不始终会使所添加的项可用用户熟悉的方式。</span><span class="sxs-lookup"><span data-stu-id="29dd2-156">However, they may not always make the added item available in a way that your users are familiar with.</span></span> <span data-ttu-id="29dd2-157">您应该仔细检查任何新增的功能仍可访问，或实现的特定于版本的自定义项。</span><span class="sxs-lookup"><span data-stu-id="29dd2-157">You should carefully check that any added functionality is still accessible, or implement a version-specific customization.</span></span> <span data-ttu-id="29dd2-158">启动 Excel 2007 中的用户界面使用的托管的代码模块，然后可以 XLL 命令紧密耦合的最佳自定义。</span><span class="sxs-lookup"><span data-stu-id="29dd2-158">Starting in Excel 2007 the user interface is best customized by using a managed code module that can then be tightly coupled to your XLL commands.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="29dd2-159">另请参阅</span><span class="sxs-lookup"><span data-stu-id="29dd2-159">See also</span></span>

- [<span data-ttu-id="29dd2-160">创建 xll （英文）</span><span class="sxs-lookup"><span data-stu-id="29dd2-160">Creating XLLs</span></span>](creating-xlls.md)
- [<span data-ttu-id="29dd2-161">从函数向导或替换对话框呼叫 XLL 函数</span><span class="sxs-lookup"><span data-stu-id="29dd2-161">Call XLL Functions from the Function Wizard or Replace Dialog Boxes</span></span>](how-to-call-xll-functions-from-the-function-wizard-or-replace-dialog-boxes.md)
- [<span data-ttu-id="29dd2-162">加载项管理器和 XLL 接口函数</span><span class="sxs-lookup"><span data-stu-id="29dd2-162">Add-in Manager and XLL Interface Functions</span></span>](add-in-manager-and-xll-interface-functions.md)
- [<span data-ttu-id="29dd2-163">Developing Excel XLLs</span><span class="sxs-lookup"><span data-stu-id="29dd2-163">Developing Excel XLLs</span></span>](developing-excel-xlls.md)



