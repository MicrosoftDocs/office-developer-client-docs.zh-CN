---
title: Connection.Execute Method (DAO)
TOCTitle: Execute Method
ms:assetid: d6140d4e-fa14-6455-525e-49d8aab3dff7
ms:mtpsurl: https://msdn.microsoft.com/library/Ff835040(v=office.15)
ms:contentKeyID: 48547978
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 3171ec1d35f08a5bc9d6a02a9a50ca80e11413de
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467916"
---
# <a name="connectionexecute-method-dao"></a><span data-ttu-id="93d3e-102">Connection.Execute Method (DAO)</span><span class="sxs-lookup"><span data-stu-id="93d3e-102">Connection.Execute Method (DAO)</span></span>


<span data-ttu-id="93d3e-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="93d3e-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="93d3e-104">对指定的对象运行动作查询，或执行 SQL 语句。</span><span class="sxs-lookup"><span data-stu-id="93d3e-104">Runs an action query or executes an SQL statement on the specified object.</span></span>

## <a name="syntax"></a><span data-ttu-id="93d3e-105">语法</span><span class="sxs-lookup"><span data-stu-id="93d3e-105">Syntax</span></span>

<span data-ttu-id="93d3e-106">*表达式*。执行 （***查询***，***选项***）</span><span class="sxs-lookup"><span data-stu-id="93d3e-106">*expression* .Execute(***Query***, ***Options***)</span></span>

<span data-ttu-id="93d3e-107">*表达式*代表**Connection**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="93d3e-107">*expression* A variable that represents a **Connection** object.</span></span>

### <a name="parameters"></a><span data-ttu-id="93d3e-108">参数</span><span class="sxs-lookup"><span data-stu-id="93d3e-108">Parameters</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="93d3e-109">名称</span><span class="sxs-lookup"><span data-stu-id="93d3e-109">Name</span></span></p></th>
<th><p><span data-ttu-id="93d3e-110">必需/可选</span><span class="sxs-lookup"><span data-stu-id="93d3e-110">Required/Optional</span></span></p></th>
<th><p><span data-ttu-id="93d3e-111">数据类型</span><span class="sxs-lookup"><span data-stu-id="93d3e-111">Data Type</span></span></p></th>
<th><p><span data-ttu-id="93d3e-112">说明</span><span class="sxs-lookup"><span data-stu-id="93d3e-112">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="93d3e-113">Query</span><span class="sxs-lookup"><span data-stu-id="93d3e-113">Query</span></span></p></td>
<td><p><span data-ttu-id="93d3e-114">必需</span><span class="sxs-lookup"><span data-stu-id="93d3e-114">Required</span></span></p></td>
<td><p><span data-ttu-id="93d3e-115"><strong>字符串</strong></span><span class="sxs-lookup"><span data-stu-id="93d3e-115"><strong>String</strong></span></span></p></td>
<td><p><span data-ttu-id="93d3e-116">一个 <strong>String</strong>，为 SQL 语句，或者 <strong>QueryDef</strong> 对象的 <strong>Name</strong> 属性值。</span><span class="sxs-lookup"><span data-stu-id="93d3e-116">A <strong>String</strong> that is an SQL statement or the <strong>Name</strong> property value of a <strong>QueryDef</strong> object.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93d3e-117">选项</span><span class="sxs-lookup"><span data-stu-id="93d3e-117">Options</span></span></p></td>
<td><p><span data-ttu-id="93d3e-118">可选</span><span class="sxs-lookup"><span data-stu-id="93d3e-118">Optional</span></span></p></td>
<td><p><span data-ttu-id="93d3e-119"><strong>Variant</strong></span><span class="sxs-lookup"><span data-stu-id="93d3e-119"><strong>Variant</strong></span></span></p></td>
<td><p><span data-ttu-id="93d3e-120">一个常量或常量组合，按 Settings 中的指定确定查询的数据完整性特征。</span><span class="sxs-lookup"><span data-stu-id="93d3e-120">A constant or combination of constants that determines the data integrity characteristics of the query, as specified in Settings.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="93d3e-121">注解</span><span class="sxs-lookup"><span data-stu-id="93d3e-121">Remarks</span></span>

