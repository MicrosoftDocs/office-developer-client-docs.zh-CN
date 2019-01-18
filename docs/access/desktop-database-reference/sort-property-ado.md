---
title: Sort 属性 (ADO)
TOCTitle: Sort property (ADO)
ms:assetid: f2a39b7f-8b96-cd1a-8248-71f8b867454a
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250230(v=office.15)
ms:contentKeyID: 48548652
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 62ac60b1c7575f0b0d3e003dc58a11fe4d86c131
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28711411"
---
# <a name="sort-property-ado"></a><span data-ttu-id="08331-102">Sort 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="08331-102">Sort property (ADO)</span></span>


<span data-ttu-id="08331-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="08331-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="08331-104">指示一个或多个作为 [Recordset](recordset-object-ado.md) 的排序依据的字段名称，并指定是按升序还是降序对字段进行排序。</span><span class="sxs-lookup"><span data-stu-id="08331-104">Indicates one or more field names on which the [Recordset](recordset-object-ado.md) is sorted, and whether each field is sorted in ascending or descending order.</span></span>

## <a name="settings-and-return-values"></a><span data-ttu-id="08331-105">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="08331-105">Settings and return values</span></span>

<span data-ttu-id="08331-p101">设置或返回一个 **String** 值，指示作为 **Recordset** 的排序依据的字段名称。每个名称由逗号分隔，可以选择后跟空格和关键字 **ASC** （以升序对字段进行排序）或 **DESC** （以降序对字段进行排序）。默认情况下，如果未指定关键字，则以升序对字段进行排序。</span><span class="sxs-lookup"><span data-stu-id="08331-p101">Sets or returns a **String** value that indicates the field names in the **Recordset** on which to sort. Each name is separated by a comma, and is optionally followed by a blank and the keyword, **ASC**, which sorts the field in ascending order, or **DESC**, which sorts the field in descending order. By default, if no keyword is specified, the field is sorted in ascending order.</span></span>

## <a name="remarks"></a><span data-ttu-id="08331-109">备注</span><span class="sxs-lookup"><span data-stu-id="08331-109">Remarks</span></span>

<span data-ttu-id="08331-p102">此属性要求 [CursorLocation](cursorlocation-property-ado.md) 属性设置为 **adUseClient** 。如果索引尚不存在，则将为 **Sort** 属性中指定的每个字段创建一个临时索引。</span><span class="sxs-lookup"><span data-stu-id="08331-p102">This property requires the [CursorLocation](cursorlocation-property-ado.md) property to be set to **adUseClient**. A temporary index will be created for each field specified in the **Sort** property if an index does not already exist.</span></span>

<span data-ttu-id="08331-112">实际上数据并没有重新排列，只是简单地按索引指定的顺序进行访问，因此排序操作效率较高。</span><span class="sxs-lookup"><span data-stu-id="08331-112">The sort operation is efficient because data is not physically rearranged, but is simply accessed in the order specified by the index.</span></span>

<span data-ttu-id="08331-p103">如果将 **Sort** 属性设置为一个空字符串，则会将行重置为其初始顺序并删除临时索引。现有的索引不会被删除。</span><span class="sxs-lookup"><span data-stu-id="08331-p103">Setting the **Sort** property to an empty string will reset the rows to their original order and delete temporary indexes. Existing indexes will not be deleted.</span></span>

<span data-ttu-id="08331-115">假设**记录集**包含三个名称分别为*firstName*、 *middleInitial*和*lastName*的字段。</span><span class="sxs-lookup"><span data-stu-id="08331-115">Suppose a **Recordset** contains three fields named *firstName*, *middleInitial*, and *lastName*.</span></span> <span data-ttu-id="08331-116">将**Sort**属性设置为字符串，"lastName DESC，firstName ASC"，其中将顺序**Recordset** ，按降序排序，最后一个名称，然后按升序排序的第一个名称。</span><span class="sxs-lookup"><span data-stu-id="08331-116">Set the **Sort** property to the string, "lastName DESC, firstName ASC", which will order the **Recordset** by last name in descending order, then by first name in ascending order.</span></span> <span data-ttu-id="08331-117">忽略中间名首字母。</span><span class="sxs-lookup"><span data-stu-id="08331-117">The middle initial is ignored.</span></span>

<span data-ttu-id="08331-p105">由于与关键字 **ASC** 和 **DESC** 发生冲突，字段无法命名为 "ASC" 或 "DESC"。请通过在返回 **Recordset** 的查询中使用 **AS** 关键字，来为名称有冲突的字段提供别名。</span><span class="sxs-lookup"><span data-stu-id="08331-p105">No field can be named "ASC" or "DESC" because those names conflict with the keywords **ASC** and **DESC**. Give a field with a conflicting name an alias by using the **AS** keyword in the query that returns the **Recordset**.</span></span>

