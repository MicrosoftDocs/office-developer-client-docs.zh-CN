---
title: QueryDef.Type Property (DAO)
TOCTitle: Type Property
ms:assetid: 03db891d-b958-7cf9-56c1-524d9ff2b9b5
ms:mtpsurl: https://msdn.microsoft.com/library/Ff844814(v=office.15)
ms:contentKeyID: 48542993
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 5129f4a50f056259c5b556c8e8ea408358718d3c
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466814"
---
# <a name="querydeftype-property-dao"></a><span data-ttu-id="4e24a-102">QueryDef.Type Property (DAO)</span><span class="sxs-lookup"><span data-stu-id="4e24a-102">QueryDef.Type Property (DAO)</span></span>


<span data-ttu-id="4e24a-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="4e24a-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="4e24a-p101">设置或返回一个值，该值指示对象的操作类型或数据类型。只读 **Integer**。</span><span class="sxs-lookup"><span data-stu-id="4e24a-p101">Sets or returns a value that indicates the operational type or data type of an object. Read-only**Integer**.</span></span>

## <a name="syntax"></a><span data-ttu-id="4e24a-106">语法</span><span class="sxs-lookup"><span data-stu-id="4e24a-106">Syntax</span></span>

<span data-ttu-id="4e24a-107">*表达式*。类型</span><span class="sxs-lookup"><span data-stu-id="4e24a-107">*expression* .Type</span></span>

<span data-ttu-id="4e24a-108">*表达式*一个代表**QueryDef**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="4e24a-108">*expression* A variable that represents a **QueryDef** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="4e24a-109">注解</span><span class="sxs-lookup"><span data-stu-id="4e24a-109">Remarks</span></span>

<span data-ttu-id="4e24a-110">对于 **QueryDef** 对象，可能的设置和返回值如下表所示。</span><span class="sxs-lookup"><span data-stu-id="4e24a-110">For a **QueryDef** object, the possible settings and return values are shown in the following table.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="4e24a-111">常量</span><span class="sxs-lookup"><span data-stu-id="4e24a-111">Constant</span></span></p></th>
<th><p><span data-ttu-id="4e24a-112">查询类型</span><span class="sxs-lookup"><span data-stu-id="4e24a-112">Query type</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4e24a-113"><strong>dbQAction</strong></span><span class="sxs-lookup"><span data-stu-id="4e24a-113"><strong>dbQAction</strong></span></span></p></td>
<td><p><span data-ttu-id="4e24a-114">操作</span><span class="sxs-lookup"><span data-stu-id="4e24a-114">Action</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e24a-115"><strong>dbQAppend</strong></span><span class="sxs-lookup"><span data-stu-id="4e24a-115"><strong>dbQAppend</strong></span></span></p></td>
<td><p><span data-ttu-id="4e24a-116">追加</span><span class="sxs-lookup"><span data-stu-id="4e24a-116">Append</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e24a-117"><strong>dbQCompound</strong></span><span class="sxs-lookup"><span data-stu-id="4e24a-117"><strong>dbQCompound</strong></span></span></p></td>
<td><p><span data-ttu-id="4e24a-118">复合</span><span class="sxs-lookup"><span data-stu-id="4e24a-118">Compound</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e24a-119"><strong>dbQCrosstab</strong></span><span class="sxs-lookup"><span data-stu-id="4e24a-119"><strong>dbQCrosstab</strong></span></span></p></td>
<td><p><span data-ttu-id="4e24a-120">交叉表</span><span class="sxs-lookup"><span data-stu-id="4e24a-120">Crosstab</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e24a-121"><strong>dbQDDL</strong></span><span class="sxs-lookup"><span data-stu-id="4e24a-121"><strong>dbQDDL</strong></span></span></p></td>
<td><p><span data-ttu-id="4e24a-122">数据定义</span><span class="sxs-lookup"><span data-stu-id="4e24a-122">Data-definition</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e24a-123"><strong>dbQDelete</strong></span><span class="sxs-lookup"><span data-stu-id="4e24a-123"><strong>dbQDelete</strong></span></span></p></td>
<td><p><span data-ttu-id="4e24a-124">Delete</span><span class="sxs-lookup"><span data-stu-id="4e24a-124">Delete</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e24a-125"><strong>dbQMakeTable</strong></span><span class="sxs-lookup"><span data-stu-id="4e24a-125"><strong>dbQMakeTable</strong></span></span></p></td>
<td><p><span data-ttu-id="4e24a-126">生成表查询</span><span class="sxs-lookup"><span data-stu-id="4e24a-126">Make-table</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e24a-127"><strong>dbQProcedure</strong></span><span class="sxs-lookup"><span data-stu-id="4e24a-127"><strong>dbQProcedure</strong></span></span></p></td>
<td><p><span data-ttu-id="4e24a-128">过程（仅适用于 ODBCDirect 工作区）</span><span class="sxs-lookup"><span data-stu-id="4e24a-128">Procedure (ODBCDirect workspaces only)</span></span></p>