<span data-ttu-id="93d3e-122">选项，可以使用以下**[RecordsetOptionEnum](recordsetoptionenum-enumeration-dao.md)** 常量。</span><span class="sxs-lookup"><span data-stu-id="93d3e-122">You can use the following **[RecordsetOptionEnum](recordsetoptionenum-enumeration-dao.md)** constants for options.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="93d3e-123">常量</span><span class="sxs-lookup"><span data-stu-id="93d3e-123">Constant</span></span></p></th>
<th><p><span data-ttu-id="93d3e-124">说明</span><span class="sxs-lookup"><span data-stu-id="93d3e-124">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="93d3e-125"><strong>dbDenyWrite</strong></span><span class="sxs-lookup"><span data-stu-id="93d3e-125"><strong>dbDenyWrite</strong></span></span></p></td>
<td><p><span data-ttu-id="93d3e-126">拒绝其他用户的写入权限（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="93d3e-126">Denies write permission to other users (Microsoft Access workspaces only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93d3e-127"><strong>dbInconsistent</strong></span><span class="sxs-lookup"><span data-stu-id="93d3e-127"><strong>dbInconsistent</strong></span></span></p></td>
<td><p><span data-ttu-id="93d3e-128">（默认值）执行不一致的更新（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="93d3e-128">(Default) Executes inconsistent updates (Microsoft Access workspaces only).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93d3e-129"><strong>dbConsistent</strong></span><span class="sxs-lookup"><span data-stu-id="93d3e-129"><strong>dbConsistent</strong></span></span></p></td>
<td><p><span data-ttu-id="93d3e-130">执行一致的更新（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="93d3e-130">Executes consistent updates (Microsoft Access workspaces only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93d3e-131"><strong>dbSQLPassThrough</strong></span><span class="sxs-lookup"><span data-stu-id="93d3e-131"><strong>dbSQLPassThrough</strong></span></span></p></td>
<td><p><span data-ttu-id="93d3e-p101">执行 SQL 传递查询。设置此选项会将 SQL 语句传递给 ODBC 数据库以进行处理（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="93d3e-p101">Executes an SQL pass-through query. Setting this option passes the SQL statement to an ODBC database for processing (Microsoft Access workspaces only).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93d3e-134"><strong>dbFailOnError</strong></span><span class="sxs-lookup"><span data-stu-id="93d3e-134"><strong>dbFailOnError</strong></span></span></p></td>
<td><p><span data-ttu-id="93d3e-135">发生错误时回滚更新（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="93d3e-135">Rolls back updates if an error occurs (Microsoft Access workspaces only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93d3e-136"><strong>dbSeeChanges</strong></span><span class="sxs-lookup"><span data-stu-id="93d3e-136"><strong>dbSeeChanges</strong></span></span></p></td>
<td><p><span data-ttu-id="93d3e-137">如果其他用户更改您正编辑的数据，则生成运行时错误（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="93d3e-137">Generates a run-time error if another user is changing data you are editing (Microsoft Access workspaces only).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93d3e-138"><strong>dbRunAsync</strong></span><span class="sxs-lookup"><span data-stu-id="93d3e-138"><strong>dbRunAsync</strong></span></span></p></td>
<td><p><span data-ttu-id="93d3e-139">异步执行查询（仅适用于 ODBCDirect Connection 和 QueryDef 对象）。</span><span class="sxs-lookup"><span data-stu-id="93d3e-139">Executes the query asynchronously (ODBCDirect Connection and QueryDef objects only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93d3e-140"><strong>一设置</strong></span><span class="sxs-lookup"><span data-stu-id="93d3e-140"><strong>dbExecDirect</strong></span></span></p></td>
<td><p><span data-ttu-id="93d3e-141">在不首先调用 SQLPrepare ODBC API 函数的情况下，执行语句（仅适用于 ODBCDirect Connection 和 QueryDef 对象）。</span><span class="sxs-lookup"><span data-stu-id="93d3e-141">Executes the statement without first calling SQLPrepare ODBC API function (ODBCDirect Connection and QueryDef objects only).</span></span></p></td>
</tr>
</tbody>
</table>



> [!NOTE]
> <P><span data-ttu-id="93d3e-142">Microsoft Access 2013 中不支持适用于 ODBCDirect 工作区。</span><span class="sxs-lookup"><span data-stu-id="93d3e-142">ODBCDirect workspaces are not supported in Microsoft Access 2013.</span></span> <span data-ttu-id="93d3e-143">如果要在不使用 Microsoft Access 数据库引擎的情况下访问外部数据源，请使用 ADO。</span><span class="sxs-lookup"><span data-stu-id="93d3e-143">Use ADO if you want to access external data sources without using the Microsoft Access database engine.</span></span></P>




> [!NOTE]
> <P><span data-ttu-id="93d3e-p103">[!注释] 常量 <STRONG>dbConsistent</STRONG> 和 <STRONG>dbInconsistent</STRONG> 是互斥的。可以在 <STRONG>OpenRecordset</STRONG> 的给定实例中使用其中的某一个，但不能同时使用此两者。同时使用 <STRONG>dbConsistent</STRONG> 和 <STRONG>dbInconsistent</STRONG> 会导致出错。</span><span class="sxs-lookup"><span data-stu-id="93d3e-p103">The constants <STRONG>dbConsistent</STRONG> and <STRONG>dbInconsistent</STRONG> are mutually exclusive. You can use one or the other, but not both in a given instance of <STRONG>OpenRecordset</STRONG>. Using both <STRONG>dbConsistent</STRONG> and <STRONG>dbInconsistent</STRONG> causes an error.</span></span></P>



<span data-ttu-id="93d3e-p104">**Execute** 方法仅对动作查询有效。如果将 **Execute** 与另一个查询类型一起使用，将会发生错误。由于动作查询不返回任何记录，因此 **Execute** 不返回 **Recordset**。（如果不返回 **Recordset**，在 ODBCDirect 工作区中执行 SQL 传递查询不会返回错误。）</span><span class="sxs-lookup"><span data-stu-id="93d3e-p104">The **Execute** method is valid only for action queries. If you use **Execute** with another type of query, an error occurs. Because an action query doesn't return any records, **Execute** doesn't return a **Recordset**. (Executing an SQL pass-through query in an ODBCDirect workspace will not return an error if a **Recordset** isn't returned.)</span></span>

<span data-ttu-id="93d3e-p105">使用 **Connection**、 **Database** 或 **QueryDef** 对象的 **RecordsAffected** 属性确定受最近的 **Execute** 方法影响的记录数。例如， **RecordsAffected** 包含执行某个动作查询时删除、更新或插入的记录数。如果使用 **Execute** 方法运行查询，会将 **QueryDef** 对象的 **RecordsAffected** 属性设置为受影响的记录数。</span><span class="sxs-lookup"><span data-stu-id="93d3e-p105">Use the **RecordsAffected** property of the **Connection**, **Database**, or **QueryDef** object to determine the number of records affected by the most recent **Execute** method. For example, **RecordsAffected** contains the number of records deleted, updated, or inserted when executing an action query. When you use the **Execute** method to run a query, the **RecordsAffected** property of the **QueryDef** object is set to the number of records affected.</span></span>

<span data-ttu-id="93d3e-p106">在 Microsoft Access 工作区中，如果提供了一个在语法上正确的 SQL 语句，并且您具有相应的权限，则 **Execute** 方法不会失败 - 即使一行都不能修改或删除，也是如此。因此，在使用 **Execute** 方法运行更新或删除查询时，请始终使用 **dbFailOnError** 选项。如果锁定了任何受影响的记录，因而无法对其进行更新或删除，此选项将生成运行时错误，同时回滚所有成功的更改。</span><span class="sxs-lookup"><span data-stu-id="93d3e-p106">In a Microsoft Access workspace, if you provide a syntactically correct SQL statement and have the appropriate permissions, the **Execute** method won't fail — even if not a single row can be modified or deleted. Therefore, always use the **dbFailOnError** option when using the **Execute** method to run an update or delete query. This option generates a run-time error and rolls back all successful changes if any of the records affected are locked and can't be updated or deleted.</span></span>

<span data-ttu-id="93d3e-p107">在早期版本的 Microsoft Jet 数据库引擎中，SQL 语句自动嵌入到隐式事务中。如果使用 **dbFailOnError** 执行的语句的一部分失败，则整个语句都会回滚。为了改善性能，从版本 3.5 开始，删除了这些隐式事务。如果要更新早期的 DAO 代码，请务必考虑对 **Execute** 语句使用显式事务。</span><span class="sxs-lookup"><span data-stu-id="93d3e-p107">In earlier versions of the Microsoft Jet database engine, SQL statements were automatically embedded in implicit transactions. If part of a statement executed with **dbFailOnError** failed, the entire statement would be rolled back. To improve performance, these implicit transactions were removed starting with version 3.5. If you are updating older DAO code, be sure to consider using explicit transactions around **Execute** statements.</span></span>

<span data-ttu-id="93d3e-p108">为了在 Microsoft Access 工作区中，特别是在多用户环境中获取最佳性能，请将 **Execute** 方法嵌套在事务中。对当前的 **Workspace** 对象使用 **BeginTrans** 方法，然后使用 **Execute** 方法，再对 **Workspace** 使用 **CommitTrans** 方法完成事务。这样可以保存磁盘上的更改，并且释放任何在运行查询时放置的锁定。</span><span class="sxs-lookup"><span data-stu-id="93d3e-p108">For best performance in a Microsoft Access workspace, especially in a multiuser environment, nest the **Execute** method inside a transaction. Use the **BeginTrans** method on the current **Workspace** object, then use the **Execute** method, and complete the transaction by using the **CommitTrans** method on the **Workspace**. This saves changes on disk and frees any locks placed while the query is running.</span></span>

