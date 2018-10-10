---
title: 构造分层记录集
TOCTitle: Fabricating Hierarchical Recordsets
ms:assetid: 0a6e41ba-015e-c07e-8876-1e744256b876
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248836(v=office.15)
ms:contentKeyID: 48543153
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 81302ba1c18645a51913cb92179f4b61f3c32ce4
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468074"
---
# <a name="fabricating-hierarchical-recordsets"></a><span data-ttu-id="1f240-102">构造分层记录集</span><span class="sxs-lookup"><span data-stu-id="1f240-102">Fabricating Hierarchical Recordsets</span></span>


<span data-ttu-id="1f240-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="1f240-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="1f240-104">下面的示例演示如何通过使用 Data Shaping 语法来定义父级、子级和孙级 **Recordset** 的列，从而构建没有基础数据源的分层 Recordset。</span><span class="sxs-lookup"><span data-stu-id="1f240-104">The following example shows how to fabricate a hierarchical Recordset without an underlying data source by using the data shaping grammar to define columns for parent, child, and grandchild **Recordsets**.</span></span>

<span data-ttu-id="1f240-p101">若要构建分层 **Recordset** ，必须指定 Microsoft Data Shaping Service for OLE DB (MSDataShape)，而且可以将 [Connection](connection-object-ado.md) 对象的 [Open](open-method-ado-connection.md) 方法的连接字符串参数的 Data Provider 值指定为 NONE。有关详细信息，请参阅 [数据定形必需的提供程序](required-providers-for-data-shaping.md)。</span><span class="sxs-lookup"><span data-stu-id="1f240-p101">To fabricate a hierarchical **Recordset**, you must specify the Microsoft Data Shaping Service for OLE DB (MSDataShape), and you may specify a Data Provider value of NONE in the connection string parameter of the [Connection](connection-object-ado.md) object's [Open](open-method-ado-connection.md) method. For more information, see [Required Providers for Data Shaping](required-providers-for-data-shaping.md).</span></span>

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

<span data-ttu-id="1f240-107">**记录集**具有构建后，它可以填充、 操作，或保存到文件。</span><span class="sxs-lookup"><span data-stu-id="1f240-107">After the **Recordset** has been fabricated, it can be populated, manipulated, or persisted to a file.</span></span>