> [!NOTE]
> <P><span data-ttu-id="4e24a-129">Microsoft Access 2013 中不支持适用于 ODBCDirect 工作区。</span><span class="sxs-lookup"><span data-stu-id="4e24a-129">ODBCDirect workspaces are not supported in Microsoft Access 2013.</span></span> <span data-ttu-id="4e24a-130">如果要在不使用 Microsoft Access 数据库引擎的情况下访问外部数据源，请使用 ADO。</span><span class="sxs-lookup"><span data-stu-id="4e24a-130">Use ADO if you want to access external data sources without using the Microsoft Access database engine.</span></span></P>


<p></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e24a-131"><strong>dbQSelect</strong></span><span class="sxs-lookup"><span data-stu-id="4e24a-131"><strong>dbQSelect</strong></span></span></p></td>
<td><p><span data-ttu-id="4e24a-132">选择</span><span class="sxs-lookup"><span data-stu-id="4e24a-132">Select</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e24a-133"><strong>dbQSetOperation</strong></span><span class="sxs-lookup"><span data-stu-id="4e24a-133"><strong>dbQSetOperation</strong></span></span></p></td>
<td><p><span data-ttu-id="4e24a-134">联合</span><span class="sxs-lookup"><span data-stu-id="4e24a-134">Union</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e24a-135"><strong>dbQSPTBulk</strong></span><span class="sxs-lookup"><span data-stu-id="4e24a-135"><strong>dbQSPTBulk</strong></span></span></p></td>
<td><p><span data-ttu-id="4e24a-136">与 <strong>dbQSQLPassThrough</strong> 一起用于指定不返回记录的查询（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="4e24a-136">Used with <strong>dbQSQLPassThrough</strong> to specify a query that doesn't return records (Microsoft Access workspaces only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e24a-137"><strong>dbQSQLPassThrough</strong></span><span class="sxs-lookup"><span data-stu-id="4e24a-137"><strong>dbQSQLPassThrough</strong></span></span></p></td>
<td><p><span data-ttu-id="4e24a-138">传递（仅适用于 Microsoft Access 工作区）</span><span class="sxs-lookup"><span data-stu-id="4e24a-138">Pass-through (Microsoft Access workspaces only)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e24a-139"><strong>dbQUpdate</strong></span><span class="sxs-lookup"><span data-stu-id="4e24a-139"><strong>dbQUpdate</strong></span></span></p></td>
<td><p><span data-ttu-id="4e24a-140">Update</span><span class="sxs-lookup"><span data-stu-id="4e24a-140">Update</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="4e24a-141">将新的 **[Field](field-object-dao.md)** 、 **[Parameter](parameter-object-dao.md)** 或 **[Property](property-object-dao.md)** 对象追加到 **[Index](index-object-dao.md)** 、 **QueryDef**、 **[Recordset](recordset-object-dao.md)** 或 **[TableDef](tabledef-object-dao.md)** 对象集合中时，如果基础数据库不支持为新对象指定的数据类型，则会发生错误。</span><span class="sxs-lookup"><span data-stu-id="4e24a-141">When you append a new **[Field](field-object-dao.md)**, **[Parameter](parameter-object-dao.md)**, or **[Property](property-object-dao.md)** object to the collection of an **[Index](index-object-dao.md)**, **QueryDef**, **[Recordset](recordset-object-dao.md)**, or **[TableDef](tabledef-object-dao.md)** object, an error occurs if the underlying database doesn't support the data type specified for the new object.</span></span>

