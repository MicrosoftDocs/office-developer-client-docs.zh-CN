---
title: 转换 Microsoft Access 表、窗体和报表
TOCTitle: Convert Microsoft Access tables, forms, and reports
description: Microsoft Access 2002 引入的更改可能会影响您的版本 1. x 或2.0 应用程序的行为。
ms:assetid: cc170e62-a663-60e8-4446-07a7a874b747
ms:mtpsurl: https://msdn.microsoft.com/library/Ff834413(v=office.15)
ms:contentKeyID: 48547731
ms.date: 10/16/2018
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm5187104
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: 9c1ff7584269ce073a805edf8710bb3ea4eb1a36
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32295581"
---
# <a name="convert-microsoft-access-tables-forms-and-reports"></a><span data-ttu-id="cba6b-103">转换 Microsoft Access 表、窗体和报表</span><span class="sxs-lookup"><span data-stu-id="cba6b-103">Convert Microsoft Access tables, forms, and reports</span></span>

<span data-ttu-id="cba6b-104">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="cba6b-104">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="cba6b-p101">由 Microsoft Access 2002 引入的某些更改可能会影响 1.*x* 或 2.0 版应用程序的行为。下面的章节将提供有关这些更改的详细信息。</span><span class="sxs-lookup"><span data-stu-id="cba6b-p101">Several changes introduced by Microsoft Access 2002 might affect the behavior of your version 1.*x* or 2.0 applications. The following sections provide more information about those changes.</span></span>

## <a name="indexes-and-relationships"></a><span data-ttu-id="cba6b-107">索引和关系</span><span class="sxs-lookup"><span data-stu-id="cba6b-107">Indexes and relationships</span></span>

<span data-ttu-id="cba6b-p102">Microsoft Access 表最多可以包含 32 个索引。非常复杂的表（这些表是许多关系的一部分）可能会超过这个索引限制，因此无法转换包含这些表的数据库。Microsoft Access 数据库引擎根据表之间的关系的双方创建索引。如果数据库不进行转换，请删除一些关系，然后再次尝试转换数据库。</span><span class="sxs-lookup"><span data-stu-id="cba6b-p102">A Microsoft Access table can contain up to 32 indexes. Very complex tables that are a part of many relationships may exceed the index limit, and you won't be able to convert the database that contains these tables. The Microsoft Access database engine creates indexes on both sides of relationships between tables. If your database won't convert, delete some relationships and try again to convert the database.</span></span>

## <a name="the-limittolist-property-of-combo-boxes"></a><span data-ttu-id="cba6b-112">组合框的 "限于数目" 属性</span><span class="sxs-lookup"><span data-stu-id="cba6b-112">The LimitToList property of combo boxes</span></span>

<span data-ttu-id="cba6b-113">在 Microsoft Access 2002 或更高版本中, 当 "**限于**列表" 属性设置为**True** (– 1) 时, 无论列表是否包含**Null**值, 组合框都可以接受**Null**值。</span><span class="sxs-lookup"><span data-stu-id="cba6b-113">In Microsoft Access 2002 or later, combo boxes accept **Null** values when the **LimitToList** property is set to **True** (–1), whether or not the list contains **Null** values.</span></span> <span data-ttu-id="cba6b-114">在版本2.0 中, 如果列表中包含**null**值, 则将 "**限于**列表" 属性设置为**True**的组合框不会接受**null**值。</span><span class="sxs-lookup"><span data-stu-id="cba6b-114">In version 2.0, a combo box that has the **LimitToList** property set to **True** won't accept a **Null** value unless the list contains a **Null** value.</span></span> <span data-ttu-id="cba6b-115">如果要阻止用户使用组合框输入**Null**值, 请将 table 中字段的**Required**属性设置为 **"是"**。</span><span class="sxs-lookup"><span data-stu-id="cba6b-115">If you want to prevent users from entering a **Null** value by using a combo box, set the **Required** property of the field in the table to **Yes**.</span></span>

## <a name="menus-and-in-place-activation-of-ole-objects"></a><span data-ttu-id="cba6b-116">OLE 对象的菜单和就地激活</span><span class="sxs-lookup"><span data-stu-id="cba6b-116">Menus and in-place activation of OLE objects</span></span>

