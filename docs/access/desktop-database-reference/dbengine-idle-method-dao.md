---
title: DBEngine.Idle 方法 (DAO)
TOCTitle: Idle Method
ms:assetid: c90b565e-626e-139d-102a-0386601ce0c8
ms:mtpsurl: https://msdn.microsoft.com/library/Ff823202(v=office.15)
ms:contentKeyID: 48547666
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1052978
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: 7a84e3cc4b35886a12b2e6b4cf92b7483fea293a
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28705111"
---
# <a name="dbengineidle-method-dao"></a><span data-ttu-id="62e04-102">DBEngine.Idle 方法 (DAO)</span><span class="sxs-lookup"><span data-stu-id="62e04-102">DBEngine.Idle method (DAO)</span></span>

<span data-ttu-id="62e04-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="62e04-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="62e04-104">挂起数据处理，使 Microsoft Access 数据库引擎完成任何待定任务，例如内存优化或页面超时（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="62e04-104">Suspends data processing, enabling the Microsoft Access database engine to complete any pending tasks, such as memory optimization or page timeouts (Microsoft Access workspaces only).</span></span>

## <a name="syntax"></a><span data-ttu-id="62e04-105">语法</span><span class="sxs-lookup"><span data-stu-id="62e04-105">Syntax</span></span>

<span data-ttu-id="62e04-106">*表达式*。空闲 （***操作***）</span><span class="sxs-lookup"><span data-stu-id="62e04-106">*expression* .Idle(***Action***)</span></span>

<span data-ttu-id="62e04-107">*表达式*一个代表**DBEngine**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="62e04-107">*expression* A variable that represents a **DBEngine** object.</span></span>

## <a name="parameters"></a><span data-ttu-id="62e04-108">Parameters</span><span class="sxs-lookup"><span data-stu-id="62e04-108">Parameters</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="62e04-109">Name</span><span class="sxs-lookup"><span data-stu-id="62e04-109">Name</span></span></p></th>
<th><p><span data-ttu-id="62e04-110">必需/可选</span><span class="sxs-lookup"><span data-stu-id="62e04-110">Required/optional</span></span></p></th>
<th><p><span data-ttu-id="62e04-111">数据类型</span><span class="sxs-lookup"><span data-stu-id="62e04-111">Data type</span></span></p></th>
<th><p><span data-ttu-id="62e04-112">说明</span><span class="sxs-lookup"><span data-stu-id="62e04-112">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="62e04-113"><em>Action</em></span><span class="sxs-lookup"><span data-stu-id="62e04-113"><em>Action</em></span></span></p></td>
<td><p><span data-ttu-id="62e04-114">可选</span><span class="sxs-lookup"><span data-stu-id="62e04-114">Optional</span></span></p></td>
<td><p><span data-ttu-id="62e04-115"><strong>Variant</strong></span><span class="sxs-lookup"><span data-stu-id="62e04-115"><strong>Variant</strong></span></span></p></td>
<td><p><span data-ttu-id="62e04-p101">指定要执行的操作。可以是 <strong><a href="idleenum-enumeration-dao.md">IdleEnum</a></strong> 常量之一。</span><span class="sxs-lookup"><span data-stu-id="62e04-p101">Specifies the action to take. Can be one of the <strong><a href="idleenum-enumeration-dao.md">IdleEnum</a></strong> constants.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="62e04-118">注解</span><span class="sxs-lookup"><span data-stu-id="62e04-118">Remarks</span></span>

<span data-ttu-id="62e04-p102">**Idle** 方法允许 Microsoft Access 数据库引擎执行由于密集的数据处理而不再处于最新状态的后台任务。在多用户、多任务环境中，由于没有足够的后台处理时间使 **[Recordset](recordset-object-dao.md)** 中的所有记录成为当前状态，因此这种情况经常出现。</span><span class="sxs-lookup"><span data-stu-id="62e04-p102">The **Idle** method allows the Microsoft Access database engine to perform background tasks that may not be up-to-date because of intense data processing. This is often true in multiuser, multitasking environments that don't have enough background processing time to keep all records in a **[Recordset](recordset-object-dao.md)** current.</span></span>

