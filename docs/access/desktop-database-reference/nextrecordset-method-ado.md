---
title: NextRecordset 方法 (ADO)
TOCTitle: NextRecordset method (ADO)
ms:assetid: d2776dd5-d521-c57f-dbe5-e02ee238104d
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250051(v=office.15)
ms:contentKeyID: 48547887
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 6ca95e311f6040d5834fa24ce24d392375953990
ms.sourcegitcommit: 980a96cf444882d3d34cecb5faac8f8a7b7c4b57
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25949934"
---
# <a name="nextrecordset-method-ado"></a><span data-ttu-id="caa8d-102">NextRecordset 方法 (ADO)</span><span class="sxs-lookup"><span data-stu-id="caa8d-102">NextRecordset method (ADO)</span></span>

<span data-ttu-id="caa8d-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="caa8d-103">**Applies to**: Access 2013, Office 2013</span></span>
 
<span data-ttu-id="caa8d-104">用于通过执行一系列命令，清除当前 [Recordset](recordset-object-ado.md) 对象并返回下一个 **Recordset** 。</span><span class="sxs-lookup"><span data-stu-id="caa8d-104">Clears the current [Recordset](recordset-object-ado.md) object and returns the next **Recordset** by advancing through a series of commands.</span></span>

## <a name="syntax"></a><span data-ttu-id="caa8d-105">语法</span><span class="sxs-lookup"><span data-stu-id="caa8d-105">Syntax</span></span>

<span data-ttu-id="caa8d-106">设置*recordset2* = *recordset1*。NextRecordset (*RecordsAffected* )</span><span class="sxs-lookup"><span data-stu-id="caa8d-106">Set *recordset2* = *recordset1*.NextRecordset(*RecordsAffected* )</span></span>

## <a name="return-value"></a><span data-ttu-id="caa8d-107">返回值</span><span class="sxs-lookup"><span data-stu-id="caa8d-107">Return value</span></span>

<span data-ttu-id="caa8d-p101">返回一个 **Recordset** 对象。在语法模型中，*recordset1* 和 *recordset2* 可以是相同的 **Recordset** 对象，也可以是不同的对象。使用不同的 **Recordset** 对象时，在调用 **NextRecordset** 之后重置原始 **Recordset** (*recordset1*) 的 **ActiveConnection** 属性将生成错误。</span><span class="sxs-lookup"><span data-stu-id="caa8d-p101">Returns a **Recordset** object. In the syntax model, *recordset1* and *recordset2* can be the same **Recordset** object, or you can use separate objects. When using separate **Recordset** objects, resetting the **ActiveConnection** property on the original **Recordset** (*recordset1*) after **NextRecordset** has been called will generate an error.</span></span>

## <a name="parameters"></a><span data-ttu-id="caa8d-111">参数</span><span class="sxs-lookup"><span data-stu-id="caa8d-111">Parameters</span></span>

|<span data-ttu-id="caa8d-112">参数</span><span class="sxs-lookup"><span data-stu-id="caa8d-112">Parameter</span></span>|<span data-ttu-id="caa8d-113">说明</span><span class="sxs-lookup"><span data-stu-id="caa8d-113">Description</span></span>|
|:--------|:----------|
|<span data-ttu-id="caa8d-114">*RecordsAffected*</span><span class="sxs-lookup"><span data-stu-id="caa8d-114">*RecordsAffected*</span></span> |<span data-ttu-id="caa8d-p102">可选。 **长整型** 变量，提供程序将受当前操作影响的记录数返回到该变量。</span><span class="sxs-lookup"><span data-stu-id="caa8d-p102">Optional. A **Long** variable to which the provider returns the number of records that the current operation affected.</span></span>|

> [!NOTE]
> <span data-ttu-id="caa8d-117">[!注释] 该参数仅返回受操作影响的记录数；它并不返回来自选择语句（用于生成 **Recordset** ）的记录计数。</span><span class="sxs-lookup"><span data-stu-id="caa8d-117">This parameter only returns the number of records affected by an operation; it does not return a count of records from a select statement used to generate the **Recordset**.</span></span>

## <a name="remarks"></a><span data-ttu-id="caa8d-118">备注</span><span class="sxs-lookup"><span data-stu-id="caa8d-118">Remarks</span></span>

<span data-ttu-id="caa8d-119">使用 **NextRecordset** 方法可以返回复合命令语句中下一个命令的结果，或可返回多个结果的存储过程的结果。</span><span class="sxs-lookup"><span data-stu-id="caa8d-119">Use the **NextRecordset** method to return the results of the next command in a compound command statement or of a stored procedure that returns multiple results.</span></span> <span data-ttu-id="caa8d-120">如果您打开一个基于复合命令语句的**Recordset**对象 (例如，"选择\*TABLE1;选择\*从 table2") 上的[命令](command-object-ado.md)或[Open](open-method-ado-recordset.md)方法在**Recordset**上的使用[Execute](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/execute-method-ado-command)方法，ADO 执行仅的第一个命令，并将结果返回到*recordset*。</span><span class="sxs-lookup"><span data-stu-id="caa8d-120">If you open a **Recordset** object based on a compound command statement (for example, "SELECT \* FROM table1;SELECT \* FROM table2") using the [Execute](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/execute-method-ado-command) method on a [Command](command-object-ado.md) or the [Open](open-method-ado-recordset.md) method on a **Recordset**, ADO executes only the first command and returns the results to *recordset*.</span></span> <span data-ttu-id="caa8d-121">若要访问语句中后续命令的结果，请调用 **NextRecordset** 方法。</span><span class="sxs-lookup"><span data-stu-id="caa8d-121">To access the results of subsequent commands in the statement, call the **NextRecordset** method.</span></span>

