---
title: Connection.CreateQueryDef 方法 (DAO)
TOCTitle: CreateQueryDef Method
ms:assetid: 254fe81a-9b45-e8e7-108d-503c1c1c0fcc
ms:mtpsurl: https://msdn.microsoft.com/library/Ff191860(v=office.15)
ms:contentKeyID: 48543781
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1053067
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 191cd2b1bdd1f1c625743d5e50037bc944b4ef23
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25928437"
---
# <a name="connectioncreatequerydef-method-dao"></a><span data-ttu-id="026dc-102">Connection.CreateQueryDef 方法 (DAO)</span><span class="sxs-lookup"><span data-stu-id="026dc-102">Connection.CreateQueryDef method (DAO)</span></span>


<span data-ttu-id="026dc-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="026dc-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="026dc-104">创建新的 **[QueryDef](querydef-object-dao.md)** 对象。</span><span class="sxs-lookup"><span data-stu-id="026dc-104">Creates a new **[QueryDef](querydef-object-dao.md)** object.</span></span>

## <a name="syntax"></a><span data-ttu-id="026dc-105">语法</span><span class="sxs-lookup"><span data-stu-id="026dc-105">Syntax</span></span>

<span data-ttu-id="026dc-106">*表达式*。CreateQueryDef （***名称***、 ***SQLText***）</span><span class="sxs-lookup"><span data-stu-id="026dc-106">*expression* .CreateQueryDef(***Name***, ***SQLText***)</span></span>

<span data-ttu-id="026dc-107">*表达式*代表**Connection**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="026dc-107">*expression* A variable that represents a **Connection** object.</span></span>

### <a name="parameters"></a><span data-ttu-id="026dc-108">参数</span><span class="sxs-lookup"><span data-stu-id="026dc-108">Parameters</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="026dc-109">名称</span><span class="sxs-lookup"><span data-stu-id="026dc-109">Name</span></span></p></th>
<th><p><span data-ttu-id="026dc-110">必需/可选</span><span class="sxs-lookup"><span data-stu-id="026dc-110">Required/Optional</span></span></p></th>
<th><p><span data-ttu-id="026dc-111">数据类型</span><span class="sxs-lookup"><span data-stu-id="026dc-111">Data Type</span></span></p></th>
<th><p><span data-ttu-id="026dc-112">说明</span><span class="sxs-lookup"><span data-stu-id="026dc-112">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="026dc-113">名称</span><span class="sxs-lookup"><span data-stu-id="026dc-113">Name</span></span></p></td>
<td><p><span data-ttu-id="026dc-114">可选</span><span class="sxs-lookup"><span data-stu-id="026dc-114">Optional</span></span></p></td>
<td><p><span data-ttu-id="026dc-115"><strong>Variant</strong></span><span class="sxs-lookup"><span data-stu-id="026dc-115"><strong>Variant</strong></span></span></p></td>
<td><p><span data-ttu-id="026dc-116">对新的 <strong>QueryDef</strong> 进行唯一命名的 <strong>Variant</strong>（<strong>String</strong> 子类型）。</span><span class="sxs-lookup"><span data-stu-id="026dc-116">A <strong>Variant</strong> (<strong>String</strong> subtype) that uniquely names the new <strong>QueryDef</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="026dc-117">SQLText</span><span class="sxs-lookup"><span data-stu-id="026dc-117">SQLText</span></span></p></td>
<td><p><span data-ttu-id="026dc-118">可选</span><span class="sxs-lookup"><span data-stu-id="026dc-118">Optional</span></span></p></td>
<td><p><span data-ttu-id="026dc-119"><strong>Variant</strong></span><span class="sxs-lookup"><span data-stu-id="026dc-119"><strong>Variant</strong></span></span></p></td>
<td><p><span data-ttu-id="026dc-p101">一个 <strong>Variant</strong>（<strong>String</strong> 子类型）类型的值，它是一个定义 <strong>QueryDef</strong> 的 SQL 语句。如果省略此参数，则可以通过在将 <strong>QueryDef</strong> 追加到集合之前或之后设置它的 <strong><a href="querydef-sql-property-dao.md">SQL</a></strong> 属性对其进行定义。</span><span class="sxs-lookup"><span data-stu-id="026dc-p101">A <strong>Variant</strong> (<strong>String</strong> subtype) that is an SQL statement defining the <strong>QueryDef</strong>. If you omit this argument, you can define the <strong>QueryDef</strong> by setting its <strong><a href="querydef-sql-property-dao.md">SQL</a></strong> property before or after you append it to a collection.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="return-value"></a><span data-ttu-id="026dc-122">返回值</span><span class="sxs-lookup"><span data-stu-id="026dc-122">Return value</span></span>

