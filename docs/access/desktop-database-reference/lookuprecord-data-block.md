---
title: LookupRecord 数据块
TOCTitle: LookupRecord data block
ms:assetid: 750dc8ca-3bab-c3d1-c91d-2196f9c0604d
ms:mtpsurl: https://msdn.microsoft.com/library/Ff195882(v=office.15)
ms:contentKeyID: 48545671
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 920f0830a310452962eb5dd1c21be63215bf0f03
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32289789"
---
# <a name="lookuprecord-data-block"></a><span data-ttu-id="f6543-102">LookupRecord 数据块</span><span class="sxs-lookup"><span data-stu-id="f6543-102">LookupRecord data block</span></span>

<span data-ttu-id="f6543-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="f6543-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="f6543-104">**LookupRecord** 数据块可对特定记录执行一组操作。</span><span class="sxs-lookup"><span data-stu-id="f6543-104">A **LookupRecord** data block performs a set of actions on a specific record.</span></span>

> [!NOTE]
> <span data-ttu-id="f6543-105">**LookupRecord** 数据块仅适用于数据宏。</span><span class="sxs-lookup"><span data-stu-id="f6543-105">The **LookupRecord** data block is available only in Data Macros.</span></span>

## <a name="setting"></a><span data-ttu-id="f6543-106">Setting</span><span class="sxs-lookup"><span data-stu-id="f6543-106">Setting</span></span>

<span data-ttu-id="f6543-107">**SetField** 操作具有以下参数。</span><span class="sxs-lookup"><span data-stu-id="f6543-107">The **SetField** action has the following arguments.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="f6543-108">参数</span><span class="sxs-lookup"><span data-stu-id="f6543-108">Argument</span></span></p></th>
<th><p><span data-ttu-id="f6543-109">必需</span><span class="sxs-lookup"><span data-stu-id="f6543-109">Required</span></span></p></th>
<th><p><span data-ttu-id="f6543-110">说明</span><span class="sxs-lookup"><span data-stu-id="f6543-110">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f6543-111">在</span><span class="sxs-lookup"><span data-stu-id="f6543-111">In</span></span></p></td>
<td><p><span data-ttu-id="f6543-112">是</span><span class="sxs-lookup"><span data-stu-id="f6543-112">Yes</span></span></p></td>
<td><p><span data-ttu-id="f6543-113">一个用于标识要对其执行操作的记录的字符串。</span><span class="sxs-lookup"><span data-stu-id="f6543-113">A string that identifies the record to operate on.</span></span> <span data-ttu-id="f6543-114"><em>In</em>参数可以包含表、选择查询或 SQL 语句的名称。</span><span class="sxs-lookup"><span data-stu-id="f6543-114">The <em>In</em> argument can contain the name of the table, a select query, or a SQL statement.</span></span></p><p><span data-ttu-id="f6543-115"><strong>注意</strong>: 指定的记录不能包含存储在链接表或 ODBC 数据源中的数据。</span><span class="sxs-lookup"><span data-stu-id="f6543-115"><strong>NOTE</strong>: The specified record cannot include data stored in a linked table or ODBC data source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6543-116">Where Condition</span><span class="sxs-lookup"><span data-stu-id="f6543-116">Where Condition</span></span></p></td>
<td><p><span data-ttu-id="f6543-117">否</span><span class="sxs-lookup"><span data-stu-id="f6543-117">No</span></span></p></td>
<td><p><span data-ttu-id="f6543-118">一个字符串表达式，用于限制对其执行 <strong>LookupRecord</strong> 数据块的数据的范围。</span><span class="sxs-lookup"><span data-stu-id="f6543-118">A string expression used to restrict the range of data on which the <strong>LookupRecord</strong> data block is performed.</span></span> <span data-ttu-id="f6543-119">例如, 条件通常等效于 SQL 表达式中的 where 子句, 而不带单词 WHERE。</span><span class="sxs-lookup"><span data-stu-id="f6543-119">For example, criteria are often equivalent to the WHERE clause in an SQL expression, without the word WHERE.</span></span> <span data-ttu-id="f6543-120">如果省略条件, 则<strong>LookupRecord</strong>数据块在由<em>In</em>参数指定的整个域上运行。</span><span class="sxs-lookup"><span data-stu-id="f6543-120">If criteria are omitted, the <strong>LookupRecord</strong> data block operates on the entire domain specified by the <em>In</em> argument.</span></span> <span data-ttu-id="f6543-121">条件中包括的所有字段还必须是 <em>In</em> 中的字段。</span><span class="sxs-lookup"><span data-stu-id="f6543-121">Any field that is included in criteria must also be a field in <em>In</em>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6543-122">别名</span><span class="sxs-lookup"><span data-stu-id="f6543-122">Alias</span></span></p></td>
<td><p><span data-ttu-id="f6543-123">否</span><span class="sxs-lookup"><span data-stu-id="f6543-123">No</span></span></p></td>
<td><p><span data-ttu-id="f6543-124">为<em>In</em>参数所指定的记录提供可选名称的字符串。</span><span class="sxs-lookup"><span data-stu-id="f6543-124">A string that provides an alternative name for the record specified by the <em>In</em> argument.</span></span> <span data-ttu-id="f6543-125">通常用于缩短后续引用的表名称，以防止可能出现的不明引用。</span><span class="sxs-lookup"><span data-stu-id="f6543-125">Often used to shorten the table name for subsequent references to prevent possible ambiguous references.</span></span> <span data-ttu-id="f6543-126">如果不指定 <em>Alias</em>，则会将表或查询名称用作别名。</span><span class="sxs-lookup"><span data-stu-id="f6543-126">If <em>Alias</em> is not specified, the table or query name will be used as the alias.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="f6543-127">注解</span><span class="sxs-lookup"><span data-stu-id="f6543-127">Remarks</span></span>

