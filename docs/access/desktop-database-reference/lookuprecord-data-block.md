---
title: LookupRecord 数据块
TOCTitle: LookupRecord data block
ms:assetid: 750dc8ca-3bab-c3d1-c91d-2196f9c0604d
ms:mtpsurl: https://msdn.microsoft.com/library/Ff195882(v=office.15)
ms:contentKeyID: 48545671
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 920f0830a310452962eb5dd1c21be63215bf0f03
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32289789"
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
<td><p>一个用于标识要对其执行操作的记录的字符串。 <em>In</em>参数可以包含表、选择查询或 SQL 语句的名称。</p><p><strong>注意</strong>: 指定的记录不能包含存储在链接表或 ODBC 数据源中的数据。</p></td>
</tr>
<tr class="even">
<td><p>Where Condition</p></td>
<td><p>否</p></td>
<td><p>一个字符串表达式，用于限制对其执行 <strong>LookupRecord</strong> 数据块的数据的范围。 例如, 条件通常等效于 SQL 表达式中的 where 子句, 而不带单词 WHERE。 如果省略条件, 则<strong>LookupRecord</strong>数据块在由<em>In</em>参数指定的整个域上运行。 条件中包括的所有字段还必须是 <em>In</em> 中的字段。</p></td>
</tr>
<tr class="odd">
<td><p>别名</p></td>
<td><p>否</p></td>
<td><p>为<em>In</em>参数所指定的记录提供可选名称的字符串。 通常用于缩短后续引用的表名称，以防止可能出现的不明引用。 如果不指定 <em>Alias</em>，则会将表或查询名称用作别名。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>注解

如果*In*和*Where Condition*参数指定的条件指定了多条记录, **LookupRecord**数据块将只对第一条记录执行操作。

## <a name="example"></a>示例

下面的示例演示如何使用 SetReturnVar 操作从已命名的数据宏中返回值。 名为**CurrentServiceRequest**的 ReturnVar 返回给宏或 Visual Basic for Applications (VBA) 子例程, 该子例程称为已命名的数据宏。

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

下面的示例演示如何使用 RaiseError 操作取消 Before Change data 宏事件。 更新 "分配" 字段后, 将使用 LookupRecord 数据块确定分配的技术人员当前是否已分配给打开的服务请求。 如果为 true, 则取消 "更改前" 事件且不更新记录。

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
