---
title: After Update 宏事件
TOCTitle: After Update macro event
ms:assetid: 5213793b-8301-0f18-3a12-4e3764c879ac
ms:mtpsurl: https://msdn.microsoft.com/library/Ff193905(v=office.15)
ms:contentKeyID: 48544838
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm85126
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 24a6bbd951fd19e7fdd25f4f1ab8bd8e9dcd2ade
ms.sourcegitcommit: 45feafb3b55de0402dddf5548c0c1c43a0eabafd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2018
ms.locfileid: "26026188"
---
# <a name="after-update-macro-event"></a><span data-ttu-id="175fc-102">After Update 宏事件</span><span class="sxs-lookup"><span data-stu-id="175fc-102">After Update macro event</span></span>

<span data-ttu-id="175fc-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="175fc-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="175fc-104">**更新后**事件发生之后更改的记录。</span><span class="sxs-lookup"><span data-stu-id="175fc-104">The **After Update** event occurs after a record is changed.</span></span>

> [!NOTE]
> <span data-ttu-id="175fc-105">**更新后**事件仅适用于数据宏。</span><span class="sxs-lookup"><span data-stu-id="175fc-105">The **After Update** event is available only in Data Macros.</span></span>

## <a name="remarks"></a><span data-ttu-id="175fc-106">备注</span><span class="sxs-lookup"><span data-stu-id="175fc-106">Remarks</span></span>

<span data-ttu-id="175fc-107">使用**更新后**事件执行您想要更改的记录时，会发生任何操作。</span><span class="sxs-lookup"><span data-stu-id="175fc-107">Use the **After Update** event to perform any actions that you want to occur when a record is changed.</span></span> <span data-ttu-id="175fc-108">**插入后**的常见用途包括强制实施业务规则、 更新聚合总数，以及发送通知。</span><span class="sxs-lookup"><span data-stu-id="175fc-108">Common uses for the **After Insert** include enforcing business rules, updating an aggregate total, and sending notifications.</span></span>

<span data-ttu-id="175fc-p102">可以使用 **Updated("*Field Name*")** 函数确定某个字段是否已更改。下面的代码示例演示了如何使用 **If** 语句来确定 PaidInFull 字段是否已更改。</span><span class="sxs-lookup"><span data-stu-id="175fc-p102">You can use the **Updated("*Field Name*")** function to determine whether a field has changed. The following code example shows how to use an **If** statement to determine determine whether the PaidInFull field has been changed.</span></span>

```vb 
 
If  Updated("PaidInFull")   Then 
 
    /* Perform actions based on changes to the field.   */ 
 
End If 
 
```

<span data-ttu-id="175fc-111">可以使用以下语法访问字段中以前的某个值。</span><span class="sxs-lookup"><span data-stu-id="175fc-111">You can use access a the previous value in a field by using the following syntax.</span></span>

`[Old].[Field Name]`

<span data-ttu-id="175fc-112">例如，若要访问 QuantityInStock 字段的以前的值，请使用以下语法。</span><span class="sxs-lookup"><span data-stu-id="175fc-112">For example, to access the previous value of the QuantityInStock field, use the following syntax.</span></span>

`[Old].[QuantityInStock]`

<span data-ttu-id="175fc-113">在**更新后**事件结束时，以前的值将被永久删除。</span><span class="sxs-lookup"><span data-stu-id="175fc-113">The previous values are deleted permanently when the **After Update** event ends.</span></span>

