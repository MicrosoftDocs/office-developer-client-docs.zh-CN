---
title: Resync 方法 (ADO)
TOCTitle: Resync Method (ADO)
ms:assetid: f594a200-56e6-fcf5-9b0a-900c56377f24
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250251(v=office.15)
ms:contentKeyID: 48548717
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 3d8e4a863449d8aea5d95002a6183978d9ca953a
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25884497"
---
# <a name="resync-method-ado"></a><span data-ttu-id="c7a2f-102">Resync 方法 (ADO)</span><span class="sxs-lookup"><span data-stu-id="c7a2f-102">Resync Method (ADO)</span></span>


<span data-ttu-id="c7a2f-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="c7a2f-103">**Applies to**: Access 2013, Office 2013</span></span>



<span data-ttu-id="c7a2f-104">用于从基础数据库刷新当前 [Recordset](recordset-object-ado.md) 对象中的数据或刷新 [Record](fields-collection-ado.md) 对象的 [Fields](record-object-ado.md) 集合中的数据。</span><span class="sxs-lookup"><span data-stu-id="c7a2f-104">Refreshes the data in the current [Recordset](recordset-object-ado.md) object, or [Fields](fields-collection-ado.md) collection of a [Record](record-object-ado.md) object, from the underlying database.</span></span>

## <a name="syntax"></a><span data-ttu-id="c7a2f-105">语法</span><span class="sxs-lookup"><span data-stu-id="c7a2f-105">Syntax</span></span>

<span data-ttu-id="c7a2f-106">*记录集*。Resync*AffectRecords*， *ResyncValues*</span><span class="sxs-lookup"><span data-stu-id="c7a2f-106">*Recordset*.Resync*AffectRecords*, *ResyncValues*</span></span>

<span data-ttu-id="c7a2f-107">*记录*。</span><span class="sxs-lookup"><span data-stu-id="c7a2f-107">*Record*.</span></span> <span data-ttu-id="c7a2f-108">*字段*。Resync*ResyncValues*</span><span class="sxs-lookup"><span data-stu-id="c7a2f-108">*Fields*.Resync*ResyncValues*</span></span>

## <a name="parameters"></a><span data-ttu-id="c7a2f-109">参数</span><span class="sxs-lookup"><span data-stu-id="c7a2f-109">Parameters</span></span>

  - <span data-ttu-id="c7a2f-110">*AffectRecords*</span><span class="sxs-lookup"><span data-stu-id="c7a2f-110">*AffectRecords*</span></span>

  - <span data-ttu-id="c7a2f-p102">可选。[AffectEnum](affectenum.md) 值，用于确定 **Resync** 方法将影响的记录数。默认值为 **adAffectAll** 。对于 **Record** 对象的 **Fields** 集合的 **Resync** 方法，此值不可用。</span><span class="sxs-lookup"><span data-stu-id="c7a2f-p102">Optional. An [AffectEnum](affectenum.md) value that determines how many records the **Resync** method will affect. The default value is **adAffectAll**. This value is not available with the **Resync** method of the **Fields** collection of a **Record** object.</span></span>

  - <span data-ttu-id="c7a2f-115">*ResyncValues*</span><span class="sxs-lookup"><span data-stu-id="c7a2f-115">*ResyncValues*</span></span>

  - <span data-ttu-id="c7a2f-p103">可选。[ResyncEnum](resyncenum.md) 值，用于指定是否覆盖基础值。默认值为 **adResyncAllValues** 。</span><span class="sxs-lookup"><span data-stu-id="c7a2f-p103">Optional. A [ResyncEnum](resyncenum.md) value that specifies whether underlying values are overwritten. The default value is **adResyncAllValues**.</span></span>

## <a name="remarks"></a><span data-ttu-id="c7a2f-119">说明</span><span class="sxs-lookup"><span data-stu-id="c7a2f-119">Remarks</span></span>

<span data-ttu-id="c7a2f-120">**Recordset**</span><span class="sxs-lookup"><span data-stu-id="c7a2f-120">**Recordset**</span></span>

<span data-ttu-id="c7a2f-p104">使用 **Resync** 方法可以用基础数据库重新同步当前 **Recordset** 中的记录。如果使用的是静态或仅向前型游标，但希望查看基础数据库中的任何更改，该方法将很有帮助。</span><span class="sxs-lookup"><span data-stu-id="c7a2f-p104">Use the **Resync** method to resynchronize records in the current **Recordset** with the underlying database. This is useful if you are using either a static or forward-only cursor, but you want to see any changes in the underlying database.</span></span>

<span data-ttu-id="c7a2f-123">如果将 [CursorLocation](cursorlocation-property-ado.md) 属性设置为 **adUseClient** ，那么 **Resync** 只能用于非只读 **Recordset** 对象。</span><span class="sxs-lookup"><span data-stu-id="c7a2f-123">If you set the [CursorLocation](cursorlocation-property-ado.md) property to **adUseClient**, **Resync** is only available for non-read-only **Recordset** objects.</span></span>

<span data-ttu-id="c7a2f-p105">与 [Requery](requery-method-ado.md) 方法不同， **Resync** 方法不重新执行 **Recordset** 对象的基础命令。基础数据库中的新记录将不可见。</span><span class="sxs-lookup"><span data-stu-id="c7a2f-p105">Unlike the [Requery](requery-method-ado.md) method, the **Resync** method does not re-execute the **Recordset** object's underlying command. New records in the underlying database will not be visible.</span></span>

