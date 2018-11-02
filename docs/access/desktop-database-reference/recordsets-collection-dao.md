---
title: Recordsets 集合 (DAO)
TOCTitle: Recordsets Collection
ms:assetid: 246d9a78-4ce8-6393-982b-77ac00cd85bb
ms:mtpsurl: https://msdn.microsoft.com/library/Ff191819(v=office.15)
ms:contentKeyID: 48543756
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 1b32ef33205e23656e7bcb86d7384876e4c404c1
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25924524"
---
# <a name="recordsets-collection-dao"></a><span data-ttu-id="95476-102">Recordsets 集合 (DAO)</span><span class="sxs-lookup"><span data-stu-id="95476-102">Recordsets collection (DAO)</span></span>

<span data-ttu-id="95476-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="95476-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="95476-104">**Recordsets** 集合包含 **Connection** 或 **Database** 对象中所有打开的 **Recordset** 对象。</span><span class="sxs-lookup"><span data-stu-id="95476-104">A **Recordsets** collection contains all open **Recordset** objects in a **Connection** or **Database** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="95476-105">注解</span><span class="sxs-lookup"><span data-stu-id="95476-105">Remarks</span></span>

<span data-ttu-id="95476-106">使用 DAO 对象时，几乎可以完全使用 **Recordset** 对象来处理数据。</span><span class="sxs-lookup"><span data-stu-id="95476-106">When you use DAO objects, you manipulate data almost entirely using **Recordset** objects.</span></span>

<span data-ttu-id="95476-107">打开 **Recordset** 对象时，会自动在 **Recordsets** 集合中添加一个新的 **Recordset** 对象；关闭该对象时，会自动删除该对象。</span><span class="sxs-lookup"><span data-stu-id="95476-107">A new **Recordset** object is automatically added to the **Recordsets** collection when you open the **Recordset** object, and is automatically removed when you close it.</span></span>

<span data-ttu-id="95476-p101">可根据需要创建任意数目的 **Recordset** 对象变量。不同的 **Recordset** 对象可以在不发生冲突的情况下访问相同的表、查询和字段。</span><span class="sxs-lookup"><span data-stu-id="95476-p101">You can create as many **Recordset** object variables as needed. Different **Recordset** objects can access the same tables, queries, and fields without conflicting.</span></span>

<span data-ttu-id="95476-110">若要按照序号或 **Name** 属性设置来引用集合中的 **Recordset** 对象，可以使用下列任何一种语法形式：</span><span class="sxs-lookup"><span data-stu-id="95476-110">To refer to a **Recordset** object in a collection by its ordinal number or by its **Name** property setting, use any of the following syntax forms:</span></span>

- <span data-ttu-id="95476-111">**Recordsets**(0)</span><span class="sxs-lookup"><span data-stu-id="95476-111">**Recordsets**(0)</span></span>

- <span data-ttu-id="95476-112">**记录集**("name")</span><span class="sxs-lookup"><span data-stu-id="95476-112">**Recordsets**("name")</span></span>

- <span data-ttu-id="95476-113">**记录集**\!\[名称\]</span><span class="sxs-lookup"><span data-stu-id="95476-113">**Recordsets**\!\[name\]</span></span>

> [!NOTE]
> <span data-ttu-id="95476-p102">[!注释] 可以多次打开同一个数据源或数据库中的 **Recordset** 对象，并在 **Recordsets** 集合中创建重复的名称。应该将 **Recordset** 对象分配给对象变量，并通过变量名来引用它们。</span><span class="sxs-lookup"><span data-stu-id="95476-p102">You can open a **Recordset** object from the same data source or database more than once, creating duplicate names in the **Recordsets** collection. You should assign **Recordset** objects to object variables and refer to them by variable name.</span></span>

## <a name="example"></a><span data-ttu-id="95476-116">示例</span><span class="sxs-lookup"><span data-stu-id="95476-116">Example</span></span>

<span data-ttu-id="95476-117">以下示例通过打开四个不同类型的 **Recordsets**，枚举当前 **Database** 的 Recordsets 集合，以及枚举每个 **Recordset** 的 **Properties** 集合，演示 **Recordset** 对象和 **Recordsets** 集合。</span><span class="sxs-lookup"><span data-stu-id="95476-117">This example demonstrates **Recordset** objects and the **Recordsets** collection by opening four different types of **Recordsets**, enumerating the Recordsets collection of the current **Database**, and enumerating the **Properties** collection of each **Recordset**.</span></span>

```vb
    Sub RecordsetX() 
     
     Dim dbsNorthwind As Database 
     Dim rstTable As Recordset 
     Dim rstDynaset As Recordset 
     Dim rstSnapshot As Recordset 
     Dim rstForwardOnly As Recordset 
     Dim rstLoop As Recordset 
     Dim prpLoop As Property 
     
     Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
     
     With dbsNorthwind 
     
     ' Open one of each type of Recordset object. 
     Set rstTable = .OpenRecordset("Categories", _ 
     dbOpenTable) 
     Set rstDynaset = .OpenRecordset("Employees", _ 
     dbOpenDynaset) 
     Set rstSnapshot = .OpenRecordset("Shippers", _ 
     dbOpenSnapshot) 
     Set rstForwardOnly = .OpenRecordset _ 
     ("Employees", dbOpenForwardOnly) 
     
     Debug.Print "Recordsets in Recordsets " & _ 
     "collection of dbsNorthwind" 
     
     ' Enumerate Recordsets collection. 
     For Each rstLoop In .Recordsets 
     
     With rstLoop 
     Debug.Print " " & .Name 
     
     ' Enumerate Properties collection of each 
     ' Recordset object. Trap for any 
     ' properties whose values are invalid in 
     ' this context. 
     For Each prpLoop In .Properties 
     On Error Resume Next 
     If prpLoop <> "" Then Debug.Print _ 
     " " & prpLoop.Name & _ 
     " = " & prpLoop 
     On Error GoTo 0 
     Next prpLoop 
     
     End With 
     
     Next rstLoop 
     
     rstTable.Close 
     rstDynaset.Close 
     rstSnapshot.Close 
     rstForwardOnly.Close 
     
     .Close 
     End With 
     
    End Sub
```
