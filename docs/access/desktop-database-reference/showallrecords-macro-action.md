---
title: ShowAllRecords 宏操作
TOCTitle: ShowAllRecords macro action
ms:assetid: 6f9741ad-0440-4b8d-abea-009063c111f8
ms:mtpsurl: https://msdn.microsoft.com/library/Ff195587(v=office.15)
ms:contentKeyID: 48545538
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: c4ea531de8c5b99c9ff85eacddcc79a596caebd5
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25922039"
---
# <a name="showallrecords-macro-action"></a>ShowAllRecords 宏操作


**适用于**： Access 2013、 Office 2013


您可以使用**ShowAllRecords**操作从活动表、 查询结果集或窗体中，删除任何应用的筛选和显示在表或结果集或窗体的基础表或查询中的所有记录的所有记录。

## <a name="setting"></a>设置

**ShowAllRecords**操作不具有任何参数。

## <a name="remarks"></a>说明

此操作可用于确保表、 查询结果集，或窗体显示 （包括任何已更改或新记录） 的所有记录。 此操作会重新查询窗体或子窗体的记录。

您还可以使用此操作删除与**ApplyFilter**操作，**主页**选项卡或**筛选器名称**或**Where Condition**参数**OpenForm**操作的**筛选器**命令应用的任何筛选器。

此操作的效果为单击的**主页**选项卡上，**切换筛选**或右键单击筛选的字段和窗体视图、 布局视图或数据表视图中，单击 **...清除从筛选器**。

若要在 Visual Basic for Applications (VBA) 模块中运行**ShowAllRecords**操作，请使用**DoCmd**对象的**ShowAllRecords**方法。

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
<th><p>注释</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>[公司名称筛选] = 1</p></td>
<td><p><strong>ApplyFilter</strong></p></td>
<td><p><strong>Where 条件</strong>: [公司名称] 像&quot;[AÀÁÂÃÄ] *&quot;</p></td>
<td><p>筛选以 A、À、Á、Â、Ã 或 Ä 开头的公司名称。</p></td>
</tr>
<tr class="even">
<td><p>[公司名称筛选] = 2</p></td>
<td><p><strong>ApplyFilter</strong></p></td>
<td><p><strong>Where 条件</strong>: [公司名称] 像&quot;B *&quot;</p></td>
<td><p>筛选以 B 开头的公司名称。</p></td>
</tr>
<tr class="odd">
<td><p>[公司名称筛选] = 3</p></td>
<td><p><strong>ApplyFilter</strong></p></td>
<td><p><strong>Where 条件</strong>: [公司名称] 像&quot;[CÇ] *&quot;</p></td>
<td><p>筛选以 C 或 Ç 开头的公司名称。</p></td>
</tr>
<tr class="even">
<td><p>... D 到 Y 的操作行与 A 到 C 的操作行具有相同的格式 ...</p></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p>[公司名称筛选] = 26</p></td>
<td><p><strong>ApplyFilter</strong></p></td>
<td><p><strong>Where 条件</strong>: [公司名称] 像&quot;[ZÆØÅ] *&quot;</p></td>
<td><p>筛选以 Z、Æ、Ø 或 Å 开头的公司名称。</p></td>
</tr>
<tr class="even">
<td><p>[公司名称筛选] = 27</p></td>
<td><p><strong>ShowAllRecords</strong></p></td>
<td><p></p></td>
<td><p>显示所有记录。</p></td>
</tr>
<tr class="odd">
<td><p>[RecordsetClone]。[RecordCount]&gt;0</p></td>
<td><p><strong>GoToControl</strong></p></td>
<td><p><strong>控件名称</strong>： 公司名称</p></td>
<td><p>如果返回了针对所选字母的记录，则将焦点移到“公司名称”控件上。</p></td>
</tr>
</tbody>
</table>

