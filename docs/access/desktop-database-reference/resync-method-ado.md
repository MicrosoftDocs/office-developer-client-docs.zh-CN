---
title: Resync 方法 (ADO)
TOCTitle: Resync method (ADO)
ms:assetid: f594a200-56e6-fcf5-9b0a-900c56377f24
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250251(v=office.15)
ms:contentKeyID: 48548717
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: fa483d86dc345968607a0752f0552ddccfe7fef5
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28709871"
---
# <a name="resync-method-ado"></a>Resync 方法 (ADO)

**适用于**： Access 2013、 Office 2013

用于从基础数据库刷新当前 [Recordset](recordset-object-ado.md) 对象中的数据或刷新 [Record](fields-collection-ado.md) 对象的 [Fields](record-object-ado.md) 集合中的数据。

## <a name="syntax"></a>语法

*记录集*。Resync*AffectRecords*， *ResyncValues*

*记录*。 *字段*。Resync*ResyncValues*

## <a name="parameters"></a>Parameters

|参数|说明|
|:--------|:----------|
|*AffectRecords* |可选。[AffectEnum](affectenum.md) 值，用于确定 **Resync** 方法将影响的记录数。默认值为 **adAffectAll** 。对于 **Record** 对象的 **Fields** 集合的 **Resync** 方法，此值不可用。|
|*ResyncValues* |可选。[ResyncEnum](resyncenum.md) 值，用于指定是否覆盖基础值。默认值为 **adResyncAllValues** 。|

## <a name="remarks"></a>说明

### <a name="recordset"></a>Recordset

使用 **Resync** 方法可以用基础数据库重新同步当前 **Recordset** 中的记录。如果使用的是静态或仅向前型游标，但希望查看基础数据库中的任何更改，该方法将很有帮助。

如果将 [CursorLocation](cursorlocation-property-ado.md) 属性设置为 **adUseClient** ，那么 **Resync** 只能用于非只读 **Recordset** 对象。

与 [Requery](requery-method-ado.md) 方法不同， **Resync** 方法不重新执行 **Recordset** 对象的基础命令。基础数据库中的新记录将不可见。

如果由于与基础数据冲突（例如，记录已被其他用户删除）使得重新同步的尝试失败，则提供程序将向 [Errors](errors-collection-ado.md) 集合返回警告，且发生运行时错误。可以使用 [Filter](filter-property-ado.md) 属性 (**adFilterConflictingRecords**) 和 [Status](status-property-ado-recordset.md) 属性查找存在冲突的记录。

如果设置了 [Unique Table](unique-table-unique-schema-unique-catalog-properties-dynamic-ado.md) 和 [Resync Command](resync-command-property-dynamic-ado.md) 动态属性，且 **Recordset** 是对多个表执行 JOIN 操作的结果，那么 **Resync** 方法将仅对在 **Unique Table** 属性中命名的表执行 **Resync Command** 属性中给定的命令。

### <a name="fields"></a>字段

**Resync** 方法可用于用基础数据源重新同步 **Record** 对象的 **Fields** 集合的值。 [Count](count-property-ado.md) 属性不受此方法的影响。

如果*ResyncValues*设置为**adResyncAllValues** （默认值），然后[UnderlyingValue](underlyingvalue-property-ado.md)、[值](value-property-ado.md)和[OriginalValue](originalvalue-property-ado.md)属性集合中的[Field](field-object-ado.md)对象的同步。 如果*ResyncValues*设置为**adResyncUnderlyingValues**，同步仅将**UnderlyingValue**属性。

每个 **Field** 对象的 **Status** 属性值在调用时也会影响 **Resync** 的行为。如果 **Field** 对象的 **Status** 值为 **adFieldPendingUnknown** 或 **adFieldPendingInsert** ，则 **Resync** 无效。如果对象的 **Status** 值为 **adFieldPendingChange** 或 **adFieldPendingDelete** ，则 **Resync** 会同步仍存在于数据源中的字段的数据值。

**Resync** 不会修改 **Field** 对象的 **Status** 值，除非在调用 **Resync** 时发生错误。例如，如果字段不再存在，提供程序将为 **Field** 对象返回适当的 **Status** 值，如 **adFieldDoesNotExist** 。返回的 **Status** 值可能被逻辑合并在 **Status** 属性值内。

