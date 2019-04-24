---
title: Append 方法 (ADO)
TOCTitle: Append method (ADO)
ms:assetid: cca133af-2b95-877d-0488-0d99631623f2
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250014(v=office.15)
ms:contentKeyID: 48547742
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: a85faf900860dabb809a10a92985559b7a7cf2ef
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32297128"
---
# <a name="append-method-ado"></a><span data-ttu-id="a9f08-102">Append 方法 (ADO)</span><span class="sxs-lookup"><span data-stu-id="a9f08-102">Append method (ADO)</span></span>

<span data-ttu-id="a9f08-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="a9f08-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="a9f08-p101">用于将对象追加到集合。如果集合为 [Fields](fields-collection-ado.md)，则在将对象追加到集合之前，可能会创建新的 [Field](field-object-ado.md) 对象。</span><span class="sxs-lookup"><span data-stu-id="a9f08-p101">Appends an object to a collection. If the collection is [Fields](fields-collection-ado.md), a new [Field](field-object-ado.md) object may be created before it is appended to the collection.</span></span>

## <a name="syntax"></a><span data-ttu-id="a9f08-106">语法</span><span class="sxs-lookup"><span data-stu-id="a9f08-106">Syntax</span></span>

<span data-ttu-id="a9f08-107">*集合*。Append*对象*</span><span class="sxs-lookup"><span data-stu-id="a9f08-107">*collection*.Append *object*</span></span>

<span data-ttu-id="a9f08-108">*字段*。Append *Name*、 *Type*、 *DefinedSize*、 *Attrib*、 *FieldValue*</span><span class="sxs-lookup"><span data-stu-id="a9f08-108">*fields*.Append *Name*, *Type*, *DefinedSize*, *Attrib*, *FieldValue*</span></span>

## <a name="parameters"></a><span data-ttu-id="a9f08-109">参数</span><span class="sxs-lookup"><span data-stu-id="a9f08-109">Parameters</span></span>

