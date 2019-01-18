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
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28706077"
---
# <a name="append-method-ado"></a>Append 方法 (ADO)

**适用于**： Access 2013、 Office 2013

用于将对象追加到集合。如果集合为 [Fields](fields-collection-ado.md)，则在将对象追加到集合之前，可能会创建新的 [Field](field-object-ado.md) 对象。

## <a name="syntax"></a>语法

*集合*。将*对象*追加

*字段*。追加*名称*、*类型*、 *DefinedSize*、 *Attrib*、 *FieldValue*

## <a name="parameters"></a>Parameters

|参数|说明|
|:--------|:----------|
|*collection* |集合对象。|
|*fields* |**Fields** 集合。|
|*object* |对象变量，表示要追加的对象。|
|*Name* |**字符串**值，包含新的 **Field** 对象的名称，不能与 *fields* 中任何其他对象同名。|
|*Type* |[DataTypeEnum](datatypeenum.md) 值，其默认值为 **adEmpty** ，用于指定新字段的数据类型。ADO 不支持以下数据类型，在将新字段追加到 **Recordset** 时不应当使用这些数据类型： **adIDispatch** 、 **adIUnknown** 、 **adVariant** 。|
|*DefinedSize* |可选。**长整型**值，表示新字段的定义大小，以字符数或字节数计。此参数的默认值由 *Type* 决定。DefinedSize 大于 255 字节的字段将被视为可变长度列。（未指定默认 *DefinedSize*。）|
|*Attrib* |可选。[FieldAttributeEnum](fieldattributeenum.md) 值，其默认值为 **adFldDefault**，用于指定新字段的属性。如果未指定此值，则字段所包含的属性由 *Type* 决定。|
|*FieldValue* |可选。 **变量型** ，表示新字段的值。如果未指定此值，则为字段追加一个 Null 值。|

## <a name="remarks"></a>说明

### <a name="parameters-collection"></a>Parameters 集合

在将 [Parameter](type-property-ado.md) 对象追加到 [Parameters](parameter-object-ado.md) 集合之前，必须设置其 **Type** 属性。如果选择可变长度的数据类型，那么还必须将 [Size](size-property-ado.md) 属性设置为大于零的值。

自己描述参数可以将对提供程序的调用次数减至最少，从而改进使用存储过程或参数化查询时的性能。不过，必须了解与要调用的存储过程或参数化查询所关联的参数属性。

可以使用 [CreateParameter](createparameter-method-ado.md) 方法创建具适当属性设置的 **Parameter** 对象，并用 **Append** 方法将对象添加到 [Parameters](parameters-collection-ado.md) 集合。这样一来，无需调用参数信息的提供程序，即可设置和返回参数值。如果正在写入未提供参数信息的提供程序，则必须使用此方法手动填充 **Parameters** 集合，才能使用参数。

### <a name="fields-collection"></a>Fields 集合

添加**Field**对象的[Record](record-object-ado.md)对象，而不**Recordset**对象时， *FieldValue*参数才有效。 通过 **Record** 对象，可以同时追加字段和提供值。 而对于 **Recordset** 对象，当 **Recordset** 关闭时必须创建字段，然后打开 **Recordset** 并为字段赋值。


> [!NOTE]
> [!注释] 对于已追加到 **Record** 对象的 **Fields** 集合中的新 **Field** 对象，必须先设置 [Value](value-property-ado.md) 属性，然后才能指定其他任何 **Field** 属性。首先，必须为 **Value** 属性赋予特定值，并对 [Fields](update-method-ado.md) 集合调用 **Update**。然后，可以访问诸如 [Type](type-property-ado.md) 或 [Attributes](attributes-property-ado.md) 等其他属性。


以下数据类型 (**DataTypeEnum**) 的 **Field** 对象不能追加到 **Fields** 集合，并将引发错误：**adArray**、**adChapter**、**adEmpty**、**adPropVariant** 和 **adUserDefined**。此外，ADO 不支持以下数据类型：**adIDispatch**、**adIUnknown** 和 **adIVariant**。对于这些类型，追加时不会发生错误，但使用时会产生不可预测的结果，如内存溢出。

### <a name="recordset"></a>Recordset

如果在调用 [Append](cursorlocation-property-ado.md) 方法之前未设置 **CursorLocation** 属性，则当调用 **Recordset** 对象的 **Open** 方法时， [CursorLocation](cursorlocationenum.md) 将自动设置为 [adUseClient](recordset-object-ado.md) （ [CursorLocationEnum](open-method-ado-recordset.md) 值）。

如果对打开的 **Recordset** 的 **Fields** 集合调用 **Append** 方法，或对设置了 **ActiveConnection** 属性的 [Recordset](activeconnection-property-ado.md) 调用该方法，则将发生运行时错误。只能将字段追加到未打开且尚未连接到数据源的 **Recordset** 。当 **Recordset** 对象用 [CreateRecordset](createrecordset-method-rds.md) 方法构成，或被分配给某对象变量时，通常为这种情况。

### <a name="record"></a>Record

如果对打开的 **Record** 的 **Fields** 集合调用 **Append** 方法，将不会发生运行时错误。新字段将添加到 **Record** 对象的 **Fields** 集合。如果 **Record** 派生自 **Recordset** ，那么新字段不会显示在 **Recordset** 对象的 **Fields** 集合中。

若要创建一个不存在的字段并追加到 **Fields** 集合，那么可以为字段对象赋值，如同它已经存在于集合中一样。赋值将触发 **Field** 对象的自动创建和追加，然后将完成赋值。

将 **Field** 追加到 **Record** 对象的 **Fields** 集合之后，可调用 **Fields** 集合的 **Update** 方法以保存更改。

