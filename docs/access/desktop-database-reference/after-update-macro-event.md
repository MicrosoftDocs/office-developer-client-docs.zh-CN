---
title: “更新后”宏事件
TOCTitle: After Update Macro Event
ms:assetid: 5213793b-8301-0f18-3a12-4e3764c879ac
ms:mtpsurl: https://msdn.microsoft.com/library/Ff193905(v=office.15)
ms:contentKeyID: 48544838
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm85126
f1_categories:
- Office.Version=v15
ms.openlocfilehash: ab9f9ef75c5db8ce1307bcd466a5c898e84ca870
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25869860"
---
# <a name="after-update-macro-event"></a>“更新后”宏事件


**适用于**： Access 2013、 Office 2013

**更新后**事件发生之后更改的记录。


> [!NOTE]
> **更新后**事件仅适用于数据宏。



## <a name="remarks"></a>说明

使用**更新后**事件执行您想要更改的记录时，会发生任何操作。 **插入后**的常见用途包括强制实施业务规则、 更新聚合总数，以及发送通知。

可以使用 **Updated("*Field Name*")** 函数确定某个字段是否已更改。下面的代码示例演示了如何使用 **If** 语句来确定 PaidInFull 字段是否已更改。

```vb 
 
If  Updated("PaidInFull")   Then 
 
    /* Perform actions based on changes to the field.   */ 
 
End If 
 
```

可以使用以下语法访问字段中以前的某个值。

`[Old].[Field Name]`

例如，若要访问 QuantityInStock 字段的以前的值，请使用以下语法。

`[Old].[QuantityInStock]`

在**更新后**事件结束时，以前的值将被永久删除。

下表列出命令可使用的**更新后**事件中的宏。

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
<td><p><a href="comment-macro-statement.md">注释宏语句</a></p></td>
</tr>
<tr class="even">
<td><p>程序流</p></td>
<td><p><a href="group-macro-statement.md">Group 宏语句</a></p></td>
</tr>
<tr class="odd">
<td><p>程序流</p></td>
<td><p><a href="if-then-else-macro-block.md">如果...然后...其他宏程序块</a></p></td>
</tr>
<tr class="even">
<td><p>数据块</p></td>
<td><p><a href="createrecord-data-block.md">CreateRecord 宏操作</a></p></td>
</tr>
<tr class="odd">
<td><p>数据块</p></td>
<td><p><a href="editrecord-data-block.md">EditRecord 宏操作</a></p></td>
</tr>
<tr class="even">
<td><p>数据块</p></td>
<td><p><a href="foreachrecord-data-block.md">ForEachRecord 宏操作</a></p></td>
</tr>
<tr class="odd">
<td><p>数据块</p></td>
<td><p><a href="lookuprecord-data-block.md">LookupRecord 数据块</a></p></td>
</tr>
<tr class="even">
<td><p>数据操作</p></td>
<td><p><a href="cancelrecordchange-macro-action.md">CancelRecordChange 宏操作</a></p></td>
</tr>
<tr class="odd">
<td><p>数据操作</p></td>
<td><p><a href="clearmacroerror-macro-action.md">ClearMacroError 宏操作</a></p></td>
</tr>
<tr class="even">
<td><p>数据操作</p></td>
<td><p><a href="deleterecord-macro-action.md">DeleteRecord 宏操作</a></p></td>
</tr>
<tr class="odd">
<td><p>数据操作</p></td>
<td><p><a href="exitforeachrecord-macro-action.md">ExitForEachRecord 宏操作</a></p></td>
</tr>
<tr class="even">
<td><p>数据操作</p></td>
<td><p><a href="logevent-macro-action.md">LogEvent 宏操作</a></p></td>
</tr>
<tr class="odd">
<td><p>数据操作</p></td>
<td><p><a href="onerror-macro-action.md">OnError 宏操作</a></p></td>
</tr>
<tr class="even">
<td><p>数据操作</p></td>
<td><p><a href="raiseerror-macro-action.md">RaiseError 宏操作</a></p></td>
</tr>
<tr class="odd">
<td><p>数据操作</p></td>
<td><p><a href="rundatamacro-macro-action.md">RunDataMacro 宏操作</a></p></td>
</tr>
<tr class="even">
<td><p>数据操作</p></td>
<td><p><a href="sendemail-macro-action.md">SendEmail 宏操作</a></p></td>
</tr>
<tr class="odd">
<td><p>数据操作</p></td>
<td><p><a href="setfield-macro-action.md">SetField 宏操作</a></p></td>
</tr>
<tr class="even">
<td><p>数据操作</p></td>
<td><p><a href="setlocalvar-macro-action.md">SetLocalVar 宏操作</a></p></td>
</tr>
<tr class="odd">
<td><p>数据操作</p></td>
<td><p><a href="stopallmacros-macro-action.md">StopAllMacros 宏操作</a></p></td>
</tr>
<tr class="even">
<td><p>数据操作</p></td>
<td><p><a href="stopmacro-macro-action.md">StopMacro 宏操作</a></p></td>
</tr>
</tbody>
</table>


