---
title: Access 启动时隐藏功能区
TOCTitle: Hide the ribbon when Access starts
description: 如何加载可隐藏 Access 2013 中所有内置选项卡的自定义功能区。
ms:assetid: f98bab58-8094-1c56-f70b-ced2e7849574
ms:mtpsurl: https://msdn.microsoft.com/library/Ff837012(v=office.15)
ms:contentKeyID: 48548817
ms.date: 10/16/2018
mtps_version: v=office.15
localization_priority: Priority
ms.openlocfilehash: 4ce9327790f620ba9163f5cdbe7b5c8900de4341
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32291936"
---
# <a name="hide-the-ribbon-when-access-starts"></a>Access 启动时隐藏功能区

**适用于**：Access 2013 | Office 2013

默认情况下，Microsoft Access 不提供用于隐藏功能区的方法。本主题介绍如何加载可隐藏所有的内置选项卡的自定义功能区。

要在 Access 启动时加载自定义的功能区，应将其设置存储在一个名为 **USysRibbons** 的表中。

必须使用特定的列名创建 **USysRibbons** 表才能实现功能区自定义。 

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
<td><p>备注</p></td>
<td><p>包含定义功能区自定义的功能区扩展性 XML (RibbonX)。</p></td>
</tr>
</tbody>
</table>

<br/>

下表列出了要存储在 **USysRibbons** 表中的功能区自定义设置。

|列名称|值|
|:----------|:----|
|**RibbonName**|HideTheRibbon|
|**RibbonXML**|`<CustomUI xmlns="https://schemas.microsoft.com/office/2006/01/CustomUI"> <ribbon startFromScratch="true"/></CustomUI>`|


## <a name="apply-a-custom-ribbon-when-access-starts"></a>Access 启动时应用自定义功能区

若要应用自定义功能区以使它在应用程序启动时可用，请执行以下过程：

1.  按照先前描述的过程将自定义的功能区提供给该应用程序使用。

2.  关闭应用程序，然后重新启动它。

3.  选择 **Microsoft Office 按钮**![O12FileMenuButton\_ZA10077102](media/access-file-menu-button.gif "O12FileMenuButton_ZA10077102")，然后选择“**Access 选项**”。

4.  选择“**当前数据库**”选项，然后在“**功能区和工具栏选项**”部分，选择“**功能区名称**”列表，然后选择“**HideTheRibbon**”。

5.  关闭再重新启动应用程序。

> [!NOTE]
> 有关其他 Office 应用程序中的功能区 UI 的详细信息，请参阅 [Office Fluent 功能区概述](https://docs.microsoft.com/office/vba/Library-Reference/Concepts/overview-of-the-office-fluent-ribbon)。


