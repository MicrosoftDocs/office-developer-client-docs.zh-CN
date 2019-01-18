---
title: 将自定义功能区应用于窗体或报表
TOCTitle: Apply a custom ribbon to a form or report
description: 如何在加载窗体或 Access 2013 中的报表时应用自定义功能区。
ms:assetid: 7dcdfa42-3eaa-43f9-b99d-56b2cac97f84
ms:mtpsurl: https://msdn.microsoft.com/library/Ff196428(v=office.15)
ms:contentKeyID: 48545865
ms.date: 10/16/2018
mtps_version: v=office.15
localization_priority: Priority
ms.openlocfilehash: 329f184a1bcd3c856ccfd0b15c3fa92bc6230c98
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28703998"
---
# <a name="apply-a-custom-ribbon-to-a-form-or-report"></a>将自定义功能区应用于窗体或报表

**适用于**： Access 2013、 Office 2013

The ribbon uses text-based, declarative XML markup that simplifies creating and customizing the ribbon. 使用几行 XML，您可以为用户创建适当的界面。 Access 在自定义功能区用户界面方面更好地提供灵活性。 

例如，自定义标记可以存储在一个表中，嵌入在 VBA 程序中，存储在另一个 Access 数据库中，或链接到某个 Excel 工作表。 本主题介绍加载窗体或报表时如何应用自定义的功能区。

## <a name="make-the-ribbon-customization-xml-available"></a>可用功能区自定义 XML

### <a name="store-ribbon-extensibility-xml-in-a-table"></a>在表中存储功能区扩展性 XML

One method that you can use to make ribbon customizations available is to store them in a table. If you store the customizations in a table named **USysRibbons**, the customizations can be implemented without using macros or VBA code.

**USysRibbons** is a user-created system table. 必须使用功能区自定义项的特定的列名称必须创建表。 

下表列出了创建 **USysRibbons** 表时要使用的设置。

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
<td><p>Memo</p></td>
<td><p>包含功能区扩展性 XML (RibbonX) 定义功能区自定义项。</p></td>
</tr>
</tbody>
</table>


### <a name="load-ribbon-extensibility-xml-programmatically"></a>以编程方式加载功能区扩展性 XML

You can use the **[LoadCustomUI](https://docs.microsoft.com/office/vba/api/Access.Application.LoadCustomUI)** method to load ribbon customizations programmatically. Typically, to create and make the ribbon available to the application, you first create a module in the database with a procedure that calls the **LoadCustomUI** method, passing in the name of the ribbon and the XML customization markup.

The XML markup can come from a **Recordset** object created from a table, from a source external to the database such as an XML file that you parse into a string, or from XML markup embedded directly inside the procedure. You can make different ribbons using multiple calls to the **LoadCustomUI** method, passing in different XML markup as long as the name of each ribbon and the **id** attribute of the tabs that make up the ribbon are unique.

After the procedure is complete, you then create an AutoExec macro that calls the procedure by using the RunCode action. That way, when the application is started, the **LoadCustomUI** method is automatically executed and all of the custom ribbons are made available to the application.

## <a name="assign-custom-ribbons-to-forms-or-reports"></a>分配窗体或报表的自定义功能区

1.  按照先前描述的过程将自定义的功能区提供给该应用程序使用。

2.  在"设计"视图中打开窗体或报表。

3.  在设计选项卡中，选择**属性表**。

4.  在属性窗口的**所有**选项卡上，选择**功能区名称**列表，然后选择功能区。

5.  保存、关闭和重新打开窗体或报表。将显示您选择的功能区 UI。


> [!NOTE]
> 在功能区 UI 中显示的选项卡是累加。 即，除非您明确隐藏选项卡或*从头开始*属性设置为**True**，选项卡显示在窗体或报表的功能区用户界面除了现有选项卡。

> [!NOTE]
> [!注释] For more information about the ribbon UI in other Office applications, see [Overview of the Office Fluent Ribbon](https://docs.microsoft.com/office/vba/Library-Reference/Concepts/overview-of-the-office-fluent-ribbon).


