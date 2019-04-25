---
title: QueryDef.OpenRecordset 方法 (DAO)
TOCTitle: OpenRecordset Method
ms:assetid: b4908c36-c156-e269-e2ad-b1fa20ec4884
ms:mtpsurl: https://msdn.microsoft.com/library/Ff822070(v=office.15)
ms:contentKeyID: 48547232
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Priority
ms.openlocfilehash: a046359f39611e38b9e517495f54041f876addfc
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32302847"
---
# <a name="querydefopenrecordset-method-dao"></a><span data-ttu-id="bdf04-102">QueryDef.OpenRecordset 方法 (DAO)</span><span class="sxs-lookup"><span data-stu-id="bdf04-102">QueryDef.OpenRecordset method (DAO)</span></span>

<span data-ttu-id="bdf04-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="bdf04-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="bdf04-104">创建一个新的 **[Recordset](recordset-object-dao.md)** 对象，并将其追加到 **Recordsets** 集合。</span><span class="sxs-lookup"><span data-stu-id="bdf04-104">Creates a new **[Recordset](recordset-object-dao.md)** object and appends it to the **Recordsets** collection.</span></span>

## <a name="syntax"></a><span data-ttu-id="bdf04-105">语法</span><span class="sxs-lookup"><span data-stu-id="bdf04-105">Syntax</span></span>

<span data-ttu-id="bdf04-106">*表达式* .OpenRecordset(***Type***, ***Options***, ***LockEdit***)</span><span class="sxs-lookup"><span data-stu-id="bdf04-106">*expression* .OpenRecordset(***Type***, ***Options***, ***LockEdit***)</span></span>

<span data-ttu-id="bdf04-107">*表达式* 一个表示 **QueryDef** 对象的变量。</span><span class="sxs-lookup"><span data-stu-id="bdf04-107">*expression*  A variable that represents a **QueryDef** object.</span></span>

## <a name="parameters"></a><span data-ttu-id="bdf04-108">参数</span><span class="sxs-lookup"><span data-stu-id="bdf04-108">Parameters</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="bdf04-109">名称</span><span class="sxs-lookup"><span data-stu-id="bdf04-109">Name</span></span></p></th>
<th><p><span data-ttu-id="bdf04-110">必需/可选</span><span class="sxs-lookup"><span data-stu-id="bdf04-110">Required/Optional</span></span></p></th>
<th><p><span data-ttu-id="bdf04-111">数据类型</span><span class="sxs-lookup"><span data-stu-id="bdf04-111">Data type</span></span></p></th>
<th><p><span data-ttu-id="bdf04-112">说明</span><span class="sxs-lookup"><span data-stu-id="bdf04-112">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bdf04-113"><em>Type</em></span><span class="sxs-lookup"><span data-stu-id="bdf04-113"><em>Type</em></span></span></p></td>
<td><p><span data-ttu-id="bdf04-114">可选</span><span class="sxs-lookup"><span data-stu-id="bdf04-114">Optional</span></span></p></td>
<td><p><span data-ttu-id="bdf04-115"><strong>Variant</strong></span><span class="sxs-lookup"><span data-stu-id="bdf04-115"><strong>Variant</strong></span></span></p></td>
<td><p><span data-ttu-id="bdf04-116">
            <strong>
            <a href="recordsettypeenum-enumeration-dao.md">RecordsetTypeEnum</a></strong> 常量，可指示要打开的 <strong>Recordset</strong> 的类型。</span><span class="sxs-lookup"><span data-stu-id="bdf04-116">A <strong><a href="recordsettypeenum-enumeration-dao.md">RecordsetTypeEnum</a></strong> constant that indicates the type of <strong>Recordset</strong> to open.</span></span></p><p><span data-ttu-id="bdf04-117"><strong>注意</strong>：如果在 Microsoft Access 工作区中打开 <STRONG>Recordset</STRONG>，并且不指定类型，<STRONG>OpenRecordset</STRONG> 会创建一个表类型 <STRONG>Recordset</STRONG>（如果可以）。</span><span class="sxs-lookup"><span data-stu-id="bdf04-117"> > If you open a Recordset in a Microsoft Access workspace and you don't specify a type, OpenRecordset creates a table-type Recordset, if possible.</span></span> <span data-ttu-id="bdf04-118">If you specify a linked table or query, <STRONG>OpenRecordset</STRONG> creates a dynaset-type <STRONG>Recordset</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="bdf04-118">If you specify a linked table or query, <STRONG>OpenRecordset</STRONG> creates a dynaset-type <STRONG>Recordset</STRONG>.</span></span></p>
</td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdf04-119"><em>选项</em></span><span class="sxs-lookup"><span data-stu-id="bdf04-119"><em>Options</em></span></span></p></td>
<td><p><span data-ttu-id="bdf04-120">可选</span><span class="sxs-lookup"><span data-stu-id="bdf04-120">Optional</span></span></p></td>
<td><p><span data-ttu-id="bdf04-121"><strong>Variant</strong></span><span class="sxs-lookup"><span data-stu-id="bdf04-121"><strong>Variant</strong></span></span></p></td>
<td><p><span data-ttu-id="bdf04-122">
            <strong>
            <a href="recordsetoptionenum-enumeration-dao.md">RecordsetOptionEnum</a></strong> 常量的组合，可指定新 <strong>Recordset</strong> 的特性。</span><span class="sxs-lookup"><span data-stu-id="bdf04-122">A combination of <strong><a href="recordsetoptionenum-enumeration-dao.md">RecordsetOptionEnum</a></strong> constants that specify characteristics of the new <strong>Recordset</strong>.</span></span></p></p><p><span data-ttu-id="bdf04-123"><strong>注意</strong>：常量 <STRONG>dbConsistent</STRONG> 和 <STRONG>dbInconsistent</STRONG> 相互排斥，同时使用两者会产生错误。</span><span class="sxs-lookup"><span data-stu-id="bdf04-123">The constants <STRONG>dbConsistent</STRONG> and <STRONG>dbInconsistent</STRONG> are mutually exclusive, and using both causes an error.</span></span> <span data-ttu-id="bdf04-124">当 Options 使用 <STRONG>dbReadOnly</STRONG> 常量时提供 LockEdit 参数也会导致错误。</span><span class="sxs-lookup"><span data-stu-id="bdf04-124">Supplying a  LockEdit argument when  Options uses the dbReadOnly constant also causes an error.</span></span></p>
