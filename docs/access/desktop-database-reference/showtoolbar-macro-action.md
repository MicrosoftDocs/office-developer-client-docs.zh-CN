---
title: ShowToolbar 宏操作
TOCTitle: ShowToolbar Macro Action
ms:assetid: 9e53009b-1e5e-1bee-3bcc-f82dc1b0dc48
ms:mtpsurl: https://msdn.microsoft.com/library/Ff198288(v=office.15)
ms:contentKeyID: 48546649
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm27417
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 84eff76b29697df46c7159c442865bd00ce051e0
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25879121"
---
# <a name="showtoolbar-macro-action"></a><span data-ttu-id="892b0-102">ShowToolbar 宏操作</span><span class="sxs-lookup"><span data-stu-id="892b0-102">ShowToolbar Macro Action</span></span>


<span data-ttu-id="892b0-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="892b0-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="892b0-104">可以使用 **ShowToolbar** 操作显示或隐藏 **"加载项"** 选项卡上的一组命令。</span><span class="sxs-lookup"><span data-stu-id="892b0-104">You can use the **ShowToolbar** action to display or hide a group of commands on the **Add-Ins** tab.</span></span>


> [!NOTE]
> <P><span data-ttu-id="892b0-105">[!注释] <STRONG>ShowToolbar</STRONG> 操作不影响快捷菜单。</span><span class="sxs-lookup"><span data-stu-id="892b0-105">The <STRONG>ShowToolbar</STRONG> action does not affect shortcut menus.</span></span></P>




> [!NOTE]
> <P><span data-ttu-id="892b0-p101">[!注释] 如果数据库不受信任，将不允许此操作。有关启用宏的详细信息，请参阅本文 See Also 一节中的链接。</span><span class="sxs-lookup"><span data-stu-id="892b0-p101">This action will not be allowed if the database is not trusted. For more information about enabling macros, see the links in the See Also section of this article.</span></span></P>



## <a name="setting"></a><span data-ttu-id="892b0-108">设置</span><span class="sxs-lookup"><span data-stu-id="892b0-108">Setting</span></span>

<span data-ttu-id="892b0-109">**ShowToolbar** 操作具有下列参数。</span><span class="sxs-lookup"><span data-stu-id="892b0-109">The **ShowToolbar** action has the following arguments.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="892b0-110">操作参数</span><span class="sxs-lookup"><span data-stu-id="892b0-110">Action argument</span></span></p></th>
<th><p><span data-ttu-id="892b0-111">说明</span><span class="sxs-lookup"><span data-stu-id="892b0-111">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="892b0-112"><strong>工具栏名称</strong></span><span class="sxs-lookup"><span data-stu-id="892b0-112"><strong>Toolbar Name</strong></span></span></p></td>
<td><p><span data-ttu-id="892b0-113">您想要显示或隐藏<strong>加载项</strong>选项卡上的命令组的名称。</span><span class="sxs-lookup"><span data-stu-id="892b0-113">The name of the command group on the <strong>Add-Ins</strong> tab you want to display or hide.</span></span> <span data-ttu-id="892b0-114">宏生成器窗格中的<strong>操作参数</strong>部分的<strong>工具栏名称</strong>框显示此操作将影响的所有可用的组。</span><span class="sxs-lookup"><span data-stu-id="892b0-114">The <strong>Toolbar Name</strong> box in the <strong>Action Arguments</strong> section of the Macro Builder Pane shows all the available groups that can be affected by this action.</span></span> <span data-ttu-id="892b0-115">这是必需参数。</span><span class="sxs-lookup"><span data-stu-id="892b0-115">This is a required argument.</span></span> <span data-ttu-id="892b0-116">如果在类库数据库中运行包含 <strong>ShowToolbar</strong> 操作的宏，Access 将先在该类库数据库中查找具有此名称的组，然后再在当前数据库中查找。</span><span class="sxs-lookup"><span data-stu-id="892b0-116">If you run a macro containing the <strong>ShowToolbar</strong> action in a library database, Access first looks for the group with this name in the library database, and then in the current database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="892b0-117"><strong>Show</strong></span><span class="sxs-lookup"><span data-stu-id="892b0-117"><strong>Show</strong></span></span></p></td>
<td><p><span data-ttu-id="892b0-118">指定是否显示还是隐藏组以及在何种视图中显示或隐藏它。</span><span class="sxs-lookup"><span data-stu-id="892b0-118">Specifies whether to display or hide the group and in which views to display or hide it.</span></span> <span data-ttu-id="892b0-119">默认值为<strong>是</strong>（始终显示组）。</span><span class="sxs-lookup"><span data-stu-id="892b0-119">The default is <strong>Yes</strong> (show the group at all times).</span></span> <span data-ttu-id="892b0-120">您可以选择<strong>是</strong>时间，<strong>其中适当</strong>显示组仅时的相应窗体或报表处于活动状态，或<strong>不</strong>隐藏组任何时候都在所有显示组。</span><span class="sxs-lookup"><span data-stu-id="892b0-120">You can select <strong>Yes</strong> to display the group at all times, <strong>Where Appropriate</strong> to display the group only when the appropriate form or report is active, or <strong>No</strong> to hide the group at all times.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="892b0-121">说明</span><span class="sxs-lookup"><span data-stu-id="892b0-121">Remarks</span></span>

<span data-ttu-id="892b0-122">可以在包含条件表达式的宏中使用此操作，以便根据某些条件来显示或隐藏组。</span><span class="sxs-lookup"><span data-stu-id="892b0-122">You can use this action in a macro with conditional expressions to display or hide a group depending on certain conditions.</span></span>

<span data-ttu-id="892b0-123">如果您想要显示在只有一个窗体或报表上的特定组，您可将窗体或报表的**OnActivate**属性设置包含**ShowToolbar**操作显示该组的宏的名称。</span><span class="sxs-lookup"><span data-stu-id="892b0-123">If you want to show a particular group on just one form or report, you can set the **OnActivate** property of the form or report to the name of a macro that contains a **ShowToolbar** action to show the group.</span></span> <span data-ttu-id="892b0-124">包含要隐藏组**ShowToolbar**操作的宏的名称，然后设置窗体或报表的**OnDeactivate**属性。</span><span class="sxs-lookup"><span data-stu-id="892b0-124">Then set the **OnDeactivate** property of the form or report to the name of a macro that contains a **ShowToolbar** action to hide the group.</span></span>

<span data-ttu-id="892b0-125">不可用来显示或隐藏如果**AllowBuiltInToolbars**属性设置为**False** (0) 在 Visual Basic for Applications (VBA) 模块中或将**允许内置工具栏**选项设置为使用此操作的内置工具栏**False**在 VBA 中使用**SetOption**方法。</span><span class="sxs-lookup"><span data-stu-id="892b0-125">The built-in toolbars are not available to display or hide by using this action if you set the **AllowBuiltInToolbars** property to **False** (0) in a Visual Basic for Applications (VBA) module, or if you set the **Allow Built-in Toolbars** option to **False** in VBA by using the **SetOption** method.</span></span>

<span data-ttu-id="892b0-126">要在 VBA 模块中运行 **ShowToolbar** 操作，请使用 **DoCmd** 对象的 **ShowToolbar** 方法。</span><span class="sxs-lookup"><span data-stu-id="892b0-126">To run the **ShowToolbar** action in a VBA module, use the **ShowToolbar** method of the **DoCmd** object.</span></span>

