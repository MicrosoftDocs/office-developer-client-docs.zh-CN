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
ms.openlocfilehash: 342b4c38b6a48ad36dc6d62ee34900e6f2057d42
ms.sourcegitcommit: 1dd744993ecb4bed241ace874ad26edaef1778b8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/06/2018
ms.locfileid: "25996865"
---
# <a name="setmenuitem-macro-action"></a><span data-ttu-id="09aea-102">SetMenuItem 宏操作</span><span class="sxs-lookup"><span data-stu-id="09aea-102">SetMenuItem macro action</span></span>

<span data-ttu-id="09aea-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="09aea-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="09aea-104">可以使用 **SetMenuItem** 操作设置 **"加载项"** 选项卡上的自定义菜单或全局菜单上的菜单项的状态（已启用或已禁用、已选择或未选择）。</span><span class="sxs-lookup"><span data-stu-id="09aea-104">You can use the **SetMenuItem** action to set the state of menu items (enabled or disabled, selected or unselected) on custom or global menus on the **Add-Ins** tab.</span></span>

> [!NOTE]
> <span data-ttu-id="09aea-105">**SetMenuItem**操作仅适用于使用菜单宏创建的自定义和全局菜单。</span><span class="sxs-lookup"><span data-stu-id="09aea-105">The **SetMenuItem** action works only with custom and global menus created by using menu macros.</span></span> <span data-ttu-id="09aea-106">仅为与早期版本兼容的 Microsoft Access 包含**SetMenuItem**操作。</span><span class="sxs-lookup"><span data-stu-id="09aea-106">The **SetMenuItem** action is included in Microsoft Access only for compatibility with previous versions.</span></span> <span data-ttu-id="09aea-107">不适用于命令栏功能。</span><span class="sxs-lookup"><span data-stu-id="09aea-107">It does not work with the command bar functionality.</span></span> <span data-ttu-id="09aea-108">但是，您可以使用在 Visual Basic for Applications (VBA) 模块禁用或启用并选择或取消选择快捷菜单上的项目中**启用**和**状态**属性或自定义或全局菜单。</span><span class="sxs-lookup"><span data-stu-id="09aea-108">However, you can use the **Enabled** and **State** properties in a Visual Basic for Applications (VBA) module to disable or enable and select or unselect items on shortcut menus or custom or global menus.</span></span>

## <a name="setting"></a><span data-ttu-id="09aea-109">设置</span><span class="sxs-lookup"><span data-stu-id="09aea-109">Setting</span></span>

