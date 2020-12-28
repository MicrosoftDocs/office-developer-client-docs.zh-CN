---
title: LookupRecord 数据块
TOCTitle: LookupRecord data block
ms:assetid: 750dc8ca-3bab-c3d1-c91d-2196f9c0604d
ms:mtpsurl: https://msdn.microsoft.com/library/Ff195882(v=office.15)
ms:contentKeyID: 48545671
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 7a5cccb77300f36f3e33cd1eccb6c6d278db3120
ms.sourcegitcommit: 0419850d5c1b3439d9da59070201fb4952ca5d07
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/28/2020
ms.locfileid: "49734208"
---
# <a name="lookuprecord-data-block"></a><span data-ttu-id="47104-102">LookupRecord 数据块</span><span class="sxs-lookup"><span data-stu-id="47104-102">LookupRecord data block</span></span>

<span data-ttu-id="47104-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="47104-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="47104-104">**LookupRecord** 数据块可对特定记录执行一组操作。</span><span class="sxs-lookup"><span data-stu-id="47104-104">A **LookupRecord** data block performs a set of actions on a specific record.</span></span>

> [!NOTE]
> <span data-ttu-id="47104-105">**LookupRecord** 数据块仅适用于数据宏。</span><span class="sxs-lookup"><span data-stu-id="47104-105">The **LookupRecord** data block is available only in Data Macros.</span></span>

## <a name="setting"></a><span data-ttu-id="47104-106">Setting</span><span class="sxs-lookup"><span data-stu-id="47104-106">Setting</span></span>

<span data-ttu-id="47104-107">**SetField** 操作具有以下参数。</span><span class="sxs-lookup"><span data-stu-id="47104-107">The **SetField** action has the following arguments.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="47104-108">参数</span><span class="sxs-lookup"><span data-stu-id="47104-108">Argument</span></span></p></th>
<th><p><span data-ttu-id="47104-109">必需</span><span class="sxs-lookup"><span data-stu-id="47104-109">Required</span></span></p></th>
<th><p><span data-ttu-id="47104-110">说明</span><span class="sxs-lookup"><span data-stu-id="47104-110">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="47104-111">在</span><span class="sxs-lookup"><span data-stu-id="47104-111">In</span></span></p></td>
<td><p><span data-ttu-id="47104-112">是</span><span class="sxs-lookup"><span data-stu-id="47104-112">Yes</span></span></p></td>
<td><p><span data-ttu-id="47104-113">一个用于标识要对其执行操作的记录的字符串。</span><span class="sxs-lookup"><span data-stu-id="47104-113">A string that identifies the record to operate on.</span></span> <span data-ttu-id="47104-114">In <em></em>参数可以包含表的名称、选择查询或 SQL 语句。</span><span class="sxs-lookup"><span data-stu-id="47104-114">The <em>In</em> argument can contain the name of the table, a select query, or a SQL statement.</span></span></p><p><span data-ttu-id="47104-115"><strong>注意</strong>：指定的记录不能包括链接表或 ODBC 数据源中存储的数据。</span><span class="sxs-lookup"><span data-stu-id="47104-115"><strong>NOTE</strong>: The specified record cannot include data stored in a linked table or ODBC data source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47104-116">Where Condition</span><span class="sxs-lookup"><span data-stu-id="47104-116">Where Condition</span></span></p></td>
<td><p><span data-ttu-id="47104-117">否</span><span class="sxs-lookup"><span data-stu-id="47104-117">No</span></span></p></td>
<td><p><span data-ttu-id="47104-118">一个字符串表达式，用于限制对其执行 <strong>LookupRecord</strong> 数据块的数据的范围。</span><span class="sxs-lookup"><span data-stu-id="47104-118">A string expression used to restrict the range of data on which the <strong>LookupRecord</strong> data block is performed.</span></span> <span data-ttu-id="47104-119">例如，条件通常等效于一个无单词 WHERE 的 SQL 表达式中的 WHERE 子句。</span><span class="sxs-lookup"><span data-stu-id="47104-119">For example, criteria are often equivalent to the WHERE clause in an SQL expression, without the word WHERE.</span></span> <span data-ttu-id="47104-120">如果省略条件 <strong>，LookupRecord</strong> 数据块将运行 In 参数 <em>指定的整个域</em> 。</span><span class="sxs-lookup"><span data-stu-id="47104-120">If criteria are omitted, the <strong>LookupRecord</strong> data block operates on the entire domain specified by the <em>In</em> argument.</span></span> <span data-ttu-id="47104-121">条件中包括的所有字段还必须是 <em>In</em> 中的字段。</span><span class="sxs-lookup"><span data-stu-id="47104-121">Any field that is included in criteria must also be a field in <em>In</em>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47104-122">Alias</span><span class="sxs-lookup"><span data-stu-id="47104-122">Alias</span></span></p></td>
<td><p><span data-ttu-id="47104-123">否</span><span class="sxs-lookup"><span data-stu-id="47104-123">No</span></span></p></td>
<td><p><span data-ttu-id="47104-124">为 In 参数指定的记录提供备用 <em>名称的字符串</em> 。</span><span class="sxs-lookup"><span data-stu-id="47104-124">A string that provides an alternative name for the record specified by the <em>In</em> argument.</span></span> <span data-ttu-id="47104-125">通常用于缩短后续引用的表名称，以防止可能出现的不明引用。</span><span class="sxs-lookup"><span data-stu-id="47104-125">Often used to shorten the table name for subsequent references to prevent possible ambiguous references.</span></span> <span data-ttu-id="47104-126">如果不指定 <em>Alias</em>，则会将表或查询名称用作别名。</span><span class="sxs-lookup"><span data-stu-id="47104-126">If <em>Alias</em> is not specified, the table or query name will be used as the alias.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="47104-127">备注</span><span class="sxs-lookup"><span data-stu-id="47104-127">Remarks</span></span>

