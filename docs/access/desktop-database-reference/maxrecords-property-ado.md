---
title: MaxRecords 属性 (ADO)
TOCTitle: MaxRecords Property (ADO)
ms:assetid: 424b2d41-073a-3fbe-30aa-99fac94f9a81
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249195(v=office.15)
ms:contentKeyID: 48544475
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: d8753bf09655371042e97ead083c6849f1736b8b
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467054"
---
# <a name="maxrecords-property-ado"></a>MaxRecords 属性 (ADO)


**适用于**： Access 2013 |Office 2013

指示通过查询返回到 [Recordset](recordset-object-ado.md) 的最大记录数。

## <a name="settings-and-return-values"></a>设置和返回值

设置或返回一个 **Long** 值，指示要返回的最大记录数。默认值为 0（没有限制）。

## <a name="remarks"></a>备注

使用 **MaxRecords** 属性可限制提供程序从数据源返回的记录数。此属性的默认设置为 0，表示提供程序可返回所有请求的记录。

**Recordset** 关闭时 **MaxRecords** 属性为可读/写属性，打开时为只读属性。

