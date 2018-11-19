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
ms.openlocfilehash: af6bc99374c67560e9cd78a9f26bc9dd601c70d8
ms.sourcegitcommit: 45feafb3b55de0402dddf5548c0c1c43a0eabafd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2018
ms.locfileid: "26026146"
---
# <a name="after-insert-macro-event"></a><span data-ttu-id="a2b8c-102">After Insert 宏事件</span><span class="sxs-lookup"><span data-stu-id="a2b8c-102">After Insert macro event</span></span>

<span data-ttu-id="a2b8c-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="a2b8c-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="a2b8c-104">添加一条记录之后，发生此事件的**插入后**事件。</span><span class="sxs-lookup"><span data-stu-id="a2b8c-104">The **After Insert** event occurs after a record is added.</span></span>

> [!NOTE]
> <span data-ttu-id="a2b8c-105">在**插入后**事件仅适用于数据宏。</span><span class="sxs-lookup"><span data-stu-id="a2b8c-105">The **After Insert** event is available only in Data Macros.</span></span>

## <a name="remarks"></a><span data-ttu-id="a2b8c-106">备注</span><span class="sxs-lookup"><span data-stu-id="a2b8c-106">Remarks</span></span>

<span data-ttu-id="a2b8c-107">使用**插入后**事件执行您想要将记录添加到表时，会发生任何操作。</span><span class="sxs-lookup"><span data-stu-id="a2b8c-107">Use the **After Insert** event to perform any actions that you want to occur when a record is added to a table.</span></span> <span data-ttu-id="a2b8c-108">**插入后**的常见用途包括强制实施业务规则，工作流、 更新聚合总数，以及发送通知。</span><span class="sxs-lookup"><span data-stu-id="a2b8c-108">Common uses for the **After Insert** include enforcing business rules, workflows, updating an aggregate total, and sending notifications.</span></span>

<span data-ttu-id="a2b8c-p102">可以使用 **Updated("*Field Name*")** 函数确定某个字段是否已更改。下面的代码示例演示了如何使用 **If** 语句来确定 PaidInFull 字段是否已更改。</span><span class="sxs-lookup"><span data-stu-id="a2b8c-p102">You can use the **Updated("*Field Name*")** function to determine whether a field has changed. The following code example shows how to use an **If** statement to determine determine whether the PaidInFull field has been changed.</span></span>

```vb 
 
If  Updated("PaidInFull")   Then 
 
    /* Perform actions based on changes to the field.   */ 
 
End If 
 
```

