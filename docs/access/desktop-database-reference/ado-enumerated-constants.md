---
title: ADO 枚举常量
TOCTitle: ADO enumerated constants
ms:assetid: 7c983acd-8b38-dc3c-6704-46e649ebb7d6
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249522(v=office.15)
ms:contentKeyID: 48545841
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 05e5d3a77dc7db5ef5a0d81a3f13d5fc5987f5de
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28707938"
---
# <a name="ado-enumerated-constants"></a>ADO 枚举常量

**适用于**： Access 2013、 Office 2013

为了有助于进行调试，ADO 枚举将列出每个常量的值。但是，此值仅仅是建议性的，不同的 ADO 版本可能会各不相同。代码应当只依赖于每个枚举常量的名称，而不是实际值。

<br/>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="even">
<th>枚举的常量</th>
<th>说明</th>
</tr>
<tr class="odd">
<td><p><a href="adcprop-asyncthreadpriority-enum.md">ADCPROP_ASYNCTHREADPRIORITY_ENUM</a></p></td>
<td><p>对于 RDS <strong>Recordset</strong> 对象，指定用于检索数据的异步线程的执行优先级。</p></td>
</tr>
<tr class="even">
<td><p><a href="adcprop-autorecalc-enum.md">ADCPROP_AUTORECALC_ENUM</a></p></td>
<td><p>指定<strong>MSDataShape</strong>提供程序何时重新计算分层<strong>Recordset</strong>中的聚合和计算列。</p></td>
</tr>
<tr class="odd">
<td><p><a href="adcprop-updatecriteria-enum.md">ADCPROP_UPDATECRITERIA_ENUM</a></p></td>
<td><p>指定在使用 <strong>Recordset</strong> 对象来对数据源中的行进行开放式更新期间可以用哪些字段来检测冲突。</p></td>
</tr>
<tr class="even">
<td><p><a href="adcprop-updateresync-enum.md">ADCPROP_UPDATERESYNC_ENUM</a></p></td>
<td><p>指定 <strong>UpdateBatch</strong> 方法后面是否跟随隐式的 <strong>Resync</strong> 方法操作，如果跟随，则指定该操作的范围。</p></td>
</tr>
<tr class="odd">
<td><p><a href="affectenum.md">AffectEnum</a></p></td>
<td><p>指定操作会影响哪些记录。</p></td>
</tr>
<tr class="even">
<td><p><a href="bookmarkenum.md">BookmarkEnum</a></p></td>
<td><p>指定一个书签，以指示操作应开始的位置。</p></td>
</tr>
<tr class="odd">
<td><p><a href="commandtypeenum.md">CommandTypeEnum</a></p></td>
<td><p>指定应当如何解释命令参数。</p></td>
</tr>
<tr class="even">
<td><p><a href="compareenum.md">CompareEnum</a></p></td>
<td><p>指定通过记录书签表示的两个记录的相对位置。</p></td>
</tr>
<tr class="odd">
<td><p><a href="connectmodeenum.md">ConnectModeEnum</a></p></td>
<td><p>指定可用于执行以下操作的权限：修改 <strong>Connection</strong> 中的数据、打开 <strong>Record</strong>，或指定 <strong>Record</strong> 和 <strong>Stream</strong> 对象的 <strong>Mode</strong> 属性的值。</p></td>
</tr>
<tr class="even">
<td><p><a href="connectoptionenum.md">ConnectOptionEnum</a></p></td>
<td><p>指定在建立连接之后（同步）或之前（异步）是否应返回 <strong>Connection</strong> 对象的 <strong>Open</strong> 方法。</p></td>
</tr>
<tr class="odd">
<td><p><a href="connectpromptenum.md">ConnectPromptEnum</a></p></td>
<td><p>指定在打开与 ODBC 数据源的连接时，是否应当显示对话框，提示输入缺少的参数。</p></td>
</tr>
<tr class="even">
<td><p><a href="copyrecordoptionsenum.md">CopyRecordOptionsEnum</a></p></td>
<td><p>指定 <strong>CopyRecord</strong> 方法的行为。</p></td>
</tr>
<tr class="odd">
<td><p><a href="cursorlocationenum.md">CursorLocationEnum</a></p></td>
<td><p>指定游标引擎的位置。</p></td>
</tr>
<tr class="even">
<td><p><a href="cursoroptionenum.md">CursorOptionEnum</a></p></td>
<td><p>指定应针对哪项功能来测试 <strong>Supports</strong> 方法。</p></td>
</tr>
<tr class="odd">
<td><p><a href="cursortypeenum.md">CursorTypeEnum</a></p></td>
<td><p>指定在 <strong>Recordset</strong> 对象中使用的游标的类型。</p></td>
</tr>
<tr class="even">
<td><p><a href="datatypeenum.md">DataTypeEnum</a></p></td>
<td><p>用于指定 <strong>Field</strong>、<strong>Parameter</strong> 或 <strong>Property</strong> 的数据类型。</p></td>
</tr>
<tr class="odd">
<td><p><a href="editmodeenum.md">EditModeEnum</a></p></td>
<td><p>指定记录的编辑状态。</p></td>
</tr>
<tr class="even">
<td><p><a href="errorvalueenum.md">ErrorValueEnum</a></p></td>
<td><p>指定 ADO 运行时错误的类型。</p></td>
</tr>
<tr class="odd">
<td><p><a href="eventreasonenum.md">EventReasonEnum</a></p></td>
<td><p>指定导致事件发生的原因。</p></td>
</tr>
<tr class="even">
<td><p><a href="eventstatusenum.md">EventStatusEnum</a></p></td>
<td><p>指定事件执行的当前状态。</p></td>
</tr>
<tr class="odd">
<td><p><a href="executeoptionenum.md">ExecuteOptionEnum</a></p></td>
<td><p>指定提供程序应当如何执行命令。</p></td>
</tr>
<tr class="even">
<td><p><a href="fieldenum.md">FieldEnum</a></p></td>
<td><p>指定在 <strong>Record</strong> 对象的 <strong>Fields</strong> 集合中引用的特殊字段。</p></td>
</tr>
<tr class="odd">
<td><p><a href="fieldattributeenum.md">FieldAttributeEnum</a></p></td>
<td><p>指定 <strong>Field</strong> 对象的一个或多个属性。</p></td>
</tr>
<tr class="even">
<td><p><a href="fieldstatusenum.md">FieldStatusEnum</a></p></td>
<td><p>指定 <strong>Field</strong> 对象的状态。</p></td>
</tr>
<tr class="odd">
<td><p><a href="filtergroupenum.md">FilterGroupEnum</a></p></td>
<td><p>指定要从 <strong>Recordset</strong> 中筛选的记录组。</p></td>
</tr>
<tr class="even">
<td><p><a href="getrowsoptionenum.md">GetRowsOptionEnum</a></p></td>
<td><p>指定要从 <strong>Recordset</strong> 中检索多少记录。</p></td>
</tr>
<tr class="odd">
<td><p><a href="isolationlevelenum.md">IsolationLevelEnum</a></p></td>
<td><p>指定 <strong>Connection</strong> 对象的事务隔离级别。</p></td>
</tr>
<tr class="even">
<td><p><a href="lineseparatorsenum.md">LineSeparatorsEnum</a></p></td>
<td><p>指定在文本 <strong>Stream</strong> 对象中用作行分隔符的字符。</p></td>
</tr>
<tr class="odd">
<td><p><a href="locktypeenum.md">LockTypeEnum</a></p></td>
<td><p>指定在编辑过程中对记录设置的锁定类型。</p></td>
</tr>
<tr class="even">
<td><p><a href="marshaloptionsenum.md">MarshalOptionsEnum</a></p></td>
<td><p>指定哪些记录应当返回到服务器。</p></td>
</tr>
<tr class="odd">
<td><p><a href="moverecordoptionsenum.md">MoveRecordOptionsEnum</a></p></td>
<td><p>指定 <strong>Record</strong> 对象的 <strong>MoveRecord</strong> 方法的行为。</p></td>
</tr>
<tr class="even">
<td><p><a href="objectstateenum.md">ObjectStateEnum</a></p></td>
<td><p>指定对象是否处于以下状态：打开还是关闭、正在连接到数据源、正在执行命令、或正在获取数据。</p></td>
</tr>
<tr class="odd">
<td><p><a href="parameterattributesenum.md">ParameterAttributesEnum</a></p></td>
<td><p>指定 <strong>Parameter</strong> 对象的属性。</p></td>
</tr>
<tr class="even">
<td><p><a href="parameterdirectionenum.md">ParameterDirectionEnum</a></p></td>
<td><p>指定 <strong>Parameter</strong> 是否表示输入参数和/或输出参数，以及参数是否是存储过程的返回值。</p></td>
</tr>
<tr class="odd">
<td><p><a href="persistformatenum.md">PersistFormatEnum</a></p></td>
<td><p>指定保存 <strong>Recordset</strong> 时所用的格式。</p></td>
</tr>
<tr class="even">
<td><p><a href="positionenum.md">PositionEnum</a></p></td>
<td><p>指定在 <strong>Recordset</strong> 中记录指针的当前位置。</p></td>
</tr>
<tr class="odd">
<td><p><a href="propertyattributesenum.md">PropertyAttributesEnum</a></p></td>
<td><p>指定 <strong>Property</strong> 对象的属性。</p></td>
</tr>
<tr class="even">
<td><p><a href="recordcreateoptionsenum.md">RecordCreateOptionsEnum</a></p></td>
<td><p>指定对于 <strong>Record</strong> 对象的 <strong>Open</strong> 方法，是应当打开现有 <strong>Record</strong>，还是应当创建新的 <strong>Record</strong>。</p></td>
</tr>
<tr class="odd">
<td><p><a href="recordopenoptionsenum.md">RecordOpenOptionsEnum</a></p></td>
<td><p>指定用于打开 <strong>Record</strong> 的选项。可以使用 OR 运算符将这些值组合在一起。</p></td>
</tr>
<tr class="even">
<td><p><a href="recordstatusenum.md">RecordStatusEnum</a></p></td>
<td><p>指定记录的批更新和其他批量操作的状态。</p></td>
</tr>
<tr class="odd">
<td><p><a href="recordtypeenum.md">RecordTypeEnum</a></p></td>
<td><p>指定 <strong>Record</strong> 对象的类型。</p></td>
</tr>
<tr class="even">
<td><p><a href="resyncenum.md">ResyncEnum</a></p></td>
<td><p>指定是否通过调用 <strong>Resync</strong> 来覆盖基础值。</p></td>
</tr>
<tr class="odd">
<td><p><a href="saveoptionsenum.md">SaveOptionsEnum</a></p></td>
<td><p>指定当从 <strong>Stream</strong> 对象进行保存时，应创建文件还是覆盖文件。可以使用 AND 运算符来组合使用这些值。</p></td>
</tr>
<tr class="even">
<td><p><a href="schemaenum.md">SchemaEnum</a></p></td>
<td><p>指定 <strong>OpenSchema</strong> 方法所检索的架构 <strong>Recordset</strong> 的类型。指定在 <strong>Recordset</strong> 内进行记录搜索的方向。</p></td>
</tr>
<tr class="odd">
<td><p><a href="searchdirectionenum.md">SearchDirectionEnum</a></p></td>
<td><p>指定在 <strong>Recordset</strong> 中进行记录搜索的方向。指定要执行的 <strong>Seek</strong> 的类型。</p></td>
</tr>
<tr class="even">
<td><p><a href="seekenum.md">SeekEnum</a></p></td>
<td><p>指定要执行的 <strong>Seek</strong> 的类型。指定用于打开 <strong>Stream</strong> 对象的选项。该值可以与 AND 运算符组合。</p></td>
</tr>
<tr class="odd">
<td><p><a href="streamopenoptionsenum.md">StreamOpenOptionsEnum</a></p></td>
<td><p>指定用于打开 <strong>Stream</strong> 对象的选项。这些值可以与 AND 运算符组合。指定应当从 <strong>Stream</strong> 对象读取整个流还是下一行。</p></td>
</tr>
<tr class="even">
<td><p><a href="streamreadenum.md">StreamReadEnum</a></p></td>
<td><p>指定应当从 <strong>Stream</strong> 对象读取整个流还是下一行。指定存储在 <strong>Stream</strong> 对象中的数据的类型。</p></td>
</tr>
<tr class="odd">
<td><p><a href="streamtypeenum.md">StreamTypeEnum</a></p></td>
<td><p>指定存储在 <strong>Stream</strong> 对象中的数据的类型。指定是否将行分隔符追加到写入 <strong>Stream</strong> 对象的字符串。</p></td>
</tr>
<tr class="even">
<td><p><a href="streamwriteenum.md">StreamWriteEnum</a></p></td>
<td><p>指定是否将行分隔符追加到写入 <strong>Stream</strong> 对象的字符串。指定检索 <strong>Recordset</strong> 时的格式为字符串。</p></td>
</tr>
<tr class="odd">
<td><p><a href="stringformatenum.md">StringFormatEnum</a></p></td>
<td><p>指定检索 <strong>Recordset</strong> 时的格式为字符串。指定 <strong>Connection</strong> 对象的事务属性。</p></td>
</tr>
<tr class="even">
<td><p><a href="xactattributeenum.md">XactAttributeEnum</a></p></td>
<td><p>指定 <strong>Connection</strong> 对象的事务属性。</p></td>
</tr>
</tbody>
</table>

