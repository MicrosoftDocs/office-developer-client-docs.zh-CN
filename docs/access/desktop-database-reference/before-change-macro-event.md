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
# <a name="before-change-macro-event"></a><span data-ttu-id="f93ff-102">Before Change 宏事件</span><span class="sxs-lookup"><span data-stu-id="f93ff-102">Before Change macro event</span></span>

<span data-ttu-id="f93ff-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="f93ff-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="f93ff-104">当记录更改，但未提交更改之前，发生此事件的**更改前**事件。</span><span class="sxs-lookup"><span data-stu-id="f93ff-104">The **Before Change** event occurs when a record changes, but before the change is committed.</span></span>

> [!NOTE]
> <span data-ttu-id="f93ff-105">仅适用于数据宏的**Before Change**事件。</span><span class="sxs-lookup"><span data-stu-id="f93ff-105">The **Before Change** event is available only in Data Macros.</span></span>

## <a name="remarks"></a><span data-ttu-id="f93ff-106">说明</span><span class="sxs-lookup"><span data-stu-id="f93ff-106">Remarks</span></span>

<span data-ttu-id="f93ff-107">使用**Before Change**事件，以执行任何操作所需记录之前，需要进行更改。</span><span class="sxs-lookup"><span data-stu-id="f93ff-107">Use the **Before Change** event to perform any actions that you want to occur before a record is changed.</span></span> <span data-ttu-id="f93ff-108">**Before Change**常用来执行验证并将引发自定义错误消息。</span><span class="sxs-lookup"><span data-stu-id="f93ff-108">The **Before Change** is commonly used to perform validation and to raise custom error messages.</span></span>

<span data-ttu-id="f93ff-109">**更新了 （"*字段名*"）** 函数可用于确定是否已更改字段。</span><span class="sxs-lookup"><span data-stu-id="f93ff-109">You can use the **Updated("*Field Name*")** function to determine whether a field has changed.</span></span> <span data-ttu-id="f93ff-110">下面的代码示例演示如何使用**If**语句确定是否已更改 PaidInFull 字段。</span><span class="sxs-lookup"><span data-stu-id="f93ff-110">The following code example shows how to use an **If** statement to determine whether the PaidInFull field has been changed.</span></span>

```vb
    If  Updated("PaidInFull")   Then 
     
        /* Perform actions based on changes to the field.   */ 
     
    End If 
```

<span data-ttu-id="f93ff-111">使用**IsInsert**属性来确定是否在**更改前**事件触发正在创建的新记录或对现有记录的更改。</span><span class="sxs-lookup"><span data-stu-id="f93ff-111">Use the **IsInsert** property to determine whether the **Before Change** event was triggered by a new record being created or a change to an existing record.</span></span> <span data-ttu-id="f93ff-112">他们**IsInsert**属性包含 **，则返回 True** ，如果通过对 en 现有记录的更改触发事件，新记录， **False**已触发该事件。</span><span class="sxs-lookup"><span data-stu-id="f93ff-112">They **IsInsert** property contains **True** if the event was triggered by a new record, **False** if the event was triggered by a change to en existing record.</span></span>

<span data-ttu-id="f93ff-113">下面的代码示例演示使用**IsInsert**属性的语法。</span><span class="sxs-lookup"><span data-stu-id="f93ff-113">The following code example shows the syntax for using the **IsInsert** property.</span></span>

```vb
    If   [IsInsert] = True   Then 
     
       /*  Actions for validating a new record go here.       */ 
     
    Else 
     
       /* Actions for processing a changed record go here.    */ 
     
    End If
```

<span data-ttu-id="f93ff-114">可以使用以下语法访问字段中以前的某个值。</span><span class="sxs-lookup"><span data-stu-id="f93ff-114">You can use access a the previous value in a field by using the following syntax.</span></span>

```vb
    [Old].[Field Name]
```

<span data-ttu-id="f93ff-115">例如，若要访问 QuantityInStock 字段的以前的值，请使用以下语法。</span><span class="sxs-lookup"><span data-stu-id="f93ff-115">For example, to access the previous value of the QuantityInStock field, use the following syntax.</span></span>

```vb
    [Old].[QuantityInStock]
```

<span data-ttu-id="f93ff-116">在**更改前**事件结束时，以前的值将被永久删除。</span><span class="sxs-lookup"><span data-stu-id="f93ff-116">The previous values are deleted permanently when the **Before Change** event ends.</span></span>

