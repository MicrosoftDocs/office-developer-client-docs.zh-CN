---
title: FieldStatusEnum （访问桌面数据库参考 （英文）
TOCTitle: FieldStatusEnum
ms:assetid: 49570042-8435-8618-3ba1-7006c47735e0
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249225(v=office.15)
ms:contentKeyID: 48544635
ms.date: 10/18/2018
mtps_version: v=office.15
ms.openlocfilehash: 007daa84e15b79d6aa82e4e1e75b1c3d2b0901ce
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25867921"
---
# <a name="fieldstatusenum"></a>FieldStatusEnum

**适用于**： Access 2013、 Office 2013

指定 **Field** 对象的状态。

**adFieldPending\*** 值指示导致设置状态的操作，可以与其他状态值一起使用。

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
<td><p><strong>adFieldAlreadyExists</strong></p></td>
<td><p>26</p></td>
<td><p>指示指定的字段已经存在。</p></td>
</tr>
<tr class="even">
<td><p><strong>adFieldBadStatus</strong></p></td>
<td><p>12</p></td>
<td><p>指示从 ADO 向 OLE DB 提供程序发送了无效的状态值。可能的原因包括 OLE DB 提供程序的版本是 1.0 或 1.1，或者 <a href="value-property-ado.md">Value 属性 (ADO)</a> 和 <a href="status-property-ado-field.md">Status 属性 (ADO Field)</a> 的组合不正确。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adFieldCannotComplete</strong></p></td>
<td><p>20</p></td>
<td><p>指示由 <a href="source-property-ado-record.md">Source 属性 (ADO Record)</a> 指定的 URL 的服务器无法完成操作。</p></td>
</tr>
<tr class="even">
<td><p><strong>adFieldCannotDeleteSource</strong></p></td>
<td><p>23</p></td>
<td><p>指示在移动操作期间，将树或子树移动到了新位置，但无法删除源。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adFieldCantConvertValue</strong></p></td>
<td><p>2</p></td>
<td><p>指示由于丢失数据而无法检索或存储字段。</p></td>
</tr>
<tr class="even">
<td><p><strong>adFieldCantCreate</strong></p></td>
<td><p>7</p></td>
<td><p>指示无法添加字段，因为提供程序超过了限制（如允许的字段数）。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adFieldDataOverflow</strong></p></td>
<td><p>6</p></td>
<td><p>指示从提供程序返回的数据使字段的数据类型发生溢出。</p></td>
</tr>
<tr class="even">
<td><p><strong>adFieldDefault</strong></p></td>
<td><p>13</p></td>
<td><p>指示在设置数据时使用字段的默认值。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adFieldDoesNotExist</strong></p></td>
<td><p>16</p></td>
<td><p>指示指定的字段不存在。</p></td>
</tr>
<tr class="even">
<td><p><strong>adFieldIgnore</strong></p></td>
<td><p>15</p></td>
<td><p>指示在设置数据源中的数据值时已跳过此字段。提供程序未设置值。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adFieldIntegrityViolation</strong></p></td>
<td><p>10</p></td>
<td><p>指示无法修改字段，因为它是计算得出的实体或派生实体。</p></td>
</tr>
<tr class="even">
<td><p><strong>adFieldInvalidURL</strong></p></td>
<td><p>17</p></td>
<td><p>指示数据源 URL 包含无效字符。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adFieldIsNull</strong></p></td>
<td><p>3</p></td>
<td><p>指示提供程序返回了类型为 VT_NULL 的 VARIANT 值，并且此字段非空。</p></td>
</tr>
<tr class="even">
<td><p><strong>adFieldOK</strong></p></td>
<td><p>0</p></td>
<td><p>默认值。指示此字段已成功添加或删除。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adFieldOutOfSpace</strong></p></td>
<td><p>22</p></td>
<td><p>指示提供程序无法获取足够的存储空间来完成移动或复制操作。</p></td>
</tr>
<tr class="even">
<td><p><strong>adFieldPendingChange</strong></p></td>
<td><p>而 0x40000 可</p></td>
<td><p>指示此字段已被删除然后重新添加（可能使用不同的数据类型）过，或者以前具有 adFieldOK 状态的此字段的值已被更改。在调用 <a href="update-method-ado.md">Update</a> 方法之后，字段的最终形式将修改 <a href="fields-collection-ado.md">Fields</a> 集合。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adFieldPendingDelete</strong></p></td>
<td><p>0x20000</p></td>
<td><p>指示 <strong>Delete</strong> 操作导致设置状态。此字段已标记为在调用 <strong>Update</strong> 方法之后从 <strong>Fields</strong> 集合中删除。</p></td>
</tr>
<tr class="even">
<td><p><strong>adFieldPendingInsert</strong></p></td>
<td><p>0x10000</p></td>
<td><p>指示 <strong>Append</strong> 操作导致设置状态。此<strong>字段</strong>已标记为在调用 <strong>Update</strong> 方法之后添加到 <strong>Fields</strong> 集合中。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adFieldPendingUnknown</strong></p></td>
<td><p>0x80000</p></td>
<td><p>指示提供程序无法确定哪个操作导致设置字段状态。</p></td>
</tr>
<tr class="even">
<td><p><strong>adFieldPendingUnknownDelete</strong></p></td>
<td><p>0x100000</p></td>
<td><p>指示提供程序无法确定哪个操作导致设置字段状态，且在调用 <strong>Update</strong> 方法之后将从 <strong>Fields</strong> 集合中删除此字段。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adFieldPermissionDenied</strong></p></td>
<td><p>9</p></td>
<td><p>指示无法修改此字段，因为它被定义为只读。</p></td>
</tr>
<tr class="even">
<td><p><strong>adFieldReadOnly</strong></p></td>
<td><p>24</p></td>
<td><p>指示数据源中的字段被定义为只读。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adFieldResourceExists</strong></p></td>
<td><p>19</p></td>
<td><p>指示提供程序无法执行此操作，因为目标 URL 中已经存在一个对象，且无法覆盖该字段。</p></td>
</tr>
<tr class="even">
<td><p><strong>adFieldResourceLocked</strong></p></td>
<td><p>18</p></td>
<td><p>指示提供程序无法执行此操作，因为数据源已被一个或多个其他应用程序或进程锁定。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adFieldResourceOutOfScope</strong></p></td>
<td><p>25</p></td>
<td><p>指示源 URL 或目标 URL 在当前记录的范围之外。</p></td>
</tr>
<tr class="even">
<td><p><strong>adFieldSchemaViolation</strong></p></td>
<td><p>11</p></td>
<td><p>指示此值违反了字段的数据源架构约束。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adFieldSignMismatch</strong></p></td>
<td><p>5</p></td>
<td><p>指示提供程序返回的数据值有符号，但 ADO 字段值的数据类型无符号。</p></td>
</tr>
<tr class="even">
<td><p><strong>adFieldTruncated</strong></p></td>
<td><p>4</p></td>
<td><p>指示从数据源进行读取时截断了长度可变的数据。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adFieldUnavailable</strong></p></td>
<td><p>8</p></td>
<td><p>指示当从数据源进行读取时，提供程序无法确定值。例如，只创建了行，列的默认值不可用，并且尚未指定新值。</p></td>
</tr>
<tr class="even">
<td><p><strong>adFieldVolumeNotFound</strong></p></td>
<td><p>21</p></td>
<td><p>指示提供程序无法定位由 URL 指定的存储卷。</p></td>
</tr>
</tbody>
</table>


### <a name="adowfc-equivalent"></a>ADO/WFC 等效值

这些常量没有 ADO/WFC 等效值。