<span data-ttu-id="a2b8c-111">下表列出了可在**插入后**事件中使用的宏命令。</span><span class="sxs-lookup"><span data-stu-id="a2b8c-111">The following table lists macro commands that can be used in the**After Insert** event.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="a2b8c-112">命令类型</span><span class="sxs-lookup"><span data-stu-id="a2b8c-112">Command Type</span></span></p></th>
<th><p><span data-ttu-id="a2b8c-113">命令</span><span class="sxs-lookup"><span data-stu-id="a2b8c-113">Command</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a2b8c-114">程序流</span><span class="sxs-lookup"><span data-stu-id="a2b8c-114">Program Flow</span></span></p></td>
<td><p><span data-ttu-id="a2b8c-115"><a href="comment-macro-statement.md">Comment 宏语句</a></span><span class="sxs-lookup"><span data-stu-id="a2b8c-115"><a href="comment-macro-statement.md">Comment macro statement</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2b8c-116">程序流</span><span class="sxs-lookup"><span data-stu-id="a2b8c-116">Program Flow</span></span></p></td>
<td><p><span data-ttu-id="a2b8c-117"><a href="group-macro-statement.md">Group 宏语句</a></span><span class="sxs-lookup"><span data-stu-id="a2b8c-117"><a href="group-macro-statement.md">Group macro statement</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2b8c-118">程序流</span><span class="sxs-lookup"><span data-stu-id="a2b8c-118">Program Flow</span></span></p></td>
<td><p><span data-ttu-id="a2b8c-119"><a href="if-then-else-macro-block.md">If...Then...Else 宏程序块</a></span><span class="sxs-lookup"><span data-stu-id="a2b8c-119"><a href="if-then-else-macro-block.md">If...Then...Else macro block</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2b8c-120">数据块</span><span class="sxs-lookup"><span data-stu-id="a2b8c-120">Data Block</span></span></p></td>
<td><p><span data-ttu-id="a2b8c-121"><a href="createrecord-data-block.md">CreateRecord 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="a2b8c-121"><a href="createrecord-data-block.md">CreateRecord macro action</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2b8c-122">数据块</span><span class="sxs-lookup"><span data-stu-id="a2b8c-122">Data Block</span></span></p></td>
<td><p><span data-ttu-id="a2b8c-123"><a href="editrecord-data-block.md">EditRecord 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="a2b8c-123"><a href="editrecord-data-block.md">EditRecord macro action</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2b8c-124">数据块</span><span class="sxs-lookup"><span data-stu-id="a2b8c-124">Data Block</span></span></p></td>
<td><p><span data-ttu-id="a2b8c-125"><a href="foreachrecord-data-block.md">ForEachRecord 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="a2b8c-125"><a href="foreachrecord-data-block.md">ForEachRecord macro action</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2b8c-126">数据块</span><span class="sxs-lookup"><span data-stu-id="a2b8c-126">Data Block</span></span></p></td>
<td><p><span data-ttu-id="a2b8c-127"><a href="lookuprecord-data-block.md">LookupRecord 数据块</a></span><span class="sxs-lookup"><span data-stu-id="a2b8c-127"><a href="lookuprecord-data-block.md">LookupRecord data block</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2b8c-128">数据操作</span><span class="sxs-lookup"><span data-stu-id="a2b8c-128">Data Action</span></span></p></td>
<td><p><span data-ttu-id="a2b8c-129"><a href="cancelrecordchange-macro-action.md">CancelRecordChange 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="a2b8c-129"><a href="cancelrecordchange-macro-action.md">CancelRecordChange macro action</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2b8c-130">数据操作</span><span class="sxs-lookup"><span data-stu-id="a2b8c-130">Data Action</span></span></p></td>
<td><p><span data-ttu-id="a2b8c-131"><a href="clearmacroerror-macro-action.md">ClearMacroError 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="a2b8c-131"><a href="clearmacroerror-macro-action.md">ClearMacroError macro action</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2b8c-132">数据操作</span><span class="sxs-lookup"><span data-stu-id="a2b8c-132">Data Action</span></span></p></td>
<td><p><span data-ttu-id="a2b8c-133"><a href="deleterecord-macro-action.md">DeleteRecord 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="a2b8c-133"><a href="deleterecord-macro-action.md">DeleteRecord macro action</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2b8c-134">数据操作</span><span class="sxs-lookup"><span data-stu-id="a2b8c-134">Data Action</span></span></p></td>
<td><p><span data-ttu-id="a2b8c-135"><a href="exitforeachrecord-macro-action.md">ExitForEachRecord 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="a2b8c-135"><a href="exitforeachrecord-macro-action.md">ExitForEachRecord macro action</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2b8c-136">数据操作</span><span class="sxs-lookup"><span data-stu-id="a2b8c-136">Data Action</span></span></p></td>
<td><p><span data-ttu-id="a2b8c-137"><a href="logevent-macro-action.md">LogEvent 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="a2b8c-137"><a href="logevent-macro-action.md">LogEvent macro action</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2b8c-138">数据操作</span><span class="sxs-lookup"><span data-stu-id="a2b8c-138">Data Action</span></span></p></td>
<td><p><span data-ttu-id="a2b8c-139"><a href="onerror-macro-action.md">OnError 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="a2b8c-139"><a href="onerror-macro-action.md">OnError macro action</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2b8c-140">数据操作</span><span class="sxs-lookup"><span data-stu-id="a2b8c-140">Data Action</span></span></p></td>
<td><p><span data-ttu-id="a2b8c-141"><a href="raiseerror-macro-action.md">RaiseError 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="a2b8c-141"><a href="raiseerror-macro-action.md">RaiseError macro action</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2b8c-142">数据操作</span><span class="sxs-lookup"><span data-stu-id="a2b8c-142">Data Action</span></span></p></td>
<td><p><span data-ttu-id="a2b8c-143"><a href="rundatamacro-macro-action.md">RunDataMacro 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="a2b8c-143"><a href="rundatamacro-macro-action.md">RunDataMacro macro action</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2b8c-144">数据操作</span><span class="sxs-lookup"><span data-stu-id="a2b8c-144">Data Action</span></span></p></td>
<td><p><span data-ttu-id="a2b8c-145"><a href="sendemail-macro-action.md">SendEmail 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="a2b8c-145"><a href="sendemail-macro-action.md">SendEmail macro action</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2b8c-146">数据操作</span><span class="sxs-lookup"><span data-stu-id="a2b8c-146">Data Action</span></span></p></td>
<td><p><span data-ttu-id="a2b8c-147"><a href="setfield-macro-action.md">SetField 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="a2b8c-147"><a href="setfield-macro-action.md">SetField macro action</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2b8c-148">数据操作</span><span class="sxs-lookup"><span data-stu-id="a2b8c-148">Data Action</span></span></p></td>
<td><p><span data-ttu-id="a2b8c-149"><a href="setlocalvar-macro-action.md">SetLocalVar 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="a2b8c-149"><a href="setlocalvar-macro-action.md">SetLocalVar macro action</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2b8c-150">数据操作</span><span class="sxs-lookup"><span data-stu-id="a2b8c-150">Data Action</span></span></p></td>
<td><p><span data-ttu-id="a2b8c-151"><a href="stopallmacros-macro-action.md">StopAllMacros 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="a2b8c-151"><a href="stopallmacros-macro-action.md">StopAllMacros macro action</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2b8c-152">数据操作</span><span class="sxs-lookup"><span data-stu-id="a2b8c-152">Data Action</span></span></p></td>
<td><p><span data-ttu-id="a2b8c-153"><a href="stopmacro-macro-action.md">StopMacro 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="a2b8c-153"><a href="stopmacro-macro-action.md">StopMacro macro action</a></span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a2b8c-154">若要创建可捕获**插入后**事件的数据宏，请使用以下步骤。</span><span class="sxs-lookup"><span data-stu-id="a2b8c-154">To create a Data macro that captures the **After Insert** event, use the following steps.</span></span>