若要创建可捕获**更新后**事件的数据宏，请使用执行以下步骤：

1.  打开要为其捕获**更新后**事件的表格。

2.  在 **“表格”** 选项卡上的 **“后期事件”** 组中，单击 **“更新后”**。

宏设计器中将显示一个空白数据宏。

## <a name="example"></a>示例

下面的代码示例使用**更新后**事件运行的已命名的数据宏，每次更新问题的状态将记录添加到注释表。

**单击此处查看您可以将其粘贴到宏设计器的宏副本。**

若要在宏设计器查看此示例，请执行以下步骤：

1.  打开要为其捕获**更新后**事件的表格。

2.  在 **“表格”** 选项卡上的 **“后期事件”** 组中，单击 **“更新后”**。

3.  选择以下代码示例中的代码，然后按 Ctrl+C 将其复制到剪贴板。

4.  激活宏设计器窗口，然后按 Ctrl+V。

<!-- end list -->

```xml
    <DataMacros xmlns="https://schemas.microsoft.com/office/accessservices/2009/04/application"> 
      <DataMacro Event="AfterUpdate"> 
        <Statements> 
          <ConditionalBlock> 
            <If> 
              <Condition>Updated("Status")</Condition> 
              <Statements> 
                <Action Name="RunDataMacro"> 
                  <Argument Name="MacroName">Comments.AddComment</Argument> 
                  <Parameters> 
                    <Parameter Name="prmRelatedID" Value="[ID]" /> 
                    <Parameter Name="prmComment" Value="&quot;-- Status changed to &quot; &amp; [Status]" /> 
                    <Parameter Name="prmUserID" Value="[UserID]" /> 
                  </Parameters> 
                </Action> 
              </Statements> 
            </If> 
          </ConditionalBlock> 
          <ConditionalBlock> 
            <If> 
              <Condition>Updated("Resolution")</Condition> 
              <Statements> 
                <Action Name="RunDataMacro"> 
                  <Argument Name="MacroName">Comments.AddComment</Argument> 
                  <Parameters> 
                    <Parameter Name="prmRelatedID" Value="[ID]" /> 
                    <Parameter Name="prmUserID" Value="[UserID]" /> 
                    <Parameter Name="prmComment" Value="&quot;-- Issue resolved as &quot; &amp; [Resolution]" /> 
                  </Parameters> 
                </Action> 
              </Statements> 
            </If> 
          </ConditionalBlock> 
        </Statements> 
      </DataMacro> 
    </DataMacros>
``` 

<br/>

```vb
If  Updated("Status")   Then 
     RunDataMacro 
        Macro Name   Comments.AddComment 
     Parameters 
       prmRelatedID   = [ID] 
         prmComment   ="--Status Changes to "&[Status] 
          prmUserID   =[ChangedByUserID] 
End If 
 
If   Updated("Resolution")   Then 
     RunDataMacro 
        Macro Name   Comments.AddComment 
     Parameters 
       prmRelatedID   = [ID] 
          prmUserID   =[ChangedByUserID] 
         prmComment   ="--Issue Resolved as "&[Status] 
End If 
```

