---
title: AbsolutePosition 属性 (ADO)
TOCTitle: AbsolutePosition property (ADO)
ms:assetid: 500be001-9fa1-177b-f19d-acf003a0cdc2
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249259(v=office.15)
ms:contentKeyID: 48544787
ms.date: 10/17/2018
mtps_version: v=office.15
ms.openlocfilehash: a090630b5db741f761314f598fcc783dd124d1cf
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25881858"
---
# <a name="absoluteposition-property-ado"></a>AbsolutePosition 属性 (ADO)

**适用于**： Access 2013、 Office 2013

指示 [Recordset](recordset-object-ado.md) 对象的当前记录的序号位置。

## <a name="settings-and-return-values"></a>设置和返回值

设置或返回一个 **Long** 值，该值的范围为 1 到 **Recordset** 对象中的记录数 ([RecordCount](recordcount-property-ado.md))；或返回 [PositionEnum](positionenum.md) 值之一。

## <a name="remarks"></a>说明

为了设置**AbsolutePosition**属性，ADO 要求所使用的 OLE DB 提供程序实现 IRowsetLocate 接口。

访问使用只进游标或动态游标打开的 **Recordset** 的 **AbsolutePosition** 属性会引发错误 **adErrFeatureNotAvailable**。对于其他游标类型，只要提供程序支持 IRowsetScroll 接口，就能返回正确的位置。如果提供程序不支持 *IRowsetScroll* 接口，该属性会设置为 **adPosUnknown**。请参阅您的提供程序文档，以确定它是否支持 *IRowsetScroll*。

使用 **AbsolutePosition** 属性，可以根据记录在 **Recordset** 对象中的序号位置移动到记录，或确定当前记录的序号位置。提供程序必须支持相应的功能，此属性才可用。

和 [AbsolutePage](absolutepage-property-ado.md) 属性一样， **AbsolutePosition** 将从 1 开始，当前记录为 **Recordset** 中的第一条记录时，它等于 1。可以通过 **RecordCount** 属性获得 [Recordset](recordcount-property-ado.md) 对象中的记录总数。

设置时， **AbsolutePosition**属性，即使它为与当前缓存中的记录，ADO 将缓存重新加载与一组新开头您指定的记录的记录。 [CacheSize](cachesize-property-ado.md) 属性将确定此组的大小。


> [!NOTE]
> [!注释] 不应当将 **AbsolutePosition** 属性用作代理记录号。 当删除位于给定记录之前的记录时，给定记录的位置会发生改变。 如果对 **Recordset** 对象进行了重新查询或重新打开操作，则也不能保证给定的记录仍然具有相同的 **AbsolutePosition** 。 仍然书签的建议的方式保留和返回到给定位置，而且是适用于所有类型的**Recordset**对象的定位的唯一方法。


