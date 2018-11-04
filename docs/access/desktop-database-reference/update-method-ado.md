---
title: Update 方法 (ADO)
TOCTitle: Update method (ADO)
ms:assetid: fc88cab6-c379-bb4f-530c-da08107924e0
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250294(v=office.15)
ms:contentKeyID: 48548893
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 7501f7607dbee558a67dd0e11d7f2498874f8870
ms.sourcegitcommit: 980a96cf444882d3d34cecb5faac8f8a7b7c4b57
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25950228"
---
# <a name="update-method-ado"></a><span data-ttu-id="5bf49-102">Update 方法 (ADO)</span><span class="sxs-lookup"><span data-stu-id="5bf49-102">Update method (ADO)</span></span>

<span data-ttu-id="5bf49-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="5bf49-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="5bf49-104">可保存对 [Recordset](recordset-object-ado.md) 对象的当前行或 [Record](fields-collection-ado.md) 对象的 [Fields](record-object-ado.md) 集合所做的任何更改。</span><span class="sxs-lookup"><span data-stu-id="5bf49-104">Saves any changes you make to the current row of a [Recordset](recordset-object-ado.md) object, or the [Fields](fields-collection-ado.md) collection of a [Record](record-object-ado.md) object.</span></span>

## <a name="syntax"></a><span data-ttu-id="5bf49-105">语法</span><span class="sxs-lookup"><span data-stu-id="5bf49-105">Syntax</span></span>

<span data-ttu-id="5bf49-106">*记录集*。更新*字段*，*值*</span><span class="sxs-lookup"><span data-stu-id="5bf49-106">*recordset*.Update*Fields*, *Values*</span></span>

<span data-ttu-id="5bf49-107">*记录*。</span><span class="sxs-lookup"><span data-stu-id="5bf49-107">*record*.</span></span> <span data-ttu-id="5bf49-108">*字段*。更新</span><span class="sxs-lookup"><span data-stu-id="5bf49-108">*Fields*.Update</span></span>

## <a name="parameters"></a><span data-ttu-id="5bf49-109">参数</span><span class="sxs-lookup"><span data-stu-id="5bf49-109">Parameters</span></span>

|<span data-ttu-id="5bf49-110">参数</span><span class="sxs-lookup"><span data-stu-id="5bf49-110">Parameter</span></span>|<span data-ttu-id="5bf49-111">说明</span><span class="sxs-lookup"><span data-stu-id="5bf49-111">Description</span></span>|
|:--------|:----------|
|<span data-ttu-id="5bf49-112">*Fields*</span><span class="sxs-lookup"><span data-stu-id="5bf49-112">*Fields*</span></span> |<span data-ttu-id="5bf49-p102">可选。一个表示单个名称的 **Variant** ，或表示要修改的字段的名称或序号位置的 **Variant** 数组。</span><span class="sxs-lookup"><span data-stu-id="5bf49-p102">Optional. A **Variant** that represents a single name, or a **Variant** array that represents names or ordinal positions of the field or fields you wish to modify.</span></span>|
|<span data-ttu-id="5bf49-115">*Values*</span><span class="sxs-lookup"><span data-stu-id="5bf49-115">*Values*</span></span> |<span data-ttu-id="5bf49-p103">可选。一个表示单个名称的 **Variant** ，或表示新记录中字段值的 **Variant** 数组。</span><span class="sxs-lookup"><span data-stu-id="5bf49-p103">Optional. A **Variant** that represents a single value, or a **Variant** array that represents values for the field or fields in the new record.</span></span>|

## <a name="remarks"></a><span data-ttu-id="5bf49-118">备注</span><span class="sxs-lookup"><span data-stu-id="5bf49-118">Remarks</span></span>

### <a name="recordset"></a><span data-ttu-id="5bf49-119">Recordset</span><span class="sxs-lookup"><span data-stu-id="5bf49-119">Recordset</span></span>

<span data-ttu-id="5bf49-p104">使用 **Update** 方法可以保存自调用 **AddNew** 方法或更改现有记录中的任何字段值之后对 [Recordset](addnew-method-ado.md) 对象的当前记录所做的任何更改。 **Recordset** 对象必须支持更新。</span><span class="sxs-lookup"><span data-stu-id="5bf49-p104">Use the **Update** method to save any changes you make to the current record of a **Recordset** object since calling the [AddNew](addnew-method-ado.md) method or since changing any field values in an existing record. The **Recordset** object must support updates.</span></span>

