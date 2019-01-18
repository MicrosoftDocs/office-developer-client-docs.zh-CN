---
title: OriginalValue 属性 (ADO)
TOCTitle: OriginalValue property (ADO)
ms:assetid: 02ffc728-4692-d439-e2a6-2f02cca53a71
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248798(v=office.15)
ms:contentKeyID: 48542974
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 0724320e1aaa1e7bfd3ceab8cf54afd5921c7425
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28700421"
---
# <a name="originalvalue-property-ado"></a>OriginalValue 属性 (ADO)

**适用于**： Access 2013、 Office 2013

指示记录发生任何更改之前的 [Field](field-object-ado.md) 值。

## <a name="return-value"></a>返回值

返回一个 **Variant** 值，表示发生任何更改之前的字段值。

## <a name="remarks"></a>备注

使用 **OriginalValue** 属性可从当前记录返回字段的原始字段值。

在*即时更新模式*中 （其中提供程序将更改写入基础数据源后调用[Update](update-method-ado.md)方法）， **OriginalValue**属性返回字段值的发生任何更改之前的状态 (也就是说，因为上次调用**Update**方法）。 该值与 [CancelUpdate](cancelupdate-method-ado.md) 方法用于替换 [Value](value-property-ado.md) 属性的值相同。

以*批更新模式*（顺序提供程序缓存多个更改和将它们写入到基础数据源，仅在调用[UpdateBatch](updatebatch-method-ado.md)方法），则**OriginalValue**属性返回任何之前存在的字段值更改 （即，因为呼叫的最后一个**UpdateBatch**方法）。 该值与 [CancelBatch](cancelbatch-method-ado.md) 方法用于替换 **Value** 属性的值相同。 与 [UnderlyingValue](underlyingvalue-property-ado.md) 属性一起使用此属性时，可以解决批更新引发的冲突。

## <a name="record"></a>Record

对于 [Record](record-object-ado.md) 对象，在调用 **Update** 之前，添加字段的 [OriginalValue](update-method-ado.md) 属性将为空。

