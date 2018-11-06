---
title: RunMacro 宏操作
TOCTitle: RunMacro macro action
ms:assetid: 25966f20-8160-0821-b88a-ed08b7786fdc
ms:mtpsurl: https://msdn.microsoft.com/library/Ff191868(v=office.15)
ms:contentKeyID: 48543787
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm43195
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 4682af5c4583b99104acf96b9cd0a4f311e6cb90
ms.sourcegitcommit: 1dd744993ecb4bed241ace874ad26edaef1778b8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/06/2018
ms.locfileid: "25997544"
---
# <a name="runmacro-macro-action"></a><span data-ttu-id="7399a-102">RunMacro 宏操作</span><span class="sxs-lookup"><span data-stu-id="7399a-102">RunMacro macro action</span></span>

<span data-ttu-id="7399a-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="7399a-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="7399a-p101">可以使用 **RunMacro** 操作运行宏。宏可以包括在宏组中。</span><span class="sxs-lookup"><span data-stu-id="7399a-p101">You can use the **RunMacro** action to run a macro. The macro can be in a macro group.</span></span>

<span data-ttu-id="7399a-106">可以使用此操作：</span><span class="sxs-lookup"><span data-stu-id="7399a-106">You can use this action:</span></span>

- <span data-ttu-id="7399a-107">从另一个宏内运行某个宏。</span><span class="sxs-lookup"><span data-stu-id="7399a-107">To run a macro from within another macro.</span></span>

- <span data-ttu-id="7399a-108">基于某个条件运行宏。</span><span class="sxs-lookup"><span data-stu-id="7399a-108">To run a macro based on a certain condition.</span></span>

- <span data-ttu-id="7399a-109">将宏附加到自定义菜单命令中。</span><span class="sxs-lookup"><span data-stu-id="7399a-109">To attach a macro to a custom menu command.</span></span>

## <a name="setting"></a><span data-ttu-id="7399a-110">设置</span><span class="sxs-lookup"><span data-stu-id="7399a-110">Setting</span></span>

<span data-ttu-id="7399a-111">**RunMacro** 操作具有下列参数。</span><span class="sxs-lookup"><span data-stu-id="7399a-111">The **RunMacro** action has the following arguments.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="7399a-112">操作参数</span><span class="sxs-lookup"><span data-stu-id="7399a-112">Action argument</span></span></p></th>
<th><p><span data-ttu-id="7399a-113">说明</span><span class="sxs-lookup"><span data-stu-id="7399a-113">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7399a-114"><strong>宏名</strong></span><span class="sxs-lookup"><span data-stu-id="7399a-114"><strong>Macro Name</strong></span></span></p></td>
<td><p><span data-ttu-id="7399a-115">要运行的宏的名称。</span><span class="sxs-lookup"><span data-stu-id="7399a-115">The name of the macro to run.</span></span> <span data-ttu-id="7399a-116">宏生成器窗格的<strong>宏名称</strong>框在<strong>操作参数</strong>部分中显示当前数据库中的所有宏 （和宏组）。</span><span class="sxs-lookup"><span data-stu-id="7399a-116">The <strong>Macro Name</strong> box in the <strong>Action Arguments</strong> section of the Macro Builder pane shows all macros (and macro groups) in the current database.</span></span> <span data-ttu-id="7399a-117">如果宏组中的宏，它是否列出在列表中的宏组名称下为<em>macrogroupname</em>。<em>macroname</em>。</span><span class="sxs-lookup"><span data-stu-id="7399a-117">If the macro is in a macro group, it's listed under the macro group name in the list as <em>macrogroupname</em>.<em>macroname</em>.</span></span> <span data-ttu-id="7399a-118">这是必需参数。</span><span class="sxs-lookup"><span data-stu-id="7399a-118">This is a required argument.</span></span> <span data-ttu-id="7399a-119">如果在类库数据库中运行包含 <strong>RunMacro</strong> 操作的宏，Microsoft Access 将在该类库数据库中查找具有此名称的宏，而不会在当前数据库中查找。</span><span class="sxs-lookup"><span data-stu-id="7399a-119">If you run a macro containing the <strong>RunMacro</strong> action in a library database, Microsoft Access looks for the macro with this name in the library database and doesn't look for it in the current database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7399a-120"><strong>重复次数</strong></span><span class="sxs-lookup"><span data-stu-id="7399a-120"><strong>Repeat Count</strong></span></span></p></td>
<td><p><span data-ttu-id="7399a-121">宏将运行最大次数。</span><span class="sxs-lookup"><span data-stu-id="7399a-121">The maximum number of times the macro will run.</span></span> <span data-ttu-id="7399a-122">如果将此参数留空 （和<strong>重复表达式</strong>参数也是空），宏将运行一次。</span><span class="sxs-lookup"><span data-stu-id="7399a-122">If you leave this argument blank (and the <strong>Repeat Expression</strong> argument is also blank), the macro runs once.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7399a-123"><strong>重复表达式</strong></span><span class="sxs-lookup"><span data-stu-id="7399a-123"><strong>Repeat Expression</strong></span></span></p></td>
<td><p><span data-ttu-id="7399a-p104">计算结果为<strong>“True”</strong>(–1) 或<strong>“False”</strong>(0) 的表达式。如果表达式的计算结果为<strong>“False”</strong>，宏将停止运行。宏每次运行时都会计算该表达式。</span><span class="sxs-lookup"><span data-stu-id="7399a-p104">An expression that evaluates to <strong>True</strong> (–1) or <strong>False</strong> (0). The macro stops running if the expression evaluates to <strong>False</strong>. The expression is evaluated each time the macro runs.</span></span></p></td>
</tr>
</tbody>
</table>