<span data-ttu-id="f93ff-117">您可以通过使用**RaiseError**操作取消**Before Change**事件。</span><span class="sxs-lookup"><span data-stu-id="f93ff-117">You can cancel the **Before Change** event by using the **RaiseError** action.</span></span> <span data-ttu-id="f93ff-118">时引发错误**Before Change**事件中包含的更改将被丢弃。</span><span class="sxs-lookup"><span data-stu-id="f93ff-118">When an error is raised the changes contained in the **Before Change** event are discarded.</span></span>

<span data-ttu-id="f93ff-119">下表列出了可在**Before Change**事件中使用的宏命令。</span><span class="sxs-lookup"><span data-stu-id="f93ff-119">The following table lists macro commands that can be used in the**Before Change** event.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="f93ff-120">命令类型</span><span class="sxs-lookup"><span data-stu-id="f93ff-120">Command Type</span></span></p></th>
<th><p><span data-ttu-id="f93ff-121">命令</span><span class="sxs-lookup"><span data-stu-id="f93ff-121">Command</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f93ff-122">程序流</span><span class="sxs-lookup"><span data-stu-id="f93ff-122">Program Flow</span></span></p></td>
<td><p><span data-ttu-id="f93ff-123"><a href="comment-macro-statement.md">Comment 宏语句</a></span><span class="sxs-lookup"><span data-stu-id="f93ff-123"><a href="comment-macro-statement.md">Comment macro statement</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f93ff-124">程序流</span><span class="sxs-lookup"><span data-stu-id="f93ff-124">Program Flow</span></span></p></td>
<td><p><span data-ttu-id="f93ff-125"><a href="group-macro-statement.md">Group 宏语句</a></span><span class="sxs-lookup"><span data-stu-id="f93ff-125"><a href="group-macro-statement.md">Group macro statement</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f93ff-126">程序流</span><span class="sxs-lookup"><span data-stu-id="f93ff-126">Program Flow</span></span></p></td>
<td><p><span data-ttu-id="f93ff-127"><a href="if-then-else-macro-block.md">If...Then...Else 宏程序块</a></span><span class="sxs-lookup"><span data-stu-id="f93ff-127"><a href="if-then-else-macro-block.md">If...Then...Else macro block</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f93ff-128">数据块</span><span class="sxs-lookup"><span data-stu-id="f93ff-128">Data Block</span></span></p></td>
<td><p><span data-ttu-id="f93ff-129"><a href="lookuprecord-data-block.md">LookupRecord 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="f93ff-129"><a href="lookuprecord-data-block.md">LookupRecord macro action</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f93ff-130">数据操作</span><span class="sxs-lookup"><span data-stu-id="f93ff-130">Data Action</span></span></p></td>
<td><p><span data-ttu-id="f93ff-131"><a href="clearmacroerror-macro-action.md">ClearMacroError 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="f93ff-131"><a href="clearmacroerror-macro-action.md">ClearMacroError macro action</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f93ff-132">数据操作</span><span class="sxs-lookup"><span data-stu-id="f93ff-132">Data Action</span></span></p></td>
<td><p><span data-ttu-id="f93ff-133"><a href="onerror-macro-action.md">OnError 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="f93ff-133"><a href="onerror-macro-action.md">OnError macro action</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f93ff-134">数据操作</span><span class="sxs-lookup"><span data-stu-id="f93ff-134">Data Action</span></span></p></td>
<td><p><span data-ttu-id="f93ff-135"><a href="raiseerror-macro-action.md">RaiseError 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="f93ff-135"><a href="raiseerror-macro-action.md">RaiseError macro action</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f93ff-136">数据操作</span><span class="sxs-lookup"><span data-stu-id="f93ff-136">Data Action</span></span></p></td>
<td><p><span data-ttu-id="f93ff-137"><a href="setfield-macro-action.md">SetField 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="f93ff-137"><a href="setfield-macro-action.md">SetField macro action</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f93ff-138">数据操作</span><span class="sxs-lookup"><span data-stu-id="f93ff-138">Data Action</span></span></p></td>
<td><p><span data-ttu-id="f93ff-139"><a href="setlocalvar-macro-action.md">SetLocalVar 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="f93ff-139"><a href="setlocalvar-macro-action.md">SetLocalVar macro action</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f93ff-140">数据操作</span><span class="sxs-lookup"><span data-stu-id="f93ff-140">Data Action</span></span></p></td>
<td><p><span data-ttu-id="f93ff-141"><a href="stopmacro-macro-action.md">StopMacro 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="f93ff-141"><a href="stopmacro-macro-action.md">StopMacro macro action</a></span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="f93ff-142">若要创建可捕获**更改前**事件的数据宏，请使用以下步骤：</span><span class="sxs-lookup"><span data-stu-id="f93ff-142">To create a Data Macro that captures the **Before Change** event, use the following steps:</span></span>

