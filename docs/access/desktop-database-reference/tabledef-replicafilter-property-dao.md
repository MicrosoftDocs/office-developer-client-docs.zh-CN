---
title: TableDef.ReplicaFilter 属性 (DAO)
TOCTitle: ReplicaFilter Property
ms:assetid: f44273de-2b6a-750f-cb7c-12c3ac2da503
ms:mtpsurl: https://msdn.microsoft.com/library/Ff836681(v=office.15)
ms:contentKeyID: 48548683
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1055548
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: ba296701faebb32696741a742b7fe01660b74c46
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28722429"
---
# <a name="tabledefreplicafilter-property-dao"></a><span data-ttu-id="9bc8d-102">TableDef.ReplicaFilter 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="9bc8d-102">TableDef.ReplicaFilter property (DAO)</span></span>

<span data-ttu-id="9bc8d-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="9bc8d-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="9bc8d-p101">设置或返回部分副本中的 **[TableDef](tabledef-object-dao.md)** 对象中的一个值，用于指示哪部分记录从完全副本复制到该表中（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="9bc8d-p101">Sets or returns a value on a **[TableDef](tabledef-object-dao.md)** object within a partial replica that indicates which subset of records is replicated to that table from a full replica. (Microsoft Access workspaces only).</span></span>

## <a name="syntax"></a><span data-ttu-id="9bc8d-106">语法</span><span class="sxs-lookup"><span data-stu-id="9bc8d-106">Syntax</span></span>

<span data-ttu-id="9bc8d-107">*表达式*。ReplicaFilter</span><span class="sxs-lookup"><span data-stu-id="9bc8d-107">*expression* .ReplicaFilter</span></span>

<span data-ttu-id="9bc8d-108">*表达式*一个代表**TableDef**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="9bc8d-108">*expression* A variable that represents a **TableDef** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="9bc8d-109">注解</span><span class="sxs-lookup"><span data-stu-id="9bc8d-109">Remarks</span></span>

<span data-ttu-id="9bc8d-110">设置或返回值是一个 **String** 或 **Boolean**，用于指示复制了哪部分记录，如下表所示：</span><span class="sxs-lookup"><span data-stu-id="9bc8d-110">The setting or return value is a **String** or **Boolean** that indicates which subset of records is replicated, as specified in the following table:</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="9bc8d-111">值</span><span class="sxs-lookup"><span data-stu-id="9bc8d-111">Value</span></span></p></th>
<th><p><span data-ttu-id="9bc8d-112">说明</span><span class="sxs-lookup"><span data-stu-id="9bc8d-112">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9bc8d-113">字符串</span><span class="sxs-lookup"><span data-stu-id="9bc8d-113">A string</span></span></p></td>
<td><p><span data-ttu-id="9bc8d-114">为了从完全副本中复制，部分副本表中的记录所必须满足的条件。</span><span class="sxs-lookup"><span data-stu-id="9bc8d-114">A criteria that a record in the partial replica table must satisfy in order to be replicated from the full replica.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9bc8d-115"><strong>True</strong></span><span class="sxs-lookup"><span data-stu-id="9bc8d-115"><strong>True</strong></span></span></p></td>
<td><p><span data-ttu-id="9bc8d-116">复制所有记录。</span><span class="sxs-lookup"><span data-stu-id="9bc8d-116">Replicates all records.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9bc8d-117"><strong>False</strong></span><span class="sxs-lookup"><span data-stu-id="9bc8d-117"><strong>False</strong></span></span></p></td>
<td><p><span data-ttu-id="9bc8d-118">（默认）不复制任何记录。</span><span class="sxs-lookup"><span data-stu-id="9bc8d-118">(Default) Doesn't replicate any records.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="9bc8d-119">该属性类似于 SQL WHERE 语句（不含 WHERE 一词），但是不能在条件中指定子查询、聚合函数（如 **Count**）或用户定义的函数。</span><span class="sxs-lookup"><span data-stu-id="9bc8d-119">This property is similar to an SQL WHERE clause (without the word WHERE), but you cannot specify subqueries, aggregate functions (such as **Count**), or user-defined functions within the criteria.</span></span>

<span data-ttu-id="9bc8d-p102">只能在完全副本与部分副本之间同步数据。不能在两个部分副本之间同步数据。另外，对于部分复制，您可以设置关于复制哪些记录的限制，但是不能指出复制哪些字段。</span><span class="sxs-lookup"><span data-stu-id="9bc8d-p102">You can only synchronize data between a full replica and a partial replica. You can't synchronize data between two partial replicas. Also, with partial replication you can set restrictions on which records are replicated, but you can't indicate which fields are replicated.</span></span>

