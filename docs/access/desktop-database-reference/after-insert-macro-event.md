---
title: “插入后”宏事件
TOCTitle: After Insert Macro Event
ms:assetid: 78013896-ee07-6979-96f7-fa0f3490419e
ms:mtpsurl: https://msdn.microsoft.com/library/Ff196099(v=office.15)
ms:contentKeyID: 48545742
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm3180
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 171c7b11db6fa79c6b69f3517abaddf052c96da3
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25880724"
---
# <a name="after-insert-macro-event"></a><span data-ttu-id="e7394-102">“插入后”宏事件</span><span class="sxs-lookup"><span data-stu-id="e7394-102">After Insert Macro Event</span></span>


<span data-ttu-id="e7394-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="e7394-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="e7394-104">添加一条记录之后，发生此事件的**插入后**事件。</span><span class="sxs-lookup"><span data-stu-id="e7394-104">The **After Insert** event occurs after a record is added.</span></span>


> [!NOTE]
> <span data-ttu-id="e7394-105">在**插入后**事件仅适用于数据宏。</span><span class="sxs-lookup"><span data-stu-id="e7394-105">The **After Insert** event is available only in Data Macros.</span></span>



## <a name="remarks"></a><span data-ttu-id="e7394-106">说明</span><span class="sxs-lookup"><span data-stu-id="e7394-106">Remarks</span></span>

<span data-ttu-id="e7394-107">使用**插入后**事件执行您想要将记录添加到表时，会发生任何操作。</span><span class="sxs-lookup"><span data-stu-id="e7394-107">Use the **After Insert** event to perform any actions that you want to occur when a record is added to a table.</span></span> <span data-ttu-id="e7394-108">**插入后**的常见用途包括强制实施业务规则，工作流、 更新聚合总数，以及发送通知。</span><span class="sxs-lookup"><span data-stu-id="e7394-108">Common uses for the **After Insert** include enforcing business rules, workflows, updating an aggregate total, and sending notifications.</span></span>

<span data-ttu-id="e7394-p102">可以使用 **Updated("*Field Name*")** 函数确定某个字段是否已更改。下面的代码示例演示了如何使用 **If** 语句来确定 PaidInFull 字段是否已更改。</span><span class="sxs-lookup"><span data-stu-id="e7394-p102">You can use the **Updated("*Field Name*")** function to determine whether a field has changed. The following code example shows how to use an **If** statement to determine determine whether the PaidInFull field has been changed.</span></span>

```vb 
 
If  Updated("PaidInFull")   Then 
 
    /* Perform actions based on changes to the field.   */ 
 
End If 
 
```

