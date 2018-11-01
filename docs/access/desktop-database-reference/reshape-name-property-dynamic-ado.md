---
title: "Reshape Name 属性 \x97 动态 (ADO)"
TOCTitle: Reshape Name Property--Dynamic (ADO)
ms:assetid: 59ef99c8-da40-5cf6-b987-d47ea1433f45
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249307(v=office.15)
ms:contentKeyID: 48545030
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 1b2797d5e77e30a9e92639920960796a9d6cae52
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25872142"
---
# <a name="reshape-name-property--dynamic-ado"></a>Reshape Name 属性  动态 (ADO)


**适用于**： Access 2013、 Office 2013

指定 [Recordset](recordset-object-ado.md) 对象的名称。

## <a name="return-values"></a>返回值

返回一个表示 **Recordset** 的名称的 **String** 值。

## <a name="remarks"></a>备注

名称会在连接持续期间保持，或一直保持到 **Recordset** 关闭为止。

**Reshape Name** 属性主要与 [Microsoft Data Shaping Service for OLE DB](microsoft-data-shaping-service-for-ole-db-ado-service-provider.md) 服务提供程序的重构功能一起使用。为了参与重构，名称必须是唯一的。

此属性是只读属性，但可以在创建 Recordset 时间接设置。例如，如果 SHAPE 命令的子句创建了一个 Recordset 并使用"AS"关键字给了它一个别名，则这个别名将分配给 Reshape Name 属性。如果没有声明别名，则会给 Reshape Name 属性分配一个由 Data Shaping 服务生成的唯一名称。如果该别名与现有的 **Recordset** 的名称相同，除非其中一个被释放，否则这两个 **Recordset** 都不会进行重构。通过将 ADO 连接上的"Unique Reshape Names"（请参阅"Microsoft Data shaping service for OLE DB"）属性设置为 TRUE，可以更改默认行为。这样就赋予了 Data Shaping 服务在必要的情况下更改用户分配的名称的权限，从而确保唯一性。

当希望引用 SHAPE 命令中的 **Recordset** 时或由于其名称是由 Data Shaping 服务生成的而不知道该名称时，请使用 **Reshape Name** 属性。在这种情况下，可以将该命令与 **Reshape Name** 属性返回的字符串进行连接，从而生成 SHAPE 命令。

**Reshape Name** 是一个动态属性，会在 **CursorLocation** 属性设置为 [adUseClient](properties-collection-ado.md) 时追加到 [Recordset](cursorlocation-property-ado.md) 对象的 **Properties** 集合中。

