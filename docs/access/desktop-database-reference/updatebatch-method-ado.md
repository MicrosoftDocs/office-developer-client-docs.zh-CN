---
title: UpdateBatch 方法 (ADO)
TOCTitle: UpdateBatch method (ADO)
ms:assetid: 69e72a65-b637-36fd-d09f-7f81050f71ad
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249416(v=office.15)
ms:contentKeyID: 48545420
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 2e998bb49fab57927a8bb233d9eeb3245a1a3876
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25929935"
---
# <a name="updatebatch-method-ado"></a><span data-ttu-id="90df8-102">UpdateBatch 方法 (ADO)</span><span class="sxs-lookup"><span data-stu-id="90df8-102">UpdateBatch method (ADO)</span></span>


<span data-ttu-id="90df8-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="90df8-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="90df8-104">用于将所有挂起的批更新写入磁盘。</span><span class="sxs-lookup"><span data-stu-id="90df8-104">Writes all pending batch updates to disk.</span></span>

## <a name="syntax"></a><span data-ttu-id="90df8-105">语法</span><span class="sxs-lookup"><span data-stu-id="90df8-105">Syntax</span></span>

<span data-ttu-id="90df8-106">*记录集*。UpdateBatch*AffectRecords*</span><span class="sxs-lookup"><span data-stu-id="90df8-106">*recordset*.UpdateBatch*AffectRecords*</span></span>

## <a name="parameters"></a><span data-ttu-id="90df8-107">参数</span><span class="sxs-lookup"><span data-stu-id="90df8-107">Parameters</span></span>

  - <span data-ttu-id="90df8-108">*AffectRecords*</span><span class="sxs-lookup"><span data-stu-id="90df8-108">*AffectRecords*</span></span>

  - <span data-ttu-id="90df8-p101">可选。[AffectEnum](affectenum.md) 值，指示 **UpdateBatch** 方法将影响的记录数。</span><span class="sxs-lookup"><span data-stu-id="90df8-p101">Optional. An [AffectEnum](affectenum.md) value that indicates how many records the **UpdateBatch** method will affect.</span></span>

## <a name="remarks"></a><span data-ttu-id="90df8-111">备注</span><span class="sxs-lookup"><span data-stu-id="90df8-111">Remarks</span></span>

<span data-ttu-id="90df8-112">以批更新模式修改 **Recordset** 对象时，可以使用 **UpdateBatch** 方法将在 **Recordset** 对象中所做的所有更改传输到基础数据库中。</span><span class="sxs-lookup"><span data-stu-id="90df8-112">Use the **UpdateBatch** method when modifying a **Recordset** object in batch update mode to transmit all changes made in a **Recordset** object to the underlying database.</span></span>

<span data-ttu-id="90df8-p102">如果 **Recordset** 对象支持批更新，则在调用 **UpdateBatch** 方法前，可以将对一个或多个记录所做的多次更改缓存在本地。如果在调用 **UpdateBatch** 方法时正在编辑当前记录或添加新记录，则在将批更改传输到提供程序前，ADO 将自动调用 [Update](update-method-ado.md) 方法来保存对当前记录所做的所有挂起的更改。批更新只应与键集或静态游标一起使用。</span><span class="sxs-lookup"><span data-stu-id="90df8-p102">If the **Recordset** object supports batch updating, you can cache multiple changes to one or more records locally until you call the **UpdateBatch** method. If you are editing the current record or adding a new record when you call the **UpdateBatch** method, ADO will automatically call the [Update](update-method-ado.md) method to save any pending changes to the current record before transmitting the batched changes to the provider. You should use batch updating with either a keyset or static cursor only.</span></span>


> [!NOTE]
> <P><span data-ttu-id="90df8-116">[!注释] 如果当前 <STRONG>Recordset</STRONG> 中没有可见记录（如没有满足筛选器的记录），则指定 <STRONG>adAffectGroup</STRONG> 作为此参数的值将导致出错。</span><span class="sxs-lookup"><span data-stu-id="90df8-116">Specifying <STRONG>adAffectGroup</STRONG> as the value for this parameter will result in an error when there are no visible records in the current <STRONG>Recordset</STRONG> (such as a filter for which no records match).</span></span></P>



<span data-ttu-id="90df8-p103">如果由于与基础数据冲突（例如，记录已被其他用户删除）使得传输任意记录或所有记录的更改的尝试失败，则提供程序将向 [Errors](errors-collection-ado.md) 集合返回警告，并会发生运行时错误。可以使用 [Filter](filter-property-ado.md) 属性 (**adFilterAffectedRecords**) 和 [Status](status-property-ado-recordset.md) 属性查找存在冲突的记录。</span><span class="sxs-lookup"><span data-stu-id="90df8-p103">If the attempt to transmit changes fails for any or all records because of a conflict with the underlying data (for example, a record has already been deleted by another user), the provider returns warnings to the [Errors](errors-collection-ado.md) collection and a run-time error occurs. Use the [Filter](filter-property-ado.md) property (**adFilterAffectedRecords**) and the [Status](status-property-ado-recordset.md) property to locate records with conflicts.</span></span>

<span data-ttu-id="90df8-119">若要取消挂起的所有批更新，请使用 [CancelBatch](cancelbatch-method-ado.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="90df8-119">To cancel all pending batch updates, use the [CancelBatch](cancelbatch-method-ado.md) method.</span></span>

<span data-ttu-id="90df8-120">如果设置了 [Unique Table](unique-table-unique-schema-unique-catalog-properties-dynamic-ado.md) 和 [Update Resync](update-resync-property-dynamic-ado.md) 动态属性，且 **Recordset** 是对多个表执行 JOIN 操作的结果，那么根据 **Update Resync** 属性的设置，在执行 [UpdateBatch](resync-method-ado.md) 方法后会隐式执行 **Resync** 方法。</span><span class="sxs-lookup"><span data-stu-id="90df8-120">If the [Unique Table](unique-table-unique-schema-unique-catalog-properties-dynamic-ado.md) and [Update Resync](update-resync-property-dynamic-ado.md) dynamic properties are set, and the **Recordset** is the result of executing a JOIN operation on multiple tables, then the execution of the **UpdateBatch** method is implicitly followed by the [Resync](resync-method-ado.md) method depending on the settings of the **Update Resync** property.</span></span>

<span data-ttu-id="90df8-p104">对数据源执行各个批更新的次序不一定要与对本地 **Recordset** 执行批更新的次序相同。更新次序取决于提供程序。在编写彼此相关的更新（如针对插入或更新的外键约束）的代码时，应将这一点考虑在内。</span><span class="sxs-lookup"><span data-stu-id="90df8-p104">The order in which the individual updates of a batch are performed on the data source is not necessarily the same as the order in which they were performed on the local **Recordset**. Update order is dependent upon the provider. Take this into account when coding updates that are related to one another, such as foreign key constraints on an insert or update.</span></span>

