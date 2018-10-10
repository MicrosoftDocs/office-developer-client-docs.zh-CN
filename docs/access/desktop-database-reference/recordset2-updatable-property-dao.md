---
title: Recordset2.Updatable Property (DAO)
TOCTitle: Updatable Property
ms:assetid: ad8184b6-ffe3-dde6-ddee-4b23cdaa9c59
ms:mtpsurl: https://msdn.microsoft.com/library/Ff821726(v=office.15)
ms:contentKeyID: 48547041
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 54ec9af0b8fa1948afe568dc57eacf9962283504
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466047"
---
# <a name="recordset2updatable-property-dao"></a><span data-ttu-id="2bcb4-102">Recordset2.Updatable Property (DAO)</span><span class="sxs-lookup"><span data-stu-id="2bcb4-102">Recordset2.Updatable Property (DAO)</span></span>


<span data-ttu-id="2bcb4-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="2bcb4-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="2bcb4-p101">返回一个值，该值指示是否可以更改 DAO 对象。只读 **Boolean**。</span><span class="sxs-lookup"><span data-stu-id="2bcb4-p101">Returns a value that indicates whether you can change a DAO object. Read-only **Boolean**.</span></span>

## <a name="syntax"></a><span data-ttu-id="2bcb4-106">语法</span><span class="sxs-lookup"><span data-stu-id="2bcb4-106">Syntax</span></span>

<span data-ttu-id="2bcb4-107">*表达式*。可更新</span><span class="sxs-lookup"><span data-stu-id="2bcb4-107">*expression* .Updatable</span></span>

<span data-ttu-id="2bcb4-108">*表达式*一个表示**Recordset2**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="2bcb4-108">*expression* A variable that represents a **Recordset2** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="2bcb4-109">说明</span><span class="sxs-lookup"><span data-stu-id="2bcb4-109">Remarks</span></span>

<span data-ttu-id="2bcb4-110">快照和转发-仅类型 Recordset 对象始终返回**False**。</span><span class="sxs-lookup"><span data-stu-id="2bcb4-110">Snapshot- and forward-only–type Recordset objects always return **False**.</span></span>

<span data-ttu-id="2bcb4-p102">许多类型的对象都可以包含不能更新的字段。例如，您可以创建动态集类型的 **Recordset** 对象，在该对象中只能更改某些字段。这些字段可能是固定的，也可能包含自动递增的数据，或者动态集可以从合并可更新表和不可更新表的查询中得出。</span><span class="sxs-lookup"><span data-stu-id="2bcb4-p102">Many types of objects can contain fields that can't be updated. For example, you can create a dynaset-type **Recordset** object in which only some fields can be changed. These fields can be fixed or contain data that increments automatically, or the dynaset can result from a query that combines updatable and nonupdatable tables.</span></span>

<span data-ttu-id="2bcb4-p103">如果该对象仅包含只读字段，则 **Updatable** 属性的值为 **False**。当一个或多个字段可更新时，属性的值为 **True**。您只能编辑可更新的字段。如果尝试向只读字段分配新值，则会发生可捕获的错误。</span><span class="sxs-lookup"><span data-stu-id="2bcb4-p103">If the object contains only read-only fields, the value of the **Updatable** property is **False**. When one or more fields are updatable, the property's value is **True**. You can edit only the updatable fields. A trappable error occurs if you try to assign a new value to a read-only field.</span></span>

<span data-ttu-id="2bcb4-118">由于可更新的对象可以包含只读字段，因此请在编辑记录之前检查 **Recordset** 对象的 **Fields** 集合中每个字段的 **DataUpdatable** 属性。</span><span class="sxs-lookup"><span data-stu-id="2bcb4-118">Because an updatable object can contain read-only fields, check the **DataUpdatable** property of each field in the **Fields** collection of a **Recordset** object before you edit a record.</span></span>