<span data-ttu-id="5bf49-122">若要设置字段值，请执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="5bf49-122">To set field values, do one of the following:</span></span>

- <span data-ttu-id="5bf49-123">将值赋给 [Field](field-object-ado.md) 对象的 [Value](value-property-ado.md) 属性并调用 **Update** 方法。</span><span class="sxs-lookup"><span data-stu-id="5bf49-123">Assign values to a [Field](field-object-ado.md) object's [Value](value-property-ado.md) property and call the **Update** method.</span></span>

- <span data-ttu-id="5bf49-124">调用 **Update** 时将字段名和值作为参数传递。</span><span class="sxs-lookup"><span data-stu-id="5bf49-124">Pass a field name and a value as arguments with the **Update** call.</span></span>

- <span data-ttu-id="5bf49-125">调用 **Update** 时传递字段名数组和值数组。</span><span class="sxs-lookup"><span data-stu-id="5bf49-125">Pass an array of field names and an array of values with the **Update** call.</span></span>

<span data-ttu-id="5bf49-p105">在使用字段和值的数组时，两个数组中的元素个数必须相同。同时，字段名的次序必须与字段值的次序匹配。如果字段和值的个数和次序不匹配，则会发生错误。</span><span class="sxs-lookup"><span data-stu-id="5bf49-p105">When you use arrays of fields and values, there must be an equal number of elements in both arrays. Also, the order of field names must match the order of field values. If the number and order of fields and values do not match, an error occurs.</span></span>

<span data-ttu-id="5bf49-p106">如果 **Recordset** 对象支持批更新，则在调用 [UpdateBatch](updatebatch-method-ado.md) 方法前，可以在本地缓存对一个或多个记录所做的多次更改。如果在调用 **UpdateBatch** 方法时正在编辑当前记录或添加新记录，则 ADO 在将批更改传输到提供程序前，将自动调用 **Update** 方法将所有挂起的更改保存到当前记录。</span><span class="sxs-lookup"><span data-stu-id="5bf49-p106">If the **Recordset** object supports batch updating, you can cache multiple changes to one or more records locally until you call the [UpdateBatch](updatebatch-method-ado.md) method. If you are editing the current record or adding a new record when you call the **UpdateBatch** method, ADO will automatically call the **Update** method to save any pending changes to the current record before transmitting the batched changes to the provider.</span></span>

<span data-ttu-id="5bf49-p107">如果在调用 **Update** 方法之前从正在添加或编辑的记录移开，则 ADO 将自动调用 **Update** 来保存所做的更改。如果要取消对当前记录所做的更改或放弃新添加的记录，则必须调用 [CancelUpdate](cancelupdate-method-ado.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="5bf49-p107">If you move from the record you are adding or editing before calling the **Update** method, ADO will automatically call **Update** to save the changes. You must call the [CancelUpdate](cancelupdate-method-ado.md) method if you want to cancel any changes made to the current record or discard a newly added record.</span></span>

<span data-ttu-id="5bf49-133">调用 **Update** 方法之后，当前记录仍然是当前记录。</span><span class="sxs-lookup"><span data-stu-id="5bf49-133">The current record remains current after you call the **Update** method.</span></span>

### <a name="record"></a><span data-ttu-id="5bf49-134">Record</span><span class="sxs-lookup"><span data-stu-id="5bf49-134">Record</span></span>

<span data-ttu-id="5bf49-135">可以使用 **Update** 方法完成在 [Record](fields-collection-ado.md) 对象的 **Fields** 集合中添加、删除或更新字段的操作。</span><span class="sxs-lookup"><span data-stu-id="5bf49-135">The **Update** method finalizes additions, deletions, and updates to fields in the [Fields](fields-collection-ado.md) collection of a **Record** object.</span></span>

<span data-ttu-id="5bf49-p108">例如，用 **Delete** 方法删除的字段被立即加上删除标记，但仍保留在集合中。必须调用 **Update** 方法来从提供程序的集合中实际删除这些字段。</span><span class="sxs-lookup"><span data-stu-id="5bf49-p108">For example, fields deleted with the **Delete** method are marked for deletion immediately but remain in the collection. The **Update** method must be called to actually delete these fields from the provider's collection.</span></span>

