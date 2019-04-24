---
title: ImportSharePointList 宏操作
TOCTitle: ImportSharePointList macro action
ms:assetid: 6a633d7d-d81d-0e2e-6c1c-706a552c1bf2
ms:mtpsurl: https://msdn.microsoft.com/library/Ff195403(v=office.15)
ms:contentKeyID: 48545429
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm152234
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: df77d2375b66df907832b6ff2717427ae54a35a4
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32291857"
---
# <a name="importsharepointlist-macro-action"></a>ImportSharePointList 宏操作

**适用于**：Access 2013、Office 2013

可以使用 **ImportSharePointList** 操作从 Microsoft SharePoint Foundation 网站导入或链接数据。

> [!NOTE]
> [!注释] 如果数据库不受信任，将不允许此操作。 

## <a name="setting"></a>设置

**ImportSharePointList** 操作具有下列参数。

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>操作参数</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>迁移类型</strong></p></td>
<td><p>请选择迁移类型。</p>
<ul>
<li><p>选择 "<strong>导入</strong>", 将 SharePoint Foundation 数据复制到 Microsoft Access 中的表中。 Access 中的数据更新不会影响 SharePoint Foundation 中的数据。 同样, 对 SharePoint Foundation 中的数据的更新不会影响 Access 中的数据。</p></li>
<li><p>选择 "<strong>链接</strong>" 可在 Access 中创建链接到 SharePoint Foundation 中的数据的链接表。 对 Access 中的数据的更新反映在 SharePoint Foundation 中。 同样, 对 SharePoint Foundation 中的数据的更新会在 Access 中反映出来。</p></li>
</ul>
<p></p></td>
</tr>
<tr class="even">
<td><p><strong>网站地址</strong></p></td>
<td><p>请输入 SharePoint 网站的完整路径。</p></td>
</tr>
<tr class="odd">
<td><p><strong>列表 ID</strong></p></td>
<td><p>请输入要迁移的列表的名称或 GUID。 此参数是必选的。</p></td>
</tr>
<tr class="even">
<td><p><strong>视图 ID</strong></p></td>
<td><p>请输入要使用的列表的视图的 GUID。将此参数留空可迁移列表中的所有行和列。</p></td>
</tr>
<tr class="odd">
<td><p><strong>表格名称</strong></p></td>
<td><p>请输入要在 Access 中显示的表或链接表的名称。</p></td>
</tr>
<tr class="even">
<td><p><strong>获取查阅的显示值</strong></p></td>
<td><p>选择<strong>“是”</strong>可迁移查阅字段的显示值而不是用于执行查阅的 ID。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>注解

- 此操作等效于单击 **"外部数据"** 选项卡上的 **"导入"** 组中的 **"SharePoint 列表"**。该操作的参数与在"获取外部数据向导"中的选择相对应。

- 若要在 VBA 模块中运行 **ImportSharePointList** 操作，请使用 **DoCmd** 对象的 **TransferSharePointList** 方法。

- 如果指定了不存在的列表或视图，不会产生任何错误，也不会传输任何数据。

- GUID 是列表或视图的唯一的十六进制标识符。GUID 必须按以下格式输入，此处的"F"是一个十六进制数字（0 到 9 或 A 到 F）。
    
  `{FFFFFFFF-FFFF-FFFF-FFFF-FFFFFFFFFFFF}`
    
  可以利用以下过程从 SharePoint 网站获得列表或视图的 GUID：
    
  1. 打开 SharePoint Foundation 中的列表。
    
  2. 如果未显示所需的视图，请单击 **"视图"** 下拉箭头，然后选择所需的视图。
    
  3. 单击 "**视图**" 下拉箭头, 然后选择 "**修改此视图**"。浏览器地址栏中的地址包含列表和视图的 guid。 列表的 guid 如下所示****, 视图的 guid 如下所示: **view =**。 但是, 在地址中, 每个 **{** (左大括号) 字符都由字符串 **% 7b**表示, **-** 每 (连字符) 字符由字符串 **% 2d**表示, 每个 **}** (右大括号) 字符由字符串表示 **% 7d**。 例如：
        
     `https://MySite12/_layouts/ViewEdit.aspx?List=%7B2A82A404%2D5529%2D47DC%2DAE13%2DAC1D9BC0A84F%7D&View=%7B357B4FE6%2D44CF%2D4275%2DB91F%2D46558301579B%7D`
        
  必须将每个 **% 7b**字符串替换为 **{** 字符, 并将每个% 的**2d**字符串替换为**-** 字符, 然后将每个% **7d**字符串替换为 **}** 字符。 请勿在列表 GUID **&** 中包含跟在 **% 7d**字符串后面的 (与号) 字符。