|<span data-ttu-id="a9f08-110">参数</span><span class="sxs-lookup"><span data-stu-id="a9f08-110">Parameter</span></span>|<span data-ttu-id="a9f08-111">描述</span><span class="sxs-lookup"><span data-stu-id="a9f08-111">Description</span></span>|
|:--------|:----------|
|<span data-ttu-id="a9f08-112">*collection*</span><span class="sxs-lookup"><span data-stu-id="a9f08-112">*collection*</span></span> |<span data-ttu-id="a9f08-113">集合对象。</span><span class="sxs-lookup"><span data-stu-id="a9f08-113">A collection object.</span></span>|
|<span data-ttu-id="a9f08-114">*fields*</span><span class="sxs-lookup"><span data-stu-id="a9f08-114">*fields*</span></span> |<span data-ttu-id="a9f08-115">**Fields** 集合。</span><span class="sxs-lookup"><span data-stu-id="a9f08-115">A **Fields** collection.</span></span>|
|<span data-ttu-id="a9f08-116">*object*</span><span class="sxs-lookup"><span data-stu-id="a9f08-116">*object*</span></span> |<span data-ttu-id="a9f08-117">对象变量，表示要追加的对象。</span><span class="sxs-lookup"><span data-stu-id="a9f08-117">An object variable that represents the object to be appended.</span></span>|
|<span data-ttu-id="a9f08-118">*Name*</span><span class="sxs-lookup"><span data-stu-id="a9f08-118">*Name*</span></span> |<span data-ttu-id="a9f08-119">**字符串**值，包含新的 **Field** 对象的名称，不能与 *fields* 中任何其他对象同名。</span><span class="sxs-lookup"><span data-stu-id="a9f08-119">A **String** value that contains the name of the new **Field** object, and must not be the same name as any other object in *fields*.</span></span>|
|<span data-ttu-id="a9f08-120">*Type*</span><span class="sxs-lookup"><span data-stu-id="a9f08-120">*Type*</span></span> |<span data-ttu-id="a9f08-p102">[DataTypeEnum](datatypeenum.md) 值，其默认值为 **adEmpty** ，用于指定新字段的数据类型。ADO 不支持以下数据类型，在将新字段追加到 **Recordset** 时不应当使用这些数据类型： **adIDispatch** 、 **adIUnknown** 、 **adVariant** 。</span><span class="sxs-lookup"><span data-stu-id="a9f08-p102">A [DataTypeEnum](datatypeenum.md) value, whose default value is **adEmpty**, that specifies the data type of the new field. The following data types are not supported by ADO, and should not be used when appending new fields to a **Recordset**: **adIDispatch**, **adIUnknown**, **adVariant**.</span></span>|
|<span data-ttu-id="a9f08-123">*DefinedSize*</span><span class="sxs-lookup"><span data-stu-id="a9f08-123">*DefinedSize*</span></span> |<span data-ttu-id="a9f08-p103">可选。**长整型**值，表示新字段的定义大小，以字符数或字节数计。此参数的默认值由 *Type* 决定。DefinedSize 大于 255 字节的字段将被视为可变长度列。（未指定默认 *DefinedSize*。）</span><span class="sxs-lookup"><span data-stu-id="a9f08-p103">Optional. A **Long** value that represents the defined size, in characters or bytes, of the new field. The default value for this parameter is derived from *Type*. Fields with a DefinedSize greater than 255 bytes, and treated as variable length columns. (The default *DefinedSize* is unspecified.)</span></span>|
|<span data-ttu-id="a9f08-129">*Attrib*</span><span class="sxs-lookup"><span data-stu-id="a9f08-129">*Attrib*</span></span> |<span data-ttu-id="a9f08-p104">可选。[FieldAttributeEnum](fieldattributeenum.md) 值，其默认值为 **adFldDefault**，用于指定新字段的属性。如果未指定此值，则字段所包含的属性由 *Type* 决定。</span><span class="sxs-lookup"><span data-stu-id="a9f08-p104">Optional. A [FieldAttributeEnum](fieldattributeenum.md) value, whose default value is **adFldDefault**, that specifies attributes for the new field. If this value is not specified, the field will contain attributes derived from *Type*.</span></span>|
|<span data-ttu-id="a9f08-133">*FieldValue*</span><span class="sxs-lookup"><span data-stu-id="a9f08-133">*FieldValue*</span></span> |<span data-ttu-id="a9f08-p105">可选。 **变量型** ，表示新字段的值。如果未指定此值，则为字段追加一个 Null 值。</span><span class="sxs-lookup"><span data-stu-id="a9f08-p105">Optional. A **Variant** that represents the value for the new field. If not specified, then the field is appended with a null value.</span></span>|

## <a name="remarks"></a><span data-ttu-id="a9f08-137">注解</span><span class="sxs-lookup"><span data-stu-id="a9f08-137">Remarks</span></span>

### <a name="parameters-collection"></a><span data-ttu-id="a9f08-138">Parameters 集合</span><span class="sxs-lookup"><span data-stu-id="a9f08-138">Parameters collection</span></span>

<span data-ttu-id="a9f08-p106">在将 [Parameter](type-property-ado.md) 对象追加到 [Parameters](parameter-object-ado.md) 集合之前，必须设置其 **Type** 属性。如果选择可变长度的数据类型，那么还必须将 [Size](size-property-ado.md) 属性设置为大于零的值。</span><span class="sxs-lookup"><span data-stu-id="a9f08-p106">You must set the [Type](type-property-ado.md) property of a [Parameter](parameter-object-ado.md) object before appending it to the **Parameters** collection. If you select a variable-length data type, you must also set the [Size](size-property-ado.md) property to a value greater than zero.</span></span>

<span data-ttu-id="a9f08-p107">自己描述参数可以将对提供程序的调用次数减至最少，从而改进使用存储过程或参数化查询时的性能。不过，必须了解与要调用的存储过程或参数化查询所关联的参数属性。</span><span class="sxs-lookup"><span data-stu-id="a9f08-p107">Describing parameters yourself minimizes calls to the provider and consequently improves performance when using stored procedures or parameterized queries. However, you must know the properties of the parameters associated with the stored procedure or parameterized query that you want to call.</span></span>