<span data-ttu-id="c7a2f-p106">如果由于与基础数据冲突（例如，记录已被其他用户删除）使得重新同步的尝试失败，则提供程序将向 [Errors](errors-collection-ado.md) 集合返回警告，且发生运行时错误。可以使用 [Filter](filter-property-ado.md) 属性 (**adFilterConflictingRecords**) 和 [Status](status-property-ado-recordset.md) 属性查找存在冲突的记录。</span><span class="sxs-lookup"><span data-stu-id="c7a2f-p106">If the attempt to resynchronize fails because of a conflict with the underlying data (for example, a record has been deleted by another user), the provider returns warnings to the [Errors](errors-collection-ado.md) collection and a run-time error occurs. Use the [Filter](filter-property-ado.md) property (**adFilterConflictingRecords**) and the [Status](status-property-ado-recordset.md) property to locate records with conflicts.</span></span>

<span data-ttu-id="c7a2f-128">如果设置了 [Unique Table](unique-table-unique-schema-unique-catalog-properties-dynamic-ado.md) 和 [Resync Command](resync-command-property-dynamic-ado.md) 动态属性，且 **Recordset** 是对多个表执行 JOIN 操作的结果，那么 **Resync** 方法将仅对在 **Unique Table** 属性中命名的表执行 **Resync Command** 属性中给定的命令。</span><span class="sxs-lookup"><span data-stu-id="c7a2f-128">If the [Unique Table](unique-table-unique-schema-unique-catalog-properties-dynamic-ado.md) and [Resync Command](resync-command-property-dynamic-ado.md) dynamic properties are set, and the **Recordset** is the result of executing a JOIN operation on multiple tables, then the **Resync** method will execute the command given in the **Resync Command** property only on the table named in the **Unique Table** property.</span></span>

<span data-ttu-id="c7a2f-129">**Fields**</span><span class="sxs-lookup"><span data-stu-id="c7a2f-129">**Fields**</span></span>

<span data-ttu-id="c7a2f-p107">**Resync** 方法可用于用基础数据源重新同步 **Record** 对象的 **Fields** 集合的值。 [Count](count-property-ado.md) 属性不受此方法的影响。</span><span class="sxs-lookup"><span data-stu-id="c7a2f-p107">Use the **Resync** method to resynchronize the values of the **Fields** collection of a **Record** object with the underlying data source. The [Count](count-property-ado.md) property is not affected by this method.</span></span>

<span data-ttu-id="c7a2f-132">如果*ResyncValues*设置为**adResyncAllValues** （默认值），然后[UnderlyingValue](underlyingvalue-property-ado.md)、[值](value-property-ado.md)和[OriginalValue](originalvalue-property-ado.md)属性集合中的[Field](field-object-ado.md)对象的同步。</span><span class="sxs-lookup"><span data-stu-id="c7a2f-132">If *ResyncValues* is set to **adResyncAllValues** (the default value), then the [UnderlyingValue](underlyingvalue-property-ado.md), [Value](value-property-ado.md), and [OriginalValue](originalvalue-property-ado.md) properties of [Field](field-object-ado.md) objects in the collection are synchronized.</span></span> <span data-ttu-id="c7a2f-133">如果*ResyncValues*设置为**adResyncUnderlyingValues**，同步仅将**UnderlyingValue**属性。</span><span class="sxs-lookup"><span data-stu-id="c7a2f-133">If *ResyncValues* is set to **adResyncUnderlyingValues**, only the **UnderlyingValue** property is synchronized.</span></span>

<span data-ttu-id="c7a2f-p109">每个 **Field** 对象的 **Status** 属性值在调用时也会影响 **Resync** 的行为。如果 **Field** 对象的 **Status** 值为 **adFieldPendingUnknown** 或 **adFieldPendingInsert** ，则 **Resync** 无效。如果对象的 **Status** 值为 **adFieldPendingChange** 或 **adFieldPendingDelete** ，则 **Resync** 会同步仍存在于数据源中的字段的数据值。</span><span class="sxs-lookup"><span data-stu-id="c7a2f-p109">The value of the **Status** property for each **Field** object at the time of the call also affects the behavior of **Resync**. For **Field** objects with **Status** values of **adFieldPendingUnknown** or **adFieldPendingInsert**, **Resync** has no effect. For **Status** values of **adFieldPendingChange** or **adFieldPendingDelete**, **Resync** synchronizes data values for fields that still exist at the data source.</span></span>

<span data-ttu-id="c7a2f-p110">**Resync** 不会修改 **Field** 对象的 **Status** 值，除非在调用 **Resync** 时发生错误。例如，如果字段不再存在，提供程序将为 **Field** 对象返回适当的 **Status** 值，如 **adFieldDoesNotExist** 。返回的 **Status** 值可能被逻辑合并在 **Status** 属性值内。</span><span class="sxs-lookup"><span data-stu-id="c7a2f-p110">**Resync** will not modify **Status** values of **Field** objects unless an error occurs when **Resync** is called. For example, if the field no longer exists, the provider will return an appropriate **Status** value for the **Field** object, such as **adFieldDoesNotExist**. Returned **Status** values may be logically combined within the value of the **Status** property.</span></span>

