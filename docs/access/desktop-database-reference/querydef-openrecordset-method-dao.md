---
title: QueryDef.OpenRecordset 方法 (DAO)
TOCTitle: OpenRecordset Method
ms:assetid: b4908c36-c156-e269-e2ad-b1fa20ec4884
ms:mtpsurl: https://msdn.microsoft.com/library/Ff822070(v=office.15)
ms:contentKeyID: 48547232
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: b3948ba2bd8eb63176483a97942984823b9f45b0
ms.sourcegitcommit: 1dd744993ecb4bed241ace874ad26edaef1778b8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/06/2018
ms.locfileid: "25997145"
---
# <a name="querydefopenrecordset-method-dao"></a><span data-ttu-id="075f9-102">QueryDef.OpenRecordset 方法 (DAO)</span><span class="sxs-lookup"><span data-stu-id="075f9-102">QueryDef.OpenRecordset method (DAO)</span></span>

<span data-ttu-id="075f9-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="075f9-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="075f9-104">创建一个新的 **[Recordset](recordset-object-dao.md)** 对象，并将其追加到 **Recordsets** 集合。</span><span class="sxs-lookup"><span data-stu-id="075f9-104">Creates a new **[Recordset](recordset-object-dao.md)** object and appends it to the **Recordsets** collection.</span></span>

## <a name="syntax"></a><span data-ttu-id="075f9-105">语法</span><span class="sxs-lookup"><span data-stu-id="075f9-105">Syntax</span></span>

<span data-ttu-id="075f9-106">*表达式*。OpenRecordset (***类型***，***选项***， ***LockEdit***)</span><span class="sxs-lookup"><span data-stu-id="075f9-106">*expression* .OpenRecordset(***Type***, ***Options***, ***LockEdit***)</span></span>

<span data-ttu-id="075f9-107">*表达式*一个代表**QueryDef**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="075f9-107">*expression* A variable that represents a **QueryDef** object.</span></span>

