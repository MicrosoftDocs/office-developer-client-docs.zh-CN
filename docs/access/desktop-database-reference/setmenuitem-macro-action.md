---
title: SetMenuItem 宏操作
TOCTitle: SetMenuItem macro action
ms:assetid: 503b3635-e721-1b99-3249-626e5dccdb8a
ms:mtpsurl: https://msdn.microsoft.com/library/Ff193803(v=office.15)
ms:contentKeyID: 48544789
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm16614
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: fe61a3368813ba3420920909f818beee2029d993
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32308678"
---
# <a name="setmenuitem-macro-action"></a><span data-ttu-id="b8552-102">SetMenuItem 宏操作</span><span class="sxs-lookup"><span data-stu-id="b8552-102">SetMenuItem macro action</span></span>

<span data-ttu-id="b8552-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="b8552-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="b8552-104">可以使用 **SetMenuItem** 操作设置 **"加载项"** 选项卡上的自定义菜单或全局菜单上的菜单项的状态（已启用或已禁用、已选择或未选择）。</span><span class="sxs-lookup"><span data-stu-id="b8552-104">You can use the **SetMenuItem** action to set the state of menu items (enabled or disabled, selected or unselected) on custom or global menus on the **Add-Ins** tab.</span></span>

> [!NOTE]
> <span data-ttu-id="b8552-p101">The **SetMenuItem** action works only with custom and global menus created by using menu macros. The **SetMenuItem** action is included in Microsoft Access only for compatibility with previous versions. It does not work with the command bar functionality. However, you can use the **Enabled** and **State** properties in a Visual Basic for Applications (VBA) module to disable or enable and select or unselect items on shortcut menus or custom or global menus.</span><span class="sxs-lookup"><span data-stu-id="b8552-p101">The **SetMenuItem** action works only with custom and global menus created by using menu macros. The **SetMenuItem** action is included in Microsoft Access only for compatibility with previous versions. It does not work with the command bar functionality. However, you can use the **Enabled** and **State** properties in a Visual Basic for Applications (VBA) module to disable or enable and select or unselect items on shortcut menus or custom or global menus.</span></span>

## <a name="setting"></a><span data-ttu-id="b8552-109">Setting</span><span class="sxs-lookup"><span data-stu-id="b8552-109">Setting</span></span>