<span data-ttu-id="e7394-111">下表列出了可在**插入后**事件中使用的宏命令。</span><span class="sxs-lookup"><span data-stu-id="e7394-111">The following table lists macro commands that can be used in the**After Insert** event.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="e7394-112">命令类型</span><span class="sxs-lookup"><span data-stu-id="e7394-112">Command Type</span></span></p></th>
<th><p><span data-ttu-id="e7394-113">命令</span><span class="sxs-lookup"><span data-stu-id="e7394-113">Command</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e7394-114">程序流</span><span class="sxs-lookup"><span data-stu-id="e7394-114">Program Flow</span></span></p></td>
<td><p><span data-ttu-id="e7394-115"><a href="comment-macro-statement.md">注释宏语句</a></span><span class="sxs-lookup"><span data-stu-id="e7394-115"><a href="comment-macro-statement.md">Comment Macro Statement</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7394-116">程序流</span><span class="sxs-lookup"><span data-stu-id="e7394-116">Program Flow</span></span></p></td>
<td><p><span data-ttu-id="e7394-117"><a href="group-macro-statement.md">Group 宏语句</a></span><span class="sxs-lookup"><span data-stu-id="e7394-117"><a href="group-macro-statement.md">Group Macro Statement</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7394-118">程序流</span><span class="sxs-lookup"><span data-stu-id="e7394-118">Program Flow</span></span></p></td>
<td><p><span data-ttu-id="e7394-119"><a href="if-then-else-macro-block.md">如果...然后...其他宏程序块</a></span><span class="sxs-lookup"><span data-stu-id="e7394-119"><a href="if-then-else-macro-block.md">If...Then...Else Macro Block</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7394-120">数据块</span><span class="sxs-lookup"><span data-stu-id="e7394-120">Data Block</span></span></p></td>
<td><p><span data-ttu-id="e7394-121"><a href="createrecord-data-block.md">CreateRecord 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="e7394-121"><a href="createrecord-data-block.md">CreateRecord Macro Action</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7394-122">数据块</span><span class="sxs-lookup"><span data-stu-id="e7394-122">Data Block</span></span></p></td>
<td><p><span data-ttu-id="e7394-123"><a href="editrecord-data-block.md">EditRecord 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="e7394-123"><a href="editrecord-data-block.md">EditRecord Macro Action</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7394-124">数据块</span><span class="sxs-lookup"><span data-stu-id="e7394-124">Data Block</span></span></p></td>
<td><p><span data-ttu-id="e7394-125"><a href="foreachrecord-data-block.md">ForEachRecord 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="e7394-125"><a href="foreachrecord-data-block.md">ForEachRecord Macro Action</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7394-126">数据块</span><span class="sxs-lookup"><span data-stu-id="e7394-126">Data Block</span></span></p></td>
<td><p><span data-ttu-id="e7394-127"><a href="lookuprecord-data-block.md">LookupRecord 数据块</a></span><span class="sxs-lookup"><span data-stu-id="e7394-127"><a href="lookuprecord-data-block.md">LookupRecord Data Block</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7394-128">数据操作</span><span class="sxs-lookup"><span data-stu-id="e7394-128">Data Action</span></span></p></td>
<td><p><span data-ttu-id="e7394-129"><a href="cancelrecordchange-macro-action.md">CancelRecordChange 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="e7394-129"><a href="cancelrecordchange-macro-action.md">CancelRecordChange Macro Action</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7394-130">数据操作</span><span class="sxs-lookup"><span data-stu-id="e7394-130">Data Action</span></span></p></td>
<td><p><span data-ttu-id="e7394-131"><a href="clearmacroerror-macro-action.md">ClearMacroError 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="e7394-131"><a href="clearmacroerror-macro-action.md">ClearMacroError Macro Action</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7394-132">数据操作</span><span class="sxs-lookup"><span data-stu-id="e7394-132">Data Action</span></span></p></td>
<td><p><span data-ttu-id="e7394-133"><a href="deleterecord-macro-action.md">DeleteRecord 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="e7394-133"><a href="deleterecord-macro-action.md">DeleteRecord Macro Action</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7394-134">数据操作</span><span class="sxs-lookup"><span data-stu-id="e7394-134">Data Action</span></span></p></td>
<td><p><span data-ttu-id="e7394-135"><a href="exitforeachrecord-macro-action.md">ExitForEachRecord 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="e7394-135"><a href="exitforeachrecord-macro-action.md">ExitForEachRecord Macro Action</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7394-136">数据操作</span><span class="sxs-lookup"><span data-stu-id="e7394-136">Data Action</span></span></p></td>
<td><p><span data-ttu-id="e7394-137"><a href="logevent-macro-action.md">LogEvent 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="e7394-137"><a href="logevent-macro-action.md">LogEvent Macro Action</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7394-138">数据操作</span><span class="sxs-lookup"><span data-stu-id="e7394-138">Data Action</span></span></p></td>
<td><p><span data-ttu-id="e7394-139"><a href="onerror-macro-action.md">OnError 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="e7394-139"><a href="onerror-macro-action.md">OnError Macro Action</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7394-140">数据操作</span><span class="sxs-lookup"><span data-stu-id="e7394-140">Data Action</span></span></p></td>
<td><p><span data-ttu-id="e7394-141"><a href="raiseerror-macro-action.md">RaiseError 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="e7394-141"><a href="raiseerror-macro-action.md">RaiseError Macro Action</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7394-142">数据操作</span><span class="sxs-lookup"><span data-stu-id="e7394-142">Data Action</span></span></p></td>
<td><p><span data-ttu-id="e7394-143"><a href="rundatamacro-macro-action.md">RunDataMacro 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="e7394-143"><a href="rundatamacro-macro-action.md">RunDataMacro Macro Action</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7394-144">数据操作</span><span class="sxs-lookup"><span data-stu-id="e7394-144">Data Action</span></span></p></td>
<td><p><span data-ttu-id="e7394-145"><a href="sendemail-macro-action.md">SendEmail 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="e7394-145"><a href="sendemail-macro-action.md">SendEmail Macro Action</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7394-146">数据操作</span><span class="sxs-lookup"><span data-stu-id="e7394-146">Data Action</span></span></p></td>
<td><p><span data-ttu-id="e7394-147"><a href="setfield-macro-action.md">SetField 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="e7394-147"><a href="setfield-macro-action.md">SetField Macro Action</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7394-148">数据操作</span><span class="sxs-lookup"><span data-stu-id="e7394-148">Data Action</span></span></p></td>
<td><p><span data-ttu-id="e7394-149"><a href="setlocalvar-macro-action.md">SetLocalVar 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="e7394-149"><a href="setlocalvar-macro-action.md">SetLocalVar Macro Action</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7394-150">数据操作</span><span class="sxs-lookup"><span data-stu-id="e7394-150">Data Action</span></span></p></td>
<td><p><span data-ttu-id="e7394-151"><a href="stopallmacros-macro-action.md">StopAllMacros 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="e7394-151"><a href="stopallmacros-macro-action.md">StopAllMacros Macro Action</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7394-152">数据操作</span><span class="sxs-lookup"><span data-stu-id="e7394-152">Data Action</span></span></p></td>
<td><p><span data-ttu-id="e7394-153"><a href="stopmacro-macro-action.md">StopMacro 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="e7394-153"><a href="stopmacro-macro-action.md">StopMacro Macro Action</a></span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e7394-154">若要创建可捕获**插入后**事件的数据宏，请使用以下步骤。</span><span class="sxs-lookup"><span data-stu-id="e7394-154">To create a Data macro that captures the **After Insert** event, use the following steps.</span></span>

