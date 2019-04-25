---
title: 启动 Access 时应用自定义功能区
TOCTitle: Apply a custom ribbon when starting Access
description: 如何在 Access 2013 中打开数据库时应用自定义功能区。
ms:assetid: 9e8ddf95-35aa-4e57-8422-d770da14711e
ms:mtpsurl: https://msdn.microsoft.com/library/Ff198313(v=office.15)
ms:contentKeyID: 48546659
ms.date: 10/16/2018
mtps_version: v=office.15
localization_priority: Priority
ms.openlocfilehash: 0acd99a498a74f098b08814e9f11d49b28bae097
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32291955"
---
# <a name="apply-a-custom-ribbon-when-starting-access"></a>启动 Access 时应用自定义功能区

**适用于**：Access 2013 | Office 2013

The ribbon uses text-based, declarative XML markup that simplifies creating and customizing the ribbon. With a few lines of XML, you can create just the right interface for the user. Access provides tremendous flexibility in customizing the ribbon UI. For example, customization markup can be stored in a table, embedded in a VBA procedure, stored in another Access database, or linked to from an Excel worksheet. This topic describes how to apply customized ribbons when opening a database.

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

完成此程序后，使用 RunCode 操作创建调用该程序的 AutoExec 宏。 这样一来，启动应用程序时，**LoadCustomUI** 方法会自动执行，所有自定义功能区将提供给应用程序。

## <a name="apply-customized-ribbons-when-access-starts"></a>Access 启动时，应用自定义功能区

To apply a custom UI so that it is available when the application starts, use the following procedure:

1.  Follow the process described previously to make the customized ribbons available to the application.

2.  Close and then restart the application.

3.  选择 **Microsoft Office 按钮**![O12FileMenuButton\_ZA10077102](media/access-file-menu-button.gif "O12FileMenuButton_ZA10077102")，然后选择“**Access 选项**”。

4.  选择“**当前数据库**”选项，然后在“**功能区和工具栏选项**”部分，选择“**功能区名称**”列表，然后选择一个功能区。

5.  Now close and restart the application. The UI you selected is displayed.

> [!NOTE]
> 有关其他 Office 应用程序中的功能区 UI 的详细信息，请参阅 [Office Fluent 功能区概述](https://docs.microsoft.com/office/vba/Library-Reference/Concepts/overview-of-the-office-fluent-ribbon)。


