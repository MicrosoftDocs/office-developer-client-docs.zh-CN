---
title: Database.PopulatePartial 方法 (DAO)
TOCTitle: PopulatePartial Method
ms:assetid: fa3227a2-c961-6a98-32b3-5b6e5329a21d
ms:mtpsurl: https://msdn.microsoft.com/library/Ff837034(v=office.15)
ms:contentKeyID: 48548834
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1101186
f1_categories:
- Office.Version=v15
ms.openlocfilehash: e73724e8e27a622bbf96f4d9cc96bf4128dca42d
ms.sourcegitcommit: 1dd744993ecb4bed241ace874ad26edaef1778b8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/06/2018
ms.locfileid: "25998131"
---
# <a name="databasepopulatepartial-method-dao"></a><span data-ttu-id="05c2d-102">Database.PopulatePartial 方法 (DAO)</span><span class="sxs-lookup"><span data-stu-id="05c2d-102">Database.PopulatePartial method (DAO)</span></span>

<span data-ttu-id="05c2d-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="05c2d-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="05c2d-p101">将部分副本中的任何更改与完全副本同步，清除部分副本中的所有记录，然后根据当前副本筛选器重新填充部分副本。（仅适用于 Microsoft Access 数据库引擎数据库。）</span><span class="sxs-lookup"><span data-stu-id="05c2d-p101">Synchronizes any changes in a partial replica with the full replica, clears all records in the partial replica, and then repopulates the partial replica based on the current replica filters. (Microsoft Access database engine databases only.).</span></span>

## <a name="syntax"></a><span data-ttu-id="05c2d-106">语法</span><span class="sxs-lookup"><span data-stu-id="05c2d-106">Syntax</span></span>

<span data-ttu-id="05c2d-107">*表达式*。PopulatePartial (***DbPathName***)</span><span class="sxs-lookup"><span data-stu-id="05c2d-107">*expression* .PopulatePartial(***DbPathName***)</span></span>

<span data-ttu-id="05c2d-108">*表达式*一个代表**Database**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="05c2d-108">*expression* A variable that represents a **Database** object.</span></span>

## <a name="parameters"></a><span data-ttu-id="05c2d-109">参数</span><span class="sxs-lookup"><span data-stu-id="05c2d-109">Parameters</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="05c2d-110">名称</span><span class="sxs-lookup"><span data-stu-id="05c2d-110">Name</span></span></p></th>
<th><p><span data-ttu-id="05c2d-111">必需/可选</span><span class="sxs-lookup"><span data-stu-id="05c2d-111">Required/optional</span></span></p></th>
<th><p><span data-ttu-id="05c2d-112">数据类型</span><span class="sxs-lookup"><span data-stu-id="05c2d-112">Data type</span></span></p></th>
<th><p><span data-ttu-id="05c2d-113">说明</span><span class="sxs-lookup"><span data-stu-id="05c2d-113">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="05c2d-114"><em>DbPathName</em></span><span class="sxs-lookup"><span data-stu-id="05c2d-114"><em>DbPathName</em></span></span></p></td>
<td><p><span data-ttu-id="05c2d-115">必需</span><span class="sxs-lookup"><span data-stu-id="05c2d-115">Required</span></span></p></td>
<td><p><span data-ttu-id="05c2d-116"><strong>字符串</strong></span><span class="sxs-lookup"><span data-stu-id="05c2d-116"><strong>String</strong></span></span></p></td>
<td><p><span data-ttu-id="05c2d-117">要使用其中的数据填充记录的完全副本的路径和名称。</span><span class="sxs-lookup"><span data-stu-id="05c2d-117">The path and name of the full replica from which to populate records.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="05c2d-118">注解</span><span class="sxs-lookup"><span data-stu-id="05c2d-118">Remarks</span></span>

<span data-ttu-id="05c2d-119">当您将部分副本与完全副本同步时，有可能在部分副本中创建"孤立"的记录。</span><span class="sxs-lookup"><span data-stu-id="05c2d-119">When you synchronize a partial replica with a full replica, it is possible to create "orphaned" records in the partial replica.</span></span> <span data-ttu-id="05c2d-120">例如，假设客户表具有其**[ReplicaFilter](tabledef-replicafilter-property-dao.md)** 设置为"区域 = 'CA'"。</span><span class="sxs-lookup"><span data-stu-id="05c2d-120">For example, suppose you have a Customers table with its **[ReplicaFilter](tabledef-replicafilter-property-dao.md)** set to "Region = 'CA'".</span></span> <span data-ttu-id="05c2d-121">如果用户在部分副本中将客户的区域由 CA 更改为 NY，然后通过 **[Synchronize](database-synchronize-method-dao.md)** 方法发生同步，更改将传播到完全副本，但是部分副本中包含 NY 的记录会变为孤立的，因为它现在不满足副本筛选器条件。</span><span class="sxs-lookup"><span data-stu-id="05c2d-121">If a user changes a customer's region from CA to NY in the partial replica, and then a synchronization occurs via the **[Synchronize](database-synchronize-method-dao.md)** method, the change is propagated to the full replica but the record containing NY in the partial replica is orphaned because it now doesn't meet the replica filter criteria.</span></span>