<span data-ttu-id="175fc-114">下表列出命令可使用的**更新后**事件中的宏。</span><span class="sxs-lookup"><span data-stu-id="175fc-114">The following table lists macro commands can be used in the**After Update** event.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="175fc-115">命令类型</span><span class="sxs-lookup"><span data-stu-id="175fc-115">Command Type</span></span></p></th>
<th><p><span data-ttu-id="175fc-116">命令</span><span class="sxs-lookup"><span data-stu-id="175fc-116">Command</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="175fc-117">程序流</span><span class="sxs-lookup"><span data-stu-id="175fc-117">Program Flow</span></span></p></td>
<td><p><span data-ttu-id="175fc-118"><a href="comment-macro-statement.md">Comment 宏语句</a></span><span class="sxs-lookup"><span data-stu-id="175fc-118"><a href="comment-macro-statement.md">Comment macro statement</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="175fc-119">程序流</span><span class="sxs-lookup"><span data-stu-id="175fc-119">Program Flow</span></span></p></td>
<td><p><span data-ttu-id="175fc-120"><a href="group-macro-statement.md">Group 宏语句</a></span><span class="sxs-lookup"><span data-stu-id="175fc-120"><a href="group-macro-statement.md">Group macro statement</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="175fc-121">程序流</span><span class="sxs-lookup"><span data-stu-id="175fc-121">Program Flow</span></span></p></td>
<td><p><span data-ttu-id="175fc-122"><a href="if-then-else-macro-block.md">If...Then...Else 宏程序块</a></span><span class="sxs-lookup"><span data-stu-id="175fc-122"><a href="if-then-else-macro-block.md">If...Then...Else macro block</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="175fc-123">数据块</span><span class="sxs-lookup"><span data-stu-id="175fc-123">Data Block</span></span></p></td>
<td><p><span data-ttu-id="175fc-124"><a href="createrecord-data-block.md">CreateRecord 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="175fc-124"><a href="createrecord-data-block.md">CreateRecord macro action</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="175fc-125">数据块</span><span class="sxs-lookup"><span data-stu-id="175fc-125">Data Block</span></span></p></td>
<td><p><span data-ttu-id="175fc-126"><a href="editrecord-data-block.md">EditRecord 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="175fc-126"><a href="editrecord-data-block.md">EditRecord macro action</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="175fc-127">数据块</span><span class="sxs-lookup"><span data-stu-id="175fc-127">Data Block</span></span></p></td>
<td><p><span data-ttu-id="175fc-128"><a href="foreachrecord-data-block.md">ForEachRecord 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="175fc-128"><a href="foreachrecord-data-block.md">ForEachRecord macro action</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="175fc-129">数据块</span><span class="sxs-lookup"><span data-stu-id="175fc-129">Data Block</span></span></p></td>
<td><p><span data-ttu-id="175fc-130"><a href="lookuprecord-data-block.md">LookupRecord 数据块</a></span><span class="sxs-lookup"><span data-stu-id="175fc-130"><a href="lookuprecord-data-block.md">LookupRecord data block</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="175fc-131">数据操作</span><span class="sxs-lookup"><span data-stu-id="175fc-131">Data Action</span></span></p></td>
<td><p><span data-ttu-id="175fc-132"><a href="cancelrecordchange-macro-action.md">CancelRecordChange 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="175fc-132"><a href="cancelrecordchange-macro-action.md">CancelRecordChange macro action</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="175fc-133">数据操作</span><span class="sxs-lookup"><span data-stu-id="175fc-133">Data Action</span></span></p></td>
<td><p><span data-ttu-id="175fc-134"><a href="clearmacroerror-macro-action.md">ClearMacroError 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="175fc-134"><a href="clearmacroerror-macro-action.md">ClearMacroError macro action</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="175fc-135">数据操作</span><span class="sxs-lookup"><span data-stu-id="175fc-135">Data Action</span></span></p></td>
<td><p><span data-ttu-id="175fc-136"><a href="deleterecord-macro-action.md">DeleteRecord 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="175fc-136"><a href="deleterecord-macro-action.md">DeleteRecord macro action</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="175fc-137">数据操作</span><span class="sxs-lookup"><span data-stu-id="175fc-137">Data Action</span></span></p></td>
<td><p><span data-ttu-id="175fc-138"><a href="exitforeachrecord-macro-action.md">ExitForEachRecord 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="175fc-138"><a href="exitforeachrecord-macro-action.md">ExitForEachRecord macro action</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="175fc-139">数据操作</span><span class="sxs-lookup"><span data-stu-id="175fc-139">Data Action</span></span></p></td>
<td><p><span data-ttu-id="175fc-140"><a href="logevent-macro-action.md">LogEvent 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="175fc-140"><a href="logevent-macro-action.md">LogEvent macro action</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="175fc-141">数据操作</span><span class="sxs-lookup"><span data-stu-id="175fc-141">Data Action</span></span></p></td>
<td><p><span data-ttu-id="175fc-142"><a href="onerror-macro-action.md">OnError 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="175fc-142"><a href="onerror-macro-action.md">OnError macro action</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="175fc-143">数据操作</span><span class="sxs-lookup"><span data-stu-id="175fc-143">Data Action</span></span></p></td>
<td><p><span data-ttu-id="175fc-144"><a href="raiseerror-macro-action.md">RaiseError 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="175fc-144"><a href="raiseerror-macro-action.md">RaiseError macro action</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="175fc-145">数据操作</span><span class="sxs-lookup"><span data-stu-id="175fc-145">Data Action</span></span></p></td>
<td><p><span data-ttu-id="175fc-146"><a href="rundatamacro-macro-action.md">RunDataMacro 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="175fc-146"><a href="rundatamacro-macro-action.md">RunDataMacro macro action</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="175fc-147">数据操作</span><span class="sxs-lookup"><span data-stu-id="175fc-147">Data Action</span></span></p></td>
<td><p><span data-ttu-id="175fc-148"><a href="sendemail-macro-action.md">SendEmail 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="175fc-148"><a href="sendemail-macro-action.md">SendEmail macro action</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="175fc-149">数据操作</span><span class="sxs-lookup"><span data-stu-id="175fc-149">Data Action</span></span></p></td>
<td><p><span data-ttu-id="175fc-150"><a href="setfield-macro-action.md">SetField 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="175fc-150"><a href="setfield-macro-action.md">SetField macro action</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="175fc-151">数据操作</span><span class="sxs-lookup"><span data-stu-id="175fc-151">Data Action</span></span></p></td>
<td><p><span data-ttu-id="175fc-152"><a href="setlocalvar-macro-action.md">SetLocalVar 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="175fc-152"><a href="setlocalvar-macro-action.md">SetLocalVar macro action</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="175fc-153">数据操作</span><span class="sxs-lookup"><span data-stu-id="175fc-153">Data Action</span></span></p></td>
<td><p><span data-ttu-id="175fc-154"><a href="stopallmacros-macro-action.md">StopAllMacros 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="175fc-154"><a href="stopallmacros-macro-action.md">StopAllMacros macro action</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="175fc-155">数据操作</span><span class="sxs-lookup"><span data-stu-id="175fc-155">Data Action</span></span></p></td>
<td><p><span data-ttu-id="175fc-156"><a href="stopmacro-macro-action.md">StopMacro 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="175fc-156"><a href="stopmacro-macro-action.md">StopMacro macro action</a></span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="175fc-157">若要创建可捕获**更新后**事件的数据宏，请使用执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="175fc-157">To create a Data macro that captures the **After Update** event, use the folloiwng steps:</span></span>

