---
title: “插入后”宏事件
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
localization_priority: Priority
ms.openlocfilehash: c84a737d08b791bfe560bfe6af6bcc59a14d2678
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32297219"
---
# <a name="after-insert-macro-event"></a><span data-ttu-id="cfee6-102">“插入后”宏事件</span><span class="sxs-lookup"><span data-stu-id="cfee6-102">After Insert macro event</span></span>

<span data-ttu-id="cfee6-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="cfee6-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="cfee6-104">在添加记录之后会发生“插入后”\*\*\*\* 事件。</span><span class="sxs-lookup"><span data-stu-id="cfee6-104">The **After Insert** event occurs after a record is added.</span></span>

> [!NOTE]
> <span data-ttu-id="cfee6-105">\*\*\*\*“插入后”事件仅适用于数据宏。</span><span class="sxs-lookup"><span data-stu-id="cfee6-105">The **After Insert** event is available only in Data Macros.</span></span>

## <a name="remarks"></a><span data-ttu-id="cfee6-106">说明</span><span class="sxs-lookup"><span data-stu-id="cfee6-106">Remarks</span></span>

<span data-ttu-id="cfee6-p101">使用“插入后”\*\*\*\* 事件可以执行您希望在向表中添加记录时发生的任何操作。“插入后”\*\*\*\* 通常用于强制实施业务规则、工作流，更新聚合总计和发送通知。</span><span class="sxs-lookup"><span data-stu-id="cfee6-p101">Use the **After Insert** event to perform any actions that you want to occur when a record is added to a table. Common uses for the **After Insert** include enforcing business rules, workflows, updating an aggregate total, and sending notifications.</span></span>

<span data-ttu-id="cfee6-109">可以使用 **Updated("*Field Name*")** 函数确定某个字段是否已更改。</span><span class="sxs-lookup"><span data-stu-id="cfee6-109">You can use the *Updated("**Field Name**")* function to determine whether a field has changed.</span></span> <span data-ttu-id="cfee6-110">下面的代码示例演示了如何使用 **If** 语句来确定 PaidInFull 字段是否已更改。</span><span class="sxs-lookup"><span data-stu-id="cfee6-110">The following code example shows how to use an **If** statement to determine determine whether the PaidInFull field has been changed.</span></span>

```vb 
 
If  Updated("PaidInFull")   Then 
 
    /* Perform actions based on changes to the field.   */ 
 
End If 
 
```

