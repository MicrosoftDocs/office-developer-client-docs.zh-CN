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
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28716010"
---
# <a name="lookuprecord-data-block"></a><span data-ttu-id="65513-102">LookupRecord 数据块</span><span class="sxs-lookup"><span data-stu-id="65513-102">LookupRecord data block</span></span>

<span data-ttu-id="65513-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="65513-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="65513-104">**LookupRecord** 数据块可对特定记录执行一组操作。</span><span class="sxs-lookup"><span data-stu-id="65513-104">A **LookupRecord** data block performs a set of actions on a specific record.</span></span>

> [!NOTE]
> <span data-ttu-id="65513-105">[!注释] **LookupRecord** 数据块仅适用于数据宏。</span><span class="sxs-lookup"><span data-stu-id="65513-105">The **LookupRecord** data block is available only in Data Macros.</span></span>

## <a name="setting"></a><span data-ttu-id="65513-106">设置</span><span class="sxs-lookup"><span data-stu-id="65513-106">Setting</span></span>

<span data-ttu-id="65513-107">**SetField** 操作具有以下参数。</span><span class="sxs-lookup"><span data-stu-id="65513-107">The **SetField** action has the following arguments.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="65513-108">参数</span><span class="sxs-lookup"><span data-stu-id="65513-108">Argument</span></span></p></th>
<th><p><span data-ttu-id="65513-109">是否必需</span><span class="sxs-lookup"><span data-stu-id="65513-109">Required</span></span></p></th>
<th><p><span data-ttu-id="65513-110">说明</span><span class="sxs-lookup"><span data-stu-id="65513-110">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="65513-111">在</span><span class="sxs-lookup"><span data-stu-id="65513-111">In</span></span></p></td>
<td><p><span data-ttu-id="65513-112">是</span><span class="sxs-lookup"><span data-stu-id="65513-112">Yes</span></span></p></td>
<td><p><span data-ttu-id="65513-113">一个字符串，标识的记录执行操作。</span><span class="sxs-lookup"><span data-stu-id="65513-113">A string that identifies the record to operate on.</span></span> <span data-ttu-id="65513-114"><em>在</em>参数可以包含表、 选择查询或 SQL 语句的名称。</span><span class="sxs-lookup"><span data-stu-id="65513-114">The <em>In</em> argument can contain the name of the table, a select query, or a SQL statement.</span></span></p><p><span data-ttu-id="65513-115"><strong>注意</strong>： 指定的记录不能包括链接的表或 ODBC 数据源中存储的数据。</span><span class="sxs-lookup"><span data-stu-id="65513-115"><strong>NOTE</strong>: The specified record cannot include data stored in a linked table or ODBC data source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="65513-116">Where Condition</span><span class="sxs-lookup"><span data-stu-id="65513-116">Where Condition</span></span></p></td>
<td><p><span data-ttu-id="65513-117">否</span><span class="sxs-lookup"><span data-stu-id="65513-117">No</span></span></p></td>
<td><p><span data-ttu-id="65513-118">执行字符串表达式，用来限制在其上的数据区域<strong>LookupRecord</strong>数据块。</span><span class="sxs-lookup"><span data-stu-id="65513-118">A string expression used to restrict the range of data on which the <strong>LookupRecord</strong> data block is performed.</span></span> <span data-ttu-id="65513-119">例如，条件是通常等同于在 SQL 表达式中，没有单词 WHERE 子句其中。</span><span class="sxs-lookup"><span data-stu-id="65513-119">For example, criteria are often equivalent to the WHERE clause in an SQL expression, without the word WHERE.</span></span> <span data-ttu-id="65513-120">如果条件都被忽略， <strong>LookupRecord</strong>数据块运行上指定<em>中</em>参数的整个域。</span><span class="sxs-lookup"><span data-stu-id="65513-120">If criteria are omitted, the <strong>LookupRecord</strong> data block operates on the entire domain specified by the <em>In</em> argument.</span></span> <span data-ttu-id="65513-121">条件中包括的任何字段必须同时是<em>中</em>的字段。</span><span class="sxs-lookup"><span data-stu-id="65513-121">Any field that is included in criteria must also be a field in <em>In</em>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="65513-122">Alias</span><span class="sxs-lookup"><span data-stu-id="65513-122">Alias</span></span></p></td>
<td><p><span data-ttu-id="65513-123">否</span><span class="sxs-lookup"><span data-stu-id="65513-123">No</span></span></p></td>
<td><p><span data-ttu-id="65513-124">提供<em>在</em>参数指定的记录的替代名称的字符串。</span><span class="sxs-lookup"><span data-stu-id="65513-124">A string that provides an alternative name for the record specified by the <em>In</em> argument.</span></span> <span data-ttu-id="65513-125">通常用于缩短后续参考，以防止可能出现的不明确引用的表名称。</span><span class="sxs-lookup"><span data-stu-id="65513-125">Often used to shorten the table name for subsequent references to prevent possible ambiguous references.</span></span> <span data-ttu-id="65513-126">如果不指定 <em>Alias</em>，则会将表或查询名称用作别名。</span><span class="sxs-lookup"><span data-stu-id="65513-126">If <em>Alias</em> is not specified, the table or query name will be used as the alias.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="65513-127">备注</span><span class="sxs-lookup"><span data-stu-id="65513-127">Remarks</span></span>