<span data-ttu-id="f6543-128">如果*In*和*Where Condition*参数指定的条件指定了多条记录, **LookupRecord**数据块将只对第一条记录执行操作。</span><span class="sxs-lookup"><span data-stu-id="f6543-128">If the criteria specified by the *In* and *Where Condition* arguments specifies more than one record, the **LookupRecord** data block will operate only on the first record.</span></span>

## <a name="example"></a><span data-ttu-id="f6543-129">示例</span><span class="sxs-lookup"><span data-stu-id="f6543-129">Example</span></span>

<span data-ttu-id="f6543-130">下面的示例演示如何使用 SetReturnVar 操作从已命名的数据宏中返回值。</span><span class="sxs-lookup"><span data-stu-id="f6543-130">The following example shows how to use the SetReturnVar action to return a value from a named data macro.</span></span> <span data-ttu-id="f6543-131">名为**CurrentServiceRequest**的 ReturnVar 返回给宏或 Visual Basic for Applications (VBA) 子例程, 该子例程称为已命名的数据宏。</span><span class="sxs-lookup"><span data-stu-id="f6543-131">A ReturnVar named **CurrentServiceRequest** is returned to the macro or Visual Basic for Applications (VBA) subroutine that called the named data macro.</span></span>

<span data-ttu-id="f6543-132">**示例代码提供方：**[Microsoft Access 2010 程序员参考](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125)。</span><span class="sxs-lookup"><span data-stu-id="f6543-132">**Sample code provided by** the [Microsoft Access 2010 Programmer’s Reference](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125).</span></span>

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

<span data-ttu-id="f6543-133">下面的示例演示如何使用 RaiseError 操作取消 Before Change data 宏事件。</span><span class="sxs-lookup"><span data-stu-id="f6543-133">The following example shows how to use the RaiseError action to cancel the Before Change data macro event.</span></span> <span data-ttu-id="f6543-134">更新 "分配" 字段后, 将使用 LookupRecord 数据块确定分配的技术人员当前是否已分配给打开的服务请求。</span><span class="sxs-lookup"><span data-stu-id="f6543-134">When the AssignedTo field is updated, a LookupRecord data block is used to determine whether the assigned technician is currently assigned to an open service request.</span></span> <span data-ttu-id="f6543-135">如果为 true, 则取消 "更改前" 事件且不更新记录。</span><span class="sxs-lookup"><span data-stu-id="f6543-135">If this is true, the Before Change event is cancelled and the record is not updated.</span></span>

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
