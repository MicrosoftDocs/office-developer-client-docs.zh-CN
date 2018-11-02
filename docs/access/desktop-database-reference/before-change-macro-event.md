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
ms.openlocfilehash: fb513c83e3956a37da019d762c5fd1e0c92da755
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25926561"
---
# <a name="before-change-macro-event"></a>Before Change 宏事件

**适用于**： Access 2013、 Office 2013

当记录更改，但未提交更改之前，发生此事件的**更改前**事件。

> [!NOTE]
> 仅适用于数据宏的**Before Change**事件。

## <a name="remarks"></a>说明

使用**Before Change**事件，以执行任何操作所需记录之前，需要进行更改。 **Before Change**常用来执行验证并将引发自定义错误消息。

**更新了 （"*字段名*"）** 函数可用于确定是否已更改字段。 下面的代码示例演示如何使用**If**语句确定是否已更改 PaidInFull 字段。

```vb
    If  Updated("PaidInFull")   Then 
     
        /* Perform actions based on changes to the field.   */ 
     
    End If 
```

使用**IsInsert**属性来确定是否在**更改前**事件触发正在创建的新记录或对现有记录的更改。 他们**IsInsert**属性包含 **，则返回 True** ，如果通过对 en 现有记录的更改触发事件，新记录， **False**已触发该事件。

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

例如，若要访问 QuantityInStock 字段的以前的值，请使用以下语法。

```vb
    [Old].[QuantityInStock]
```

在**更改前**事件结束时，以前的值将被永久删除。

您可以通过使用**RaiseError**操作取消**Before Change**事件。 时引发错误**Before Change**事件中包含的更改将被丢弃。

下表列出了可在**Before Change**事件中使用的宏命令。

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>命令类型</p></th>
<th><p>命令</p></th>
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


若要创建可捕获**更改前**事件的数据宏，请使用以下步骤：

1.  打开要为其捕获**Before Change**事件的表格。

2.  在 **“表格”** 选项卡上的 **“前期事件”** 组中，单击 **“更改前”**。

宏设计器中将显示一个空白数据宏。

## <a name="example"></a>示例

下面的代码示例使用**Before Change**事件来验证状态域。 如果在解决方案字段包含不正确的值，则，引发错误。

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

1.  打开要为其捕获**Before Change**事件的表格。

2.  在 **“表格”** 选项卡上的 **“前期事件”** 组中，单击 **“更改前”**。

3.  下面的代码示例中选择的代码，然后按**CTRL + C**将其复制到剪贴板。

4.  激活宏设计器窗口，然后按**CTRL + V**。



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

下面的示例演示如何使用 RaiseError 操作取消 Before Change 数据宏事件。 更新 AssignedTo 字段时，LookupRecord 数据块用于确定是否已分配的技术人员当前分配给打开服务请求。 如果是这样，然后取消 Before Change 事件并不会更新记录。

**示例代码提供者** [Microsoft Access 2010 Programmer's Reference](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125)。

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