<span data-ttu-id="cba6b-117">若要在就地激活 ole 对象时提供其他功能, 则在激活 ole 服务器时, 某些菜单命令可能已移至未被替换的菜单中。</span><span class="sxs-lookup"><span data-stu-id="cba6b-117">To make additional functionality available to you while activating OLE objects in place, some menu commands may have been moved to a menu that isn't replaced when you activate an OLE server.</span></span>

<span data-ttu-id="cba6b-p104">更改不会影响这个已转换的应用程序中的宏，该宏当激活某组件时使用 DoMenuItem 操作来执行 2.0 版的菜单命令。2.0 版本的命令对应于在 Microsoft Access 的更高版本中的等价命令。</span><span class="sxs-lookup"><span data-stu-id="cba6b-p104">Macros in your converted application that use a DoMenuItem action to carry out a version 2.0 menu command when a component is activated won't be affected by the changes. Version 2.0 commands are mapped to their equivalents in later versions of Microsoft Access.</span></span>

## <a name="referencing-a-control-on-a-read-only-form"></a><span data-ttu-id="cba6b-120">引用只读窗体上的控件</span><span class="sxs-lookup"><span data-stu-id="cba6b-120">Referencing a control on a read-only form</span></span>

<span data-ttu-id="cba6b-p105">在 Microsoft Access 2002 或更高版本中，不能使用表达式引用绑定到空记录源的只读窗体上控件的值。在旧版本中，表达式返回 **Null** 值。在引用只读窗体上的控件之前，应该确定窗体的记录源中包含记录。</span><span class="sxs-lookup"><span data-stu-id="cba6b-p105">In Microsoft Access 2002 or later, you can't use an expression to refer to the value of a control on a read-only form that's bound to an empty record source. In previous versions, the expression returns a **Null** value. Before you reference a control on a read-only form, you should make sure that the form's record source contains records.</span></span>

## <a name="date-fields-and-data-entry"></a><span data-ttu-id="cba6b-124">日期字段和数据输入</span><span class="sxs-lookup"><span data-stu-id="cba6b-124">Date fields and data entry</span></span>

