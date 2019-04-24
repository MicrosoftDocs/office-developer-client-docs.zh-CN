---
title: ShowAllRecords 宏操作
TOCTitle: ShowAllRecords macro action
ms:assetid: 6f9741ad-0440-4b8d-abea-009063c111f8
ms:mtpsurl: https://msdn.microsoft.com/library/Ff195587(v=office.15)
ms:contentKeyID: 48545538
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 201b284a56fbd3030b41a95424b41c73ee13e385
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32308643"
---
# <a name="showallrecords-macro-action"></a>ShowAllRecords 宏操作


**适用于**：Access 2013、Office 2013


您可以使用**ShowAllRecords**操作从活动表、查询结果集或窗体中删除任何已应用的筛选, 并显示表或结果集中的所有记录, 或者窗体的基础表或查询中的所有记录。

## <a name="setting"></a>Setting

**ShowAllRecords**操作不具有任何参数。

## <a name="remarks"></a>注解

您可以使用此操作来确保为表、查询结果集或窗体显示所有记录 (包括任何已更改或新记录)。 此操作会对窗体或子窗体的记录进行重新查询。

您还可以使用此操作删除应用于**ApplyFilter**操作的任何筛选器、"**开始**" 选项卡上的 "**筛选**" 命令或 "**筛选器名称**" 或 "在**OpenForm** " 操作的 " **Where 条件**" 参数。

此操作等效于单击 "**开始**" 选项卡上的 "**切换筛选**", 或右键单击筛选字段, 然后单击 "窗体" 视图、"布局视图" 或 "数据表视图" 中的 "**清除筛选 ...** "。

若要在 Visual Basic for Applications (VBA) 模块中运行**ShowAllRecords**操作, 请使用**DoCmd**对象的**ShowAllRecords**方法。

## <a name="example"></a>示例

**使用宏应用筛选**

下面的宏包含一组操作，其中每项操作都会对"客户电话列表"窗体中的记录进行筛选。它演示如何使用 **ApplyFilter** 、 **ShowAllRecords** 和 **GoToControl** 操作。它还演示了如何使用条件来确定已在窗体的选项组中选择了哪个切换按钮。每个操作行都与一个切换按钮相关联，这些切换按钮分别用于选择以 A、B、C 等字母开头的一组记录或所有记录。此宏应附加到 CompanyNameFilter 选项组的 **AfterUpdate** 事件。

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p>条件</p></th>
<th><p>操作</p></th>
<th><p>参数：设置</p></th>
<th><p>Comment</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>[公司名称筛选器] = 1</p></td>
<td><p><strong>ApplyFilter</strong></p></td>
<td><p><strong>Where 条件</strong>: [公司名称] Like &quot;[AÀÁÂÃÄ] *&quot;</p></td>
<td><p>筛选以 A、À、Á、Â、Ã 或 Ä 开头的公司名称。</p></td>
</tr>
<tr class="even">
<td><p>[公司名称筛选器] = 2</p></td>
<td><p><strong>ApplyFilter</strong></p></td>
<td><p><strong>Where 条件</strong>: [公司名称] Like &quot;B *&quot;</p></td>
<td><p>筛选以 B 开头的公司名称。</p></td>
</tr>
<tr class="odd">
<td><p>[公司名称筛选器] = 3</p></td>
<td><p><strong>ApplyFilter</strong></p></td>
<td><p><strong>Where 条件</strong>: [公司名称] Like &quot;[CÇ] *&quot;</p></td>
<td><p>筛选以 C 或 Ç 开头的公司名称。</p></td>
</tr>
<tr class="even">
<td><p>... D 到 Y 的操作行与 A 到 C 的操作行具有相同的格式 ...</p></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p>[公司名称筛选器] = 26</p></td>
<td><p><strong>ApplyFilter</strong></p></td>
<td><p><strong>Where 条件</strong>: [公司名称] Like &quot;[ZÆØÅ] *&quot;</p></td>
<td><p>筛选以 Z、Æ、Ø 或 Å 开头的公司名称。</p></td>
</tr>
<tr class="even">
<td><p>[公司名称筛选器] = 27</p></td>
<td><p><strong>ShowAllRecords</strong></p></td>
<td><p></p></td>
<td><p>显示所有记录。</p></td>
</tr>
<tr class="odd">
<td><p>[RecordsetClone]。RecordCount&gt;0</p></td>
<td><p><strong>GoToControl</strong></p></td>
<td><p><strong>控件名称</strong>: 公司名称</p></td>
<td><p>如果返回了针对所选字母的记录，则将焦点移到“公司名称”控件上。</p></td>
</tr>
</tbody>
</table>