<span data-ttu-id="026dc-123">QueryDef</span><span class="sxs-lookup"><span data-stu-id="026dc-123">QueryDef</span></span>

## <a name="remarks"></a><span data-ttu-id="026dc-124">注解</span><span class="sxs-lookup"><span data-stu-id="026dc-124">Remarks</span></span>

<span data-ttu-id="026dc-125">在 Microsoft Access 工作区中，如果在创建 **QueryDef** 时为名称提供了除零长度字符串之外的信息，产生的 **QueryDef** 对象将自动追加到 **[QueryDefs](querydefs-collection-dao.md)** 集合。</span><span class="sxs-lookup"><span data-stu-id="026dc-125">In a Microsoft Access workspace, if you provide anything other than a zero-length string for the name when you create a **QueryDef**, the resulting **QueryDef** object is automatically appended to the **[QueryDefs](querydefs-collection-dao.md)** collection.</span></span>

<span data-ttu-id="026dc-126">如果按名称指定的对象已**QueryDefs**集合的成员，将发生运行时错误。</span><span class="sxs-lookup"><span data-stu-id="026dc-126">If the object specified by name is already a member of the **QueryDefs** collection, a run-time error occurs.</span></span> <span data-ttu-id="026dc-127">您可以通过执行**CreateQueryDef**方法时的名称参数使用一个零长度字符串创建临时**QueryDef** 。</span><span class="sxs-lookup"><span data-stu-id="026dc-127">You can create a temporary **QueryDef** by using a zero-length string for the name argument when you execute the **CreateQueryDef** method.</span></span> <span data-ttu-id="026dc-128">还可以通过将新建的 [QueryDef](connection-name-property-dao.md) 的 \*\*\*\*Name\*\*\*\* 属性设置为零长度字符串 ("") 来完成此操作。</span><span class="sxs-lookup"><span data-stu-id="026dc-128">You can also accomplish this by setting the **[Name](connection-name-property-dao.md)** property of a newly created **QueryDef** to a zero-length string ("").</span></span> <span data-ttu-id="026dc-129">如果您希望反复使用动态 SQL 语句，且不必在 **QueryDefs** 集合中创建任何新的永久对象，则使用临时的 **QueryDef** 对象十分有帮助。</span><span class="sxs-lookup"><span data-stu-id="026dc-129">Temporary **QueryDef** objects are useful if you want to repeatedly use dynamic SQL statements without having to create any new permanent objects in the **QueryDefs** collection.</span></span> <span data-ttu-id="026dc-130">不能将临时的 **QueryDef** 追加到任何集合，因为零长度字符串对永久的 **QueryDef** 对象来说是无效名称。</span><span class="sxs-lookup"><span data-stu-id="026dc-130">You can't append a temporary **QueryDef** to any collection because a zero-length string isn't a valid name for a permanent **QueryDef** object.</span></span> <span data-ttu-id="026dc-131">始终可以设置新建 **QueryDef** 的 **Name** 和 **SQL** 属性，然后将 **QueryDef** 追加到 **QueryDefs** 集合。</span><span class="sxs-lookup"><span data-stu-id="026dc-131">You can always set the **Name** and **SQL** properties of the newly created **QueryDef** object and subsequently append the **QueryDef** to the **QueryDefs** collection.</span></span>

<span data-ttu-id="026dc-132">若要在 **QueryDef** 对象中运行 SQL 语句，请使用 **[Execute](connection-execute-method-dao.md)** 或 **[OpenRecordset](connection-openrecordset-method-dao.md)** 方法。</span><span class="sxs-lookup"><span data-stu-id="026dc-132">To run the SQL statement in a **QueryDef** object, use the **[Execute](connection-execute-method-dao.md)** or **[OpenRecordset](connection-openrecordset-method-dao.md)** method.</span></span>

<span data-ttu-id="026dc-133">使用 **QueryDef** 对象是对 ODBC 数据库执行 SQL 传递查询的首选方法。</span><span class="sxs-lookup"><span data-stu-id="026dc-133">Using a **QueryDef** object is the preferred way to perform SQL pass-through queries with ODBC databases.</span></span>

<span data-ttu-id="026dc-134">若要从 Microsoft Access 数据库引擎数据库中的 **QueryDefs** 集合中删除一个 **QueryDef** 对象，请对该集合使用 **[Delete](fields-delete-method-dao.md)** 方法。</span><span class="sxs-lookup"><span data-stu-id="026dc-134">To remove a **QueryDef** object from a **QueryDefs** collection in a Microsoft Access database engine database, use the **[Delete](fields-delete-method-dao.md)** method on the collection.</span></span>