<span data-ttu-id="b8552-110">**SetMenuItem** 操作具有下列参数。</span><span class="sxs-lookup"><span data-stu-id="b8552-110">The **SetMenuItem** action has the following arguments.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="b8552-111">操作参数</span><span class="sxs-lookup"><span data-stu-id="b8552-111">Action argument</span></span></p></th>
<th><p><span data-ttu-id="b8552-112">说明</span><span class="sxs-lookup"><span data-stu-id="b8552-112">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b8552-113"><strong>菜单索引</strong></span><span class="sxs-lookup"><span data-stu-id="b8552-113"><strong>Menu Index</strong></span></span></p></td>
<td><p><span data-ttu-id="b8552-114">包含要设置其状态的命令的菜单的索引。</span><span class="sxs-lookup"><span data-stu-id="b8552-114">The index of the menu that contains the command for which you want to set the state.</span></span> <span data-ttu-id="b8552-115">在自定义或全局菜单中，为所需菜单的索引输入 Integer 数据类型的值（从 0 开始）。</span><span class="sxs-lookup"><span data-stu-id="b8552-115">Enter an integer value, starting from 0, for the index of the desired menu in the custom or global menu.</span></span> <span data-ttu-id="b8552-116">请在“宏生成器”窗格<strong>“操作参数”</strong>部分的<strong>“菜单索引”</strong>框中输入索引值。</span><span class="sxs-lookup"><span data-stu-id="b8552-116">Enter the index value in the <strong>Menu Index</strong> box in the <strong>Action Arguments</strong> section of the Macro Builder pane.</span></span> <span data-ttu-id="b8552-117">该索引相对于菜单在自定义菜单或全局菜单的菜单宏中的位置（此菜单的 <strong>AddMenu</strong> 操作在菜单宏中的位置，从 0 开始计数）。</span><span class="sxs-lookup"><span data-stu-id="b8552-117">The index is relative to the menu's position in the menu macro for the custom or global menu (the position of this menu's <strong>AddMenu</strong> action in the menu macro, counting from 0).</span></span> <span data-ttu-id="b8552-118">由于您可以在菜单宏中使用条件表达式来隐藏或显示自定义菜单项，因此菜单的显示可能会稍有不同。</span><span class="sxs-lookup"><span data-stu-id="b8552-118">The menu's display may be somewhat different, because you can use conditional expressions in the menu macro to hide or display custom menu items.</span></span> <span data-ttu-id="b8552-119">这是一个必选参数。</span><span class="sxs-lookup"><span data-stu-id="b8552-119">This is a required argument.</span></span> <span data-ttu-id="b8552-120">如果您选择带有此参数的菜单并将“命令索引”<strong></strong>和“子命令索引”<strong></strong>参数留空，则您可以启用或禁用菜单名称本身。</span><span class="sxs-lookup"><span data-stu-id="b8552-120">If you select a menu with this argument and leave the <strong>Command Index</strong> and <strong>Subcommand Index</strong> arguments blank, you can enable or disable the menu name itself.</span></span> <span data-ttu-id="b8552-121">但您无法选择或取消选择菜单名称（Access 将忽略菜单名称的“标志”<strong></strong>参数的“选取”<strong></strong>和“不选取”<strong></strong>设置）。</span><span class="sxs-lookup"><span data-stu-id="b8552-121">You cannot, however, select or unselect a menu name (Access ignores the <strong>Check</strong> and <strong>Uncheck</strong> settings for the <strong>Flag</strong> argument for menu names).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b8552-122"><strong>命令索引</strong></span><span class="sxs-lookup"><span data-stu-id="b8552-122"><strong>Command Index</strong></span></span></p></td>
<td><p><span data-ttu-id="b8552-p103">要设置其状态的命令的索引。请在通过“菜单索引”<strong></strong>参数选择的菜单中输入所需命令索引的整数值（从 0 开始）。索引相对于命令在为自定义或全局菜单定义选择的菜单的宏组中位置（此命令的宏在宏组中的位置，从 0 开始计数）。由于您可以在菜单的宏组中使用条件表达式来隐藏或显示自定义菜单命令，因此菜单的显示可能会稍有不同。</span><span class="sxs-lookup"><span data-stu-id="b8552-p103">The index of the command for which you want to set the state. Enter an integer value, starting from 0, for the index of the desired command in the menu selected by the <strong>Menu Index</strong> argument. The index is relative to the command's position in the macro group that defines the selected menu for the custom or global menu (the position of this command's macro in the macro group, counting from 0). The menu's display may be somewhat different, because you can use conditional expressions in the menu's macro group to hide or display custom menu commands.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b8552-127"><strong>子命令索引</strong></span><span class="sxs-lookup"><span data-stu-id="b8552-127"><strong>Subcommand Index</strong></span></span></p></td>
<td><p><span data-ttu-id="b8552-p104">要设置其状态的子命令的索引。仅当所需的命令有子菜单时，此参数才适用。在通过“命令索引”<strong></strong>参数选择的子菜单中，输入所需子命令索引的整数值（从 0 开始）。索引相对于子命令在为自定义或全局菜单定义选择的子菜单的宏组中的位置（此子命令的宏在宏组中的位置，从 0 开始计数）。</span><span class="sxs-lookup"><span data-stu-id="b8552-p104">The index of the subcommand for which you want to set the state. This applies only if the desired command has a submenu. Enter an integer value, starting from 0, for the index of the desired subcommand in the submenu selected by the <strong>Command Index</strong> argument. The index is relative to the subcommand's position in the macro group that defines the selected submenu for the custom or global menu (the position of this subcommand's macro in the macro group, counting from 0).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b8552-132"><strong>Flag</strong></span><span class="sxs-lookup"><span data-stu-id="b8552-132"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="b8552-p105">要将命令或子命令设置成的状态。请单击<strong>“变灰”</strong>（禁用命令 - 命令显示为灰色）、<strong>“变实”</strong>（启用该命令）、<strong>“选取”</strong>（在命令旁放置一个选中标记 - 通常指示已选中该命令或已切换到该命令）或<strong>“不选取”</strong>（删除选中标记）。默认值为<strong>“变实”</strong>。</span><span class="sxs-lookup"><span data-stu-id="b8552-p105">The state you want to set the command or subcommand to. Click <strong>Gray</strong> (to disable the command — it appears dimmed), <strong>Ungray</strong> (to enable it), <strong>Check</strong> (to place a check by the command — typically indicating it has been selected or toggled), or <strong>Uncheck</strong> (to remove the check). The default is <strong>Ungray</strong>.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="b8552-136">注解</span><span class="sxs-lookup"><span data-stu-id="b8552-136">Remarks</span></span>

<span data-ttu-id="b8552-p106">**SetMenuItem** 操作仅适用于自定义菜单或全局菜单。如果活动窗口没有自定义菜单或全局菜单，则运行包含 **SetMenuItem** 操作的宏会导致运行时错误。</span><span class="sxs-lookup"><span data-stu-id="b8552-p106">The **SetMenuItem** action works only on a custom or global menu. If the active window does not have a custom or global menu, running a macro containing the **SetMenuItem** action causes a run-time error.</span></span>

<span data-ttu-id="b8552-139">可以使用此操作设置菜单命令和子命令的状态，但不能设置子命令的子命令的状态。</span><span class="sxs-lookup"><span data-stu-id="b8552-139">You can use this action to set the state of menu commands and subcommands, but not subcommands of subcommands.</span></span>

<span data-ttu-id="b8552-140">要在 Visual Basic for Applications (VBA) 模块中运行 **SetMenuItem** 操作，请使用 **DoCmd** 对象的 **SetMenuItem** 方法。</span><span class="sxs-lookup"><span data-stu-id="b8552-140">To run the **SetMenuItem** action in a Visual Basic for Applications (VBA) module, use the **SetMenuItem** method of the **DoCmd** object.</span></span>