<span data-ttu-id="9bc8d-p103">通常，在想要复制另一组记录时重置副本筛选器。例如，当一个销售代表临时接替另一个销售代表所负责的区域时，数据库应用程序可以临时复制这两个区域的数据，然后恢复使用上一个筛选器。在这种情况下，应用程序重置 **ReplicaFilter** 属性，然后重新填充部分副本。</span><span class="sxs-lookup"><span data-stu-id="9bc8d-p103">Usually, you reset a replica filter when you want to replicate a different set of records. For example, when a sales representative temporarily takes over another sales representative's region, the database application can temporarily replicate data for both regions and then return to the previous filter. In this scenario, the application resets the **ReplicaFilter** property and then repopulates the partial replica.</span></span>

<span data-ttu-id="9bc8d-126">如果应用程序更改了副本筛选器，您应当执行下列步骤：</span><span class="sxs-lookup"><span data-stu-id="9bc8d-126">If your application changes replica filters, you should follow these steps:</span></span>

1.  <span data-ttu-id="9bc8d-127">使用 **[Synchronize](database-synchronize-method-dao.md)** 方法将完全副本与更改了筛选器的部分副本同步。</span><span class="sxs-lookup"><span data-stu-id="9bc8d-127">Use the **[Synchronize](database-synchronize-method-dao.md)** method to synchronize your full replica with the partial replica in which the filters are being changed.</span></span>

2.  <span data-ttu-id="9bc8d-128">使用 **ReplicaFilter** 属性对副本筛选器进行必要的更改。</span><span class="sxs-lookup"><span data-stu-id="9bc8d-128">Use the **ReplicaFilter** property to make the desired changes to the replica filter.</span></span>

3.  <span data-ttu-id="9bc8d-129">使用 **[PopulatePartial](database-populatepartial-method-dao.md)** 方法删除部分副本中的所有记录，然后从完全副本传输所有符合新副本筛选条件的记录。</span><span class="sxs-lookup"><span data-stu-id="9bc8d-129">Use the **[PopulatePartial](database-populatepartial-method-dao.md)** method to remove all records from the partial replica and transfer all records from the full replica that meet the new replica filter criteria.</span></span>

<span data-ttu-id="9bc8d-p104">若要删除筛选器，请将 **ReplicaFilter** 属性设置为 **False**。如果删除所有筛选器并调用 **PopulatePartial** 方法，则部分副本中的所有已复制表中都不会显示任何记录。</span><span class="sxs-lookup"><span data-stu-id="9bc8d-p104">To remove a filter, set the **ReplicaFilter** property to **False**. If you remove all filters and invoke the **PopulatePartial** method, no records will appear in any replicated tables in the partial replica.</span></span>

> [!NOTE]
> <span data-ttu-id="9bc8d-132">[!注释] 如果副本筛选器已更改，并且在未首先调用 **PopulatePartial** 的情况下调用了 **Synchronize** 方法，则会发生可捕获的错误。</span><span class="sxs-lookup"><span data-stu-id="9bc8d-132">If a replica filter has changed, and the **Synchronize** method is invoked without first invoking **PopulatePartial**, a trappable error occurs.</span></span>

## <a name="example"></a><span data-ttu-id="9bc8d-133">示例</span><span class="sxs-lookup"><span data-stu-id="9bc8d-133">Example</span></span>

<span data-ttu-id="9bc8d-134">以下示例使用 **ReplicaFilter** 属性来仅复制加利福尼亚地区的客户记录。</span><span class="sxs-lookup"><span data-stu-id="9bc8d-134">The following example uses the **ReplicaFilter** property to replicate only customer records from the California region.</span></span>

```vb 
Sub ReplicaFilterX() 
 
 ' This example assumes the current open database 
 ' is the replica. 
 Dim tdfCustomers As TableDef 
 Dim strFilter As String 
 Dim dbsTemp As Database 
 
 Set dbsTemp = OpenDatabase("Northwind.mdb") 
 Set tdfCustomers = dbsTemp.TableDefs("Customers") 
 
 ' Synchronize with full replica 
 ' before setting replica filter. 
 dbsTemp.Synchronize "C:\SALES\FY96.MDB" 
 
 strFilter = "Region = 'CA'" 
 tdfCustomers.ReplicaFilter = strFilter 
 dbsTemp.PopulatePartial "C:\SALES\FY96.MDB" 
 
 ' Now remove the replica filter (for example purposes 
 ' only). 
 tdfCustomers.ReplicaFilter = False 
 ' Repopulate the database. 
 dbsTemp.PopulatePartial "C:\SALES\DATA96.MDB" 
 
End Sub 
 
```

