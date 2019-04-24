---
title: After Delete 宏事件
TOCTitle: After Delete macro event
ms:assetid: ecf9e6d4-345f-9b78-eb36-bd526e5df09b
ms:mtpsurl: https://msdn.microsoft.com/library/Ff836323(v=office.15)
ms:contentKeyID: 48548527
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm15155
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: f524a544736f68bcfa6bd15e3bcc720ffa2bc4d6
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32297212"
---
# <a name="after-delete-macro-event"></a><span data-ttu-id="fa989-102">After Delete 宏事件</span><span class="sxs-lookup"><span data-stu-id="fa989-102">After Delete macro event</span></span>

<span data-ttu-id="fa989-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="fa989-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="fa989-104">在删除记录之后会发生“删除后”\*\*\*\* 事件。</span><span class="sxs-lookup"><span data-stu-id="fa989-104">The **After Delete** event occurs after a record is deleted.</span></span>

> [!NOTE]
> <span data-ttu-id="fa989-105">\*\*\*\*“删除后”事件仅适用于数据宏。</span><span class="sxs-lookup"><span data-stu-id="fa989-105">The **After Delete** event is available only in Data Macros.</span></span>

## <a name="remarks"></a><span data-ttu-id="fa989-106">注解</span><span class="sxs-lookup"><span data-stu-id="fa989-106">Remarks</span></span>

<span data-ttu-id="fa989-p101">使用“删除后”\*\*\*\* 事件可以执行您希望在删除记录时发生的任何操作。“删除后”\*\*\*\* 通常用于强制实施业务规则、工作流，更新聚合总计和发送通知。</span><span class="sxs-lookup"><span data-stu-id="fa989-p101">Use the **After Delete** event to perform any actions that you want to occur when a record is deleted. Common uses for the **After Delete** include enforcing business rules, workflows, updating an aggregate total, and sending notifications.</span></span>

<span data-ttu-id="fa989-109">当发生 "**删除后**" 事件时, 已删除记录中包含的值仍可用。</span><span class="sxs-lookup"><span data-stu-id="fa989-109">When the **After Delete** event occurs, the values contained in the deleted record are still available.</span></span> <span data-ttu-id="fa989-110">您可能需要使用已删除的值来增加或减少总计、创建审核跟踪或与*WhereCondition*参数中的现有值进行比较。</span><span class="sxs-lookup"><span data-stu-id="fa989-110">You may want to use a deleted value to increment or decrement a total, create an audit trail, or compare to an existing value in a *WhereCondition* argument.</span></span>

<span data-ttu-id="fa989-111">您可以使用**更新的 ("*Field Name*")** 函数来确定字段是否已更改。</span><span class="sxs-lookup"><span data-stu-id="fa989-111">You can use the **Updated("*Field Name*")** function to determine whether a field has changed.</span></span> <span data-ttu-id="fa989-112">下面的代码示例演示了如何使用 If 语句来确定 PaidInFull 字段是否已更改。</span><span class="sxs-lookup"><span data-stu-id="fa989-112">The following code example shows how to use an If staement to determine determine whether the PaidInFull field has been changed.</span></span>

```vb 
 
If  Updated("PaidInFull")   Then 
 
    /* Perform actions based on changes to the field.   */ 
 
End If 
 
```

<span data-ttu-id="fa989-113">可以使用以下语法访问已删除记录中的某个值。</span><span class="sxs-lookup"><span data-stu-id="fa989-113">You can use access a value in the deleted record by using the following syntax.</span></span>

`[Old].[Field Name]`

<span data-ttu-id="fa989-114">例如, 若要访问已删除记录中的 QuantityInStock 字段的值, 请使用以下语法。</span><span class="sxs-lookup"><span data-stu-id="fa989-114">For example, to access the value of the QuantityInStock field in the deleted record, use the following syntax.</span></span>

`[Old].[QuantityInStock]`

<span data-ttu-id="fa989-115">当“删除后”\*\*\*\* 事件结束时，已删除记录中包含的值将被永久删除。</span><span class="sxs-lookup"><span data-stu-id="fa989-115">The values contained in the deleted record are deleted permanently when the **After Delete** event ends.</span></span>

