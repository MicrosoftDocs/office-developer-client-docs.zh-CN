---
title: 转换 Microsoft Access 表、窗体和报表
TOCTitle: Convert Microsoft Access tables, forms, and reports
description: 通过 Microsoft Access 2002 引入的更改可能会影响您的版本的行为 1.x 或 2.0 应用程序。
ms:assetid: cc170e62-a663-60e8-4446-07a7a874b747
ms:mtpsurl: https://msdn.microsoft.com/library/Ff834413(v=office.15)
ms:contentKeyID: 48547731
ms.date: 10/16/2018
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm5187104
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 69bd93b84bb0bca768203933e64e385648d52730
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/01/2018
ms.locfileid: "25891070"
---
# <a name="convert-microsoft-access-tables-forms-and-reports"></a>转换 Microsoft Access 表、窗体和报表

**适用于**： Access 2013、 Office 2013

由 Microsoft Access 2002 引入的某些更改可能会影响 1.*x* 或 2.0 版应用程序的行为。下面的章节将提供有关这些更改的详细信息。

## <a name="indexes-and-relationships"></a>索引和关系

Microsoft Access 表最多可以包含 32 个索引。非常复杂的表（这些表是许多关系的一部分）可能会超过这个索引限制，因此无法转换包含这些表的数据库。Microsoft Access 数据库引擎根据表之间的关系的双方创建索引。如果数据库不进行转换，请删除一些关系，然后再次尝试转换数据库。

## <a name="the-limittolist-property-of-combo-boxes"></a>组合框的 LimitToList 属性

在 Microsoft Access 2002 或更高版本，组合框接受**空**值时**LimitToList**属性设置为**True** (– 1)，列表包含**Null**值。 2.0 版中，除非该列表包含**Null**值，组合框的**LimitToList**属性将设置为**True**不会接受**空**值。 如果您想要防止用户使用组合框中输入一个**Null**值，设置为**是**表中字段的**必需**属性。

## <a name="menus-and-in-place-activation-of-ole-objects"></a>菜单和就地激活的 OLE 对象

若要使其他功能可供您激活就地 OLE 对象时，某些菜单命令可能已移到的菜单上时激活 OLE 服务器未被替换。

更改不会影响这个已转换的应用程序中的宏，该宏当激活某组件时使用 DoMenuItem 操作来执行 2.0 版的菜单命令。2.0 版本的命令对应于在 Microsoft Access 的更高版本中的等价命令。

## <a name="referencing-a-control-on-a-read-only-form"></a>引用只读窗体上的控件

在 Microsoft Access 2002 或更高版本中，不能使用表达式引用绑定到空记录源的只读窗体上控件的值。在旧版本中，表达式返回 **Null** 值。在引用只读窗体上的控件之前，应该确定窗体的记录源中包含记录。

## <a name="date-fields-and-data-entry"></a>日期字段和数据输入

如果在窗体或表数据表上的"日期"类型字段中输入 **3/3** ，在 Microsoft Access 2002 或更高版本中，将自动添加当前的年份。不过如果在同样的字段中输入 **3/3/** ，Microsoft Access 将返回错误消息。必须省略日期最后的斜线，这样 Microsoft Access 才能将日期转换为正确的格式。

## <a name="buttons-created-with-the-command-button-wizard"></a>使用命令按钮向导创建的按钮

如果在 2.0 或 7.0 版的 Microsoft Access 中，使用"命令按钮向导"生成调用其他应用程序的代码，应该删除该按钮，并使用 Microsoft Access 2002 或更高版本的"命令按钮向导"来重新创建该按钮。

## <a name="form-and-report-class-modules"></a>窗体和报表类模块

在 Microsoft Access 2002 以前的版本中，即使在对象的背后没有代码， **Form** 和 **Report** 对象也仍具有相关的类模块。在 Microsoft Access 2002 或更高版本中，可以将窗体或报表的 **HasModule** 属性设为 **False** 。当将 **HasModule** 属性设为 **False** 时，因为窗体或报表将不再具有相关的类模块，所以占用的磁盘空间会减少，并且加载速度更快。

## <a name="converted-version-20-report-has-different-margins"></a>转换后的 2.0 版报表具有不同的页边距

当试图打印或打印预览从 Microsoft Access 2.0 转换的 Microsoft Access 2002 或更高版本的报表时，如果报表的某些页边距设为 0，可能会遇到问题。当转换 Microsoft Access 2.0 报表时，页边距不能设为 0，而应设为对默认打印机有效的最小页边距。这将避免报表在打印机的不可打印区域打印数据。

要解决这个问题，可减少报表中的列宽度、列间距或列数，使得列宽度加上默认页边距的宽度等于或小于纸张的宽度。

## <a name="cant-use-the-format-property-to-distinguish-null-values-and-zero-length-strings"></a>不能使用 Format 属性来区别 Null 值和零长度字符串

在版本 1。*x*和 2.0，您可以使用控件的**Format**属性来显示不同的值为**Null**值和零长度字符串 ("")。 而在 Microsoft Access 2002 或更高版本中，要区别窗体控件中的 **Null** 值和零长度字符串，必须将控件的 **ControlSource** 属性设为一个表达式，以测试 **Null** 值情形。 例如，要在控件中显示"Null"或"ZLS"，请将它的 **ControlSource** 属性设为下面的表达式：

`=IIf(IsNull([MyControl]), "Null", Format([MyControl], "@;ZLS"))`