1.  <span data-ttu-id="e7394-155">打开要为其捕获**插入后**事件的表格。</span><span class="sxs-lookup"><span data-stu-id="e7394-155">Open the table for which you want to capture the **After Insert** event.</span></span>

2.  <span data-ttu-id="e7394-156">在 **“表格”** 选项卡上的 **“后期事件”** 组中，单击 **“插入后”**。</span><span class="sxs-lookup"><span data-stu-id="e7394-156">On the **Table** tab, in the **After Events** group, click **After Insert**.</span></span>

<span data-ttu-id="e7394-157">宏设计器中将显示一个空白数据宏。</span><span class="sxs-lookup"><span data-stu-id="e7394-157">An empty data macro is displayed in the macro designer.</span></span>

## <a name="example"></a><span data-ttu-id="e7394-158">示例</span><span class="sxs-lookup"><span data-stu-id="e7394-158">Example</span></span>

<span data-ttu-id="e7394-159">下面的代码示例使用**插入后**事件执行一些处理，当记录被添加到捐赠表。</span><span class="sxs-lookup"><span data-stu-id="e7394-159">The following code example uses the **After Insert** event to perform some processing when a record is added to the Donations table.</span></span> <span data-ttu-id="e7394-160">当记录被添加时，捐赠量添加到活动表中的 DonationsReceived 字段和 TotalDonatedField 赞助商表中。</span><span class="sxs-lookup"><span data-stu-id="e7394-160">When a record is added, the amount of the donation is added to the DonationsReceived field in the Campaigns table and the TotalDonatedField in the Donors table.</span></span>

<span data-ttu-id="e7394-161">**单击此处查看您可以将其粘贴到宏设计器的宏副本。**</span><span class="sxs-lookup"><span data-stu-id="e7394-161">**Click here to view a copy of the macro that you can paste into Macro Designer.**</span></span>

<span data-ttu-id="e7394-162">若要在宏设计器查看此示例，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="e7394-162">To view this example in the macro designer, use the following steps:</span></span>

1.  <span data-ttu-id="e7394-163">打开要为其捕获**插入后**事件的表格。</span><span class="sxs-lookup"><span data-stu-id="e7394-163">Open the table for which you want to capture the **After Insert** event.</span></span>

2.  <span data-ttu-id="e7394-164">在 **“表格”** 选项卡上的 **“后期事件”** 组中，单击 **“插入后”**。</span><span class="sxs-lookup"><span data-stu-id="e7394-164">On the **Table** tab, in the **After Events** group, click **After Insert**.</span></span>

3.  <span data-ttu-id="e7394-165">选择以下代码示例中的代码，然后按 Ctrl+C 将其复制到剪贴板。</span><span class="sxs-lookup"><span data-stu-id="e7394-165">Select the code in the following code example and then press CTRL+C to copy it to the Clipboard.</span></span>

4.  <span data-ttu-id="e7394-166">激活宏设计器窗口，然后按 Ctrl+V。</span><span class="sxs-lookup"><span data-stu-id="e7394-166">Activate the macro designer window and then press CTRL+V.</span></span>

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
