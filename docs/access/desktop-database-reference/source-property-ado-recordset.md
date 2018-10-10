---
title: Source 属性 (ADO Recordset)
TOCTitle: Source Property (ADO Recordset)
ms:assetid: 523ea81e-d011-8d87-436e-084b6eba0908
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249269(v=office.15)
ms:contentKeyID: 48544843
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: a3caeef4bb13ac4b68f3d3d5a62e0ce624d9d515
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25465965"
---
# <a name="source-property-ado-recordset"></a>Source 属性 (ADO Recordset)


**适用于**： Access 2013 |Office 2013

指示 [Recordset](recordset-object-ado.md) 对象的数据源。

## <a name="settings-and-return-values"></a>设置和返回值

设置一个 **String** 值或 [Command](command-object-ado.md) 对象引用；仅返回一个 **String** 值，该值指示 **Recordset** 的数据源。

## <a name="remarks"></a>备注

使用 **Source** 属性可指定使用 **Command** 对象变量、SQL 语句、存储过程或表名之一的 **Recordset** 对象的数据源。

如果将 **Source** 属性设置为 **Command** 对象，则 [Recordset](activeconnection-property-ado.md) 对象的 **ActiveConnection** 属性将继承所指定的 **Command** 对象的 **ActiveConnection** 属性值。然而，读取 **Source** 属性不会返回 **Command** 对象；而会返回 [Source](commandtext-property-ado.md) 属性被设置为的 **Command** 对象的 **CommandText** 属性。

如果**Source**属性是 SQL 语句、 存储的过程或表名，您可以通过传递[Open](open-method-ado-recordset.md)方法调用合适的*Options*参数来优化性能。

对于关闭的 **Recordset** 对象， **Source** 属性为可读/写属性；对于打开的 **Recordset** 对象，则为只读属性。