<span data-ttu-id="cba6b-p106">如果在窗体或表数据表上的"日期"类型字段中输入 **3/3** ，在 Microsoft Access 2002 或更高版本中，将自动添加当前的年份。不过如果在同样的字段中输入 **3/3/** ，Microsoft Access 将返回错误消息。必须省略日期最后的斜线，这样 Microsoft Access 才能将日期转换为正确的格式。</span><span class="sxs-lookup"><span data-stu-id="cba6b-p106">If you enter **3/3** in a field of type Date on a form or a table datasheet, the current year is automatically added in Microsoft Access 2002 or later. However, if you enter **3/3/** in the same field, Microsoft Access returns an error message. You must omit the last date delimiter so that Microsoft Access can translate the date into the proper format.</span></span>

## <a name="buttons-created-with-the-command-button-wizard"></a><span data-ttu-id="cba6b-128">使用 "命令按钮向导" 创建的按钮</span><span class="sxs-lookup"><span data-stu-id="cba6b-128">Buttons created with the Command Button Wizard</span></span>

<span data-ttu-id="cba6b-129">如果在 2.0 或 7.0 版的 Microsoft Access 中，使用"命令按钮向导"生成调用其他应用程序的代码，应该删除该按钮，并使用 Microsoft Access 2002 或更高版本的"命令按钮向导"来重新创建该按钮。</span><span class="sxs-lookup"><span data-stu-id="cba6b-129">If you used the Command Button Wizard in version 2.0 or 7.0 of Microsoft Access to generate code that called another application, you should delete the button and re-create it by using the Command Button Wizard in Microsoft Access 2002 or later.</span></span>

## <a name="form-and-report-class-modules"></a><span data-ttu-id="cba6b-130">窗体和报表类模块</span><span class="sxs-lookup"><span data-stu-id="cba6b-130">Form and report class modules</span></span>

<span data-ttu-id="cba6b-p107">在 Microsoft Access 2002 以前的版本中，即使在对象的背后没有代码， **Form** 和 **Report** 对象也仍具有相关的类模块。在 Microsoft Access 2002 或更高版本中，可以将窗体或报表的 **HasModule** 属性设为 **False** 。当将 **HasModule** 属性设为 **False** 时，因为窗体或报表将不再具有相关的类模块，所以占用的磁盘空间会减少，并且加载速度更快。</span><span class="sxs-lookup"><span data-stu-id="cba6b-p107">In versions of Microsoft Access prior to 2002, **Form** and **Report** objects have associated class modules even if there's no code behind the object. In Microsoft Access 2002 or later, you can set a form's or report's **HasModule** property to **False**. When you set the **HasModule** property to **False**, the form or report will take up less disk space and will load faster because it will no longer have an associated class module.</span></span>

## <a name="converted-version-20-report-has-different-margins"></a><span data-ttu-id="cba6b-134">转换后的版本2.0 报表具有不同的边距</span><span class="sxs-lookup"><span data-stu-id="cba6b-134">Converted version 2.0 report has different margins</span></span>

<span data-ttu-id="cba6b-p108">当试图打印或打印预览从 Microsoft Access 2.0 转换的 Microsoft Access 2002 或更高版本的报表时，如果报表的某些页边距设为 0，可能会遇到问题。当转换 Microsoft Access 2.0 报表时，页边距不能设为 0，而应设为对默认打印机有效的最小页边距。这将避免报表在打印机的不可打印区域打印数据。</span><span class="sxs-lookup"><span data-stu-id="cba6b-p108">You may encounter problems when trying to print or preview a report in Microsoft Access 2002 or later that has been converted from Microsoft Access 2.0 if the report has some margins set to 0. When you convert a Microsoft Access 2.0 report, margins aren't set to 0; they are instead set to the minimum margin that's valid for the default printer. This prevents the report from printing data in the unprintable region of the printer.</span></span>

<span data-ttu-id="cba6b-138">要解决这个问题，可减少报表中的列宽度、列间距或列数，使得列宽度加上默认页边距的宽度等于或小于纸张的宽度。</span><span class="sxs-lookup"><span data-stu-id="cba6b-138">To resolve this problem, reduce the column width, column spacing, or number of columns in the report so that the width of the columns plus the width of the default margins is equal to or less than the width of your paper.</span></span>

## <a name="cant-use-the-format-property-to-distinguish-null-values-and-zero-length-strings"></a><span data-ttu-id="cba6b-139">无法使用 Format 属性来区分 Null 值和零长度字符串</span><span class="sxs-lookup"><span data-stu-id="cba6b-139">Can't use the Format property to distinguish Null values and zero-length strings</span></span>

<span data-ttu-id="cba6b-140">在版本1中。*x*和 2.0, 可以使用控件的**Format**属性来显示**Null**值和零长度字符串 ("") 的不同值。</span><span class="sxs-lookup"><span data-stu-id="cba6b-140">In versions 1.*x* and 2.0, you can use the **Format** property of a control to display different values for **Null** values and zero-length strings (" ").</span></span> <span data-ttu-id="cba6b-141">而在 Microsoft Access 2002 或更高版本中，要区别窗体控件中的 **Null** 值和零长度字符串，必须将控件的 **ControlSource** 属性设为一个表达式，以测试 **Null** 值情形。</span><span class="sxs-lookup"><span data-stu-id="cba6b-141">In Microsoft Access 2002 or later, to distinguish between **Null** values and zero-length strings in a control on a form, set the control's **ControlSource** property to an expression that tests for the **Null** value case.</span></span> <span data-ttu-id="cba6b-142">例如，要在控件中显示"Null"或"ZLS"，请将它的 **ControlSource** 属性设为下面的表达式：</span><span class="sxs-lookup"><span data-stu-id="cba6b-142">For example, to display "Null" or "ZLS" in a control, set its **ControlSource** property to the following expression:</span></span>

`=IIf(IsNull([MyControl]), "Null", Format([MyControl], "@;ZLS"))`

