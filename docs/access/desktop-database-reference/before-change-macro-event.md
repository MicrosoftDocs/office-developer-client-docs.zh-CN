---
title: Before Change 宏事件
TOCTitle: Before Change macro event
ms:assetid: da456d55-a773-abeb-1fac-ef58e3331cb5
ms:mtpsurl: https://msdn.microsoft.com/library/Ff835322(v=office.15)
ms:contentKeyID: 48548077
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm19867
dev_langs:
- xml
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: b37fb96ddfeaabc97c6f445f8951876e8026fbfe
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32296855"
---
# <a name="before-change-macro-event"></a>Before Change 宏事件

**适用于**：Access 2013、Office 2013

当记录更改但未提交更改时会发生“更改前”**** 事件。

> [!NOTE]
> “更改前”**** 事件仅适用于数据宏。

## <a name="remarks"></a>注解

使用“更改前”**** 事件可以执行您希望在更改记录前发生的任何操作。“更改前”**** 通常用于执行验证和引发自定义错误消息。

您可以使用**更新的 ("*Field Name*")** 函数来确定字段是否已更改。 下面的代码示例演示如何使用**If**语句来确定 PaidInFull 字段是否已更改。

```vb
    If  Updated("PaidInFull")   Then 
     
        /* Perform actions based on changes to the field.   */ 
     
    End If 
```

使用 **IsInsert** 属性可确定“更改前”**** 事件是由正在创建的新记录触发，还是由对现有记录的更改触发。如果该事件由新记录触发，**IsInsert** 属性将包含 **True**；如果该事件由对现有记录的更改触发，则该属性将包含 **False**。

下面的代码示例演示使用**IsInsert**属性的语法。

```vb
    If   [IsInsert] = True   Then 
     
       /*  Actions for validating a new record go here.       */ 
     
    Else 
     
       /* Actions for processing a changed record go here.    */ 
     
    End If
```

可以使用以下语法访问字段中以前的某个值。

```vb
    [Old].[Field Name]
```

例如, 若要访问 QuantityInStock 字段的以前的值, 请使用以下语法。

```vb
    [Old].[QuantityInStock]
```

当“更改前”**** 事件结束时，以前的值将被永久删除。

您可以使用 **RaiseError** 操作取消“更改前”**** 事件。当引发错误时，将放弃“更改前”**** 事件中包含的更改。

下表列出了可在“更改前”**** 事件中使用的宏命令。

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>命令类型</p></th>
<th><p>Command</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>程序流</p></td>
<td><p><a href="comment-macro-statement.md">Comment 宏语句</a></p></td>
</tr>
<tr class="even">
<td><p>程序流</p></td>
<td><p><a href="group-macro-statement.md">Group 宏语句</a></p></td>
</tr>
<tr class="odd">
<td><p>程序流</p></td>
<td><p><a href="if-then-else-macro-block.md">If...Then...Else 宏程序块</a></p></td>
</tr>
<tr class="even">
<td><p>数据块</p></td>
<td><p><a href="lookuprecord-data-block.md">LookupRecord 宏操作</a></p></td>
</tr>
<tr class="odd">
<td><p>数据操作</p></td>
<td><p><a href="clearmacroerror-macro-action.md">ClearMacroError 宏操作</a></p></td>
</tr>
<tr class="even">
<td><p>数据操作</p></td>
<td><p><a href="onerror-macro-action.md">OnError 宏操作</a></p></td>
</tr>
<tr class="odd">
<td><p>数据操作</p></td>
<td><p><a href="raiseerror-macro-action.md">RaiseError 宏操作</a></p></td>
</tr>
<tr class="even">
<td><p>数据操作</p></td>
<td><p><a href="setfield-macro-action.md">SetField 宏操作</a></p></td>
</tr>
<tr class="odd">
<td><p>数据操作</p></td>
<td><p><a href="setlocalvar-macro-action.md">SetLocalVar 宏操作</a></p></td>
</tr>
<tr class="even">
<td><p>数据操作</p></td>
<td><p><a href="stopmacro-macro-action.md">StopMacro 宏操作</a></p></td>
</tr>
</tbody>
</table>


