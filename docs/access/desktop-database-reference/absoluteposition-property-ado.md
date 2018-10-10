---
title: AbsolutePosition 属性 (ADO)
TOCTitle: AbsolutePosition Property (ADO)
ms:assetid: 500be001-9fa1-177b-f19d-acf003a0cdc2
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249259(v=office.15)
ms:contentKeyID: 48544787
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 3258ffcab87b16e4931c9881a8e8d1cd2143262f
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468465"
---
# <a name="absoluteposition-property-ado"></a>AbsolutePosition 属性 (ADO)


**适用于**： Access 2013 |Office 2013

指示 [Recordset](recordset-object-ado.md) 对象的当前记录的序号位置。

## <a name="settings-and-return-values"></a>设置和返回值

设置或返回一个 **Long** 值，该值的范围为 1 到 **Recordset** 对象中的记录数 ([RecordCount](recordcount-property-ado.md))；或返回 [PositionEnum](positionenum.md) 值之一。

## <a name="remarks"></a>备注

为了设置 **AbsolutePosition** 属性，ADO 要求所使用的 OLE DB 提供程序实现 IRowsetLocate 接口。

访问使用只进游标或动态游标打开的 **Recordset** 的 **AbsolutePosition** 属性会引发错误 **adErrFeatureNotAvailable**。对于其他游标类型，只要提供程序支持 IRowsetScroll 接口，就能返回正确的位置。如果提供程序不支持 *IRowsetScroll* 接口，该属性会设置为 **adPosUnknown**。请参阅您的提供程序文档，以确定它是否支持 *IRowsetScroll*。

使用 **AbsolutePosition** 属性，可以根据记录在 **Recordset** 对象中的序号位置移动到记录，或确定当前记录的序号位置。提供程序必须支持相应的功能，此属性才可用。

和 [AbsolutePage](absolutepage-property-ado.md) 属性一样， **AbsolutePosition** 将从 1 开始，当前记录为 **Recordset** 中的第一条记录时，它等于 1。可以通过 **RecordCount** 属性获得 [Recordset](recordcount-property-ado.md) 对象中的记录总数。

设置 **AbsolutePosition** 属性时，即使设置为当前缓存中的记录，ADO 也会向缓存中重新加载从指定的记录开始的一组新记录。 [CacheSize](cachesize-property-ado.md) 属性将确定此组的大小。


> [!NOTE]
> <P>[!注释] 不应使用 <STRONG>AbsolutePosition</STRONG> 属性作为代理记录号。当删除位于给定记录之前的记录时，给定记录的位置会发生改变。如果对 <STRONG>Recordset</STRONG> 对象进行了重新查询或重新打开操作，则也不能保证给定的记录仍然具有相同的 <STRONG>AbsolutePosition</STRONG> 。仍然建议采用书签保留和返回到给定位置，而且这是唯一能适用于所有 <STRONG>Recordset</STRONG> 对象类型的定位方法。</P>