## <a name="parameters"></a><span data-ttu-id="075f9-108">参数</span><span class="sxs-lookup"><span data-stu-id="075f9-108">Parameters</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="075f9-109">名称</span><span class="sxs-lookup"><span data-stu-id="075f9-109">Name</span></span></p></th>
<th><p><span data-ttu-id="075f9-110">必需/可选</span><span class="sxs-lookup"><span data-stu-id="075f9-110">Required/optional</span></span></p></th>
<th><p><span data-ttu-id="075f9-111">数据类型</span><span class="sxs-lookup"><span data-stu-id="075f9-111">Data type</span></span></p></th>
<th><p><span data-ttu-id="075f9-112">说明</span><span class="sxs-lookup"><span data-stu-id="075f9-112">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="075f9-113"><em>Type</em></span><span class="sxs-lookup"><span data-stu-id="075f9-113"><em>Type</em></span></span></p></td>
<td><p><span data-ttu-id="075f9-114">可选</span><span class="sxs-lookup"><span data-stu-id="075f9-114">Optional</span></span></p></td>
<td><p><span data-ttu-id="075f9-115"><strong>Variant</strong></span><span class="sxs-lookup"><span data-stu-id="075f9-115"><strong>Variant</strong></span></span></p></td>
<td><p><span data-ttu-id="075f9-116"><strong><a href="recordsettypeenum-enumeration-dao.md">RecordsetTypeEnum</a></strong> 常量，可指示要打开的 <strong>Recordset</strong> 的类型。</span><span class="sxs-lookup"><span data-stu-id="075f9-116">A <strong><a href="recordsettypeenum-enumeration-dao.md">RecordsetTypeEnum</a></strong> constant that indicates the type of <strong>Recordset</strong> to open.</span></span></p><p><span data-ttu-id="075f9-117"><strong>注意</strong>： 如果在 Microsoft Access 工作区中打开<STRONG>Recordset</STRONG>时未指定类型， <STRONG>OpenRecordset</STRONG>创建表类型<STRONG>Recordset</STRONG>，如果可能。</span><span class="sxs-lookup"><span data-stu-id="075f9-117"><strong>NOTE</strong>: If you open a <STRONG>Recordset</STRONG> in a Microsoft Access workspace and you don't specify a type, <STRONG>OpenRecordset</STRONG> creates a table-type <STRONG>Recordset</STRONG>, if possible.</span></span> <span data-ttu-id="075f9-118">如果您指定的链接的表或查询， <STRONG>OpenRecordset</STRONG>创建动态集类型<STRONG>Recordset</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="075f9-118">If you specify a linked table or query, <STRONG>OpenRecordset</STRONG> creates a dynaset-type <STRONG>Recordset</STRONG>.</span></span></p>
</td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="075f9-119"><em>Options</em></span><span class="sxs-lookup"><span data-stu-id="075f9-119"><em>Options</em></span></span></p></td>
<td><p><span data-ttu-id="075f9-120">可选</span><span class="sxs-lookup"><span data-stu-id="075f9-120">Optional</span></span></p></td>
<td><p><span data-ttu-id="075f9-121"><strong>Variant</strong></span><span class="sxs-lookup"><span data-stu-id="075f9-121"><strong>Variant</strong></span></span></p></td>
<td><p><span data-ttu-id="075f9-122"><strong><a href="recordsetoptionenum-enumeration-dao.md">RecordsetOptionEnum</a></strong> 常量的组合，可指定新 <strong>Recordset</strong> 的特性。</span><span class="sxs-lookup"><span data-stu-id="075f9-122">A combination of <strong><a href="recordsetoptionenum-enumeration-dao.md">RecordsetOptionEnum</a></strong> constants that specify characteristics of the new <strong>Recordset</strong>.</span></span></p></p><p><span data-ttu-id="075f9-123"><strong>注意</strong>： 常量<STRONG>dbConsistent</STRONG>和<STRONG>dbInconsistent</STRONG>是互斥的并且在同时使用将导致出错。</span><span class="sxs-lookup"><span data-stu-id="075f9-123"><strong>NOTE</strong>: The constants <STRONG>dbConsistent</STRONG> and <STRONG>dbInconsistent</STRONG> are mutually exclusive, and using both causes an error.</span></span> <span data-ttu-id="075f9-124">提供 lockedits 实参，当选项使用<STRONG>dbReadOnly</STRONG>常量还会导致错误。</span><span class="sxs-lookup"><span data-stu-id="075f9-124">Supplying a lockedits argument when options uses the <STRONG>dbReadOnly</STRONG> constant also causes an error.</span></span></p>
</td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="075f9-125"><em>LockEdit</em></span><span class="sxs-lookup"><span data-stu-id="075f9-125"><em>LockEdit</em></span></span></p></td>
<td><p><span data-ttu-id="075f9-126">可选</span><span class="sxs-lookup"><span data-stu-id="075f9-126">Optional</span></span></p></td>
<td><p><span data-ttu-id="075f9-127"><strong>Variant</strong></span><span class="sxs-lookup"><span data-stu-id="075f9-127"><strong>Variant</strong></span></span></p></td>
<td><p><span data-ttu-id="075f9-128"><strong><a href="locktypeenum-enumeration-dao.md">LockTypeEnum</a></strong> 常量，可确定 <strong>Recordset</strong> 是否锁定。</span><span class="sxs-lookup"><span data-stu-id="075f9-128">A <strong><a href="locktypeenum-enumeration-dao.md">LockTypeEnum</a></strong> constant that determines the locking for the <strong>Recordset</strong>.</span></span></p></p><p><span data-ttu-id="075f9-129"><strong>注意</strong>： 您可以使用<STRONG>dbReadOnly</STRONG> options 参数或 lockedits 参数，但不是能同时中。</span><span class="sxs-lookup"><span data-stu-id="075f9-129"><strong>NOTE</strong>: You can use <STRONG>dbReadOnly</STRONG> in either the options argument or the lockedits argument, but not both.</span></span> <span data-ttu-id="075f9-130">如果您使用它为两个参数，将发生运行时错误。</span><span class="sxs-lookup"><span data-stu-id="075f9-130">If you use it for both arguments, a run-time error occurs.</span></span></p>
</td>
</tr>
</tbody>
</table>


