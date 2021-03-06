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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32293201"
---
# <a name="fabricating-hierarchical-recordsets"></a>构建层次记录集


**适用于**：Access 2013、Office 2013

下面的示例演示如何通过使用 Data Shaping 语法来定义父级、子级和孙级 **Recordset** 的列，从而构建没有基础数据源的分层 Recordset。

若要构建分层 **Recordset** ，必须指定 Microsoft Data Shaping Service for OLE DB (MSDataShape)，而且可以将 [Connection](connection-object-ado.md) 对象的 [Open](open-method-ado-connection.md) 方法的连接字符串参数的 Data Provider 值指定为 NONE。有关详细信息，请参阅 [数据定形必需的提供程序](required-providers-for-data-shaping.md)。

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

构建完**Recordset**后, 可以对其进行填充、操作或将其保存到文件中。

