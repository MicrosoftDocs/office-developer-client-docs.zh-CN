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
# <a name="after-delete-macro-event"></a><span data-ttu-id="1c0c3-102">“删除后”宏事件</span><span class="sxs-lookup"><span data-stu-id="1c0c3-102">After Delete Macro Event</span></span>


<span data-ttu-id="1c0c3-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="1c0c3-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="1c0c3-104">删除记录之后，发生此事件**后删除**事件。</span><span class="sxs-lookup"><span data-stu-id="1c0c3-104">The **After Delete** event occurs after a record is deleted.</span></span>


> [!NOTE]
> <span data-ttu-id="1c0c3-105">**删除后**事件仅适用于数据宏。</span><span class="sxs-lookup"><span data-stu-id="1c0c3-105">The **After Delete** event is available only in Data Macros.</span></span>



## <a name="remarks"></a><span data-ttu-id="1c0c3-106">说明</span><span class="sxs-lookup"><span data-stu-id="1c0c3-106">Remarks</span></span>

<span data-ttu-id="1c0c3-107">使用**删除后**事件执行您想要删除记录时，会发生任何操作。</span><span class="sxs-lookup"><span data-stu-id="1c0c3-107">Use the **After Delete** event to perform any actions that you want to occur when a record is deleted.</span></span> <span data-ttu-id="1c0c3-108">**删除后**的常见用途包括强制实施业务规则，工作流、 更新聚合总数，以及发送通知。</span><span class="sxs-lookup"><span data-stu-id="1c0c3-108">Common uses for the **After Delete** include enforcing business rules, workflows, updating an aggregate total, and sending notifications.</span></span>

<span data-ttu-id="1c0c3-109">**删除后**事件发生时，已删除记录中包含的值是仍然可用。</span><span class="sxs-lookup"><span data-stu-id="1c0c3-109">When the **After Delete** event occurs, the values contained in the deleted record are still available.</span></span> <span data-ttu-id="1c0c3-110">您可能要删除的值用于递增或递减总共、 创建审计线索，或与*WhereCondition*参数中的现有值进行比较。</span><span class="sxs-lookup"><span data-stu-id="1c0c3-110">You may want to use a deleted value to increment or decrement a total, create an audit trail, or compare to an existing value in a *WhereCondition* argument.</span></span>

<span data-ttu-id="1c0c3-p103">可以使用 **Updated("*Field Name*")** 函数确定某个字段是否已更改。下面的代码示例演示了如何使用 If 语句来确定 PaidInFull 字段是否已更改。</span><span class="sxs-lookup"><span data-stu-id="1c0c3-p103">You can use the **Updated("*Field Name*")** function to determine whether a field has changed. The following code example shows how to use an If staement to determine determine whether the PaidInFull field has been changed.</span></span>

```vb 
 
If  Updated("PaidInFull")   Then 
 
    /* Perform actions based on changes to the field.   */ 
 
End If 
 
```

<span data-ttu-id="1c0c3-113">可以使用以下语法访问已删除记录中的某个值。</span><span class="sxs-lookup"><span data-stu-id="1c0c3-113">You can use access a value in the deleted record by using the following syntax.</span></span>

`[Old].[Field Name]`

<span data-ttu-id="1c0c3-114">例如，若要访问已删除记录中 QuantityInStock 字段的值，请使用以下语法。</span><span class="sxs-lookup"><span data-stu-id="1c0c3-114">For example, to access the value of the QuantityInStock field in the deleted record, use the following syntax.</span></span>

`[Old].[QuantityInStock]`

<span data-ttu-id="1c0c3-115">在**删除后**事件结束时，已删除记录中包含的值将被永久删除。</span><span class="sxs-lookup"><span data-stu-id="1c0c3-115">The values contained in the deleted record are deleted permanently when the **After Delete** event ends.</span></span>

