---
title: Microsoft Data Shaping Service for OLE DB（ADO 服务提供程序）
TOCTitle: Microsoft Data Shaping Service for OLE DB (ADO Service Provider)
ms:assetid: 6e6e5f39-6f43-7c7b-5812-796096d1d31b
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249436(v=office.15)
ms:contentKeyID: 48545511
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 5065b966608f8d6a3ef1cb05be890b9a1f147dc8
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32288958"
---
# <a name="microsoft-data-shaping-service-for-ole-db-ado-service-provider"></a>用于 OLE DB 的 Microsoft 数据成型服务（ADO 服务提供程序）


**适用于**：Access 2013、Office 2013

Microsoft Data Shaping Service for OLE DB 服务提供程序支持以下操作，即根据数据提供程序构造分层（定形）的 [Recordset](recordset-object-ado.md) 对象。

## <a name="provider-keyword"></a>提供程序关键字

要调用 Data Shaping Service for OLE DB，请在连接字符串中指定以下关键字和值。

```vb 
 
"Provider=MSDataShape" 
```

## <a name="dynamic-properties"></a>动态属性

调用此服务提供程序时，会将以下动态属性添加到 [Connection](connection-object-ado.md) 对象的 [Properties](properties-collection-ado.md) 集合中。

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>动态属性名称</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Unique Reshape Names</strong></p></td>
<td><p>指示是否允许对其<strong>改变名称</strong>属性使用重复值的<strong>Recordset</strong>对象。 如果此动态属性为<strong>True</strong> , 并且使用与现有<strong>recordset</strong>相同的用户指定的重新整形名称创建新的<strong>recordset</strong> , 则会修改新的<strong>recordset</strong>对象的重定名称, 以使其成为唯一的。 如果此属性为<strong>False</strong> , 并且使用与现有<strong>recordset</strong>相同的用户指定的重命名名称创建新的<strong>recordset</strong> , 则这两个<strong>recordset</strong>对象的名称改变名称相同。 因此, 只要两个记录集都存在, 则这两个<strong>recordset</strong>都不能被重整形。 该属性的默认值是 <strong>False</strong>。</p></td>
</tr>
<tr class="even">
<td><p><strong>Data Provider</strong></p></td>
<td><p>指示提供程序的名称，该程序将提供要定形的行。如果不使用提供程序来提供行，则此值可以是 NONE。</p></td>
</tr>
</tbody>
</table>


您还可以在连接字符串中将可写动态属性的名称指定为关键字，从而设置这些属性。例如，在 Microsoft Visual Basic 中，通过以下代码将 **Data Provider** 动态属性设置为"MSDASQL"：

```vb 
 
Dim cn as New ADODB.Connection 
cn.Open "Provider=MSDataShape;Data Provider=MSDASQL" 
```

您还可以将某个动态属性的名称指定为 [Properties](properties-collection-ado.md) 属性的索引，从而设置或检索该动态属性。例如，可以获取并输出 **Data Provider** 动态属性的当前值，然后设置一个新值，如下所示：

```vb 
 
Debug.Print cn.Properties("Data Provider") 
cn.Properties("Data Provider") = "MSDASQL" 
```

有关数据定形的详细信息，请参阅[数据定形摘要](data-shaping.md)。

