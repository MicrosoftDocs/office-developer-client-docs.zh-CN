---
title: MaxRecords 属性 (ADO)
TOCTitle: MaxRecords property (ADO)
ms:assetid: 424b2d41-073a-3fbe-30aa-99fac94f9a81
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249195(v=office.15)
ms:contentKeyID: 48544475
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 8ed643ca3b1341d7f933901e15c20c84acb025f5
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28709353"
---
# <a name="maxrecords-property-ado"></a>MaxRecords 属性 (ADO)


**适用于**： Access 2013、 Office 2013

指示通过查询返回到 [Recordset](recordset-object-ado.md) 的最大记录数。

## <a name="settings-and-return-values"></a>设置和返回值

设置或返回一个 **Long** 值，指示要返回的最大记录数。默认值为 0（没有限制）。

## <a name="remarks"></a>备注

使用 **MaxRecords** 属性可限制提供程序从数据源返回的记录数。此属性的默认设置为 0，表示提供程序可返回所有请求的记录。

**Recordset** 关闭时 **MaxRecords** 属性为可读/写属性，打开时为只读属性。

