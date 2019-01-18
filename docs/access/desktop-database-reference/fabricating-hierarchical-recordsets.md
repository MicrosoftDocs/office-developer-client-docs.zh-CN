---
title: 构建层次记录集
TOCTitle: Fabricating hierarchical Recordsets
ms:assetid: 0a6e41ba-015e-c07e-8876-1e744256b876
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248836(v=office.15)
ms:contentKeyID: 48543153
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: f644f25a04c5573a93aa106884473fed6b45440e
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28715576"
---
# <a name="fabricating-hierarchical-recordsets"></a><span data-ttu-id="6fde3-102">构建层次记录集</span><span class="sxs-lookup"><span data-stu-id="6fde3-102">Fabricating hierarchical Recordsets</span></span>


<span data-ttu-id="6fde3-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="6fde3-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="6fde3-104">下面的示例演示如何通过使用 Data Shaping 语法来定义父级、子级和孙级 **Recordset** 的列，从而构建没有基础数据源的分层 Recordset。</span><span class="sxs-lookup"><span data-stu-id="6fde3-104">The following example shows how to fabricate a hierarchical Recordset without an underlying data source by using the data shaping grammar to define columns for parent, child, and grandchild **Recordsets**.</span></span>

<span data-ttu-id="6fde3-p101">若要构建分层 **Recordset** ，必须指定 Microsoft Data Shaping Service for OLE DB (MSDataShape)，而且可以将 [Connection](connection-object-ado.md) 对象的 [Open](open-method-ado-connection.md) 方法的连接字符串参数的 Data Provider 值指定为 NONE。有关详细信息，请参阅 [数据定形必需的提供程序](required-providers-for-data-shaping.md)。</span><span class="sxs-lookup"><span data-stu-id="6fde3-p101">To fabricate a hierarchical **Recordset**, you must specify the Microsoft Data Shaping Service for OLE DB (MSDataShape), and you may specify a Data Provider value of NONE in the connection string parameter of the [Connection](connection-object-ado.md) object's [Open](open-method-ado-connection.md) method. For more information, see [Required Providers for Data Shaping](required-providers-for-data-shaping.md).</span></span>

```vb
    Dim cn As New ADODB.Connection
    Dim rsCustomers As New ADODB.Recordset
    
    cn.Open "Provider=MSDataShape;Data Provider=NONE;"
     
    strShape = _
    "SHAPE APPEND NEW adInteger AS CustID," & _
                " NEW adChar(25) AS FirstName," & _
                " NEW adChar(25) AS LastName," & _
                " NEW adChar(12) AS SSN," & _
                " NEW adChar(50) AS Address," & _
             " ((SHAPE APPEND NEW adChar(80) AS VIN_NO," & _
                            " NEW adInteger AS CustID," & _
                            " NEW adChar(20) AS BodyColor, " & _
                         " ((SHAPE APPEND NEW adChar(80) AS VIN_NO," & _
                                        " NEW adChar(20) AS Make, " & _
                                        " NEW adChar(20) AS Model," & _
                                        " NEW adChar(4) AS Year) " & _
                            " AS VINS RELATE VIN_NO TO VIN_NO))" & _
                " AS Vehicles RELATE CustID TO CustID) "
     
    rsCustomers.Open strShape, cn, adOpenStatic, adLockOptimistic, -1
```

<span data-ttu-id="6fde3-107">**记录集**具有构建后，它可以填充、 操作，或保存到文件。</span><span class="sxs-lookup"><span data-stu-id="6fde3-107">After the **Recordset** has been fabricated, it can be populated, manipulated, or persisted to a file.</span></span>