<span data-ttu-id="fa989-116">可以在 "**删除后**" 事件中使用以下宏命令。</span><span class="sxs-lookup"><span data-stu-id="fa989-116">The following macro commands can be used in the **After Delete** event.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="fa989-117">命令类型</span><span class="sxs-lookup"><span data-stu-id="fa989-117">Command Type</span></span></p></th>
<th><p><span data-ttu-id="fa989-118">Command</span><span class="sxs-lookup"><span data-stu-id="fa989-118">Command</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fa989-119">程序流</span><span class="sxs-lookup"><span data-stu-id="fa989-119">Program Flow</span></span></p></td>
<td><p><span data-ttu-id="fa989-120"><a href="comment-macro-statement.md">Comment 宏语句</a></span><span class="sxs-lookup"><span data-stu-id="fa989-120"><a href="comment-macro-statement.md">Comment macro statement</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa989-121">程序流</span><span class="sxs-lookup"><span data-stu-id="fa989-121">Program Flow</span></span></p></td>
<td><p><span data-ttu-id="fa989-122"><a href="group-macro-statement.md">Group 宏语句</a></span><span class="sxs-lookup"><span data-stu-id="fa989-122"><a href="group-macro-statement.md">Group macro statement</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa989-123">程序流</span><span class="sxs-lookup"><span data-stu-id="fa989-123">Program Flow</span></span></p></td>
<td><p><span data-ttu-id="fa989-124"><a href="if-then-else-macro-block.md">If...Then...Else 宏程序块</a></span><span class="sxs-lookup"><span data-stu-id="fa989-124"><a href="if-then-else-macro-block.md">If...Then...Else macro block</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa989-125">数据块</span><span class="sxs-lookup"><span data-stu-id="fa989-125">Data Block</span></span></p></td>
<td><p><span data-ttu-id="fa989-126"><a href="createrecord-data-block.md">CreateRecord 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="fa989-126"><a href="createrecord-data-block.md">CreateRecord macro action</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa989-127">数据块</span><span class="sxs-lookup"><span data-stu-id="fa989-127">Data Block</span></span></p></td>
<td><p><span data-ttu-id="fa989-128"><a href="editrecord-data-block.md">EditRecord 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="fa989-128"><a href="editrecord-data-block.md">EditRecord macro action</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa989-129">数据块</span><span class="sxs-lookup"><span data-stu-id="fa989-129">Data Block</span></span></p></td>
<td><p><span data-ttu-id="fa989-130"><a href="foreachrecord-data-block.md">ForEachRecord 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="fa989-130"><a href="foreachrecord-data-block.md">ForEachRecord macro action</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa989-131">数据块</span><span class="sxs-lookup"><span data-stu-id="fa989-131">Data Block</span></span></p></td>
<td><p><span data-ttu-id="fa989-132"><a href="lookuprecord-data-block.md">LookupRecord 数据块</a></span><span class="sxs-lookup"><span data-stu-id="fa989-132"><a href="lookuprecord-data-block.md">LookupRecord data block</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa989-133">数据操作</span><span class="sxs-lookup"><span data-stu-id="fa989-133">Data Action</span></span></p></td>
<td><p><span data-ttu-id="fa989-134"><a href="cancelrecordchange-macro-action.md">CancelRecordChange 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="fa989-134"><a href="cancelrecordchange-macro-action.md">CancelRecordChange macro action</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa989-135">数据操作</span><span class="sxs-lookup"><span data-stu-id="fa989-135">Data Action</span></span></p></td>
<td><p><span data-ttu-id="fa989-136"><a href="clearmacroerror-macro-action.md">ClearMacroError 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="fa989-136"><a href="clearmacroerror-macro-action.md">ClearMacroError macro action</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa989-137">数据操作</span><span class="sxs-lookup"><span data-stu-id="fa989-137">Data Action</span></span></p></td>
<td><p><span data-ttu-id="fa989-138"><a href="deleterecord-macro-action.md">DeleteRecord 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="fa989-138"><a href="deleterecord-macro-action.md">DeleteRecord macro action</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa989-139">数据操作</span><span class="sxs-lookup"><span data-stu-id="fa989-139">Data Action</span></span></p></td>
<td><p><span data-ttu-id="fa989-140"><a href="exitforeachrecord-macro-action.md">ExitForEachRecord 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="fa989-140"><a href="exitforeachrecord-macro-action.md">ExitForEachRecord macro action</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa989-141">数据操作</span><span class="sxs-lookup"><span data-stu-id="fa989-141">Data Action</span></span></p></td>
<td><p><span data-ttu-id="fa989-142"><a href="logevent-macro-action.md">LogEvent 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="fa989-142"><a href="logevent-macro-action.md">LogEvent macro action</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa989-143">数据操作</span><span class="sxs-lookup"><span data-stu-id="fa989-143">Data Action</span></span></p></td>
<td><p><span data-ttu-id="fa989-144"><a href="onerror-macro-action.md">OnError 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="fa989-144"><a href="onerror-macro-action.md">OnError macro action</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa989-145">数据操作</span><span class="sxs-lookup"><span data-stu-id="fa989-145">Data Action</span></span></p></td>
<td><p><span data-ttu-id="fa989-146"><a href="raiseerror-macro-action.md">RaiseError 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="fa989-146"><a href="raiseerror-macro-action.md">RaiseError macro action</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa989-147">数据操作</span><span class="sxs-lookup"><span data-stu-id="fa989-147">Data Action</span></span></p></td>
<td><p><span data-ttu-id="fa989-148"><a href="rundatamacro-macro-action.md">RunDataMacro 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="fa989-148"><a href="rundatamacro-macro-action.md">RunDataMacro macro action</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa989-149">数据操作</span><span class="sxs-lookup"><span data-stu-id="fa989-149">Data Action</span></span></p></td>
<td><p><span data-ttu-id="fa989-150"><a href="sendemail-macro-action.md">SendEmail 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="fa989-150"><a href="sendemail-macro-action.md">SendEmail macro action</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa989-151">数据操作</span><span class="sxs-lookup"><span data-stu-id="fa989-151">Data Action</span></span></p></td>
<td><p><span data-ttu-id="fa989-152"><a href="setfield-macro-action.md">SetField 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="fa989-152"><a href="setfield-macro-action.md">SetField macro action</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa989-153">数据操作</span><span class="sxs-lookup"><span data-stu-id="fa989-153">Data Action</span></span></p></td>
<td><p><span data-ttu-id="fa989-154"><a href="setlocalvar-macro-action.md">SetLocalVar 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="fa989-154"><a href="setlocalvar-macro-action.md">SetLocalVar macro action</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa989-155">数据操作</span><span class="sxs-lookup"><span data-stu-id="fa989-155">Data Action</span></span></p></td>
<td><p><span data-ttu-id="fa989-156"><a href="stopallmacros-macro-action.md">StopAllMacros 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="fa989-156"><a href="stopallmacros-macro-action.md">StopAllMacros macro action</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa989-157">数据操作</span><span class="sxs-lookup"><span data-stu-id="fa989-157">Data Action</span></span></p></td>
<td><p><span data-ttu-id="fa989-158"><a href="stopmacro-macro-action.md">StopMacro 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="fa989-158"><a href="stopmacro-macro-action.md">StopMacro macro action</a></span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="fa989-159">若要创建可捕获“删除后”\*\*\*\* 事件的数据宏，请执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="fa989-159">To create a Data Macro that captures the **After Delete** event, use the following steps.</span></span>

