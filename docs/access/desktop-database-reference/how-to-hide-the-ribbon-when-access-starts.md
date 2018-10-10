---
title: 在 Access 启动时隐藏功能区
TOCTitle: Hide the ribbon when Access starts
ms:assetid: f98bab58-8094-1c56-f70b-ced2e7849574
ms:mtpsurl: https://msdn.microsoft.com/library/Ff837012(v=office.15)
ms:contentKeyID: 48548817
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 2b2b3e28157662a585fa03353da92a598b96bd2c
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466193"
---
# <a name="hide-the-ribbon-when-access-starts"></a>在 Access 启动时隐藏功能区

**适用于：** Access 2013 |Office 2013

默认情况下，Microsoft Access 不提供用于隐藏功能区的方法。本主题介绍如何加载可隐藏所有的内置选项卡的自定义功能区。

要在 Access 启动时加载自定义的功能区，应将其设置存储在一个名为 **USysRibbons** 的表中。

必须使用特定的列名创建 **USysRibbons** 表才能实现功能区自定义。下表列出了创建 **USysRibbons** 表时要使用的设置。

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
<td><p>Contains the Ribbon Extensibility XML (RibbonX) that defines the ribbon customization.</p></td>
</tr>
</tbody>
</table>


下表列出了要存储在 **USysRibbons** 表中的功能区自定义设置。

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>列名</p></th>
<th><p>值</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>RibbonName</strong></p></td>
<td><p>HideTheRibbon</p></td>
</tr>
<tr class="even">
<td><p><strong>RibbonXML</strong></p></td>
<td><p>&lt;CustomUI xmlns =&quot;https://schemas.microsoft.com/office/2006/01/CustomUI&quot;&gt; &lt;功能区 startFromScratch =&quot;true&quot;/&gt;&lt;/CustomUI&gt;</p></td>
</tr>
</tbody>
</table>


## <a name="applying-a-custom-ribbon-when-access-starts"></a>在 Access 启动时应用自定义功能区

若要应用自定义功能区以使它在应用程序启动时可用，请执行以下过程：

1.  按照前面描述的过程使自定义功能区可供应用程序使用。

2.  关闭应用程序，然后重新启动它。

3.  单击**Microsoft Office 按钮**![O12FileMenuButton\_ZA10077102](media/access-file-menu-button.gif "O12FileMenuButton_ZA10077102") ，然后单击**Access 选项**。

4.  单击 **"当前数据库"** 选项，然后在 **"功能区和工具栏选项"** 部分单击 **"功能区名称"** 列表并选择 **"HideTheRibbon"** 。

5.  关闭应用程序，然后重新启动它。

> [!NOTE]
> [!注释] For more information about the ribbon UI in other Office applications, see [Overview of the Office Fluent Ribbon](https://docs.microsoft.com/office/vba/Library-Reference/Concepts/overview-of-the-office-fluent-ribbon).


