---
title: ShowToolbar 宏操作
TOCTitle: ShowToolbar macro action
ms:assetid: 9e53009b-1e5e-1bee-3bcc-f82dc1b0dc48
ms:mtpsurl: https://msdn.microsoft.com/library/Ff198288(v=office.15)
ms:contentKeyID: 48546649
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm27417
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: 01ba59ce0898068788adb9269b3203794d1f31d4
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32306473"
---
# <a name="showtoolbar-macro-action"></a><span data-ttu-id="93627-102">ShowToolbar 宏操作</span><span class="sxs-lookup"><span data-stu-id="93627-102">ShowToolbar macro action</span></span>

<span data-ttu-id="93627-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="93627-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="93627-104">可以使用 **ShowToolbar** 操作显示或隐藏 **“加载项”** 选项卡上的一组命令。</span><span class="sxs-lookup"><span data-stu-id="93627-104">You can use the **ShowToolbar** action to display or hide a group of commands on the **Add-Ins** tab.</span></span>

> [!NOTE]
> - <span data-ttu-id="93627-105">[!注释] **ShowToolbar** 操作不影响快捷菜单。</span><span class="sxs-lookup"><span data-stu-id="93627-105">The **ShowToolbar** action does not affect shortcut menus.</span></span>
> - <span data-ttu-id="93627-106">[!注释] 如果数据库不受信任，将不允许此操作。</span><span class="sxs-lookup"><span data-stu-id="93627-106">This action will not be allowed if the database is not trusted.</span></span> 

## <a name="setting"></a><span data-ttu-id="93627-107">设置</span><span class="sxs-lookup"><span data-stu-id="93627-107">Setting</span></span>

<span data-ttu-id="93627-108">**ShowToolbar** 操作具有下列参数。</span><span class="sxs-lookup"><span data-stu-id="93627-108">The **ShowToolbar** action has the following arguments.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="93627-109">操作参数</span><span class="sxs-lookup"><span data-stu-id="93627-109">Action argument</span></span></p></th>
<th><p><span data-ttu-id="93627-110">说明</span><span class="sxs-lookup"><span data-stu-id="93627-110">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="93627-111"><strong>工具栏名称</strong></span><span class="sxs-lookup"><span data-stu-id="93627-111"><strong>Toolbar Name</strong></span></span></p></td>
<td><p><span data-ttu-id="93627-112">在<strong>“加载项”</strong>选项卡上要显示或隐藏的命令组的名称。</span><span class="sxs-lookup"><span data-stu-id="93627-112">The name of the command group on the <strong>Add-Ins</strong> tab you want to display or hide.</span></span> <span data-ttu-id="93627-113">“宏生成器”窗格<strong>“操作参数”</strong>部分的<strong>“工具栏名称”</strong>框会显示此操作可以影响到的所有可用的组。</span><span class="sxs-lookup"><span data-stu-id="93627-113">The <strong>Toolbar Name</strong> box in the <strong>Action Arguments</strong> section of the Macro Builder Pane shows all the available groups that can be affected by this action.</span></span> <span data-ttu-id="93627-114">这是一个必选参数。</span><span class="sxs-lookup"><span data-stu-id="93627-114">This is a required argument.</span></span> <span data-ttu-id="93627-115">如果在类库数据库中运行包含 <strong>ShowToolbar</strong> 操作的宏，Access 将先在该类库数据库中查找具有此名称的组，然后再在当前数据库中查找。</span><span class="sxs-lookup"><span data-stu-id="93627-115">If you run a macro containing the <strong>ShowToolbar</strong> action in a library database, Access first looks for the group with this name in the library database, and then in the current database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93627-116"><strong>Show</strong></span><span class="sxs-lookup"><span data-stu-id="93627-116"><strong>Show</strong></span></span></p></td>
<td><p><span data-ttu-id="93627-117">指定是显示还是隐藏组以及在哪些视图中显示或隐藏组。</span><span class="sxs-lookup"><span data-stu-id="93627-117">Specifies whether to display or hide the group and in which views to display or hide it.</span></span> <span data-ttu-id="93627-118">默认值为<strong>"是"</strong> (在所有时间都显示组)。</span><span class="sxs-lookup"><span data-stu-id="93627-118">The default is <strong>Yes</strong> (show the group at all times).</span></span> <span data-ttu-id="93627-119">您可以选择<strong>"是"</strong>以始终显示组, 在<strong>适当</strong>的窗体或报表处于活动状态时仅显示组, 或 "<strong>否</strong>" 则始终隐藏组。</span><span class="sxs-lookup"><span data-stu-id="93627-119">You can select <strong>Yes</strong> to display the group at all times, <strong>Where Appropriate</strong> to display the group only when the appropriate form or report is active, or <strong>No</strong> to hide the group at all times.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="93627-120">注解</span><span class="sxs-lookup"><span data-stu-id="93627-120">Remarks</span></span>

<span data-ttu-id="93627-121">可以在包含条件表达式的宏中使用此操作，以便根据某些条件来显示或隐藏组。</span><span class="sxs-lookup"><span data-stu-id="93627-121">You can use this action in a macro with conditional expressions to display or hide a group depending on certain conditions.</span></span>

<span data-ttu-id="93627-p103">If you want to show a particular group on just one form or report, you can set the **OnActivate** property of the form or report to the name of a macro that contains a **ShowToolbar** action to show the group. Then set the **OnDeactivate** property of the form or report to the name of a macro that contains a **ShowToolbar** action to hide the group.</span><span class="sxs-lookup"><span data-stu-id="93627-p103">If you want to show a particular group on just one form or report, you can set the **OnActivate** property of the form or report to the name of a macro that contains a **ShowToolbar** action to show the group. Then set the **OnDeactivate** property of the form or report to the name of a macro that contains a **ShowToolbar** action to hide the group.</span></span>

<span data-ttu-id="93627-124">The built-in toolbars are not available to display or hide by using this action if you set the **AllowBuiltInToolbars** property to **False** (0) in a Visual Basic for Applications (VBA) module, or if you set the **Allow Built-in Toolbars** option to **False** in VBA by using the **SetOption** method.</span><span class="sxs-lookup"><span data-stu-id="93627-124">The built-in toolbars are not available to display or hide by using this action if you set the **AllowBuiltInToolbars** property to **False** (0) in a Visual Basic for Applications (VBA) module, or if you set the **Allow Built-in Toolbars** option to **False** in VBA by using the **SetOption** method.</span></span>

<span data-ttu-id="93627-125">要在 VBA 模块中运行 **ShowToolbar** 操作，请使用 **DoCmd** 对象的 **ShowToolbar** 方法。</span><span class="sxs-lookup"><span data-stu-id="93627-125">To run the **ShowToolbar** action in a VBA module, use the **ShowToolbar** method of the **DoCmd** object.</span></span>

