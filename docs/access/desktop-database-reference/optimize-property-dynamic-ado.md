---
title: Optimize dynamic 属性 (ADO)
TOCTitle: Optimize dynamic property (ADO)
ms:assetid: 2253b052-2d8a-f6f0-f8b8-f56e79d243de
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249001(v=office.15)
ms:contentKeyID: 48543705
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 11bb7872514a828fdd97fb404f5366c35ff9a883
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32288250"
---
# <a name="optimize-dynamic-property-ado"></a>Optimize dynamic 属性 (ADO)


**适用于**：Access 2013、Office 2013

指定是否应在字段上创建索引。

## <a name="settings-and-return-values"></a>设置和返回值

设置或返回一个 **Boolean** 值，指示是否应创建索引。

## <a name="remarks"></a>注解

索引可提高在 [Recordset](recordset-object-ado.md) 中对值进行查找和排序的操作性能。索引由 ADO 内部使用  无法在应用程序中显式访问或使用。

若要在字段上创建索引，请将 **Optimize** 属性设置为 **True** 。若要删除索引，请将此属性设置为 **False** 。

**Optimize** 是一个动态属性，会在 [CursorLocation](field-object-ado.md) 属性设置为 [adUseClient](properties-collection-ado.md) 时追加到 [Field](cursorlocation-property-ado.md) 对象的 **Properties** 集合中。

**用法**

```vb
    Dim rs As New Recordset
    Dim fld As Field
    rs.CursorLocation = adUseClient      'Enable index creation
    rs.Fields.Append "Field1", adChar, 35, adFldIsNullable
    rs.Open
    Set fld = rs.Fields(0)
    fld.Properties("Optimize") = True    'Create an index
    fld.Properties("Optimize") = False   'Delete an index
```