<span data-ttu-id="47104-128">如果 In 和Where *条件* 参数指定的条件返回多个记录 **，LookupRecord** 数据块将只对第一条记录进行操作。</span><span class="sxs-lookup"><span data-stu-id="47104-128">If the criteria specified by the *In* and *Where Condition* arguments returns more than one record, the **LookupRecord** data block will operate only on the first record.</span></span>  <span data-ttu-id="47104-129">如果没有与指定条件匹配的记录，Access 将跳过 **LookupRecord** 块中包含的一组操作，就像它是计算为 false 的 **[If](if-then-else-macro-block.md)** 宏块表达式一样。</span><span class="sxs-lookup"><span data-stu-id="47104-129">In the case that no records match the specified criteria, Access will skip over the set of actions contained within the **LookupRecord** block, as if it had been an **[If](if-then-else-macro-block.md)** macro block expression that evaluated as false.</span></span>

## <a name="example"></a><span data-ttu-id="47104-130">示例</span><span class="sxs-lookup"><span data-stu-id="47104-130">Example</span></span>

<span data-ttu-id="47104-131">以下示例演示如何使用 SetReturnVar 操作从命名数据宏返回值。</span><span class="sxs-lookup"><span data-stu-id="47104-131">The following example shows how to use the SetReturnVar action to return a value from a named data macro.</span></span> <span data-ttu-id="47104-132">名为 **CurrentServiceRequest** 的 ReturnVar 将返回到宏或Visual Basic for Applications (VBA) 调用命名数据宏的子例程。</span><span class="sxs-lookup"><span data-stu-id="47104-132">A ReturnVar named **CurrentServiceRequest** is returned to the macro or Visual Basic for Applications (VBA) subroutine that called the named data macro.</span></span>

<span data-ttu-id="47104-133">**示例代码提供方：**[Microsoft Access 2010 程序员参考](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125)。</span><span class="sxs-lookup"><span data-stu-id="47104-133">**Sample code provided by** the [Microsoft Access 2010 Programmer’s Reference](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125).</span></span>

```vb
    RunDataMacro
        Macro Name tblServiceRequests.dmGetCurrentServiceRequest
    
    Parameters
        prmAssignedTo =[ID]
    
    SetProperty
        Control Name txtCurrentSR
        Property Value
        Value =[ReturnVars]![CurrentServiceRequest]
```

<br/>

<span data-ttu-id="47104-134">下面的示例演示如何使用 RaiseError 操作取消 Before Change 数据宏事件。</span><span class="sxs-lookup"><span data-stu-id="47104-134">The following example shows how to use the RaiseError action to cancel the Before Change data macro event.</span></span> <span data-ttu-id="47104-135">更新 AssignedTo 字段时，LookupRecord 数据块用于确定当前是否将分配的技术人员分配给打开的服务请求。</span><span class="sxs-lookup"><span data-stu-id="47104-135">When the AssignedTo field is updated, a LookupRecord data block is used to determine whether the assigned technician is currently assigned to an open service request.</span></span> <span data-ttu-id="47104-136">如果为 true，则取消 Before Change 事件，并且不会更新记录。</span><span class="sxs-lookup"><span data-stu-id="47104-136">If this is true, the Before Change event is cancelled and the record is not updated.</span></span>

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