1.  <span data-ttu-id="a2b8c-155">打开要为其捕获**插入后**事件的表格。</span><span class="sxs-lookup"><span data-stu-id="a2b8c-155">Open the table for which you want to capture the **After Insert** event.</span></span>

2.  <span data-ttu-id="a2b8c-156">在 **“表格”** 选项卡上的 **“后期事件”** 组中，单击 **“插入后”**。</span><span class="sxs-lookup"><span data-stu-id="a2b8c-156">On the **Table** tab, in the **After Events** group, click **After Insert**.</span></span>

<span data-ttu-id="a2b8c-157">宏设计器中将显示一个空白数据宏。</span><span class="sxs-lookup"><span data-stu-id="a2b8c-157">An empty data macro is displayed in the macro designer.</span></span>

## <a name="example"></a><span data-ttu-id="a2b8c-158">示例</span><span class="sxs-lookup"><span data-stu-id="a2b8c-158">Example</span></span>

<span data-ttu-id="a2b8c-159">下面的代码示例使用**插入后**事件执行一些处理，当记录被添加到捐赠表。</span><span class="sxs-lookup"><span data-stu-id="a2b8c-159">The following code example uses the **After Insert** event to perform some processing when a record is added to the Donations table.</span></span> <span data-ttu-id="a2b8c-160">当记录被添加时，捐赠量添加到活动表中的 DonationsReceived 字段和 TotalDonatedField 赞助商表中。</span><span class="sxs-lookup"><span data-stu-id="a2b8c-160">When a record is added, the amount of the donation is added to the DonationsReceived field in the Campaigns table and the TotalDonatedField in the Donors table.</span></span>

<span data-ttu-id="a2b8c-161">**单击此处查看您可以将其粘贴到宏设计器的宏副本。**</span><span class="sxs-lookup"><span data-stu-id="a2b8c-161">**Click here to view a copy of the macro that you can paste into Macro Designer.**</span></span>

<span data-ttu-id="a2b8c-162">若要在宏设计器查看此示例，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="a2b8c-162">To view this example in the macro designer, use the following steps:</span></span>

1.  <span data-ttu-id="a2b8c-163">打开要为其捕获**插入后**事件的表格。</span><span class="sxs-lookup"><span data-stu-id="a2b8c-163">Open the table for which you want to capture the **After Insert** event.</span></span>

2.  <span data-ttu-id="a2b8c-164">在 **“表格”** 选项卡上的 **“后期事件”** 组中，单击 **“插入后”**。</span><span class="sxs-lookup"><span data-stu-id="a2b8c-164">On the **Table** tab, in the **After Events** group, click **After Insert**.</span></span>

3.  <span data-ttu-id="a2b8c-165">选择以下代码示例中的代码，然后按 Ctrl+C 将其复制到剪贴板。</span><span class="sxs-lookup"><span data-stu-id="a2b8c-165">Select the code in the following code example and then press CTRL+C to copy it to the Clipboard.</span></span>

4.  <span data-ttu-id="a2b8c-166">激活宏设计器窗口，然后按 Ctrl+V。</span><span class="sxs-lookup"><span data-stu-id="a2b8c-166">Activate the macro designer window and then press CTRL+V.</span></span>

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