1.  <span data-ttu-id="fa989-160">打开要捕获其“删除后”\*\*\*\* 事件的表格。</span><span class="sxs-lookup"><span data-stu-id="fa989-160">Open the table for which you want to capture the **After Delete** event.</span></span>

2.  <span data-ttu-id="fa989-161">在 **“表格”** 选项卡上的 **“后期事件”** 组中，单击 **“删除后”**。</span><span class="sxs-lookup"><span data-stu-id="fa989-161">On the **Table** tab, in the **After Events** group, click **After Delete**.</span></span>

<span data-ttu-id="fa989-162">宏设计器中将显示一个空白数据宏。</span><span class="sxs-lookup"><span data-stu-id="fa989-162">An empty Data Macro is displayed in the macro designer.</span></span>

## <a name="example"></a><span data-ttu-id="fa989-163">示例</span><span class="sxs-lookup"><span data-stu-id="fa989-163">Example</span></span>

<span data-ttu-id="fa989-164">下面的代码示例使用“删除后”\*\*\*\* 事件来在从“捐赠”(Donations) 表中删除记录时执行一些处理。</span><span class="sxs-lookup"><span data-stu-id="fa989-164">The following code example uses the **After Delete** event to perform some processing when a record is deleted from the Donations table.</span></span> <span data-ttu-id="fa989-165">当记录被删除时, 捐赠量将 subracted 在 DonationsReceived 表中的 DonationsReceived 字段和捐赠人表中的 TotalDonatedField 组成。</span><span class="sxs-lookup"><span data-stu-id="fa989-165">When a record is deleted, the amount of the donation is subracted form the DonationsReceived field in the DonationsReceived table and the TotalDonatedField in the Donors table.</span></span>

<span data-ttu-id="fa989-166">**单击此处查看可粘贴到宏设计器中的宏副本。**</span><span class="sxs-lookup"><span data-stu-id="fa989-166">**Click here to view a copy of the macro that you can paste into Macro Designer.**</span></span>

<span data-ttu-id="fa989-167">若要在宏设计器查看此示例，请执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="fa989-167">To view this example in the macro designer, use the following steps.</span></span>

1.  <span data-ttu-id="fa989-168">打开要捕获其“删除后”\*\*\*\* 事件的表格。</span><span class="sxs-lookup"><span data-stu-id="fa989-168">Open the table for which you want to capture the **After Delete** event.</span></span>

2.  <span data-ttu-id="fa989-169">在 **“表格”** 选项卡上的 **“后期事件”** 组中，单击 **“删除后”**。</span><span class="sxs-lookup"><span data-stu-id="fa989-169">On the **Table** tab, in the **After Events** group, click **After Delete**.</span></span>

3.  <span data-ttu-id="fa989-170">选择下面列出的代码，然后按 Ctrl+C 将其复制到剪贴板。</span><span class="sxs-lookup"><span data-stu-id="fa989-170">Select the code listed below and then press CTRL+C to copy it to the Clipboard.</span></span>

4.  <span data-ttu-id="fa989-171">激活宏设计器窗口，然后按 Ctrl+V。</span><span class="sxs-lookup"><span data-stu-id="fa989-171">Activate the macro designer window and then press CTRL+V.</span></span>

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