<span data-ttu-id="a9f08-p108">可以使用 [CreateParameter](createparameter-method-ado.md) 方法创建具适当属性设置的 **Parameter** 对象，并用 **Append** 方法将对象添加到 [Parameters](parameters-collection-ado.md) 集合。这样一来，无需调用参数信息的提供程序，即可设置和返回参数值。如果正在写入未提供参数信息的提供程序，则必须使用此方法手动填充 **Parameters** 集合，才能使用参数。</span><span class="sxs-lookup"><span data-stu-id="a9f08-p108">Use the [CreateParameter](createparameter-method-ado.md) method to create **Parameter** objects with the appropriate property settings and use the **Append** method to add them to the [Parameters](parameters-collection-ado.md) collection. This lets you set and return parameter values without having to call the provider for the parameter information. If you are writing to a provider that does not supply parameter information, you must use this method to manually populate the **Parameters** collection in order to use parameters at all.</span></span>

### <a name="fields-collection"></a><span data-ttu-id="a9f08-146">Fields 集合</span><span class="sxs-lookup"><span data-stu-id="a9f08-146">Fields collection</span></span>

<span data-ttu-id="a9f08-p109">只有在将 **Field** 对象添加到 [Record](record-object-ado.md) 对象（而非 **Recordset** 对象）时，*FieldValue* 参数才有效。通过 **Record** 对象，可以同时追加字段和提供值。而对于 **Recordset** 对象，当 **Recordset** 关闭时必须创建字段，然后打开 **Recordset** 并为字段赋值。</span><span class="sxs-lookup"><span data-stu-id="a9f08-p109">The *FieldValue* parameter is only valid when adding a **Field** object to a [Record](record-object-ado.md) object, not to a **Recordset** object. With a **Record** object, you may append fields and provide values at the same time. With a **Recordset** object, you must create fields while the **Recordset** is closed, then open the **Recordset** and assign values to the fields.</span></span>


> [!NOTE]
> <span data-ttu-id="a9f08-p110">[!注释] 对于已追加到 **Record** 对象的 **Fields** 集合中的新 **Field** 对象，必须先设置 [Value](value-property-ado.md) 属性，然后才能指定其他任何 **Field** 属性。首先，必须为 **Value** 属性赋予特定值，并对 [Fields](update-method-ado.md) 集合调用 **Update**。然后，可以访问诸如 [Type](type-property-ado.md) 或 [Attributes](attributes-property-ado.md) 等其他属性。</span><span class="sxs-lookup"><span data-stu-id="a9f08-p110">For new **Field** objects that have been appended to the **Fields** collection of a **Record** object, the [Value](value-property-ado.md) property must be set before any other **Field** properties can be specified. First, a specific value for the **Value** property must have been assigned and [Update](update-method-ado.md) on the **Fields** collection called. Then, other properties such as [Type](type-property-ado.md) or [Attributes](attributes-property-ado.md) can be accessed.</span></span>


<span data-ttu-id="a9f08-p111">以下数据类型 (**DataTypeEnum**) 的 **Field** 对象不能追加到 **Fields** 集合，并将引发错误：**adArray**、**adChapter**、**adEmpty**、**adPropVariant** 和 **adUserDefined**。此外，ADO 不支持以下数据类型：**adIDispatch**、**adIUnknown** 和 **adIVariant**。对于这些类型，追加时不会发生错误，但使用时会产生不可预测的结果，如内存溢出。</span><span class="sxs-lookup"><span data-stu-id="a9f08-p111">**Field** objects of the following data types (**DataTypeEnum**) cannot be appended to the **Fields** collection and will cause an error to occur: **adArray**, **adChapter**, **adEmpty**, **adPropVariant**, and **adUserDefined**. Also, the following data types are not supported by ADO: **adIDispatch**, **adIUnknown**, and **adIVariant**. For these types, no error will occur when appended, but usage can produce unpredictable results including memory leaks.</span></span>