<span data-ttu-id="09aea-110">**SetMenuItem** 操作具有下列参数。</span><span class="sxs-lookup"><span data-stu-id="09aea-110">The **SetMenuItem** action has the following arguments.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="09aea-111">操作参数</span><span class="sxs-lookup"><span data-stu-id="09aea-111">Action argument</span></span></p></th>
<th><p><span data-ttu-id="09aea-112">说明</span><span class="sxs-lookup"><span data-stu-id="09aea-112">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="09aea-113"><strong>菜单索引</strong></span><span class="sxs-lookup"><span data-stu-id="09aea-113"><strong>Menu Index</strong></span></span></p></td>
<td><p><span data-ttu-id="09aea-114">包含您要为其设置的状态的命令的菜单的索引。</span><span class="sxs-lookup"><span data-stu-id="09aea-114">The index of the menu that contains the command for which you want to set the state.</span></span> <span data-ttu-id="09aea-115">输入从 0，需菜单自定义或全局菜单中的索引的整数值。</span><span class="sxs-lookup"><span data-stu-id="09aea-115">Enter an integer value, starting from 0, for the index of the desired menu in the custom or global menu.</span></span> <span data-ttu-id="09aea-116">在宏生成器窗格的<strong>操作参数</strong>部分的<strong>菜单索引</strong>框中输入的索引值。</span><span class="sxs-lookup"><span data-stu-id="09aea-116">Enter the index value in the <strong>Menu Index</strong> box in the <strong>Action Arguments</strong> section of the Macro Builder pane.</span></span> <span data-ttu-id="09aea-117">索引是相对于菜单宏自定义或全局菜单 （此菜单<strong>AddMenu</strong>操作在菜单宏，从 0 开始计数的位置） 中的菜单上的位置。</span><span class="sxs-lookup"><span data-stu-id="09aea-117">The index is relative to the menu's position in the menu macro for the custom or global menu (the position of this menu's <strong>AddMenu</strong> action in the menu macro, counting from 0).</span></span> <span data-ttu-id="09aea-118">菜单的显示可能有所不同，因为您可以在菜单宏中使用条件表达式，隐藏或显示自定义菜单项。</span><span class="sxs-lookup"><span data-stu-id="09aea-118">The menu's display may be somewhat different, because you can use conditional expressions in the menu macro to hide or display custom menu items.</span></span> <span data-ttu-id="09aea-119">这是必需参数。</span><span class="sxs-lookup"><span data-stu-id="09aea-119">This is a required argument.</span></span> <span data-ttu-id="09aea-120">如果您选择菜单与此参数，并将<strong>命令索引</strong>和<strong>子命令索引</strong>参数留空，您可以启用或禁用菜单名称本身。</span><span class="sxs-lookup"><span data-stu-id="09aea-120">If you select a menu with this argument and leave the <strong>Command Index</strong> and <strong>Subcommand Index</strong> arguments blank, you can enable or disable the menu name itself.</span></span> <span data-ttu-id="09aea-121">但是，不能选择或取消选择菜单名称 （访问忽略菜单名为<strong>标志</strong>参数<strong>检查</strong>和<strong>取消选中</strong>设置）。</span><span class="sxs-lookup"><span data-stu-id="09aea-121">You cannot, however, select or unselect a menu name (Access ignores the <strong>Check</strong> and <strong>Uncheck</strong> settings for the <strong>Flag</strong> argument for menu names).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09aea-122"><strong>命令索引</strong></span><span class="sxs-lookup"><span data-stu-id="09aea-122"><strong>Command Index</strong></span></span></p></td>
<td><p><span data-ttu-id="09aea-123">您要为其设置的状态命令的索引。</span><span class="sxs-lookup"><span data-stu-id="09aea-123">The index of the command for which you want to set the state.</span></span> <span data-ttu-id="09aea-124">输入所需的命令通过<strong>菜单索引</strong>参数选定的菜单中的索引为 0，启动一个整数值。</span><span class="sxs-lookup"><span data-stu-id="09aea-124">Enter an integer value, starting from 0, for the index of the desired command in the menu selected by the <strong>Menu Index</strong> argument.</span></span> <span data-ttu-id="09aea-125">索引是宏的相对于定义自定义或全局菜单 （宏组中，从 0 开始计数中该命令的位置） 的所选的菜单宏组中的命令的位置。</span><span class="sxs-lookup"><span data-stu-id="09aea-125">The index is relative to the command's position in the macro group that defines the selected menu for the custom or global menu (the position of this command's macro in the macro group, counting from 0).</span></span> <span data-ttu-id="09aea-126">菜单的显示可能有所不同，因为您可以在菜单的宏组中使用条件表达式可隐藏或显示自定义菜单命令。</span><span class="sxs-lookup"><span data-stu-id="09aea-126">The menu's display may be somewhat different, because you can use conditional expressions in the menu's macro group to hide or display custom menu commands.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="09aea-127"><strong>子命令索引</strong></span><span class="sxs-lookup"><span data-stu-id="09aea-127"><strong>Subcommand Index</strong></span></span></p></td>
<td><p><span data-ttu-id="09aea-128">您要为其设置的状态的子命令索引。</span><span class="sxs-lookup"><span data-stu-id="09aea-128">The index of the subcommand for which you want to set the state.</span></span> <span data-ttu-id="09aea-129">这仅适用于所需的命令具有子菜单。</span><span class="sxs-lookup"><span data-stu-id="09aea-129">This applies only if the desired command has a submenu.</span></span> <span data-ttu-id="09aea-130">输入所需子<strong>命令索引</strong>参数选择子菜单中的索引为 0，启动一个整数值。</span><span class="sxs-lookup"><span data-stu-id="09aea-130">Enter an integer value, starting from 0, for the index of the desired subcommand in the submenu selected by the <strong>Command Index</strong> argument.</span></span> <span data-ttu-id="09aea-131">索引是宏的相对于定义自定义或全局菜单 （从 0 开始计数的宏组中的此子命令位置） 所选子菜单宏组中的子命令的位置。</span><span class="sxs-lookup"><span data-stu-id="09aea-131">The index is relative to the subcommand's position in the macro group that defines the selected submenu for the custom or global menu (the position of this subcommand's macro in the macro group, counting from 0).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09aea-132"><strong>Flag</strong></span><span class="sxs-lookup"><span data-stu-id="09aea-132"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="09aea-p105">要将命令或子命令设置成的状态。请单击<strong>“变灰”</strong>（禁用命令 - 命令显示为灰色）、<strong>“变实”</strong>（启用该命令）、<strong>“选取”</strong>（在命令旁放置一个选中标记 - 通常指示已选中该命令或已切换到该命令）或<strong>“不选取”</strong>（删除选中标记）。默认值为<strong>“变实”</strong>。</span><span class="sxs-lookup"><span data-stu-id="09aea-p105">The state you want to set the command or subcommand to. Click <strong>Gray</strong> (to disable the command — it appears dimmed), <strong>Ungray</strong> (to enable it), <strong>Check</strong> (to place a check by the command — typically indicating it has been selected or toggled), or <strong>Uncheck</strong> (to remove the check). The default is <strong>Ungray</strong>.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="09aea-136">说明</span><span class="sxs-lookup"><span data-stu-id="09aea-136">Remarks</span></span>

<span data-ttu-id="09aea-p106">**SetMenuItem** 操作仅适用于自定义菜单或全局菜单。如果活动窗口没有自定义菜单或全局菜单，则运行包含 **SetMenuItem** 操作的宏会导致运行时错误。</span><span class="sxs-lookup"><span data-stu-id="09aea-p106">The **SetMenuItem** action works only on a custom or global menu. If the active window does not have a custom or global menu, running a macro containing the **SetMenuItem** action causes a run-time error.</span></span>

<span data-ttu-id="09aea-139">可以使用此操作设置菜单命令和子命令的状态，但不能设置子命令的子命令的状态。</span><span class="sxs-lookup"><span data-stu-id="09aea-139">You can use this action to set the state of menu commands and subcommands, but not subcommands of subcommands.</span></span>

<span data-ttu-id="09aea-140">要在 Visual Basic for Applications (VBA) 模块中运行 **SetMenuItem** 操作，请使用 **DoCmd** 对象的 **SetMenuItem** 方法。</span><span class="sxs-lookup"><span data-stu-id="09aea-140">To run the **SetMenuItem** action in a Visual Basic for Applications (VBA) module, use the **SetMenuItem** method of the **DoCmd** object.</span></span>

