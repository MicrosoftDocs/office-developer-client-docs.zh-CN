---
title: “删除后”宏事件
TOCTitle: After Delete Macro Event
ms:assetid: ecf9e6d4-345f-9b78-eb36-bd526e5df09b
ms:mtpsurl: https://msdn.microsoft.com/library/Ff836323(v=office.15)
ms:contentKeyID: 48548527
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm15155
f1_categories:
- Office.Version=v15
ms.openlocfilehash: b180acb99ab2ac406a7b60fdecf8aff5d63eb71f
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25869111"
---
# <a name="after-delete-macro-event"></a>“删除后”宏事件


**适用于**： Access 2013、 Office 2013

删除记录之后，发生此事件**后删除**事件。


> [!NOTE]
> **删除后**事件仅适用于数据宏。



## <a name="remarks"></a>说明

使用**删除后**事件执行您想要删除记录时，会发生任何操作。 **删除后**的常见用途包括强制实施业务规则，工作流、 更新聚合总数，以及发送通知。

**删除后**事件发生时，已删除记录中包含的值是仍然可用。 您可能要删除的值用于递增或递减总共、 创建审计线索，或与*WhereCondition*参数中的现有值进行比较。

可以使用 **Updated("*Field Name*")** 函数确定某个字段是否已更改。下面的代码示例演示了如何使用 If 语句来确定 PaidInFull 字段是否已更改。

```vb 
 
If  Updated("PaidInFull")   Then 
 
    /* Perform actions based on changes to the field.   */ 
 
End If 
 
```

可以使用以下语法访问已删除记录中的某个值。

`[Old].[Field Name]`

例如，若要访问已删除记录中 QuantityInStock 字段的值，请使用以下语法。

`[Old].[QuantityInStock]`

在**删除后**事件结束时，已删除记录中包含的值将被永久删除。

以下宏命令可中的**删除后**事件。

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


若要创建可捕获**删除后**事件的数据宏，请使用以下步骤。

1.  打开要为其捕获**删除后**事件的表格。

2.  在 **“表格”** 选项卡上的 **“后期事件”** 组中，单击 **“删除后”**。

宏设计器中将显示一个空白数据宏。

## <a name="example"></a>示例

下面的代码示例使用**删除后**事件执行一些处理时从捐赠表中删除一条记录。 当删除记录时，捐赠量 subracted 窗体 DonationsReceived 表中的 DonationsReceived 字段和 TotalDonatedField 赞助商表中。

**单击此处查看您可以将其粘贴到宏设计器的宏副本。**

若要在宏设计器查看此示例，请执行以下步骤。

1.  打开要为其捕获**删除后**事件的表格。

2.  在 **“表格”** 选项卡上的 **“后期事件”** 组中，单击 **“删除后”**。

3.  选择下面列出的代码，然后按 Ctrl+C 将其复制到剪贴板。

4.  激活宏设计器窗口，然后按 Ctrl+V。

<!-- end list -->

```xml
    <?xml version="1.0" encoding="UTF-16" standalone="no"?> 
    <DataMacros xmlns="https://schemas.microsoft.com/office/accessservices/2009/04/application"> 
      <DataMacro Event="AfterDelete"> 
        <Statements> 
          <Comment>Initialize a variable and assign the old</Comment> 
          <Action Name="SetLocalVar"> 
            <Argument Name="Name">varAmount</Argument> 
            <Argument Name="Value">[Old].[Amount]</Argument> 
          </Action> 
          <ConditionalBlock> 
            <If> 
              <Condition>Not (IsNull([Old].[CampaignID]))</Condition> 
              <Statements> 
                <ForEachRecord> 
                  <Data> 
                    <Reference>Campaigns</Reference> 
                    <WhereCondition>[ID]=[Old].[CampaignID]</WhereCondition> 
                  </Data> 
                  <Statements> 
                    <EditRecord> 
                      <Data /> 
                      <Statements> 
                        <Action Collapsed="true" Name="SetField"> 
                          <Argument Name="Field">[DonationsReceived]</Argument> 
                          <Argument Name="Value">[DonationsReceived]-[varAmount]</Argument> 
                        </Action> 
                      </Statements> 
                    </EditRecord> 
                  </Statements> 
                </ForEachRecord> 
              </Statements> 
            </If> 
          </ConditionalBlock> 
          <ConditionalBlock> 
            <If> 
              <Condition>Not (IsNull([Old].[DonorID]))</Condition> 
              <Statements> 
                <ForEachRecord> 
                  <Data> 
                    <Reference>Donors</Reference> 
                    <WhereCondition>[ID]=[Old].[DonorID]</WhereCondition> 
                  </Data> 
                  <Statements> 
                    <EditRecord> 
                      <Data /> 
                      <Statements> 
                        <Action Name="SetField"> 
                          <Argument Name="Field">[TotalDonated]</Argument> 
                          <Argument Name="Value">[TotalDonated]-[varAmount]</Argument> 
                        </Action> 
                      </Statements> 
                    </EditRecord> 
                  </Statements> 
                </ForEachRecord> 
              </Statements> 
            </If> 
          </ConditionalBlock> 
        </Statements> 
      </DataMacro> 
    </DataMacros>
```

<br/>

```vb
    SetLocalVar 
                    Name    varAmount 
              Expression   =[Old].[Amount] 
     
    If   Not(IsNull([Old].[CampaignID]]))   Then 
     
         For Each Record In     Campaigns 
            Where Condition     =[ID]=[Old].[CampaignID] 
                      Alias 
            EditRecord 
                      Alias 
                  SetField   ([DonationsReceived], [DonationsReceived] - [varAmount]) 
            End EditRecord 
     
    End If 
     
    If   Not(IsNull([Old].[DonorID]]))   Then 
     
         For Each Record In    Donors 
            Where Condition     =[ID]=[Old].[DonorID] 
                      Alias 
            EditRecord 
                      Alias 
     
              SetField 
                             Name   [TotalDonated] 
                            Value   =[TotalDonated]-[varAmount] 
            End EditRecord 
    End If
```
