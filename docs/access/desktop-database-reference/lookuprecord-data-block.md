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
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28716010"
---
# <a name="lookuprecord-data-block"></a>LookupRecord 数据块

**适用于**： Access 2013、 Office 2013

**LookupRecord** 数据块可对特定记录执行一组操作。

> [!NOTE]
> [!注释] **LookupRecord** 数据块仅适用于数据宏。

## <a name="setting"></a>设置

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
<th><p>是否必需</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>在</p></td>
<td><p>是</p></td>
<td><p>一个字符串，标识的记录执行操作。 <em>在</em>参数可以包含表、 选择查询或 SQL 语句的名称。</p><p><strong>注意</strong>： 指定的记录不能包括链接的表或 ODBC 数据源中存储的数据。</p></td>
</tr>
<tr class="even">
<td><p>Where Condition</p></td>
<td><p>否</p></td>
<td><p>执行字符串表达式，用来限制在其上的数据区域<strong>LookupRecord</strong>数据块。 例如，条件是通常等同于在 SQL 表达式中，没有单词 WHERE 子句其中。 如果条件都被忽略， <strong>LookupRecord</strong>数据块运行上指定<em>中</em>参数的整个域。 条件中包括的任何字段必须同时是<em>中</em>的字段。</p></td>
</tr>
<tr class="odd">
<td><p>Alias</p></td>
<td><p>否</p></td>
<td><p>提供<em>在</em>参数指定的记录的替代名称的字符串。 通常用于缩短后续参考，以防止可能出现的不明确引用的表名称。 如果不指定 <em>Alias</em>，则会将表或查询名称用作别名。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>备注

如果*在*和*Where Condition*参数指定的条件指定多个记录， **LookupRecord**数据块将操作仅在第一条记录上。

## <a name="example"></a>示例

下面的示例演示如何使用 SetReturnVar 操作从已命名的数据宏返回值。 名为**CurrentServiceRequest** ReturnVar 调用已命名的数据宏的 Applications (VBA) 子例程返回到宏或 Visual Basic。

**示例代码提供者** [Microsoft Access 2010 Programmer's Reference](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125)。

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

下面的示例演示如何使用 RaiseError 操作取消 Before Change 数据宏事件。 更新 AssignedTo 字段时，LookupRecord 数据块用于确定是否已分配的技术人员当前分配给打开服务请求。 如果是这样，取消 Before Change 事件并不会更新记录。

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