若要创建可捕获“更改前”**** 事件的数据宏，请执行以下步骤：

1.  打开要捕获其“更改前”**** 事件的表格。

2.  在 **“表格”** 选项卡上的 **“前期事件”** 组中，单击 **“更改前”**。

宏设计器中将显示一个空白数据宏。

## <a name="example"></a>示例

下面的代码示例使用**Before Change**事件验证状态字段。 如果“解决方案”(Resolution) 字段中包含不合适的值，将会引发错误。

```vb 
 
/* Check to ensure that if the bug is resloved that the user has selected a resolution      */ 
If   [Status]="3 - Resolved" And IsNull([Resolution])   Then 
 
     RaiseError 
             Error Number   1 
        Error Description   You must select a resolution. 
End If 
 
/* Check to ensure that if a bug is closed that the user has selected a resolution first     */ 
If   [Status]="4 - Closed" And IsNull([Resolution])   Then 
 
      RaiseError 
             Error Number   2 
        Error Description   An issue must be resolved before it can be closed. 
End If 
 
If   [Status]<>"3 - Resolved" And [Status]<>"4 - Closed"   Then 
 
      SetField 
             Name   Resolution 
            Value   =Null 
End If 
 
```

若要在宏设计器查看此示例，请执行以下步骤。

1.  打开要捕获其“更改前”**** 事件的表格。

2.  在 **“表格”** 选项卡上的 **“前期事件”** 组中，单击 **“更改前”**。

3.  在下面的代码示例中选择代码, 然后按**CTRL + C**将其复制到剪贴板。

4.  激活宏设计器窗口, 然后按**CTRL + V**。



```xml
<DataMacros xmlns="https://schemas.microsoft.com/office/accessservices/2009/04/application"> 
  <DataMacro Event="BeforeChange"> 
    <Statements> 
      <Comment>Check to ensure that if the bug is resloved that the user has selected a resolution </Comment> 
      <ConditionalBlock> 
        <If> 
          <Condition>[Status]="3 - Resolved" And IsNull([Resolution])</Condition> 
          <Statements> 
            <Action Name="RaiseError"> 
              <Argument Name="Number">1</Argument> 
              <Argument Name="Description">You must select a resolution.</Argument> 
            </Action> 
          </Statements> 
        </If> 
      </ConditionalBlock> 
      <Comment>Check to ensure that if a bug is closed that the user has selected a resolution first </Comment> 
      <ConditionalBlock> 
        <If> 
          <Condition>[Status]="4 - Closed" And IsNull([Resolution])</Condition> 
          <Statements> 
            <Action Name="RaiseError"> 
              <Argument Name="Number">2</Argument> 
              <Argument Name="Description">An issue must be resolved before it can be closed.</Argument> 
            </Action> 
          </Statements> 
        </If> 
      </ConditionalBlock> 
      <ConditionalBlock> 
        <If> 
          <Condition>[Status]&lt;&gt;"3 - Resolved" And [Status]&lt;&gt;"4 - Closed"</Condition> 
          <Statements> 
            <Action Name="SetField"> 
              <Argument Name="Field">Resolution</Argument> 
              <Argument Name="Value">Null</Argument> 
            </Action> 
          </Statements> 
        </If> 
      </ConditionalBlock> 
    </Statements> 
  </DataMacro> 
</DataMacros>
```

下面的示例演示如何使用 RaiseError 操作取消 Before Change data 宏事件。 更新 "分配" 字段后, 将使用 LookupRecord 数据块确定分配的技术人员当前是否已分配给打开的服务请求。 如果为 true, 则取消前更改事件, 且不更新记录。

**示例代码提供方：**[Microsoft Access 2010 程序员参考](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125)。

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
