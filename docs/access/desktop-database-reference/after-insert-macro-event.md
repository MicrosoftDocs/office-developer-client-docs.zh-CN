---
title: After Insert 宏事件
TOCTitle: After Insert macro event
ms:assetid: 78013896-ee07-6979-96f7-fa0f3490419e
ms:mtpsurl: https://msdn.microsoft.com/library/Ff196099(v=office.15)
ms:contentKeyID: 48545742
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm3180
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 4dc9d509dedfb74769c84f44a6237b9f6354dc16
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25921682"
---
# <a name="after-insert-macro-event"></a>After Insert 宏事件


**适用于**： Access 2013、 Office 2013

添加一条记录之后，发生此事件的**插入后**事件。


> [!NOTE]
> 在**插入后**事件仅适用于数据宏。



## <a name="remarks"></a>说明

使用**插入后**事件执行您想要将记录添加到表时，会发生任何操作。 **插入后**的常见用途包括强制实施业务规则，工作流、 更新聚合总数，以及发送通知。

可以使用 **Updated("*Field Name*")** 函数确定某个字段是否已更改。下面的代码示例演示了如何使用 **If** 语句来确定 PaidInFull 字段是否已更改。

```vb 
 
If  Updated("PaidInFull")   Then 
 
    /* Perform actions based on changes to the field.   */ 
 
End If 
 
```

下表列出了可在**插入后**事件中使用的宏命令。

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


若要创建可捕获**插入后**事件的数据宏，请使用以下步骤。

1.  打开要为其捕获**插入后**事件的表格。

2.  在 **“表格”** 选项卡上的 **“后期事件”** 组中，单击 **“插入后”**。

宏设计器中将显示一个空白数据宏。

## <a name="example"></a>示例

下面的代码示例使用**插入后**事件执行一些处理，当记录被添加到捐赠表。 当记录被添加时，捐赠量添加到活动表中的 DonationsReceived 字段和 TotalDonatedField 赞助商表中。

**单击此处查看您可以将其粘贴到宏设计器的宏副本。**

若要在宏设计器查看此示例，请执行以下步骤：

1.  打开要为其捕获**插入后**事件的表格。

2.  在 **“表格”** 选项卡上的 **“后期事件”** 组中，单击 **“插入后”**。

3.  选择以下代码示例中的代码，然后按 Ctrl+C 将其复制到剪贴板。

4.  激活宏设计器窗口，然后按 Ctrl+V。

<!-- end list -->

```xml
    <DataMacros> 
      <DataMacro Event="AfterInsert"> 
        <Statements> 
          <Comment>This data macro increments the DonationsReceived field in Campaigns and theAmountCollected field in Pledges </Comment> 
          <Action Name="SetLocalVar"> 
            <Argument Name="Name">varAmount</Argument> 
            <Argument Name="Value">[Amount]</Argument> 
          </Action> 
          <ConditionalBlock> 
            <If> 
              <Condition>Not (IsNull([CampaignID]))</Condition> 
              <Statements> 
                <ForEachRecord> 
                  <Data> 
                    <Reference>Campaigns</Reference> 
                    <WhereCondition>[ID]=[Donations].[CampaignID]</WhereCondition> 
                  </Data> 
                  <Statements> 
                    <EditRecord> 
                      <Data /> 
                      <Statements> 
                        <Action Name="SetField"> 
                          <Argument Name="Field">[DonationsReceived]</Argument> 
                          <Argument Name="Value">[DonationsReceived]+[varAmount]</Argument> 
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
              <Condition>Not (IsNull([DonorID]))</Condition> 
              <Statements> 
                <ForEachRecord> 
                  <Data> 
                    <Reference>Donors</Reference> 
                    <WhereCondition>[ID]=[Donations].[DonorID]</WhereCondition> 
                  </Data> 
                  <Statements> 
                    <EditRecord> 
                      <Data /> 
                      <Statements> 
                        <Action Name="SetField"> 
                          <Argument Name="Field">[TotalDonated]</Argument> 
                          <Argument Name="Value">[TotalDonated]+[varAmount]</Argument> 
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
                  Name   varAmount 
            Expression   =[Amount] 
     
    If   Not (IsNull([CampaignID]))   Then 
     
         For Each Record In   Campaigns 
            Where Condition   =[ID]=[Donations].[CampaignID] 
                      Alias 
     
                 EditRecord 
                              Alias 
                     SetField 
                                 Name   [DonationsReceived] 
                                Value   =[DonationsReceived]+[varAmount] 
                End EditRecord 
    End If 
     
    If   Not (IsNull([DonorID]))   Then 
     
         For Each Record In  Donors 
            WhereCondition   =[ID]=[Donations].[DonorID] 
                     Alias 
     
                 EditRecord 
                              Alias 
                     SetField 
                                 Name   [TotalDonated] 
                                Value   =[TotalDonated]+[varAmount] 
                 End EditRecord 
    End If
```