</td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdf04-125"><em>LockEdit</em></span><span class="sxs-lookup"><span data-stu-id="bdf04-125"><em>LockEdit</em></span></span></p></td>
<td><p><span data-ttu-id="bdf04-126">可选</span><span class="sxs-lookup"><span data-stu-id="bdf04-126">Optional</span></span></p></td>
<td><p><span data-ttu-id="bdf04-127"><strong>Variant</strong></span><span class="sxs-lookup"><span data-stu-id="bdf04-127"><strong>Variant</strong></span></span></p></td>
<td><p><span data-ttu-id="bdf04-128">
            <strong>
            <a href="locktypeenum-enumeration-dao.md">LockTypeEnum</a></strong> 常量，可确定 <strong>Recordset</strong> 是否锁定。</span><span class="sxs-lookup"><span data-stu-id="bdf04-128">A <strong><a href="locktypeenum-enumeration-dao.md">LockTypeEnum</a></strong> constant that determines the locking for the <strong>Recordset</strong>.</span></span></p></p><p><span data-ttu-id="bdf04-129"><strong>注意</strong>：可以在 Options 参数或 LockedEdit 参数中使用 <STRONG>dbReadOnly</STRONG>，但不能同时在两个参数中使用。</span><span class="sxs-lookup"><span data-stu-id="bdf04-129">You can use dbReadOnly in either the Options argument or the LockedEdit argument, but not both.</span></span> <span data-ttu-id="bdf04-130">如果将其同时用于这两个参数，将出现运行时错误。</span><span class="sxs-lookup"><span data-stu-id="bdf04-130">If you use it for both arguments, a run-time error occurs.</span></span></p>
</td>
</tr>
</tbody>
</table>


## <a name="return-value"></a><span data-ttu-id="bdf04-131">返回值</span><span class="sxs-lookup"><span data-stu-id="bdf04-131">Return value</span></span>

<span data-ttu-id="bdf04-132">Recordset</span><span class="sxs-lookup"><span data-stu-id="bdf04-132">Recordset</span></span>

## <a name="remarks"></a><span data-ttu-id="bdf04-133">说明</span><span class="sxs-lookup"><span data-stu-id="bdf04-133">Remarks</span></span>

<span data-ttu-id="bdf04-134">如果在 Microsoft Access 数据库引擎连接的 ODBC 工作区中，对包含 IDENTITY 列的 Microsoft SQL Server 6.0（或更新版本）表打开了 **Recordset**，则还应该使用 **[dbSeeChanges](recordsetoptionenum-enumeration-dao.md)** 常量，否则会导致出错。</span><span class="sxs-lookup"><span data-stu-id="bdf04-134">You should also use the [**dbSeeChanges**](recordsetoptionenum-enumeration-dao.md) constant if you open a **Recordset** in a Microsoft Access database engine-connected ODBC workspace against a Microsoft SQL Server 6.0 (or later) table that has an IDENTITY column, otherwise an error may result.</span></span>

<span data-ttu-id="bdf04-p104">对一个 ODBC 数据源打开多个 **Recordset** 可能会失败，因为连接正被 **OpenRecordset** 调用占用。解决此问题的一种方法是在打开 **Recordset** 后立即使用 **[MoveLast](recordset-movelast-method-dao.md)** 方法，以完全填充 **Recordset**。</span><span class="sxs-lookup"><span data-stu-id="bdf04-p104">Opening more than one **Recordset** on an ODBC data source may fail because the connection is busy with a prior **OpenRecordset** call. One way around this is to fully populate the **Recordset** by using the **[MoveLast](recordset-movelast-method-dao.md)** method as soon as the **Recordset** is opened.</span></span>

<span data-ttu-id="bdf04-137">使用 **Close** 方法关闭 **Recordset** 会自动从 **Recordsets** 集合中将其删除。</span><span class="sxs-lookup"><span data-stu-id="bdf04-137">Closing a **Recordset** with the **Close** method automatically deletes it from the **Recordsets** collection.</span></span>

> [!NOTE]
> <span data-ttu-id="bdf04-138">如果*源*引用了一个由连接了非整数值的字符串组成的 SQL 语句，并且系统参数指定了诸如逗号的非美国格式小数字符（例如 strSQL = "PRICE &gt; " &amp; lngPrice 和 lngPrice = 125,50），那么在尝试打开 **Recordset** 时会发生错误。</span><span class="sxs-lookup"><span data-stu-id="bdf04-138">If source refers to an SQL statement composed of a string concatenated with a non-integer value, and the system parameters specify a non-U.S. decimal character such as a comma (for example, strSQL = "PRICE > " & lngPrice, and lngPrice = 125,50), an error occurs when you try to open the Recordset.</span></span> <span data-ttu-id="bdf04-139">这是因为在连接过程中，需要使用系统的默认小数字符将数字转换为字符串，并且 SQL 只接受美国格式的小数字符。</span><span class="sxs-lookup"><span data-stu-id="bdf04-139">This is because during concatenation, the number will be converted to a string using your system's default decimal character, and SQL only accepts U.S. decimal characters.</span></span>


