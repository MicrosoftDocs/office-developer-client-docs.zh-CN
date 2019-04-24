---
title: CursorOptionEnum (Access desktop database reference)
TOCTitle: CursorOptionEnum
ms:assetid: 3c118c08-02f2-5290-1cef-29e97c35fddc
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249155(v=office.15)
ms:contentKeyID: 48544303
ms.date: 10/18/2018
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 7443e0cb29954fae9dfc193ffc6aa8dee9886089
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32295196"
---
# <a name="cursoroptionenum"></a>CursorOptionEnum

**适用于**：Access 2013、Office 2013

指定应针对哪项功能来测试 [Supports](supports-method-ado.md) 方法。

<br/>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>常量</p></th>
<th><p>值</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>adAddNew</strong></p></td>
<td><p>0x1000400</p></td>
<td><p>支持 <a href="addnew-method-ado.md">AddNew</a> 方法以添加新记录。</p></td>
</tr>
<tr class="even">
<td><p><strong>adApproxPosition</strong></p></td>
<td><p>0x4000</p></td>
<td><p>支持 <a href="absoluteposition-property-ado.md">AbsolutePosition</a> 和 <a href="absolutepage-property-ado.md">AbsolutePage</a> 属性。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adBookmark</strong></p></td>
<td><p>0x2000</p></td>
<td><p>支持 <a href="bookmark-property-ado.md">Bookmark</a> 属性以获取对特定记录的访问权限。</p></td>
</tr>
<tr class="even">
<td><p><strong>adDelete</strong></p></td>
<td><p>0x1000800</p></td>
<td><p>支持 <a href="delete-method-ado-recordset.md">Delete</a> 方法以删除记录。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adFind</strong></p></td>
<td><p>0x80000</p></td>
<td><p>支持 <a href="find-method-ado.md">Find</a> 方法以便在 <a href="recordset-object-ado.md">Recordset</a> 中查找行。</p></td>
</tr>
<tr class="even">
<td><p><strong>adHoldRecords</strong></p></td>
<td><p>0x100</p></td>
<td><p>检索多个记录或更改下一个位置（不提交所有挂起更改）。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adIndex</strong></p></td>
<td><p>0x100000</p></td>
<td><p>支持 <a href="index-property-ado.md">Index</a> 属性以命名索引。</p></td>
</tr>
<tr class="even">
<td><p><strong>带有 admoveprevious</strong></p></td>
<td><p>0x200</p></td>
<td><p>支持 <a href="movefirst-movelast-movenext-and-moveprevious-methods-ado.md">MoveFirst</a> 和 <a href="movefirst-movelast-movenext-and-moveprevious-methods-ado.md">MovePrevious</a> 方法，以及 <a href="move-method-ado.md">Move</a> 或 <a href="getrows-method-ado.md">GetRows</a> 方法，以便向后移动当前记录位置而不需要书签。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adNotify</strong></p></td>
<td><p>0x40000</p></td>
<td><p>指示基础数据提供程序支持通知（用于确定是否支持 <strong>Recordset</strong> 事件）。</p></td>
</tr>
<tr class="even">
<td><p><strong>adResync</strong></p></td>
<td><p>0x20000</p></td>
<td><p>支持 <a href="resync-method-ado.md">Resync</a> 方法，以使用在基础数据库中可见的数据来更新游标。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adSeek</strong></p></td>
<td><p>0x200000</p></td>
<td><p>支持 <a href="seek-method-ado.md">Seek</a> 方法，以便在 <strong>Recordset</strong> 中查找行。</p></td>
</tr>
<tr class="even">
<td><p><strong>adUpdate</strong></p></td>
<td><p>0x1008000</p></td>
<td><p>支持 <a href="update-method-ado.md">Update</a> 方法以修改现有数据。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adUpdateBatch</strong></p></td>
<td><p>0x10000</p></td>
<td><p>支持批更新（<a href="updatebatch-method-ado.md">UpdateBatch</a> 和 <a href="cancelbatch-method-ado.md">CancelBatch</a> 方法），以便将成组更改传输到提供程序。</p></td>
</tr>
</tbody>
</table>


### <a name="adowfc-equivalent"></a>ADO/WFC 等效项

包：**com.ms.wfc.data**

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p>常量</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>AdoEnums CursorOption</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums CursorOption</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums CursorOption</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums CursorOption</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums. CursorOption</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums CursorOption</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums CursorOption</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums CursorOption</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums CursorOption</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums CursorOption</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums CursorOption</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums CursorOption</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums CursorOption</p></td>
</tr>
</tbody>
</table>