## <a name="return-value"></a><span data-ttu-id="075f9-131">返回值</span><span class="sxs-lookup"><span data-stu-id="075f9-131">Return value</span></span>

<span data-ttu-id="075f9-132">Recordset</span><span class="sxs-lookup"><span data-stu-id="075f9-132">Recordset</span></span>

## <a name="remarks"></a><span data-ttu-id="075f9-133">注解</span><span class="sxs-lookup"><span data-stu-id="075f9-133">Remarks</span></span>

<span data-ttu-id="075f9-134">如果在 Microsoft Access 数据库引擎连接的 ODBC 工作区中，对包含 IDENTITY 列的 Microsoft SQL Server 6.0（或更新版本）表打开了 [Recordset](recordsetoptionenum-enumeration-dao.md)，则还应该使用 \*\*\*\*dbSeeChanges\*\*\*\* 常量，否则会导致出错。</span><span class="sxs-lookup"><span data-stu-id="075f9-134">You should also use the **[dbSeeChanges](recordsetoptionenum-enumeration-dao.md)** constant if you open a **Recordset** in a Microsoft Access database engine-connected ODBC workspace against a Microsoft SQL Server 6.0 (or later) table that has an IDENTITY column, otherwise an error may result.</span></span>

<span data-ttu-id="075f9-p104">对一个 ODBC 数据源打开多个 **Recordset** 可能会失败，因为连接正被 **OpenRecordset** 调用占用。解决此问题的一种方法是在打开 **Recordset** 后立即使用 **[MoveLast](recordset-movelast-method-dao.md)** 方法，以完全填充 **Recordset**。</span><span class="sxs-lookup"><span data-stu-id="075f9-p104">Opening more than one **Recordset** on an ODBC data source may fail because the connection is busy with a prior **OpenRecordset** call. One way around this is to fully populate the **Recordset** by using the **[MoveLast](recordset-movelast-method-dao.md)** method as soon as the **Recordset** is opened.</span></span>

<span data-ttu-id="075f9-137">使用 **Close** 方法关闭 **Recordset** 会自动从 **Recordsets** 集合中将其删除。</span><span class="sxs-lookup"><span data-stu-id="075f9-137">Closing a **Recordset** with the **Close** method automatically deletes it from the **Recordsets** collection.</span></span>

> [!NOTE]
> <span data-ttu-id="075f9-138">如果*源*是指的 SQL 语句组成非整数值时，连接字符串和系统参数指定非美国十进制字符，例如逗号分隔 (例如，strSQL ="价格&gt;" &amp; lngPrice，和 lngPrice =125,50)，当您尝试打开**Recordset**时就会出错。</span><span class="sxs-lookup"><span data-stu-id="075f9-138">If *source* refers to an SQL statement composed of a string concatenated with a non-integer value, and the system parameters specify a non-U.S. decimal character such as a comma (for example, strSQL = "PRICE &gt; " &amp; lngPrice, and lngPrice = 125,50), an error occurs when you try to open the **Recordset**.</span></span> <span data-ttu-id="075f9-139">这是因为在连接过程中，需要使用系统的默认小数字符将数字转换为字符串，并且 SQL 只接受美国格式的小数字符。</span><span class="sxs-lookup"><span data-stu-id="075f9-139">This is because during concatenation, the number will be converted to a string using your system's default decimal character, and SQL only accepts U.S. decimal characters.</span></span>


