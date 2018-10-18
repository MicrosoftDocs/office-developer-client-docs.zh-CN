---
title: Status 属性 (ADO Field)
TOCTitle: Status Property (ADO Field)
ms:assetid: 7a7b45e8-2934-2e8e-77fa-a4f38272548d
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249507(v=office.15)
ms:contentKeyID: 48545795
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 41534132fd4f199294e317310215d4f6e8ac5426
ms.sourcegitcommit: a49b77f4c8cec69f90656a86f0872cf34c35968e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2018
ms.locfileid: "25603264"
---
# <a name="status-property-ado-field"></a>Status 属性 (ADO Field)


**适用于**： Access 2013 |Office 2013

指示 [Field](field-object-ado.md) 对象的状态。

<<<<<<< 标头
## <a name="return-value"></a>返回值
=======
## <a name="return-value"></a>返回值
>>>>>>> master

返回一个 [FieldStatusEnum](fieldstatusenum.md) 值。默认值是 **adFieldOK** 。

## <a name="remarks"></a>备注

对于 **Recordset** 对象的字段，此属性通常返回 [adFieldOK](recordset-object-ado.md) 。

对 [Record](fields-collection-ado.md) 对象的 [Fields](record-object-ado.md) 集合所做的添加和删除均保存在缓存中，直到调用 [Update](update-method-ado.md) 方法时才生效。通过 **Status** 属性可确定成功添加或删除的字段。

为了提高性能，架构更改均保存在缓存中，直到调用 **Update** 时才生效，然后在批量优化更新中进行更改。 如果未调用 **Update** 方法，则不会更新服务器。 如果任何更新失败，则返回错误，并且 **Status** 属性将指示操作和错误状态代码的组合值。 例如， **adFieldPendingInsert** **或** **adFieldPermissionDenied** 。 每个 **Field** 的 **Status** 属性均可用于确定未添加、修改或删除 **Field** 的原因。 仅有意义地对**记录**公开**状态**。**Fields**集合并不**记录集**。**Fields**集合。

添加、修改或删除 **Field** 时会出现两个问题。如果用户要删除一个 **Field** ，则在 **Fields** 集合中标识该字段以便删除。如果随后由于用户试图删除不具权限的 **Field** 而导致 **Update** 返回错误，则 **Field** 的状态将为 **adFieldPermissionDenied** **或** **adFieldPendingDelete** 。调用 [CancelUpdate](cancelupdate-method-ado.md) 方法可还原原始值并将 **Status** 设置为 **adFieldOK** 。同样，添加新的 **Field** 并提供不恰当的值也会导致 **Update** 方法返回错误。此时，新的 **Field** 将位于 **Fields** 集合中，其状态为 **adFieldPendingInsert** （或 **adFieldCantCreate** ）。可以为该新 **Field** 提供一个恰当的值并再次调用 **Update** 。注意，调用 **Resync** 则需要请求提供程序。