<span data-ttu-id="1c0c3-116">以下宏命令可中的**删除后**事件。</span><span class="sxs-lookup"><span data-stu-id="1c0c3-116">The following macro commands can be used in the **After Delete** event.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="1c0c3-117">命令类型</span><span class="sxs-lookup"><span data-stu-id="1c0c3-117">Command Type</span></span></p></th>
<th><p><span data-ttu-id="1c0c3-118">命令</span><span class="sxs-lookup"><span data-stu-id="1c0c3-118">Command</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1c0c3-119">程序流</span><span class="sxs-lookup"><span data-stu-id="1c0c3-119">Program Flow</span></span></p></td>
<td><p><span data-ttu-id="1c0c3-120"><a href="comment-macro-statement.md">注释宏语句</a></span><span class="sxs-lookup"><span data-stu-id="1c0c3-120"><a href="comment-macro-statement.md">Comment Macro Statement</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1c0c3-121">程序流</span><span class="sxs-lookup"><span data-stu-id="1c0c3-121">Program Flow</span></span></p></td>
<td><p><span data-ttu-id="1c0c3-122"><a href="group-macro-statement.md">Group 宏语句</a></span><span class="sxs-lookup"><span data-stu-id="1c0c3-122"><a href="group-macro-statement.md">Group Macro Statement</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1c0c3-123">程序流</span><span class="sxs-lookup"><span data-stu-id="1c0c3-123">Program Flow</span></span></p></td>
<td><p><span data-ttu-id="1c0c3-124"><a href="if-then-else-macro-block.md">如果...然后...其他宏程序块</a></span><span class="sxs-lookup"><span data-stu-id="1c0c3-124"><a href="if-then-else-macro-block.md">If...Then...Else Macro Block</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1c0c3-125">数据块</span><span class="sxs-lookup"><span data-stu-id="1c0c3-125">Data Block</span></span></p></td>
<td><p><span data-ttu-id="1c0c3-126"><a href="createrecord-data-block.md">CreateRecord 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="1c0c3-126"><a href="createrecord-data-block.md">CreateRecord Macro Action</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1c0c3-127">数据块</span><span class="sxs-lookup"><span data-stu-id="1c0c3-127">Data Block</span></span></p></td>
<td><p><span data-ttu-id="1c0c3-128"><a href="editrecord-data-block.md">EditRecord 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="1c0c3-128"><a href="editrecord-data-block.md">EditRecord Macro Action</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1c0c3-129">数据块</span><span class="sxs-lookup"><span data-stu-id="1c0c3-129">Data Block</span></span></p></td>
<td><p><span data-ttu-id="1c0c3-130"><a href="foreachrecord-data-block.md">ForEachRecord 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="1c0c3-130"><a href="foreachrecord-data-block.md">ForEachRecord Macro Action</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1c0c3-131">数据块</span><span class="sxs-lookup"><span data-stu-id="1c0c3-131">Data Block</span></span></p></td>
<td><p><span data-ttu-id="1c0c3-132"><a href="lookuprecord-data-block.md">LookupRecord 数据块</a></span><span class="sxs-lookup"><span data-stu-id="1c0c3-132"><a href="lookuprecord-data-block.md">LookupRecord Data Block</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1c0c3-133">数据操作</span><span class="sxs-lookup"><span data-stu-id="1c0c3-133">Data Action</span></span></p></td>
<td><p><span data-ttu-id="1c0c3-134"><a href="cancelrecordchange-macro-action.md">CancelRecordChange 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="1c0c3-134"><a href="cancelrecordchange-macro-action.md">CancelRecordChange Macro Action</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1c0c3-135">数据操作</span><span class="sxs-lookup"><span data-stu-id="1c0c3-135">Data Action</span></span></p></td>
<td><p><span data-ttu-id="1c0c3-136"><a href="clearmacroerror-macro-action.md">ClearMacroError 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="1c0c3-136"><a href="clearmacroerror-macro-action.md">ClearMacroError Macro Action</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1c0c3-137">数据操作</span><span class="sxs-lookup"><span data-stu-id="1c0c3-137">Data Action</span></span></p></td>
<td><p><span data-ttu-id="1c0c3-138"><a href="deleterecord-macro-action.md">DeleteRecord 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="1c0c3-138"><a href="deleterecord-macro-action.md">DeleteRecord Macro Action</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1c0c3-139">数据操作</span><span class="sxs-lookup"><span data-stu-id="1c0c3-139">Data Action</span></span></p></td>
<td><p><span data-ttu-id="1c0c3-140"><a href="exitforeachrecord-macro-action.md">ExitForEachRecord 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="1c0c3-140"><a href="exitforeachrecord-macro-action.md">ExitForEachRecord Macro Action</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1c0c3-141">数据操作</span><span class="sxs-lookup"><span data-stu-id="1c0c3-141">Data Action</span></span></p></td>
<td><p><span data-ttu-id="1c0c3-142"><a href="logevent-macro-action.md">LogEvent 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="1c0c3-142"><a href="logevent-macro-action.md">LogEvent Macro Action</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1c0c3-143">数据操作</span><span class="sxs-lookup"><span data-stu-id="1c0c3-143">Data Action</span></span></p></td>
<td><p><span data-ttu-id="1c0c3-144"><a href="onerror-macro-action.md">OnError 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="1c0c3-144"><a href="onerror-macro-action.md">OnError Macro Action</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1c0c3-145">数据操作</span><span class="sxs-lookup"><span data-stu-id="1c0c3-145">Data Action</span></span></p></td>
<td><p><span data-ttu-id="1c0c3-146"><a href="raiseerror-macro-action.md">RaiseError 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="1c0c3-146"><a href="raiseerror-macro-action.md">RaiseError Macro Action</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1c0c3-147">数据操作</span><span class="sxs-lookup"><span data-stu-id="1c0c3-147">Data Action</span></span></p></td>
<td><p><span data-ttu-id="1c0c3-148"><a href="rundatamacro-macro-action.md">RunDataMacro 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="1c0c3-148"><a href="rundatamacro-macro-action.md">RunDataMacro Macro Action</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1c0c3-149">数据操作</span><span class="sxs-lookup"><span data-stu-id="1c0c3-149">Data Action</span></span></p></td>
<td><p><span data-ttu-id="1c0c3-150"><a href="sendemail-macro-action.md">SendEmail 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="1c0c3-150"><a href="sendemail-macro-action.md">SendEmail Macro Action</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1c0c3-151">数据操作</span><span class="sxs-lookup"><span data-stu-id="1c0c3-151">Data Action</span></span></p></td>
<td><p><span data-ttu-id="1c0c3-152"><a href="setfield-macro-action.md">SetField 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="1c0c3-152"><a href="setfield-macro-action.md">SetField Macro Action</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1c0c3-153">数据操作</span><span class="sxs-lookup"><span data-stu-id="1c0c3-153">Data Action</span></span></p></td>
<td><p><span data-ttu-id="1c0c3-154"><a href="setlocalvar-macro-action.md">SetLocalVar 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="1c0c3-154"><a href="setlocalvar-macro-action.md">SetLocalVar Macro Action</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1c0c3-155">数据操作</span><span class="sxs-lookup"><span data-stu-id="1c0c3-155">Data Action</span></span></p></td>
<td><p><span data-ttu-id="1c0c3-156"><a href="stopallmacros-macro-action.md">StopAllMacros 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="1c0c3-156"><a href="stopallmacros-macro-action.md">StopAllMacros Macro Action</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1c0c3-157">数据操作</span><span class="sxs-lookup"><span data-stu-id="1c0c3-157">Data Action</span></span></p></td>
<td><p><span data-ttu-id="1c0c3-158"><a href="stopmacro-macro-action.md">StopMacro 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="1c0c3-158"><a href="stopmacro-macro-action.md">StopMacro Macro Action</a></span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="1c0c3-159">若要创建可捕获**删除后**事件的数据宏，请使用以下步骤。</span><span class="sxs-lookup"><span data-stu-id="1c0c3-159">To create a Data Macro that captures the **After Delete** event, use the following steps.</span></span>