<span data-ttu-id="62e04-p103">通常，仅当没有其他操作（包括鼠标移动）发生时，才会取消读取锁定，并更新本地动态集类型 **Recordset** 对象中的数据。如果定期使用 **Idle** 方法，Microsoft Access 数据库引擎可通过解除不需要的读取锁定来结束后台处理任务。</span><span class="sxs-lookup"><span data-stu-id="62e04-p103">Usually, read locks are removed and data in local dynaset-type **Recordset** objects are updated only when no other actions (including mouse movements) occur. If you periodically use the **Idle** method, the Microsoft Access database engine can catch up on background processing tasks by releasing unneeded read locks.</span></span>

<span data-ttu-id="62e04-123">如果指定可选的 **dbRefreshCache** 参数，将只使用数据库中的最新数据刷新内存。</span><span class="sxs-lookup"><span data-stu-id="62e04-123">Specifying the optional **dbRefreshCache** argument refreshes memory with only the most current data from the database.</span></span>

<span data-ttu-id="62e04-p104">在单一用户环境中，除非应用程序的多个实例正在运行，否则不需要使用此方法。在多用户环境中， **Idle** 方法可提高性能，因为它会强制数据库引擎将数据写入磁盘，同时解除内存的锁定。</span><span class="sxs-lookup"><span data-stu-id="62e04-p104">You don't need to use this method in single-user environments unless multiple instances of an application are running. The **Idle** method may increase performance in a multiuser environment because it forces the database engine to write data to disk, releasing locks on memory.</span></span>


> [!NOTE]
> <span data-ttu-id="62e04-126">[!注释] 还可以通过将操作指定为事务处理的一部分来解除读取锁定。</span><span class="sxs-lookup"><span data-stu-id="62e04-126">You can also release read locks by making operations part of a transaction.</span></span>

## <a name="example"></a><span data-ttu-id="62e04-127">示例</span><span class="sxs-lookup"><span data-stu-id="62e04-127">Example</span></span>

<span data-ttu-id="62e04-p105">以下示例使用 **Idle** 方法确保输出过程访问数据库中可用的最新数据。若要使该过程运行，需要使用 IdleOutput 过程。</span><span class="sxs-lookup"><span data-stu-id="62e04-p105">This example uses the **Idle** method to ensure that an output procedure is accessing the most current data available from the database. The IdleOutput procedure is required for this procedure to run.</span></span>

```vb 
Sub IdleX() 
 
 Dim dbsNorthwind As Database 
 Dim strCountry As String 
 Dim strSQL As String 
 Dim rstOrders As Recordset 
 
 Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
 
 ' Get name of country from user and build SQL statement 
 ' with it. 
 strCountry = Trim(InputBox("Enter country:")) 
 strSQL = "SELECT * FROM Orders WHERE ShipCountry = '" & _ 
 strCountry & "' ORDER BY OrderID" 
 
 ' Open Recordset object with SQL statement. 
 Set rstOrders = dbsNorthwind.OpenRecordset(strSQL) 
 
 ' Display contents of Recordset object. 
 IdleOutput rstOrders, strCountry 
 
 rstOrders.Close 
 dbsNorthwind.Close 
 
End Sub 
 
Sub IdleOutput(rstTemp As Recordset, strTemp As String) 
 
 ' Call the Idle method to release unneeded locks, force 
 ' pending writes, and refresh the memory with the current 
 ' data in the .mdb file. 
 DBEngine.Idle dbRefreshCache 
 
 ' Enumerate the Recordset object. 
 With rstTemp 
 Debug.Print "Orders from " & strTemp & ":" 
 Debug.Print , "OrderID", "CustomerID", "OrderDate" 
 Do While Not .EOF 
 Debug.Print , !OrderID, !CustomerID, !OrderDate 
 .MoveNext 
 Loop 
 End With 
 
End Sub 
 
```