<span data-ttu-id="05c2d-p103">若要解决孤立记录的问题，可以使用 **PopulatePartial** 方法。 **PopulatePartial** 方法类似于 **Synchronize** 方法，但是它将任何更改与完全副本同步，再删除部分副本中的所有记录，然后基于当前的副本筛选器重新填充部分副本。即使未更改副本筛选器， **PopulatePartial** 也始终清除部分副本中的所有记录，然后基于当前筛选器重新填充部分副本。</span><span class="sxs-lookup"><span data-stu-id="05c2d-p103">To solve the problem of orphaned records, you can use the **PopulatePartial** method. The **PopulatePartial** method is similar to the **Synchronize** method, but it synchronizes any changes with the full replica, removes all records in the partial replica, and then repopulates the partial replica based on the current replica filters. Even if your replica filters have not changed, **PopulatePartial** will always clear all records in the partial replica and repopulate it based on the current filters.</span></span>

<span data-ttu-id="05c2d-p104">一般而言，在创建部分副本时，以及无论何时更改副本筛选器时，都应该使用 **PopulatePartial** 方法。如果应用程序更改了副本筛选器，应遵循以下步骤：</span><span class="sxs-lookup"><span data-stu-id="05c2d-p104">Generally, you should use the **PopulatePartial** method when you create a partial replica and whenever you change your replica filters. If your application changes replica filters, you should follow these steps:</span></span>

1.  <span data-ttu-id="05c2d-127">将完全副本与其中更改了筛选器的部分副本同步。</span><span class="sxs-lookup"><span data-stu-id="05c2d-127">Synchronize your full replica with the partial replica in which the filters are being changed.</span></span>

2.  <span data-ttu-id="05c2d-128">使用 **ReplicaFilter** 和 **[PartialReplica](relation-partialreplica-property-dao.md)** 属性对副本筛选器执行所需的更改。</span><span class="sxs-lookup"><span data-stu-id="05c2d-128">Use the **ReplicaFilter** and **[PartialReplica](relation-partialreplica-property-dao.md)** properties to make the desired changes to the replica filter.</span></span>

3.  <span data-ttu-id="05c2d-129">调用 **PopulatePartial** 方法可从部分副本中删除所有记录，并从完全副本中传输符合新的副本筛选条件的所有记录。</span><span class="sxs-lookup"><span data-stu-id="05c2d-129">Call the **PopulatePartial** method to remove all records from the partial replica and transfer all records from the full replica that meet the new replica filter criteria.</span></span>

<span data-ttu-id="05c2d-130">如果副本筛选器已更改，并且在未首先调用 **PopulatePartial** 的情况下调用了 **Synchronize** 方法，则会发生可捕获的错误。</span><span class="sxs-lookup"><span data-stu-id="05c2d-130">If a replica filter has changed, and the **Synchronize** method is invoked without first invoking **PopulatePartial**, a trappable error occurs.</span></span>

<span data-ttu-id="05c2d-p105">只能对已打开以便进行独占访问的部分副本调用 **PopulatePartial** 方法。此外，不能从运行于部分副本自身内的代码调用 **PopulatePartial** 方法，而应当从完全副本或另一个数据库以独占方式打开部分副本，然后调用 **PopulatePartial**。</span><span class="sxs-lookup"><span data-stu-id="05c2d-p105">The **PopulatePartial** method can only be invoked on a partial replica that has been opened for exclusive access. Furthermore, you can't call the **PopulatePartial** method from code running within the partial replica itself. Instead, open the partial replica exclusively from the full replica or another database, then call **PopulatePartial**.</span></span>


> [!NOTE]
> <span data-ttu-id="05c2d-p106">[!注释] 尽管 **PopulatePartial** 在清除和重新填充部分副本之前执行单向同步，但是，最好是仍然在调用 **PopulatePartial** 之前调用 **Synchronize**。这是因为如果调用 **Synchronize** 失败，将发生可捕获的错误。可以使用此错误决定是否继续 **PopulatePartial** 方法（此方法将删除部分副本中的所有记录）。如果 **PopulatePartial** 由其自身调用，并且在同步记录时出错，则仍然会清除部分副本中的记录，这可能是不希望得到的结果。</span><span class="sxs-lookup"><span data-stu-id="05c2d-p106">Although **PopulatePartial** performs a one-way synchronization before clearing and repopulating the partial replica, it is still a good idea to call **Synchronize** before calling **PopulatePartial**. This is because if the call to **Synchronize** fails, a trappable error occurs. You can use this error to decide whether or not to proceed with the **PopulatePartial** method (which removes all records in the partial replica). If **PopulatePartial** is called by itself and an error occurs while records are being synchronized, records in the partial replica will still be cleared, which may not be the desired result.</span></span>



## <a name="example"></a><span data-ttu-id="05c2d-138">示例</span><span class="sxs-lookup"><span data-stu-id="05c2d-138">Example</span></span>

<span data-ttu-id="05c2d-139">以下示例在更改副本筛选器后使用 **PopulatePartial** 方法。</span><span class="sxs-lookup"><span data-stu-id="05c2d-139">The following example uses the **PopulatePartial** method after changing a replica filter.</span></span>

```vb 
Sub PopulatePartialX() 
 
 Dim tdfCustomers As TableDef 
 Dim strFilter As String 
 Dim dbsTemp As Database 
 
 ' Open the partial replica in exclusive mode. 
 Set dbsTemp = OpenDatabase("F:\SALES\FY96CA.MDB", True) 
 
 With dbsTemp 
 Set tdfCustomers = .TableDefs("Customers") 
 
 ' Synchronize with full replica 
 ' before setting replica filter. 
 .Synchronize "C:\SALES\FY96.MDB" 
 
 strFilter = "Region = 'CA'" 
 tdfCustomers.ReplicaFilter = strFilter 
 
 ' Populate records from the full replica. 
 .PopulatePartial "C:\SALES\FY96.MDB" 
 
 .Close 
 End With 
 
End Sub 
 
```