## <a name="remarks"></a><span data-ttu-id="7399a-127">说明</span><span class="sxs-lookup"><span data-stu-id="7399a-127">Remarks</span></span>

<span data-ttu-id="7399a-128">如果您输入宏组名为**宏名称**参数，Access 将运行宏组中的第一个宏。</span><span class="sxs-lookup"><span data-stu-id="7399a-128">If you enter a macro group name for the **Macro Name** argument, Access runs the first macro in the macro group.</span></span>

<span data-ttu-id="7399a-p105">此操作类似于单击 **"数据库工具"** 选项卡上的 **"运行宏"**，选择宏，然后单击 **"确定"**。但是，此命令仅运行一次宏，而 **RunMacro** 操作则可以将宏运行任意次。</span><span class="sxs-lookup"><span data-stu-id="7399a-p105">This action is similar to clicking **Run Macro** on the **Database Tools** tab, selecting a macro, and clicking **OK**. However, this command runs the macro only once, whereas the **RunMacro** action can run a macro as many times as you want.</span></span>

> [!TIP]
> <span data-ttu-id="7399a-131">您可以使用的**重复次数**和**重复表达式**参数确定宏将运行的次数：</span><span class="sxs-lookup"><span data-stu-id="7399a-131">You can use the **Repeat Count** and **Repeat Expression** arguments to determine how many times the macro runs:</span></span>
> - <span data-ttu-id="7399a-132">如果将这两个参数均留空，宏将运行一次。</span><span class="sxs-lookup"><span data-stu-id="7399a-132">If you leave both arguments blank, the macro runs once.</span></span>
> - <span data-ttu-id="7399a-133">如果您的**重复次数**输入号码，但保留**重复表达式**为空，宏将运行指定的次数。</span><span class="sxs-lookup"><span data-stu-id="7399a-133">If you enter a number for **Repeat Count** but leave **Repeat Expression** blank, the macro runs the specified number of times.</span></span>
> - <span data-ttu-id="7399a-134">如果您将**重复次数**保留为空，但为**重复表达式**输入一个表达式，宏将运行，直到该表达式的计算结果为**False**。</span><span class="sxs-lookup"><span data-stu-id="7399a-134">If you leave **Repeat Count** blank but enter an expression for **Repeat Expression**, the macro runs until the expression evaluates to **False**.</span></span>
> - <span data-ttu-id="7399a-135">如果为这两个参数，则宏将运行的次数指定在**重复次数**或直到**重复表达式**计算结果为**False**，输入值前进哪个事件首先发生。</span><span class="sxs-lookup"><span data-stu-id="7399a-135">If you enter values for both arguments, the macro runs the number of times specified in **Repeat Count** or until **Repeat Expression** evaluates to **False**, whichever occurs first.</span></span>

<span data-ttu-id="7399a-p106">在运行包含 **RunMacro** 操作的宏并且该宏执行到 **RunMacro** 操作时，Access 将运行被调用的宏。在被调用的宏运行完后，Access 将继续运行原来的宏并运行下一个操作。</span><span class="sxs-lookup"><span data-stu-id="7399a-p106">When you run a macro containing the **RunMacro** action, and it reaches the **RunMacro** action, Access runs the called macro. When the called macro has finished, Access returns to the original macro and runs the next action.</span></span>

> [!NOTE]
> - <span data-ttu-id="7399a-138">可以调用同一个宏组或者另一个宏组中的宏。</span><span class="sxs-lookup"><span data-stu-id="7399a-138">You can call a macro in the same macro group or in another macro group.</span></span>
> - <span data-ttu-id="7399a-p107">可以嵌套宏。也就是说，您可以运行宏 A，宏 A 继而调用宏 B，依此类推。在每种情况下，当被调用的宏运行完后，Access 将继续运行调用它的宏并运行该宏中的下一个操作。</span><span class="sxs-lookup"><span data-stu-id="7399a-p107">You can nest macros. That is, you can run macro A, which in turn calls macro B, and so on. In each case, when the called macro has finished, Access returns to the macro that called it and runs the next action in that macro.</span></span>

<span data-ttu-id="7399a-142">要在 Visual Basic for Applications (VBA) 模块中运行 **RunMacro** 操作，请使用 **DoCmd** 对象的 **RunMacro** 方法。</span><span class="sxs-lookup"><span data-stu-id="7399a-142">To run the **RunMacro** action in a Visual Basic for Applications (VBA) module, use the **RunMacro** method of the **DoCmd** object.</span></span>