1.  <span data-ttu-id="1c0c3-160">打开要为其捕获**删除后**事件的表格。</span><span class="sxs-lookup"><span data-stu-id="1c0c3-160">Open the table for which you want to capture the **After Delete** event.</span></span>

2.  <span data-ttu-id="1c0c3-161">在 **“表格”** 选项卡上的 **“后期事件”** 组中，单击 **“删除后”**。</span><span class="sxs-lookup"><span data-stu-id="1c0c3-161">On the **Table** tab, in the **After Events** group, click **After Delete**.</span></span>

<span data-ttu-id="1c0c3-162">宏设计器中将显示一个空白数据宏。</span><span class="sxs-lookup"><span data-stu-id="1c0c3-162">An empty Data Macro is displayed in the macro designer.</span></span>

## <a name="example"></a><span data-ttu-id="1c0c3-163">示例</span><span class="sxs-lookup"><span data-stu-id="1c0c3-163">Example</span></span>

<span data-ttu-id="1c0c3-164">下面的代码示例使用**删除后**事件执行一些处理时从捐赠表中删除一条记录。</span><span class="sxs-lookup"><span data-stu-id="1c0c3-164">The following code example uses the **After Delete** event to perform some processing when a record is deleted from the Donations table.</span></span> <span data-ttu-id="1c0c3-165">当删除记录时，捐赠量 subracted 窗体 DonationsReceived 表中的 DonationsReceived 字段和 TotalDonatedField 赞助商表中。</span><span class="sxs-lookup"><span data-stu-id="1c0c3-165">When a record is deleted, the amount of the donation is subracted form the DonationsReceived field in the DonationsReceived table and the TotalDonatedField in the Donors table.</span></span>

<span data-ttu-id="1c0c3-166">**单击此处查看您可以将其粘贴到宏设计器的宏副本。**</span><span class="sxs-lookup"><span data-stu-id="1c0c3-166">**Click here to view a copy of the macro that you can paste into Macro Designer.**</span></span>

<span data-ttu-id="1c0c3-167">若要在宏设计器查看此示例，请执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="1c0c3-167">To view this example in the macro designer, use the following steps.</span></span>

1.  <span data-ttu-id="1c0c3-168">打开要为其捕获**删除后**事件的表格。</span><span class="sxs-lookup"><span data-stu-id="1c0c3-168">Open the table for which you want to capture the **After Delete** event.</span></span>

2.  <span data-ttu-id="1c0c3-169">在 **“表格”** 选项卡上的 **“后期事件”** 组中，单击 **“删除后”**。</span><span class="sxs-lookup"><span data-stu-id="1c0c3-169">On the **Table** tab, in the **After Events** group, click **After Delete**.</span></span>

3.  <span data-ttu-id="1c0c3-170">选择下面列出的代码，然后按 Ctrl+C 将其复制到剪贴板。</span><span class="sxs-lookup"><span data-stu-id="1c0c3-170">Select the code listed below and then press CTRL+C to copy it to the Clipboard.</span></span>

4.  <span data-ttu-id="1c0c3-171">激活宏设计器窗口，然后按 Ctrl+V。</span><span class="sxs-lookup"><span data-stu-id="1c0c3-171">Activate the macro designer window and then press CTRL+V.</span></span>

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