<span data-ttu-id="cfee6-111">下表列出了可在“插入后”\*\*\*\* 事件中使用的宏命令。</span><span class="sxs-lookup"><span data-stu-id="cfee6-111">The following table lists macro commands that can be used in the**After Insert** event.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="cfee6-112">命令类型</span><span class="sxs-lookup"><span data-stu-id="cfee6-112">Command Type</span></span></p></th>
<th><p><span data-ttu-id="cfee6-113">命令</span><span class="sxs-lookup"><span data-stu-id="cfee6-113">Command</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cfee6-114">程序流</span><span class="sxs-lookup"><span data-stu-id="cfee6-114">Program Flow</span></span></p></td>
<td><p><span data-ttu-id="cfee6-115"><a href="comment-macro-statement.md">Comment 宏语句</a></span><span class="sxs-lookup"><span data-stu-id="cfee6-115"><a href="comment-macro-statement.md">Comment macro statement</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cfee6-116">程序流</span><span class="sxs-lookup"><span data-stu-id="cfee6-116">Program Flow</span></span></p></td>
<td><p><span data-ttu-id="cfee6-117"><a href="group-macro-statement.md">Group 宏语句</a></span><span class="sxs-lookup"><span data-stu-id="cfee6-117"><a href="group-macro-statement.md">Group macro statement</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cfee6-118">程序流</span><span class="sxs-lookup"><span data-stu-id="cfee6-118">Program Flow</span></span></p></td>
<td><p><span data-ttu-id="cfee6-119"><a href="if-then-else-macro-block.md">If...Then...Else 宏程序块</a></span><span class="sxs-lookup"><span data-stu-id="cfee6-119"><a href="if-then-else-macro-block.md">If...Then...Else macro block</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cfee6-120">数据块</span><span class="sxs-lookup"><span data-stu-id="cfee6-120">Data Block</span></span></p></td>
<td><p><span data-ttu-id="cfee6-121"><a href="createrecord-data-block.md">CreateRecord 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="cfee6-121"><a href="createrecord-data-block.md">CreateRecord Macro Action</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cfee6-122">数据块</span><span class="sxs-lookup"><span data-stu-id="cfee6-122">Data Block</span></span></p></td>
<td><p><span data-ttu-id="cfee6-123"><a href="editrecord-data-block.md">EditRecord 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="cfee6-123"><a href="editrecord-data-block.md">EditRecord Macro Action</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cfee6-124">数据块</span><span class="sxs-lookup"><span data-stu-id="cfee6-124">Data Block</span></span></p></td>
<td><p><span data-ttu-id="cfee6-125"><a href="foreachrecord-data-block.md">ForEachRecord 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="cfee6-125"><a href="foreachrecord-data-block.md">ForEachRecord Macro Action</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cfee6-126">数据块</span><span class="sxs-lookup"><span data-stu-id="cfee6-126">Data Block</span></span></p></td>
<td><p><span data-ttu-id="cfee6-127"><a href="lookuprecord-data-block.md">LookupRecord 数据块</a></span><span class="sxs-lookup"><span data-stu-id="cfee6-127"><a href="lookuprecord-data-block.md">LookupRecord Data Block</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cfee6-128">数据操作</span><span class="sxs-lookup"><span data-stu-id="cfee6-128">Data Action</span></span></p></td>
<td><p><span data-ttu-id="cfee6-129"><a href="cancelrecordchange-macro-action.md">CancelRecordChange 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="cfee6-129"><a href="cancelrecordchange-macro-action.md">CancelRecordChange macro action</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cfee6-130">数据操作</span><span class="sxs-lookup"><span data-stu-id="cfee6-130">Data Action</span></span></p></td>
<td><p><span data-ttu-id="cfee6-131"><a href="clearmacroerror-macro-action.md">ClearMacroError 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="cfee6-131"><a href="clearmacroerror-macro-action.md">ClearMacroError macro action</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cfee6-132">数据操作</span><span class="sxs-lookup"><span data-stu-id="cfee6-132">Data Action</span></span></p></td>
<td><p><span data-ttu-id="cfee6-133"><a href="deleterecord-macro-action.md">DeleteRecord 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="cfee6-133"><a href="deleterecord-macro-action.md">DeleteRecord macro action</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cfee6-134">数据操作</span><span class="sxs-lookup"><span data-stu-id="cfee6-134">Data Action</span></span></p></td>
<td><p><span data-ttu-id="cfee6-135"><a href="exitforeachrecord-macro-action.md">ExitForEachRecord 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="cfee6-135"><a href="exitforeachrecord-macro-action.md">ExitForEachRecord macro action</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cfee6-136">数据操作</span><span class="sxs-lookup"><span data-stu-id="cfee6-136">Data Action</span></span></p></td>
<td><p><span data-ttu-id="cfee6-137"><a href="logevent-macro-action.md">LogEvent 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="cfee6-137"><a href="logevent-macro-action.md">LogEvent macro action</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cfee6-138">数据操作</span><span class="sxs-lookup"><span data-stu-id="cfee6-138">Data Action</span></span></p></td>
<td><p><span data-ttu-id="cfee6-139"><a href="onerror-macro-action.md">OnError 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="cfee6-139"><a href="onerror-macro-action.md">OnError macro action</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cfee6-140">数据操作</span><span class="sxs-lookup"><span data-stu-id="cfee6-140">Data Action</span></span></p></td>
<td><p><span data-ttu-id="cfee6-141"><a href="raiseerror-macro-action.md">RaiseError 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="cfee6-141"><a href="raiseerror-macro-action.md">RaiseError macro action</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cfee6-142">数据操作</span><span class="sxs-lookup"><span data-stu-id="cfee6-142">Data Action</span></span></p></td>
<td><p><span data-ttu-id="cfee6-143"><a href="rundatamacro-macro-action.md">RunDataMacro 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="cfee6-143"><a href="rundatamacro-macro-action.md">RunDataMacro macro action</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cfee6-144">数据操作</span><span class="sxs-lookup"><span data-stu-id="cfee6-144">Data Action</span></span></p></td>
<td><p><span data-ttu-id="cfee6-145"><a href="sendemail-macro-action.md">SendEmail 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="cfee6-145"><a href="sendemail-macro-action.md">SendEmail macro action</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cfee6-146">数据操作</span><span class="sxs-lookup"><span data-stu-id="cfee6-146">Data Action</span></span></p></td>
<td><p><span data-ttu-id="cfee6-147"><a href="setfield-macro-action.md">SetField 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="cfee6-147"><a href="setfield-macro-action.md">SetField macro action</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cfee6-148">数据操作</span><span class="sxs-lookup"><span data-stu-id="cfee6-148">Data Action</span></span></p></td>
<td><p><span data-ttu-id="cfee6-149"><a href="setlocalvar-macro-action.md">SetLocalVar 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="cfee6-149"><a href="setlocalvar-macro-action.md">SetLocalVar macro action</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cfee6-150">数据操作</span><span class="sxs-lookup"><span data-stu-id="cfee6-150">Data Action</span></span></p></td>
<td><p><span data-ttu-id="cfee6-151"><a href="stopallmacros-macro-action.md">StopAllMacros 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="cfee6-151"><a href="stopallmacros-macro-action.md">StopAllMacros macro action</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cfee6-152">数据操作</span><span class="sxs-lookup"><span data-stu-id="cfee6-152">Data Action</span></span></p></td>
<td><p><span data-ttu-id="cfee6-153"><a href="stopmacro-macro-action.md">StopMacro 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="cfee6-153"><a href="stopmacro-macro-action.md">StopMacro macro action</a></span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="cfee6-154">若要创建可捕获“插入后”\*\*\*\* 事件的数据宏，请执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="cfee6-154">To create a Data macro that captures the **After Insert** event, use the following steps.</span></span>

