---
title: Relation.PartialReplica 属性 (DAO)
TOCTitle: PartialReplica Property
ms:assetid: 3cb15639-371e-06e3-e2ba-30466ce09a72
ms:mtpsurl: https://msdn.microsoft.com/library/Ff192692(v=office.15)
ms:contentKeyID: 48544324
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1053557
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: fef48902b806f13947ae4b81728af4c5704c2b8e
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28698405"
---
# <a name="relationpartialreplica-property-dao"></a><span data-ttu-id="1891e-102">Relation.PartialReplica 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="1891e-102">Relation.PartialReplica property (DAO)</span></span>

<span data-ttu-id="1891e-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="1891e-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="1891e-p101">设置或返回 **Relation** 对象的值，用于指示从完全副本填充部分副本时是否应当考虑关系。（仅适用于 Microsoft Access 数据库引擎数据库）。可读写 **Boolean**。</span><span class="sxs-lookup"><span data-stu-id="1891e-p101">Sets or returns a value on a **Relation** object indicating whether that relation should be considered when populating a partial replica from a full replica. (Microsoft Access database engine databases only). Read/write **Boolean**.</span></span>

## <a name="syntax"></a><span data-ttu-id="1891e-107">语法</span><span class="sxs-lookup"><span data-stu-id="1891e-107">Syntax</span></span>

<span data-ttu-id="1891e-108">*表达式*。PartialReplica</span><span class="sxs-lookup"><span data-stu-id="1891e-108">*expression* .PartialReplica</span></span>

<span data-ttu-id="1891e-109">*表达式*一个返回**Relation**对象的表达式。</span><span class="sxs-lookup"><span data-stu-id="1891e-109">*expression* An expression that returns a **Relation** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="1891e-110">注解</span><span class="sxs-lookup"><span data-stu-id="1891e-110">Remarks</span></span>

<span data-ttu-id="1891e-111">设置或返回值属于 Boolean 数据类型，如果同步期间应当实施关系，则为 **True**。</span><span class="sxs-lookup"><span data-stu-id="1891e-111">The setting or return value is a Boolean data type that is **True** when the relation should be enforced during synchronization.</span></span>

<span data-ttu-id="1891e-p102">该属性使您可以基于表之间的关系将完全副本中的数据复制到部分副本中。如果单独设置 **ReplicaFilter** 属性无法准确指定应当复制到部分副本的数据，则可以使用 **PartialReplica** 属性。例如，假设您有一个数据库，其中的“客户”表与“订单”表具有一对多关系，您想要配置只从加利福尼亚地区复制订单（而不是复制所有订单）的部分副本。由于“地区”字段位于“客户”表而不是“订单”表中，因此无法将“订单”表中的 **ReplicaFilter** 属性设置为 Region = 'CA'。</span><span class="sxs-lookup"><span data-stu-id="1891e-p102">This property enables you to replicate data from the full replica to the partial replica based on relationships between tables. You can use the **PartialReplica** property when setting the **ReplicaFilter** property alone can't adequately specify what data should be replicated to the partial. For example, suppose you have a database in which the Customers table has a one-to-many relationship with the Orders table, and you want to configure a partial replica that only replicates orders from customers in the California region (instead of all orders). It is not possible to set the **ReplicaFilter** property on the Orders table to Region = 'CA' because the Region field is in the Customers table, not the Orders table.</span></span>

<span data-ttu-id="1891e-p103">若要从加利福尼亚地区复制所有订单，必须指明在复制期间"订单"与"客户"表之间的关系将是活动的。一旦创建了部分副本，以下步骤将使用加利福尼亚地区的所有订单填充该副本：</span><span class="sxs-lookup"><span data-stu-id="1891e-p103">To replicate all orders from the California region, you must indicate that the relation between the Orders and Customers tables will be active during replication. Once you've created a partial replica, the following steps will populate it with all orders from the California region:</span></span>

1.  <span data-ttu-id="1891e-118">设置客户**TableDef**对象的**ReplicaFilter**属性"区域 = 'CA'"。</span><span class="sxs-lookup"><span data-stu-id="1891e-118">Set the **ReplicaFilter** property on the Customers **TableDef** object to "Region = 'CA'".</span></span>

2.  <span data-ttu-id="1891e-119">对于对应于"订单"与"客户"之间的关系的 **Relation** 对象，将 **PartialReplica** 属性设置为 **True**。</span><span class="sxs-lookup"><span data-stu-id="1891e-119">Set the value of the **PartialReplica** property to **True** on the **Relation** object corresponding to the relationship between Orders and Customers.</span></span>

3.  <span data-ttu-id="1891e-120">调用 **PopulatePartial** 方法。</span><span class="sxs-lookup"><span data-stu-id="1891e-120">Invoke the **PopulatePartial** method.</span></span>
    

> [!NOTE]
> <span data-ttu-id="1891e-121">[!注释] 当设置副本筛选器或副本关系时，一定要注意，不满足限制条件的部分副本中的记录将会从部分副本中删除，而不是从完全副本中删除。</span><span class="sxs-lookup"><span data-stu-id="1891e-121">When you set a replica filter or replica relation, be aware that records in the partial replica that don't satisfy the restriction criteria will be removed from the partial replica, but not from the full replica.</span></span> <span data-ttu-id="1891e-122">例如，假设您将**ReplicaFilter**属性设置为部分副本中客户**TableDef**上"区域 = 'CA'"并重新填充数据库。</span><span class="sxs-lookup"><span data-stu-id="1891e-122">For example, suppose you set the **ReplicaFilter** property on the Customers **TableDef** in the partial replica to "Region = 'CA'" and you then repopulate the database.</span></span> <span data-ttu-id="1891e-123">此操作将会插入或更新加利福尼亚客户的所有记录。</span><span class="sxs-lookup"><span data-stu-id="1891e-123">This will insert or update all records for California-based customers.</span></span> 
> 
> <span data-ttu-id="1891e-124">如果然后重置将**ReplicaFilter**属性设为"区域 FL ="重新填充数据库、 部分副本中的所有加利福尼亚地区记录都将被都删除，和从基于佛罗里达客户的所有记录将都插入从完全副本。</span><span class="sxs-lookup"><span data-stu-id="1891e-124">If you then reset the **ReplicaFilter** property to "Region = 'FL'" and repopulate the database, all California region records in the partial replica will be removed, and all records from Florida-based customers will be inserted from the full replica.</span></span> <span data-ttu-id="1891e-125">不会删除完全副本中的任何记录。</span><span class="sxs-lookup"><span data-stu-id="1891e-125">No records in the full replica will be deleted.</span></span> 
>
> <span data-ttu-id="1891e-126">在设置 **ReplicaFilter** 或 **PartialReplica** 属性之前，最好将设置这些属性的部分副本与完全副本同步。</span><span class="sxs-lookup"><span data-stu-id="1891e-126">Before setting either the **ReplicaFilter** or **PartialReplica** property, it's a good idea to synchronize the partial replica in which you are setting these properties with the full replica.</span></span> <span data-ttu-id="1891e-127">这可以确保在部分副本中删除任何记录之前，部分副本中的挂起更改合并到完全副本中。</span><span class="sxs-lookup"><span data-stu-id="1891e-127">This will ensure that pending changes in the partial replica will be merged into the full replica before any records are removed in the partial replica.</span></span>


