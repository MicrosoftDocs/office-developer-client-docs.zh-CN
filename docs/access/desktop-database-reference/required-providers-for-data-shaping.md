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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32306655"
---
# <a name="required-providers-for-data-shaping"></a><span data-ttu-id="6f1a8-102">需要数据成型提供程序</span><span class="sxs-lookup"><span data-stu-id="6f1a8-102">Required providers for data shaping</span></span>

<span data-ttu-id="6f1a8-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="6f1a8-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="6f1a8-p101">数据定形通常需要两个提供程序。即服务提供程序 ([Data Shaping Service for OLE DB](microsoft-data-shaping-service-for-ole-db-ado-service-provider.md)) 和数据提供程序（如 OLE DB Provider for SQL Server），前者提供数据定形功能，后者提供用于填充已定形的 [Recordset](recordset-object-ado.md) 的数据行。</span><span class="sxs-lookup"><span data-stu-id="6f1a8-p101">Data shaping typically requires two providers. The service provider, [Data Shaping Service for OLE DB](microsoft-data-shaping-service-for-ole-db-ado-service-provider.md), supplies the data shaping functionality, and a data provider, such as the OLE DB Provider for SQL Server, supplies rows of data to populate the shaped [Recordset](recordset-object-ado.md).</span></span>

<span data-ttu-id="6f1a8-106">可以将服务提供程序的名称 (MSDataShape) 指定为 [Connection](connection-object-ado.md) 对象的 [Provider](provider-property-ado.md) 属性的值，或连接字符串关键字"Provider=MSDataShape;"。</span><span class="sxs-lookup"><span data-stu-id="6f1a8-106">The name of the service provider (MSDataShape) can be specified as the value of the [Connection](connection-object-ado.md) object [Provider](provider-property-ado.md) property or the connection string keyword "Provider=MSDataShape;".</span></span>

<span data-ttu-id="6f1a8-107">可将数据提供程序的名称指定为**数据提供程序**动态属性的值, 该属性将添加到由数据定形服务用于 OLE DB 的**connection**对象[Properties](properties-collection-ado.md)集合中, 或连接字符串关键字 "\*\*Data provider = \*\*\* \* Provider "。</span><span class="sxs-lookup"><span data-stu-id="6f1a8-107">The name of the data provider can be specified as the value of the **Data Provider** dynamic property, which is added to the **Connection** object [Properties](properties-collection-ado.md) collection by the Data Shaping Service for OLE DB, or the connection string keyword "\**Data Provider=\*\*\*provider*".</span></span>

<span data-ttu-id="6f1a8-p102">如果未填充 **Recordset**（例如，在构造的 **Recordset** 中，用 NEW 关键字创建其中的列），则不需要数据提供程序。这种情况下，请指定“**Data Provider=** none;”。</span><span class="sxs-lookup"><span data-stu-id="6f1a8-p102">No data provider is required if the **Recordset** is not populated (for example, as in a fabricated **Recordset** where columns are created with the NEW keyword). In that case, specify "**Data Provider=** none;".</span></span>

## <a name="example"></a><span data-ttu-id="6f1a8-110">示例</span><span class="sxs-lookup"><span data-stu-id="6f1a8-110">Example</span></span>

```vb 
 
Dim cnn As New ADODB.Connection 
cnn.Provider = "MSDataShape" 
cnn.Open "Data Provider=SQLOLEDB;Integrated Security=SSPI;Database=Northwind" 
```

