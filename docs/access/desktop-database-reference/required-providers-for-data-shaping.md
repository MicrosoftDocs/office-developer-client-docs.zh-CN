---
title: 数据定形必需的提供程序
TOCTitle: Required Providers for Data Shaping
ms:assetid: eb8933fb-d533-3ea7-e045-35c1ca585765
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250194(v=office.15)
ms:contentKeyID: 48548488
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: de8634503c81bd2c66eeda0c64a8b1ff1b6f5363
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25885348"
---
# <a name="required-providers-for-data-shaping"></a>数据定形必需的提供程序


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

