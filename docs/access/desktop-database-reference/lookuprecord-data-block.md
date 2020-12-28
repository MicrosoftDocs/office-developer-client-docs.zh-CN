---
title: LookupRecord 数据块
TOCTitle: LookupRecord data block
ms:assetid: 750dc8ca-3bab-c3d1-c91d-2196f9c0604d
ms:mtpsurl: https://msdn.microsoft.com/library/Ff195882(v=office.15)
ms:contentKeyID: 48545671
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 7a5cccb77300f36f3e33cd1eccb6c6d278db3120
ms.sourcegitcommit: 0419850d5c1b3439d9da59070201fb4952ca5d07
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/28/2020
ms.locfileid: "49734208"
---
# <a name="lookuprecord-data-block"></a>LookupRecord 数据块

**适用于**：Access 2013、Office 2013

**LookupRecord** 数据块可对特定记录执行一组操作。

> [!NOTE]
> **LookupRecord** 数据块仅适用于数据宏。

## <a name="setting"></a>Setting

**SetField** 操作具有以下参数。

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>参数</p></th>
<th><p>必需</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>在</p></td>
<td><p>是</p></td>
<td><p>一个用于标识要对其执行操作的记录的字符串。 In <em></em>参数可以包含表的名称、选择查询或 SQL 语句。</p><p><strong>注意</strong>：指定的记录不能包括链接表或 ODBC 数据源中存储的数据。</p></td>
</tr>
<tr class="even">
<td><p>Where Condition</p></td>
<td><p>否</p></td>
<td><p>一个字符串表达式，用于限制对其执行 <strong>LookupRecord</strong> 数据块的数据的范围。 例如，条件通常等效于一个无单词 WHERE 的 SQL 表达式中的 WHERE 子句。 如果省略条件 <strong>，LookupRecord</strong> 数据块将运行 In 参数 <em>指定的整个域</em> 。 条件中包括的所有字段还必须是 <em>In</em> 中的字段。</p></td>
</tr>
<tr class="odd">
<td><p>Alias</p></td>
<td><p>否</p></td>
<td><p>为 In 参数指定的记录提供备用 <em>名称的字符串</em> 。 通常用于缩短后续引用的表名称，以防止可能出现的不明引用。 如果不指定 <em>Alias</em>，则会将表或查询名称用作别名。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>备注

如果 In 和Where *条件* 参数指定的条件返回多个记录 **，LookupRecord** 数据块将只对第一条记录进行操作。  如果没有与指定条件匹配的记录，Access 将跳过 **LookupRecord** 块中包含的一组操作，就像它是计算为 false 的 **[If](if-then-else-macro-block.md)** 宏块表达式一样。

## <a name="example"></a>示例

以下示例演示如何使用 SetReturnVar 操作从命名数据宏返回值。 名为 **CurrentServiceRequest** 的 ReturnVar 将返回到宏或Visual Basic for Applications (VBA) 调用命名数据宏的子例程。

**示例代码提供方：**[Microsoft Access 2010 程序员参考](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125)。

```vb
    RunDataMacro
        Macro Name tblServiceRequests.dmGetCurrentServiceRequest
    
    Parameters
        prmAssignedTo =[ID]
    
    SetProperty
        Control Name txtCurrentSR
        Property Value
        Value =[ReturnVars]![CurrentServiceRequest]
```

<br/>

下面的示例演示如何使用 RaiseError 操作取消 Before Change 数据宏事件。 更新 AssignedTo 字段时，LookupRecord 数据块用于确定当前是否将分配的技术人员分配给打开的服务请求。 如果为 true，则取消 Before Change 事件，并且不会更新记录。

```vb
    /* Get the name of the technician  */
    Look Up A Record In tblTechnicians
        Where Condition =[tblTechnicians].[ID]=[tblServiceRequests].[AssignedTo]
    SetLocalVar
        Name TechName
        Expression [tblTechnicians].[FirstName] & " " & [tblTechnicians].[LastName]
    /* End LookUpRecord  */
    
    If Updated("AssignedTo") Then
        Look Up A Record In tblServiceRequests
            Where Condition SR.[AssignedTo]=tblServiceRequests[AssignedTo] And 
                SR.[ID]<>tblServiceRequests.[ID] And IsNull(SR.[ActualCompletionDate])
            Alias SR
            RaiseError
                Error Number 1234
                Error Description ="Cannot assign a request to the specified technician: " & [TechName]
    
    End If
```
