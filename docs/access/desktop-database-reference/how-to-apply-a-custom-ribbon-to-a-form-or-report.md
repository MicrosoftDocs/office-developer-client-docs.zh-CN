---
title: 将自定义功能区应用于窗体或报表
TOCTitle: Apply a custom ribbon to a form or report
description: 如何在 Access 2013 中加载窗体或报表时应用自定义功能区。
ms:assetid: 7dcdfa42-3eaa-43f9-b99d-56b2cac97f84
ms:mtpsurl: https://msdn.microsoft.com/library/Ff196428(v=office.15)
ms:contentKeyID: 48545865
ms.date: 10/16/2018
mtps_version: v=office.15
localization_priority: Priority
ms.openlocfilehash: 329f184a1bcd3c856ccfd0b15c3fa92bc6230c98
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32291913"
---
# <a name="apply-a-custom-ribbon-to-a-form-or-report"></a>将自定义功能区应用于窗体或报表

**适用于**：Access 2013、Office 2013

The ribbon uses text-based, declarative XML markup that simplifies creating and customizing the ribbon. 使用几行 XML，您可以为用户创建适当的界面。 Access 在自定义功能区用户界面方面更好地提供灵活性。 

例如，自定义标记可以存储在一个表中，嵌入在 VBA 程序中，存储在另一个 Access 数据库中，或链接到某个 Excel 工作表。 本主题介绍加载窗体或报表时如何应用自定义的功能区。

## <a name="make-the-ribbon-customization-xml-available"></a>提供功能区自定义 XML

### <a name="store-ribbon-extensibility-xml-in-a-table"></a>在表中存储功能区可扩展性 XML

One method that you can use to make ribbon customizations available is to store them in a table. If you store the customizations in a table named **USysRibbons**, the customizations can be implemented without using macros or VBA code.

**USysRibbons** 是用户创建的系统表。 必须使用特定的列名创建表才能实现功能区自定义。 

下表列出创建 **USysRibbons** 表时要使用的设置。

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>列名称</p></th>
<th><p>数据类型</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>RibbonName</strong></p></td>
<td><p>Text</p></td>
<td><p>Contains the name of the custom ribbon to be associated with this customization.</p></td>
</tr>
<tr class="even">
<td><p><strong>RibbonXML</strong></p></td>
<td><p>备注</p></td>
<td><p>包含定义功能区自定义的功能区扩展性 XML (RibbonX)。</p></td>
</tr>
</tbody>
</table>


### <a name="load-ribbon-extensibility-xml-programmatically"></a>以编程的方式加载功能区扩展性 XML

You can use the **[LoadCustomUI](https://docs.microsoft.com/office/vba/api/Access.Application.LoadCustomUI)** method to load ribbon customizations programmatically. Typically, to create and make the ribbon available to the application, you first create a module in the database with a procedure that calls the **LoadCustomUI** method, passing in the name of the ribbon and the XML customization markup.

XML 标记可以来自表中创建的“Recordset”**** 对象，来自数据库的外部源（如您解析成字符串的 XML 文件），或来自直接嵌入在程序中的 XML 标记。您可以使用对“LoadCustomUI”**** 方法的多个调用创建不同的功能区，传递不同的 XML 标记，只要各功能区的名称和构成功能区的选项卡的“id”**** 属性是唯一的。

完成此程序后，再创建一个使用 RunCode 操作调用该程序的 AutoExec 宏。如此一来，当应用程序启动时，系统将自动执行“LoadCustomUI”**** 方法，并且所有自定义功能区都可提供给该应用程序使用。

## <a name="assign-custom-ribbons-to-forms-or-reports"></a>为窗体或报表指定自定义功能区

1.  按照先前描述的过程将自定义的功能区提供给该应用程序使用。

2.  在“设计”视图中打开窗体或报表。

3.  在“设计”选项卡上，选择“**属性表**”。

4.  在“属性”窗口的“**所有**”选项卡上，选择“**功能区名称**”列表，然后选择一个功能区。

5.  保存、关闭和重新打开窗体或报表。 将显示您选择的功能区 UI。


> [!NOTE]
> 在功能区 UI 中显示的选项卡具有累加性。即，除非明确隐藏选项卡或将“从头开始”** 属性设置为“True”****，否则显示在窗体或报表功能区用户界面中的选项卡是对现有选项卡的补充。

> [!NOTE]
> 有关其他 Office 应用程序中的功能区 UI 的详细信息，请参阅 [Office Fluent 功能区概述](https://docs.microsoft.com/office/vba/Library-Reference/Concepts/overview-of-the-office-fluent-ribbon)。


