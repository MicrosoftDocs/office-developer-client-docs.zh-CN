---
title: AddMenu 宏操作
TOCTitle: AddMenu macro action
ms:assetid: 4eb2afa0-ed1f-41b1-d27f-b3ce7a73d2bb
ms:mtpsurl: https://msdn.microsoft.com/library/Ff193760(v=office.15)
ms:contentKeyID: 48544762
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm37891
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: 119e824cae71d54bb398aa68f476a667f14a6888
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32280271"
---
# <a name="addmenu-macro-action"></a><span data-ttu-id="24177-102">AddMenu 宏操作</span><span class="sxs-lookup"><span data-stu-id="24177-102">AddMenu macro action</span></span>


<span data-ttu-id="24177-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="24177-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="24177-104">本文介绍 **AddMenu** 宏操作的基本操作。</span><span class="sxs-lookup"><span data-stu-id="24177-104">This article describes the basic operation of the **AddMenu** macro action.</span></span>

<span data-ttu-id="24177-105">可以使用 **AddMenu** 操作创建：</span><span class="sxs-lookup"><span data-stu-id="24177-105">You can use the **AddMenu** action to create:</span></span>

- <span data-ttu-id="24177-106">特定窗体或报表的 **"加载项"** 选项卡上的自定义菜单。</span><span class="sxs-lookup"><span data-stu-id="24177-106">Custom menus on the **Add-Ins** tab for a particular form or report.</span></span>

- <span data-ttu-id="24177-p101">窗体、报表或控件的自定义快捷菜单。自定义快捷菜单会替换窗体、报表或控件的内置快捷菜单。</span><span class="sxs-lookup"><span data-stu-id="24177-p101">A custom shortcut menu for a form, report, or control. The custom shortcut menu replaces the built-in shortcut menu for the form, report, or control.</span></span>

- <span data-ttu-id="24177-p102">全局快捷菜单。全局快捷菜单会替换表数据表、查询数据表、窗体和报表中各字段的内置快捷菜单，但为窗体、报表或控件添加的自定义快捷菜单除外。</span><span class="sxs-lookup"><span data-stu-id="24177-p102">A global shortcut menu. The global shortcut menu replaces the built-in shortcut menu for fields in table and query datasheets, forms, and reports, except where you've added a custom shortcut menu for a form, report, or control.</span></span>

## <a name="setting"></a><span data-ttu-id="24177-111">Setting</span><span class="sxs-lookup"><span data-stu-id="24177-111">Setting</span></span>

<span data-ttu-id="24177-112">**AddMenu** 操作具有下列参数。</span><span class="sxs-lookup"><span data-stu-id="24177-112">The **AddMenu** action has the following arguments.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="24177-113">操作参数</span><span class="sxs-lookup"><span data-stu-id="24177-113">Action argument</span></span></p></th>
<th><p><span data-ttu-id="24177-114">说明</span><span class="sxs-lookup"><span data-stu-id="24177-114">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="24177-115"><strong>菜单名称</strong></span><span class="sxs-lookup"><span data-stu-id="24177-115"><strong>Menu Name</strong></span></span></p></td>
<td><p><span data-ttu-id="24177-116">菜单的&quot;名称, 例如, 报表命令&quot;或&quot;工具。&quot;</span><span class="sxs-lookup"><span data-stu-id="24177-116">The name of the menu, for example, &quot;Report Commands&quot; or &quot;Tools&quot;.</span></span> <span data-ttu-id="24177-117">若要创建访问键以便可以使用键盘选择菜单, 请在要用作访问键的字母前面<strong>&amp;</strong>键入 "and" 符 ()。</span><span class="sxs-lookup"><span data-stu-id="24177-117">To create an access key so that you can use the keyboard to choose the menu, type an ampersand (<strong>&amp;</strong>) before the letter you want to be the access key.</span></span> <span data-ttu-id="24177-118">在<strong>“加载项”</strong>选项卡上的菜单名称中，此字母将带有下划线。</span><span class="sxs-lookup"><span data-stu-id="24177-118">This letter will be underlined in the menu name on the <strong>Add-Ins</strong> tab.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24177-119"><strong>菜单宏名称</strong></span><span class="sxs-lookup"><span data-stu-id="24177-119"><strong>Menu Macro Name</strong></span></span></p></td>
<td><p><span data-ttu-id="24177-120">包含与菜单命令相对应的宏的宏组的名称。</span><span class="sxs-lookup"><span data-stu-id="24177-120">The name of the macro group that contains the macros for the menu's commands.</span></span> <span data-ttu-id="24177-121">这是一个必选参数。</span><span class="sxs-lookup"><span data-stu-id="24177-121">This is a required argument.</span></span></p>
<p><span data-ttu-id="24177-122"><strong>注意</strong>: 如果在类库数据库中运行包含<strong>AddMenu</strong>操作的宏, Microsoft Office Access 2007 将仅在当前数据库中查找具有此名称的宏组。</span><span class="sxs-lookup"><span data-stu-id="24177-122"><strong>NOTE</strong>: If you run a macro containing the <strong>AddMenu</strong> action in a library database, Microsoft Office Access 2007 looks for the macro group with this name in the current database only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24177-123"><strong>状态栏文字</strong></span><span class="sxs-lookup"><span data-stu-id="24177-123"><strong>Status Bar Text</strong></span></span></p></td>
<td><p><span data-ttu-id="24177-124">选中菜单时在状态栏中显示的文字。</span><span class="sxs-lookup"><span data-stu-id="24177-124">The text to display in the status bar when the menu is selected.</span></span> <span data-ttu-id="24177-125">对于快捷菜单，将忽略此参数。</span><span class="sxs-lookup"><span data-stu-id="24177-125">This argument is ignored for shortcut menus.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="24177-126">注解</span><span class="sxs-lookup"><span data-stu-id="24177-126">Remarks</span></span>

<span data-ttu-id="24177-p106">要在 Visual Basic for Applications (VBA) 模块中运行 **AddMenu** 操作，请使用 **DoCmd** 对象的 **AddMenu** 方法。在 VBA 中，还可以设置 **MenuBar** 或 **ShortcutMenuBar** 属性，以便在 **"加载项"** 选项卡上创建自定义菜单，或在窗体、报表或控件上附加自定义快捷菜单。可以设置 **Application** 对象的 **ShortcutMenuBar** 属性，以便创建全局快捷菜单。</span><span class="sxs-lookup"><span data-stu-id="24177-p106">To run the **AddMenu** action in a Visual Basic for Applications (VBA) module, use the **AddMenu** method of the **DoCmd** object. You can also set the **MenuBar** or **ShortcutMenuBar** property in VBA to create a custom menu on the **Add-Ins** tab or to attach a custom shortcut menu to a form, report, or control. You can set the **ShortcutMenuBar** property of the **Application** object to create a global shortcut menu.</span></span>

