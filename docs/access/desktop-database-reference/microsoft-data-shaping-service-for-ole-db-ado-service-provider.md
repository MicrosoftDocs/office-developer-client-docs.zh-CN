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
# <a name="microsoft-data-shaping-service-for-ole-db-ado-service-provider"></a><span data-ttu-id="8a4f5-102">用于 OLE DB 的 Microsoft 数据成型服务（ADO 服务提供程序）</span><span class="sxs-lookup"><span data-stu-id="8a4f5-102">Microsoft Data Shaping Service for OLE DB (ADO Service Provider)</span></span>


<span data-ttu-id="8a4f5-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="8a4f5-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="8a4f5-104">Microsoft Data Shaping Service for OLE DB 服务提供程序支持以下操作，即根据数据提供程序构造分层（定形）的 [Recordset](recordset-object-ado.md) 对象。</span><span class="sxs-lookup"><span data-stu-id="8a4f5-104">The Microsoft Data Shaping Service for OLE DB service provider supports the construction of hierarchical (shaped) [Recordset](recordset-object-ado.md) objects from a data provider.</span></span>

## <a name="provider-keyword"></a><span data-ttu-id="8a4f5-105">提供程序关键字</span><span class="sxs-lookup"><span data-stu-id="8a4f5-105">Provider Keyword</span></span>

<span data-ttu-id="8a4f5-106">要调用 Data Shaping Service for OLE DB，请在连接字符串中指定以下关键字和值。</span><span class="sxs-lookup"><span data-stu-id="8a4f5-106">To invoke the Data Shaping Service for OLE DB, specify the following keyword and value in the connection string.</span></span>

```vb 
 
"Provider=MSDataShape" 
```

## <a name="dynamic-properties"></a><span data-ttu-id="8a4f5-107">动态属性</span><span class="sxs-lookup"><span data-stu-id="8a4f5-107">Dynamic Properties</span></span>

<span data-ttu-id="8a4f5-108">调用此服务提供程序时，会将以下动态属性添加到 [Connection](connection-object-ado.md) 对象的 [Properties](properties-collection-ado.md) 集合中。</span><span class="sxs-lookup"><span data-stu-id="8a4f5-108">When this service provider is invoked, the following dynamic properties are added to the [Connection](connection-object-ado.md) object's [Properties](properties-collection-ado.md) collection.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="8a4f5-109">动态属性名称</span><span class="sxs-lookup"><span data-stu-id="8a4f5-109">Dynamic Property Name</span></span></p></th>
<th><p><span data-ttu-id="8a4f5-110">说明</span><span class="sxs-lookup"><span data-stu-id="8a4f5-110">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8a4f5-111"><strong>Unique Reshape Names</strong></span><span class="sxs-lookup"><span data-stu-id="8a4f5-111"><strong>Unique Reshape Names</strong></span></span></p></td>
<td><p><span data-ttu-id="8a4f5-112">指示是否允许对其<strong>改变名称</strong>属性使用重复值的<strong>Recordset</strong>对象。</span><span class="sxs-lookup"><span data-stu-id="8a4f5-112">Indicates whether <strong>Recordset</strong> objects with duplicate values for their <strong>Reshape Name</strong> properties are allowed.</span></span> <span data-ttu-id="8a4f5-113">如果此动态属性为<strong>True</strong> , 并且使用与现有<strong>recordset</strong>相同的用户指定的重新整形名称创建新的<strong>recordset</strong> , 则会修改新的<strong>recordset</strong>对象的重定名称, 以使其成为唯一的。</span><span class="sxs-lookup"><span data-stu-id="8a4f5-113">If this dynamic property is <strong>True</strong> and a new <strong>Recordset</strong> is created with the same user-specified reshape name as an existing <strong>Recordset</strong>, then the new <strong>Recordset</strong> object's reshape name is modified to make it unique.</span></span> <span data-ttu-id="8a4f5-114">如果此属性为<strong>False</strong> , 并且使用与现有<strong>recordset</strong>相同的用户指定的重命名名称创建新的<strong>recordset</strong> , 则这两个<strong>recordset</strong>对象的名称改变名称相同。</span><span class="sxs-lookup"><span data-stu-id="8a4f5-114">If this property is <strong>False</strong> and a new <strong>Recordset</strong> is created with the same user-specified reshape name as the existing <strong>Recordset</strong>, both <strong>Recordset</strong> objects will have the same reshape name.</span></span> <span data-ttu-id="8a4f5-115">因此, 只要两个记录集都存在, 则这两个<strong>recordset</strong>都不能被重整形。</span><span class="sxs-lookup"><span data-stu-id="8a4f5-115">Therefore, neither <strong>Recordset</strong> can be reshaped as long as both recordsets exist.</span></span> <span data-ttu-id="8a4f5-116">该属性的默认值是 <strong>False</strong>。</span><span class="sxs-lookup"><span data-stu-id="8a4f5-116">The default value of the property is <strong>False</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8a4f5-117"><strong>Data Provider</strong></span><span class="sxs-lookup"><span data-stu-id="8a4f5-117"><strong>Data Provider</strong></span></span></p></td>
<td><p><span data-ttu-id="8a4f5-p102">指示提供程序的名称，该程序将提供要定形的行。如果不使用提供程序来提供行，则此值可以是 NONE。</span><span class="sxs-lookup"><span data-stu-id="8a4f5-p102">Indicates the name of the provider that will supply rows to be shaped. This value may be NONE if a provider will not be used to supply rows.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="8a4f5-p103">您还可以在连接字符串中将可写动态属性的名称指定为关键字，从而设置这些属性。例如，在 Microsoft Visual Basic 中，通过以下代码将 **Data Provider** 动态属性设置为"MSDASQL"：</span><span class="sxs-lookup"><span data-stu-id="8a4f5-p103">You may also set writable dynamic properties by specifying their names as keywords in the connection string. For example, in Microsoft Visual Basic, set the **Data Provider** dynamic property to "MSDASQL" by specifying:</span></span>

```vb 
 
Dim cn as New ADODB.Connection 
cn.Open "Provider=MSDataShape;Data Provider=MSDASQL" 
```

<span data-ttu-id="8a4f5-p104">您还可以将某个动态属性的名称指定为 [Properties](properties-collection-ado.md) 属性的索引，从而设置或检索该动态属性。例如，可以获取并输出 **Data Provider** 动态属性的当前值，然后设置一个新值，如下所示：</span><span class="sxs-lookup"><span data-stu-id="8a4f5-p104">You may also set or retrieve a dynamic property by specifying its name as the index to the [Properties](properties-collection-ado.md) property. For example, get and print the current value of the **Data Provider** dynamic property, then set a new value, like this:</span></span>

```vb 
 
Debug.Print cn.Properties("Data Provider") 
cn.Properties("Data Provider") = "MSDASQL" 
```

<span data-ttu-id="8a4f5-124">有关数据定形的详细信息，请参阅[数据定形摘要](data-shaping.md)。</span><span class="sxs-lookup"><span data-stu-id="8a4f5-124">For more information about data shaping, see [Data Shaping](data-shaping.md).</span></span>