<span data-ttu-id="65513-128">如果*在*和*Where Condition*参数指定的条件指定多个记录， **LookupRecord**数据块将操作仅在第一条记录上。</span><span class="sxs-lookup"><span data-stu-id="65513-128">If the criteria specified by the *In* and *Where Condition* arguments specifies more than one record, the **LookupRecord** data block will operate only on the first record.</span></span>

## <a name="example"></a><span data-ttu-id="65513-129">示例</span><span class="sxs-lookup"><span data-stu-id="65513-129">Example</span></span>

<span data-ttu-id="65513-130">下面的示例演示如何使用 SetReturnVar 操作从已命名的数据宏返回值。</span><span class="sxs-lookup"><span data-stu-id="65513-130">The following example shows how to use the SetReturnVar action to return a value from a named data macro.</span></span> <span data-ttu-id="65513-131">名为**CurrentServiceRequest** ReturnVar 调用已命名的数据宏的 Applications (VBA) 子例程返回到宏或 Visual Basic。</span><span class="sxs-lookup"><span data-stu-id="65513-131">A ReturnVar named **CurrentServiceRequest** is returned to the macro or Visual Basic for Applications (VBA) subroutine that called the named data macro.</span></span>

<span data-ttu-id="65513-132">**示例代码提供者** [Microsoft Access 2010 Programmer's Reference](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125)。</span><span class="sxs-lookup"><span data-stu-id="65513-132">**Sample code provided by** the [Microsoft Access 2010 Programmer’s Reference](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125).</span></span>

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

<span data-ttu-id="65513-133">下面的示例演示如何使用 RaiseError 操作取消 Before Change 数据宏事件。</span><span class="sxs-lookup"><span data-stu-id="65513-133">The following example shows how to use the RaiseError action to cancel the Before Change data macro event.</span></span> <span data-ttu-id="65513-134">更新 AssignedTo 字段时，LookupRecord 数据块用于确定是否已分配的技术人员当前分配给打开服务请求。</span><span class="sxs-lookup"><span data-stu-id="65513-134">When the AssignedTo field is updated, a LookupRecord data block is used to determine whether the assigned technician is currently assigned to an open service request.</span></span> <span data-ttu-id="65513-135">如果是这样，取消 Before Change 事件并不会更新记录。</span><span class="sxs-lookup"><span data-stu-id="65513-135">If this is true, the Before Change event is cancelled and the record is not updated.</span></span>

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
