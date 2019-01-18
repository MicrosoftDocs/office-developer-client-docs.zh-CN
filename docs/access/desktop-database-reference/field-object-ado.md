---
title: Field 对象的 ActiveX 数据对象 (ADO)
TOCTitle: Field object (ADO)
ms:assetid: 1dbd535e-48ad-a5c8-a1b2-6776c1e3e19d
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248968(v=office.15)
ms:contentKeyID: 48543600
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: a2bf17029a706ad6902a8a01a14e73183f94d7a4
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28715213"
---
# <a name="field-object-ado"></a>Field 对象 (ADO)


**适用于**： Access 2013、 Office 2013

表示具有常规数据类型的数据列。

## <a name="remarks"></a>说明

每个 **Field** 对应于 [Recordset](recordset-object-ado.md) 中的一个列。使用 [Field](value-property-ado.md) 对象的 **Value** 属性可以设置或返回当前记录的数据。取决于提供程序所公开的功能， **Field** 对象的某些集合、方法或属性可能不可用。

使用 **Field** 对象的集合、方法和属性，可以执行以下操作：

  - 使用 [Name](name-property-ado.md) 属性返回字段的名称。

  - 使用 **Value** 属性查看或更改字段中的数据。 **Value** 是 **Field** 对象的默认属性。

  - 使用 [Type](type-property-ado.md)、[Precision](precision-property-ado.md) 和 [NumericScale](numericscale-property-ado.md) 属性，返回字段的基本特征。

  - 使用 [DefinedSize](definedsize-property-ado.md) 属性，返回字段的声明大小。

  - 使用 [ActualSize](actualsize-property-ado.md) 属性，返回给定字段中数据的实际大小。

  - 使用 [Attributes](attributes-property-ado.md) 属性和 [Properties](properties-collection-ado.md) 集合，确定给定字段所支持的功能类型。

  - 使用 [AppendChunk](appendchunk-method-ado.md) 和 [GetChunk](getchunk-method-ado.md) 方法，对包含长二进制或长字符数据的字段的值进行操作。

  - 如果提供程序支持批更新，则在批更新过程中，使用 [OriginalValue](originalvalue-property-ado.md) 和 [UnderlyingValue](underlyingvalue-property-ado.md) 属性解决字段值中的差异。

打开 **Field** 对象的 **Recordset** 之前，所有元数据属性（**Name**、**Type**、**DefinedSize**、**Precision** 和 **NumericScale**）都可用。在此时设置它们有助于动态构造窗体。

