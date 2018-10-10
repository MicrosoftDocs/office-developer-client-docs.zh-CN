---
title: 适用于窗体或报表的自定义功能区
TOCTitle: Apply a custom ribbon to a form or report
ms:assetid: 7dcdfa42-3eaa-43f9-b99d-56b2cac97f84
ms:mtpsurl: https://msdn.microsoft.com/library/Ff196428(v=office.15)
ms:contentKeyID: 48545865
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: f4fb0155b1a1ed36b6fe924f72a4da385197cc21
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468113"
---
# <a name="apply-a-custom-ribbon-to-a-form-or-report"></a>适用于窗体或报表的自定义功能区


**适用于**： Access 2013 |Office 2013

功能区采用基于文本的声明性 XML 标记，从而简化了创建和自定义功能区。使用几行 XML，您可以为用户创建适当的界面。Access 在自定义功能区用户界面方面更好地提供灵活性。例如，自定义标记可以存储在一个表中，嵌入在 VBA 程序中，存储在另一个 Access 数据库中，或链接到某个 Excel 工作表。本主题介绍加载窗体或报表时如何应用自定义的功能区。

## <a name="making-the-ribbon-customization-xml-available"></a>提供功能区自定义 XML

**Storing Ribbon Extensibility XML in a Table**

One method that you can use to make ribbon customizations available is to store them in a table. If you store the customizations in a table named **USysRibbons**, the customizations can be implemented without using macros or VBA code.

**USysRibbons** is a user-created system table. The table must be created using specific column names in order for the ribbon customizations to be implemented. The following table lists the settings to use when creating the **USysRibbons** table.

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
<td><p>文本</p></td>
<td><p>包含要与该自定义项关联的自定义功能区名称</p></td>
</tr>
<tr class="even">
<td><p><strong>RibbonXML</strong></p></td>
<td><p>备注</p></td>
<td><p>包含定义功能区自定义项的功能区扩展性 XML (RibbonX)</p></td>
</tr>
</tbody>
</table>


**以编程的方式加载功能区扩展性 XML**

You can use the **[LoadCustomUI](https://msdn.microsoft.com/library/ff194416\(v=office.15\))** method to load ribbon customizations programmatically. Typically, to create and make the ribbon available to the application, you first create a module in the database with a procedure that calls the **LoadCustomUI** method, passing in the name of the ribbon and the XML customization markup.

The XML markup can come from a **Recordset** object created from a table, from a source external to the database such as an XML file that you parse into a string, or from XML markup embedded directly inside the procedure. You can make different ribbons using multiple calls to the **LoadCustomUI** method, passing in different XML markup as long as the name of each ribbon and the **id** attribute of the tabs that make up the ribbon are unique.

After the procedure is complete, you then create an AutoExec macro that calls the procedure by using the RunCode action. That way, when the application is started, the **LoadCustomUI** method is automatically executed and all of the custom ribbons are made available to the application.

## <a name="assigning-custom-ribbons-to-forms-or-reports"></a>将自定义功能区分配到窗体或报表

1.  按照先前描述的过程将自定义的功能区提供给该应用程序使用。

2.  在"设计"视图中打开窗体或报表。

3.  在设计选项卡中，单击**属性表**。

4.  在属性窗口的**所有**选项卡上，单击**功能区名称**列表，然后选择功能区。

5.  保存、关闭和重新打开窗体或报表。将显示您选择的功能区 UI。


> [!NOTE]
> 在功能区 UI 中显示的选项卡是累加。 即，除非您明确隐藏选项卡或*从头开始*属性设置为**True**，选项卡显示在窗体或报表的功能区用户界面除了现有选项卡。

> [!NOTE]
> [!注释] For more information about the ribbon UI in other Office applications, see [Overview of the Office Fluent Ribbon](https://docs.microsoft.com/office/vba/Library-Reference/Concepts/overview-of-the-office-fluent-ribbon).


