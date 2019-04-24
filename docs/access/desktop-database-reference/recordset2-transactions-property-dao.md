---
title: Recordset2 属性 (DAO)
TOCTitle: Transactions Property
ms:assetid: f2169565-f782-4089-0e4b-bc5d58d37db5
ms:mtpsurl: https://msdn.microsoft.com/library/Ff836614(v=office.15)
ms:contentKeyID: 48548642
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 58610ee87e61a8b342955107c2ba2b690e610c8b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32309239"
---
# <a name="recordset2transactions-property-dao"></a><span data-ttu-id="c85b3-102">Recordset2 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="c85b3-102">Recordset2.Transactions property (DAO)</span></span>


<span data-ttu-id="c85b3-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="c85b3-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="c85b3-104">返回一个值，该值指示对象是否支持事务。</span><span class="sxs-lookup"><span data-stu-id="c85b3-104">Returns a value that indicates whether an object supports transactions.</span></span> <span data-ttu-id="c85b3-105">只读 **Boolean** 类型。</span><span class="sxs-lookup"><span data-stu-id="c85b3-105">Read-only **Boolean**.</span></span>

## <a name="syntax"></a><span data-ttu-id="c85b3-106">语法</span><span class="sxs-lookup"><span data-stu-id="c85b3-106">Syntax</span></span>

<span data-ttu-id="c85b3-107">*表达式*。处理</span><span class="sxs-lookup"><span data-stu-id="c85b3-107">*expression* .Transactions</span></span>

<span data-ttu-id="c85b3-108">*表达式*一个代表**Recordset2**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="c85b3-108">*expression* A variable that represents a **Recordset2** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="c85b3-109">注解</span><span class="sxs-lookup"><span data-stu-id="c85b3-109">Remarks</span></span>

<span data-ttu-id="c85b3-110">在 Microsoft Access 工作区中，也可以将 **Transactions** 属性用于动态集类型或表类型的 **Recordset** 对象。</span><span class="sxs-lookup"><span data-stu-id="c85b3-110">In a Microsoft Access workspace, you can also use the **Transactions** property with dynaset- or table-type **Recordset** objects.</span></span> <span data-ttu-id="c85b3-111">仅快照类型和仅向前类型的**[Recordset](recordset-object-dao.md)** 对象始终返回**False**。</span><span class="sxs-lookup"><span data-stu-id="c85b3-111">Snapshot- and forward–only–type **[Recordset](recordset-object-dao.md)** objects always return **False**.</span></span>

<span data-ttu-id="c85b3-p103">如果动态集类型或表类型的 **Recordset** 基于 Microsoft Access 数据库引擎表，则 **Transactions** 属性为 **True** 且您可以使用事务。其他数据库引擎可能不支持事务。例如，不能在基于 Paradox 表的动态集类型 **Recordset** 对象中使用事务。</span><span class="sxs-lookup"><span data-stu-id="c85b3-p103">If a dynaset- or table-type **Recordset** is based on a Microsoft Access database engine table, the **Transactions** property is **True** and you can use transactions. Other database engines may not support transactions. For example, you can't use transactions in a dynaset-type **Recordset** object based on a Paradox table.</span></span>

<span data-ttu-id="c85b3-p104">在对 **Recordset** 对象的 **[Workspace](dbengine-begintrans-method-dao.md)** 对象使用 [**BeginTrans**](workspace-object-dao.md) 方法之前，检查 **Transactions** 属性，以确保支持事务。对不受支持的对象使用 **BeginTrans**、 **CommitTrans** 或 **Rollback** 方法没有效果。</span><span class="sxs-lookup"><span data-stu-id="c85b3-p104">Check the **Transactions** property before using the **[BeginTrans](dbengine-begintrans-method-dao.md)** method on the **Recordset** object's **[Workspace](workspace-object-dao.md)** object to make sure that transactions are supported. Using the **BeginTrans**, **CommitTrans**, or **Rollback** methods on an unsupported object has no effect.</span></span>

## <a name="example"></a><span data-ttu-id="c85b3-117">示例</span><span class="sxs-lookup"><span data-stu-id="c85b3-117">Example</span></span>

<span data-ttu-id="c85b3-118">以下示例在 Microsoft Access 工作区中演示 **Transactions** 属性。</span><span class="sxs-lookup"><span data-stu-id="c85b3-118">This example demonstrates the **Transactions** property in Microsoft Access workspaces.</span></span>

```vb 
Sub TransactionsX() 
 
 Dim wrkAcc As Workspace 
 Dim dbsNorthwind As Database 
 Dim conPubs As Connection 
 Dim rstTemp As Recordset 
 
 Set wrkAcc = CreateWorkspace("", "admin", "", dbUseJet) 
 Set dbsNorthwind = wrkAcc.OpenDatabase("Northwind.mdb") 
 
 ' Open two different Recordset objects and display the 
 ' Transactions property of each. 
 
 Debug.Print "Opening Microsoft Access table-type " & _ 
 "recordset..." 
 Set rstTemp = dbsNorthwind.OpenRecordset( _ 
 "Employees", dbOpenTable) 
 Debug.Print " Transactions = " & rstTemp.Transactions 
 
 Debug.Print "Opening forward-only-type " & _ 
 "recordset where the source is an SQL statement..." 
 Set rstTemp = dbsNorthwind.OpenRecordset( _ 
 "SELECT * FROM Employees", dbOpenForwardOnly) 
 Debug.Print " Transactions = " & rstTemp.Transactions 
 
 rstTemp.Close 
 dbsNorthwind.Close 
 conPubs.Close 
 wrkAcc.Close 
End Sub 
 
```