1.  <span data-ttu-id="cfee6-155">打开要捕获其“插入后”\*\*\*\* 事件的表格。</span><span class="sxs-lookup"><span data-stu-id="cfee6-155">Open the table for which you want to capture the **After Insert** event.</span></span>

2.  <span data-ttu-id="cfee6-156">在 **“表格”** 选项卡上的 **“后期事件”** 组中，单击 **“插入后”**。</span><span class="sxs-lookup"><span data-stu-id="cfee6-156">On the **Table** tab, in the **After Events** group, click **After Insert**.</span></span>

<span data-ttu-id="cfee6-157">宏设计器中将显示一个空白数据宏。</span><span class="sxs-lookup"><span data-stu-id="cfee6-157">An empty data macro is displayed in the macro designer.</span></span>

## <a name="example"></a><span data-ttu-id="cfee6-158">示例</span><span class="sxs-lookup"><span data-stu-id="cfee6-158">Example</span></span>

<span data-ttu-id="cfee6-159">以下代码示例使用**插入后**事件在将记录添加到 Donations 表时执行某些处理。</span><span class="sxs-lookup"><span data-stu-id="cfee6-159">The following code example uses the **After Insert** event to perform some processing when a record is added to the Donations table.</span></span> <span data-ttu-id="cfee6-160">添加记录时，将向 Campaigns 表中的 DonationsReceived 字段和 Donors 表中的 TotalDonated 字段中添加捐赠金额。</span><span class="sxs-lookup"><span data-stu-id="cfee6-160">When a record is added, the amount of the donation is added to the DonationsReceived field in the  Campaigns table and the TotalDonatedField in the Donors table.</span></span>

<span data-ttu-id="cfee6-161">**单击此处查看可以粘贴到宏设计器中的宏副本。**</span><span class="sxs-lookup"><span data-stu-id="cfee6-161">**Click here to view  a copy of the macro that you can paste into Macro Designer.**</span></span>

<span data-ttu-id="cfee6-162">若要在宏设计器查看此示例，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="cfee6-162">To view this example in the macro designer, use the following steps:</span></span>

1.  <span data-ttu-id="cfee6-163">打开要捕获其“插入后”\*\*\*\* 事件的表格。</span><span class="sxs-lookup"><span data-stu-id="cfee6-163">Open the table for which you want to capture the **After Insert** event.</span></span>

2.  <span data-ttu-id="cfee6-164">在 **“表格”** 选项卡上的 **“后期事件”** 组中，单击 **“插入后”**。</span><span class="sxs-lookup"><span data-stu-id="cfee6-164">On the **Table** tab, in the **After Events** group, click **After Insert**.</span></span>

3.  <span data-ttu-id="cfee6-165">选择以下代码示例中的代码，然后按 Ctrl+C 将其复制到剪贴板。</span><span class="sxs-lookup"><span data-stu-id="cfee6-165">Select the code in the following code example and then press CTRL+C to copy it to the Clipboard.</span></span>

4.  <span data-ttu-id="cfee6-166">激活宏设计器窗口，然后按 Ctrl+V。</span><span class="sxs-lookup"><span data-stu-id="cfee6-166">Activate the macro designer window and then press CTRL+V.</span></span>

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