<span data-ttu-id="caa8d-122">只要存在其他结果，且包含复合语句的 **Recordset** 未断开连接或跨进程边界封送，则 **NextRecordset** 方法将继续返回 **Recordset** 对象。</span><span class="sxs-lookup"><span data-stu-id="caa8d-122">As long as there are additional results and the **Recordset** containing the compound statements is not disconnected or marshaled across process boundaries, the **NextRecordset** method will continue to return **Recordset** objects.</span></span> <span data-ttu-id="caa8d-123">如果返回行的命令成功执行但未返回记录，则返回的 **Recordset** 对象将打开，但为空。</span><span class="sxs-lookup"><span data-stu-id="caa8d-123">If a row-returning command executes successfully but returns no records, the returned **Recordset** object will be open but empty.</span></span> <span data-ttu-id="caa8d-124">可通过验证 [BOF](bof-eof-properties-ado.md) 和 [EOF](bof-eof-properties-ado.md) 属性是否都为 **True** 来测试该情况。</span><span class="sxs-lookup"><span data-stu-id="caa8d-124">Test for this case by verifying that the [BOF](bof-eof-properties-ado.md) and [EOF](bof-eof-properties-ado.md) properties are both **True**.</span></span> <span data-ttu-id="caa8d-125">如果非行返回命令执行成功，返回的**Recordset**对象将关闭，这可以验证通过测试在**Recordset**上的[状态](state-property-ado.md)属性。</span><span class="sxs-lookup"><span data-stu-id="caa8d-125">If a non–row-returning command executes successfully, the returned **Recordset** object will be closed, which you can verify by testing the [State](state-property-ado.md) property on the **Recordset**.</span></span> <span data-ttu-id="caa8d-126">当没有更多结果时， *recordset*将设置为*Nothing*。</span><span class="sxs-lookup"><span data-stu-id="caa8d-126">When there are no more results, *recordset* will be set to *Nothing*.</span></span>

<span data-ttu-id="caa8d-127">**NextRecordset** 方法对于断开连接的 **Recordset** 对象不可用，在该对象中， [ActiveConnection](activeconnection-property-ado.md) 已设置为 **Nothing** （用 Microsoft Visual Basic）或 NULL（用其他语言）。</span><span class="sxs-lookup"><span data-stu-id="caa8d-127">The **NextRecordset** method is not available on a disconnected **Recordset** object, where [ActiveConnection](activeconnection-property-ado.md) has been set to **Nothing** (in Microsoft Visual Basic) or NULL (in other languages).</span></span>

<span data-ttu-id="caa8d-128">如果正在进行编辑，且正处于即时更新模式下，则调用 **NextRecordset** 方法会生成错误；应首先调用 [Update](update-method-ado.md) 或 [CancelUpdate](cancelupdate-method-ado.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="caa8d-128">If an edit is in progress while in immediate update mode, calling the **NextRecordset** method generates an error; call the [Update](update-method-ado.md) or [CancelUpdate](cancelupdate-method-ado.md) method first.</span></span>

<span data-ttu-id="caa8d-p105">若要通过填充 [Parameters](parameters-collection-ado.md) 集合或通过使用原始的 **Open** 或 **Execute** 调用传递数组，在复合语句中传递多个命令的参数，这些参数在集合或数组中的顺序必须与它们各自的命令在命令系列中的顺序相同。读取输出参数值之前，必须完成所有结果的读取。</span><span class="sxs-lookup"><span data-stu-id="caa8d-p105">To pass parameters for more than one command in the compound statement by filling the [Parameters](parameters-collection-ado.md) collection, or by passing an array with the original **Open** or **Execute** call, the parameters must be in the same order in the collection or array as their respective commands in the command series. You must finish reading all the results before reading output parameter values.</span></span>

<span data-ttu-id="caa8d-p106">OLE DB 提供程序确定什么时候执行复合语句中的每个命令。例如，[Microsoft OLE DB Provider for SQL Server](microsoft-ole-db-provider-for-sql-server.md) 在收到复合语句时执行一批中的所有命令。调用 **NextRecordset** 时，将仅返回生成的 **Recordset** 。</span><span class="sxs-lookup"><span data-stu-id="caa8d-p106">Your OLE DB provider determines when each command command in a compound statement is executed. The [Microsoft OLE DB Provider for SQL Server](microsoft-ole-db-provider-for-sql-server.md), for example, executes all commands in a batch upon receiving the compound statement. The resulting **Recordsets** are simply returned when you call **NextRecordset**.</span></span>

<span data-ttu-id="caa8d-p107">但是，其他提供程序可能只有在调用 NextRecordset 之后才能执行语句中的下一个命令。对于这些提供程序，如果在单步执行整个命令语句之前显式关闭 **Recordset** 对象，ADO 将永远不会执行剩余的语句。</span><span class="sxs-lookup"><span data-stu-id="caa8d-p107">However, other providers may execute the next command in a statement only after NextRecordset is called. For these providers, if you explicitly close the **Recordset** object before stepping through the entire command statement, ADO never executes the remaining commands.</span></span>