### <a name="recordset"></a><span data-ttu-id="a9f08-156">Recordset</span><span class="sxs-lookup"><span data-stu-id="a9f08-156">Recordset</span></span>

<span data-ttu-id="a9f08-157">如果在调用 **Append** 方法之前未设置 [CursorLocation](cursorlocation-property-ado.md) 属性，则当调用 [Recordset](recordset-object-ado.md) 对象的 [Open](open-method-ado-recordset.md) 方法时，**CursorLocation** 将自动设置为 **adUseClient**（[CursorLocationEnum](cursorlocationenum.md) 值）。</span><span class="sxs-lookup"><span data-stu-id="a9f08-157">If you do not set the [CursorLocation](cursorlocation-property-ado.md) property before calling the **Append** method, **CursorLocation** will be set to **adUseClient** (a [CursorLocationEnum](cursorlocationenum.md) value) automatically when the [Recordset](recordset-object-ado.md) object's [Open](open-method-ado-recordset.md) method is called.</span></span>

<span data-ttu-id="a9f08-p112">如果对打开的 **Recordset** 的 **Fields** 集合调用 **Append** 方法，或对设置了 **ActiveConnection** 属性的 [Recordset](activeconnection-property-ado.md) 调用该方法，则将发生运行时错误。只能将字段追加到未打开且尚未连接到数据源的 **Recordset** 。当 **Recordset** 对象用 [CreateRecordset](createrecordset-method-rds.md) 方法构成，或被分配给某对象变量时，通常为这种情况。</span><span class="sxs-lookup"><span data-stu-id="a9f08-p112">A run-time error will occur if the **Append** method is called on the **Fields** collection of an open **Recordset**, or on a **Recordset** where the [ActiveConnection](activeconnection-property-ado.md) property has been set. You can only append fields to a **Recordset** that is not open and has not yet been connected to a data source. This is typically the case when a **Recordset** object is fabricated with the [CreateRecordset](createrecordset-method-rds.md) method or assigned to an object variable.</span></span>

### <a name="record"></a><span data-ttu-id="a9f08-161">Record</span><span class="sxs-lookup"><span data-stu-id="a9f08-161">Record</span></span>

<span data-ttu-id="a9f08-p113">如果对打开的 **Record** 的 **Fields** 集合调用 **Append** 方法，将不会发生运行时错误。新字段将添加到 **Record** 对象的 **Fields** 集合。如果 **Record** 派生自 **Recordset** ，那么新字段不会显示在 **Recordset** 对象的 **Fields** 集合中。</span><span class="sxs-lookup"><span data-stu-id="a9f08-p113">A run-time error will not occur if the **Append** method is called on the **Fields** collection of an open **Record**. The new field will be added to the **Record** object's **Fields** collection. If the **Record** was derived from a **Recordset**, then the new field will not appear in the **Recordset** object's **Fields** collection.</span></span>

<span data-ttu-id="a9f08-p114">若要创建一个不存在的字段并追加到 **Fields** 集合，那么可以为字段对象赋值，如同它已经存在于集合中一样。赋值将触发 **Field** 对象的自动创建和追加，然后将完成赋值。</span><span class="sxs-lookup"><span data-stu-id="a9f08-p114">A non-existent field can be created and appended to the **Fields** collection by assigning a value to the field object as if it already existed in the collection. The assignment will trigger the automatic creation and appending of the **Field** object, then the assignment will be completed.</span></span>

<span data-ttu-id="a9f08-167">将 **Field** 追加到 **Record** 对象的 **Fields** 集合之后，可调用 **Fields** 集合的 **Update** 方法以保存更改。</span><span class="sxs-lookup"><span data-stu-id="a9f08-167">After appending a **Field** to a **Record** object's **Fields** collection, call the **Update** method of the **Fields** collection to save the change.</span></span>