1.  <span data-ttu-id="f93ff-143">打开要为其捕获**Before Change**事件的表格。</span><span class="sxs-lookup"><span data-stu-id="f93ff-143">Open the table for which you want to capture the **Before Change** event.</span></span>

2.  <span data-ttu-id="f93ff-144">在 **“表格”** 选项卡上的 **“前期事件”** 组中，单击 **“更改前”**。</span><span class="sxs-lookup"><span data-stu-id="f93ff-144">On the **Table** tab, in the **Before Events** group, click **Before Change**.</span></span>

<span data-ttu-id="f93ff-145">宏设计器中将显示一个空白数据宏。</span><span class="sxs-lookup"><span data-stu-id="f93ff-145">An empty data macro is displayed in the macro designer.</span></span>

## <a name="example"></a><span data-ttu-id="f93ff-146">示例</span><span class="sxs-lookup"><span data-stu-id="f93ff-146">Example</span></span>

<span data-ttu-id="f93ff-147">下面的代码示例使用**Before Change**事件来验证状态域。</span><span class="sxs-lookup"><span data-stu-id="f93ff-147">The following code example uses the **Before Change** event to validate the Status fields.</span></span> <span data-ttu-id="f93ff-148">如果在解决方案字段包含不正确的值，则，引发错误。</span><span class="sxs-lookup"><span data-stu-id="f93ff-148">An error is raised if an inappropriate value is contained in the Resolution field.</span></span>

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

<span data-ttu-id="f93ff-149">若要在宏设计器查看此示例，请执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="f93ff-149">To view this example in the macro designer, use the following steps.</span></span>

1.  <span data-ttu-id="f93ff-150">打开要为其捕获**Before Change**事件的表格。</span><span class="sxs-lookup"><span data-stu-id="f93ff-150">Open the table for which you want to capture the **Before Change** event.</span></span>

2.  <span data-ttu-id="f93ff-151">在 **“表格”** 选项卡上的 **“前期事件”** 组中，单击 **“更改前”**。</span><span class="sxs-lookup"><span data-stu-id="f93ff-151">On the **Table** tab, in the **Before Events** group, click **Before Change**.</span></span>

3.  <span data-ttu-id="f93ff-152">下面的代码示例中选择的代码，然后按**CTRL + C**将其复制到剪贴板。</span><span class="sxs-lookup"><span data-stu-id="f93ff-152">Select the code in the following code example and then press **CTRL+C** to copy it to the Clipboard.</span></span>

4.  <span data-ttu-id="f93ff-153">激活宏设计器窗口，然后按**CTRL + V**。</span><span class="sxs-lookup"><span data-stu-id="f93ff-153">Activate the macro designer window and then press **CTRL+V**.</span></span>



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

<span data-ttu-id="f93ff-154">下面的示例演示如何使用 RaiseError 操作取消 Before Change 数据宏事件。</span><span class="sxs-lookup"><span data-stu-id="f93ff-154">The following example shows how to use the RaiseError action to cancel the Before Change data macro event.</span></span> <span data-ttu-id="f93ff-155">更新 AssignedTo 字段时，LookupRecord 数据块用于确定是否已分配的技术人员当前分配给打开服务请求。</span><span class="sxs-lookup"><span data-stu-id="f93ff-155">When the AssignedTo field is updated, a LookupRecord data block is used to determine whether the assigned technician is currently assigned to an open service request.</span></span> <span data-ttu-id="f93ff-156">如果是这样，然后取消 Before Change 事件并不会更新记录。</span><span class="sxs-lookup"><span data-stu-id="f93ff-156">If this is true, then the Before Change event is cancelled and the record is not updated.</span></span>

<span data-ttu-id="f93ff-157">**示例代码提供者** [Microsoft Access 2010 Programmer's Reference](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125)。</span><span class="sxs-lookup"><span data-stu-id="f93ff-157">**Sample code provided by** the [Microsoft Access 2010 Programmer’s Reference](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125).</span></span>

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
