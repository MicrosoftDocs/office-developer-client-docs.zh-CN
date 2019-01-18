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
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28709619"
---
# <a name="apply-a-custom-ribbon-when-starting-access"></a>启动 Access 时应用自定义功能区

**适用于：** Access 2013 |Office 2013

The ribbon uses text-based, declarative XML markup that simplifies creating and customizing the ribbon. With a few lines of XML, you can create just the right interface for the user. Access provides tremendous flexibility in customizing the ribbon UI. For example, customization markup can be stored in a table, embedded in a VBA procedure, stored in another Access database, or linked to from an Excel worksheet. This topic describes how to apply customized ribbons when opening a database.

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

After the procedure is complete, you then create an AutoExec macro that calls the procedure by using the RunCode action. 这样，当应用程序启动和自动执行**LoadCustomUI**方法时，所有自定义功能区可向应用程序。

## <a name="apply-customized-ribbons-when-access-starts"></a>在 Access 启动时应用自定义功能区

To apply a custom UI so that it is available when the application starts, use the following procedure:

1.  Follow the process described previously to make the customized ribbons available to the application.

2.  Close and then restart the application.

3.  选择**Microsoft Office 按钮**![O12FileMenuButton\_ZA10077102](media/access-file-menu-button.gif "O12FileMenuButton_ZA10077102") ，然后选择**访问选项**。

4.  选择**当前数据库**选项然后，在**功能区和工具栏选项**部分中，选择**功能区名称**列表并选择一个功能区。

5.  Now close and restart the application. The UI you selected is displayed.

> [!NOTE]
> [!注释] For more information about the ribbon UI in other Office applications, see [Overview of the Office Fluent Ribbon](https://docs.microsoft.com/office/vba/Library-Reference/Concepts/overview-of-the-office-fluent-ribbon).


