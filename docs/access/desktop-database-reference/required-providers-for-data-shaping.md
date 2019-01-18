---
title: 需要数据成型提供程序
TOCTitle: Required providers for data shaping
ms:assetid: eb8933fb-d533-3ea7-e045-35c1ca585765
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250194(v=office.15)
ms:contentKeyID: 48548488
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: ffb45599c01121204fe036cfdf60f17865388cd4
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28706672"
---
# <a name="required-providers-for-data-shaping"></a>需要数据成型提供程序

**适用于**： Access 2013、 Office 2013

数据定形通常需要两个提供程序。即服务提供程序 ([Data Shaping Service for OLE DB](microsoft-data-shaping-service-for-ole-db-ado-service-provider.md)) 和数据提供程序（如 OLE DB Provider for SQL Server），前者提供数据定形功能，后者提供用于填充已定形的 [Recordset](recordset-object-ado.md) 的数据行。

可以将服务提供程序的名称 (MSDataShape) 指定为 [Connection](connection-object-ado.md) 对象的 [Provider](provider-property-ado.md) 属性的值，或连接字符串关键字"Provider=MSDataShape;"。

可以为的**数据提供程序**动态属性，将添加到**Connection**对象的[Properties](properties-collection-ado.md)集合中 Data Shaping Service for OLE DB 或连接字符串关键字的值指定的数据提供程序名称"**数据提供程序 = *** 提供程序*"。

如果未填充 **Recordset**（例如，在构造的 **Recordset** 中，用 NEW 关键字创建其中的列），则不需要数据提供程序。这种情况下，请指定“**Data Provider=** none;”。

## <a name="example"></a>示例

```vb 
 
Dim cnn As New ADODB.Connection 
cnn.Provider = "MSDataShape" 
cnn.Open "Data Provider=SQLOLEDB;Integrated Security=SSPI;Database=Northwind" 
```

