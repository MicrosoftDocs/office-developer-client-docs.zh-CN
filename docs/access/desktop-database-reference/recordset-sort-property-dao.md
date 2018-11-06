---
title: Recordset.Sort 属性 (DAO)
TOCTitle: Sort Property
ms:assetid: 9be9bf62-f713-537e-4df0-3a54d485a523
ms:mtpsurl: https://msdn.microsoft.com/library/Ff198077(v=office.15)
ms:contentKeyID: 48546582
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1053063
f1_categories:
- Office.Version=v15
ms.openlocfilehash: b8dc3c551c9aa75da205717fef682f0abed7a54b
ms.sourcegitcommit: 1dd744993ecb4bed241ace874ad26edaef1778b8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/06/2018
ms.locfileid: "25998726"
---
# <a name="recordsetsort-property-dao"></a><span data-ttu-id="9cb2a-102">Recordset.Sort 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="9cb2a-102">Recordset.Sort property (DAO)</span></span>

<span data-ttu-id="9cb2a-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="9cb2a-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="9cb2a-104">设置或返回 **[Recordset](recordset-object-dao.md)** 对象中的记录的排序次序（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="9cb2a-104">Sets or returns the sort order for records in a **[Recordset](recordset-object-dao.md)** object (Microsoft Access workspaces only).</span></span>

## <a name="syntax"></a><span data-ttu-id="9cb2a-105">语法</span><span class="sxs-lookup"><span data-stu-id="9cb2a-105">Syntax</span></span>

<span data-ttu-id="9cb2a-106">*表达式*。排序</span><span class="sxs-lookup"><span data-stu-id="9cb2a-106">*expression* .Sort</span></span>

<span data-ttu-id="9cb2a-107">*表达式*一个表示**Recordset**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="9cb2a-107">*expression* A variable that represents a **Recordset** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="9cb2a-108">备注</span><span class="sxs-lookup"><span data-stu-id="9cb2a-108">Remarks</span></span>

<span data-ttu-id="9cb2a-109">您可以使用**Sort**属性与动态集类型和快照 – 类型的**Recordset**对象。</span><span class="sxs-lookup"><span data-stu-id="9cb2a-109">You can use the **Sort** property with dynaset– and snapshot–type **Recordset** objects.</span></span>

<span data-ttu-id="9cb2a-p101">如果为某对象设置了该属性，当从该对象创建后续 **Recordset** 对象时会进行排序。 **Sort** 属性设置重写为 **[QueryDef](querydef-object-dao.md)** 对象指定的任何排序次序。</span><span class="sxs-lookup"><span data-stu-id="9cb2a-p101">When you set this property for an object, sorting occurs when a subsequent **Recordset** object is created from that object. The **Sort** property setting overrides any sort order specified for a **[QueryDef](querydef-object-dao.md)** object.</span></span>

<span data-ttu-id="9cb2a-112">默认的排序次序是升序（A 到 Z，0 到 100）。</span><span class="sxs-lookup"><span data-stu-id="9cb2a-112">The default sort order is ascending (A to Z or 0 to 100).</span></span>

<span data-ttu-id="9cb2a-113">**Sort**属性不适用于为表 – 或向前仅类型的**Recordset**对象。</span><span class="sxs-lookup"><span data-stu-id="9cb2a-113">The **Sort** property doesn't apply to table– or forward–only–type **Recordset** objects.</span></span> <span data-ttu-id="9cb2a-114">若要对表类型**Recordset**对象进行排序，使用的**[索引](recordset-index-property-dao.md)** 属性。</span><span class="sxs-lookup"><span data-stu-id="9cb2a-114">To sort a table–type **Recordset** object, use the **[Index](recordset-index-property-dao.md)** property.</span></span>

> [!NOTE]
> <span data-ttu-id="9cb2a-115">[!注释] 在许多情况下，使用包含排序条件的 SQL 语句打开新的 **Recordset** 对象会快一些。</span><span class="sxs-lookup"><span data-stu-id="9cb2a-115">In many cases, it's faster to open a new **Recordset** object by using an SQL statement that includes the sorting criteria.</span></span>

## <a name="example"></a><span data-ttu-id="9cb2a-116">示例</span><span class="sxs-lookup"><span data-stu-id="9cb2a-116">Example</span></span>

<span data-ttu-id="9cb2a-p103">以下示例通过更改 **Sort** 属性的值和创建新的 **Recordset** 来演示该属性。若要使该过程运行，需要 SortOutput 函数。</span><span class="sxs-lookup"><span data-stu-id="9cb2a-p103">This example demonstrates the **Sort** property by changing its value and creating a new **Recordset**. The SortOutput function is required for this procedure to run.</span></span>

```vb
    Sub SortX() 
     
     Dim dbsNorthwind As Database 
     Dim rstEmployees As Recordset 
     Dim rstSortEmployees As Recordset 
     
     Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
     Set rstEmployees = _ 
     dbsNorthwind.OpenRecordset("Employees", _ 
     dbOpenDynaset) 
     
     With rstEmployees 
     SortOutput "Original Recordset:", rstEmployees 
     .Sort = "LastName, FirstName" 
     ' Print report showing Sort property and record order. 
     SortOutput _ 
     "Recordset after changing Sort property:", _ 
     rstEmployees 
     ' Open new Recordset from current one. 
     Set rstSortEmployees = .OpenRecordset 
     ' Print report showing Sort property and record order. 
     SortOutput "New Recordset:", rstSortEmployees 
     rstSortEmployees.Close 
     .Close 
     End With 
     
     dbsNorthwind.Close 
     
    End Sub 
     
    Function SortOutput(strTemp As String, _ 
     rstTemp As Recordset) 
     
     With rstTemp 
     Debug.Print strTemp 
     Debug.Print " Sort = " & _ 
     IIf(.Sort <> "", .Sort, "[Empty]") 
     .MoveFirst 
     
     ' Enumerate Recordset. 
     Do While Not .EOF 
     Debug.Print " " & !LastName & _ 
     ", " & !FirstName 
     .MoveNext 
     Loop 
     
     End With 
     
    End Function 
```

<br/>

<span data-ttu-id="9cb2a-p104">如果知道要选择的数据，通过 SQL 语句创建 **Recordset** 通常效率更高。以下示例演示如何仅创建一个 **Recordset** 并获取与上例一样的结果。</span><span class="sxs-lookup"><span data-stu-id="9cb2a-p104">When you know the data you want to select, it's usually more efficient to create a **Recordset** with an SQL statement. This example shows how you can create just one **Recordset** and obtain the same results as in the preceding example.</span></span>

```vb
    Sub SortX2() 
     
     Dim dbsNorthwind As Database 
     Dim rstEmployees As Recordset 
     
     Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
     ' Open a Recordset from an SQL statement that specifies a 
     ' sort order. 
     Set rstEmployees = _ 
     dbsNorthwind.OpenRecordset("SELECT * " & _ 
     "FROM Employees ORDER BY LastName, FirstName", _ 
     dbOpenDynaset) 
     
     dbsNorthwind.Close 
     
    End Sub
```