1.  <span data-ttu-id="175fc-158">打开要为其捕获**更新后**事件的表格。</span><span class="sxs-lookup"><span data-stu-id="175fc-158">Open the table for which you want to capture the **After Update** event.</span></span>

2.  <span data-ttu-id="175fc-159">在 **“表格”** 选项卡上的 **“后期事件”** 组中，单击 **“更新后”**。</span><span class="sxs-lookup"><span data-stu-id="175fc-159">On the **Table** tab, in the **After Events** group, click **After Update**.</span></span>

<span data-ttu-id="175fc-160">宏设计器中将显示一个空白数据宏。</span><span class="sxs-lookup"><span data-stu-id="175fc-160">An empty data macro is displayed in the macro designer.</span></span>

## <a name="example"></a><span data-ttu-id="175fc-161">示例</span><span class="sxs-lookup"><span data-stu-id="175fc-161">Example</span></span>

<span data-ttu-id="175fc-162">下面的代码示例使用**更新后**事件运行的已命名的数据宏，每次更新问题的状态将记录添加到注释表。</span><span class="sxs-lookup"><span data-stu-id="175fc-162">The following code example uses the **After Update** event to run a named data macro that adds a record to the Comment table each time the status of an issue is updated.</span></span>

<span data-ttu-id="175fc-163">**单击此处查看您可以将其粘贴到宏设计器的宏副本。**</span><span class="sxs-lookup"><span data-stu-id="175fc-163">**Click here to view a copy of the macro that you can paste into Macro Designer.**</span></span>

<span data-ttu-id="175fc-164">若要在宏设计器查看此示例，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="175fc-164">To view this example in the macro designer, use the following steps:</span></span>

1.  <span data-ttu-id="175fc-165">打开要为其捕获**更新后**事件的表格。</span><span class="sxs-lookup"><span data-stu-id="175fc-165">Open the table for which you want to capture the **After Update** event.</span></span>

2.  <span data-ttu-id="175fc-166">在 **“表格”** 选项卡上的 **“后期事件”** 组中，单击 **“更新后”**。</span><span class="sxs-lookup"><span data-stu-id="175fc-166">On the **Table** tab, in the **After Events** group, click **After Update**.</span></span>

3.  <span data-ttu-id="175fc-167">选择以下代码示例中的代码，然后按 Ctrl+C 将其复制到剪贴板。</span><span class="sxs-lookup"><span data-stu-id="175fc-167">Select the code in the following code example and then press CTRL+C to copy it to the Clipboard.</span></span>

4.  <span data-ttu-id="175fc-168">激活宏设计器窗口，然后按 Ctrl+V。</span><span class="sxs-lookup"><span data-stu-id="175fc-168">Activate the macro designer window and then press CTRL+V.</span></span>

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

