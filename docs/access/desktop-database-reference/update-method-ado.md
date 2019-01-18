---
title: Update 方法 (ADO)
TOCTitle: Update method (ADO)
ms:assetid: fc88cab6-c379-bb4f-530c-da08107924e0
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250294(v=office.15)
ms:contentKeyID: 48548893
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: f077634abea6fadfe5c4305fc25b28e6d57bf13e
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28710634"
---
# <a name="update-method-ado"></a>Update 方法 (ADO)

**适用于**： Access 2013、 Office 2013

可保存对 [Recordset](recordset-object-ado.md) 对象的当前行或 [Record](fields-collection-ado.md) 对象的 [Fields](record-object-ado.md) 集合所做的任何更改。

## <a name="syntax"></a>语法

*记录集*。更新*字段*，*值*

*记录*。 *字段*。更新

## <a name="parameters"></a>Parameters

|参数|说明|
|:--------|:----------|
|*Fields* |可选。一个表示单个名称的 **Variant** ，或表示要修改的字段的名称或序号位置的 **Variant** 数组。|
|*Values* |可选。一个表示单个名称的 **Variant** ，或表示新记录中字段值的 **Variant** 数组。|

## <a name="remarks"></a>备注

### <a name="recordset"></a>Recordset

使用 **Update** 方法可以保存自调用 **AddNew** 方法或更改现有记录中的任何字段值之后对 [Recordset](addnew-method-ado.md) 对象的当前记录所做的任何更改。 **Recordset** 对象必须支持更新。

若要设置字段值，请执行下列操作之一：

- 将值赋给 [Field](field-object-ado.md) 对象的 [Value](value-property-ado.md) 属性并调用 **Update** 方法。

- 调用 **Update** 时将字段名和值作为参数传递。

- 调用 **Update** 时传递字段名数组和值数组。

在使用字段和值的数组时，两个数组中的元素个数必须相同。同时，字段名的次序必须与字段值的次序匹配。如果字段和值的个数和次序不匹配，则会发生错误。

如果 **Recordset** 对象支持批更新，则在调用 [UpdateBatch](updatebatch-method-ado.md) 方法前，可以在本地缓存对一个或多个记录所做的多次更改。如果在调用 **UpdateBatch** 方法时正在编辑当前记录或添加新记录，则 ADO 在将批更改传输到提供程序前，将自动调用 **Update** 方法将所有挂起的更改保存到当前记录。

如果在调用 **Update** 方法之前从正在添加或编辑的记录移开，则 ADO 将自动调用 **Update** 来保存所做的更改。如果要取消对当前记录所做的更改或放弃新添加的记录，则必须调用 [CancelUpdate](cancelupdate-method-ado.md) 方法。

调用 **Update** 方法之后，当前记录仍然是当前记录。

### <a name="record"></a>Record

可以使用 **Update** 方法完成在 [Record](fields-collection-ado.md) 对象的 **Fields** 集合中添加、删除或更新字段的操作。

例如，用 **Delete** 方法删除的字段被立即加上删除标记，但仍保留在集合中。必须调用 **Update** 方法来从提供程序的集合中实际删除这些字段。

