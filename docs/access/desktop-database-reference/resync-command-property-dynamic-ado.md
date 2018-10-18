---
title: "Resync Command 属性 \x97 动态 (ADO)"
TOCTitle: Resync Command Property--Dynamic (ADO)
ms:assetid: 5c0c0819-620a-6eb0-a217-69113ec8d094
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249322(v=office.15)
ms:contentKeyID: 48545081
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 6d9133f37b236cfa876a5d6ae8642f25f919f2cb
ms.sourcegitcommit: a49b77f4c8cec69f90656a86f0872cf34c35968e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2018
ms.locfileid: "25602802"
---
# <a name="resync-command-property--dynamic-ado"></a>Resync Command 属性  动态 (ADO)

**适用于**： Access 2013 |Office 2013

指定一个用户提供的命令字符串，[Resync](resync-method-ado.md) 方法会发出此命令字符串以刷新 [Unique Table](unique-table-unique-schema-unique-catalog-properties-dynamic-ado.md) 动态属性中指定的表中的数据。

<<<<<<< 标头
## <a name="settings-and-return-values"></a>设置和返回值
=======
## <a name="settings-and-return-values"></a>设置和返回值
>>>>>>> master

设置或返回一个 **String** 值，该值为一个命令字符串。

## <a name="remarks"></a>备注

[Recordset](recordset-object-ado.md) 对象是在多个基表上执行的 JOIN 操作的结果。 受影响的行取决于[Resync](resync-method-ado.md)方法的*AffectRecords*参数。 如果未设置 **Unique Table** 和 [Resync Command](unique-table-unique-schema-unique-catalog-properties-dynamic-ado.md) 属性，则将执行标准 **Resync** 方法。

**Resync Command** 属性的命令字符串是唯一标识要刷新的行的参数化命令或存储过程，并返回单个行，其中包含的列与要被刷新的行中的列的数量和顺序都相同。对于 **Unique Table** 中的每个主键列，命令字符串都应包含一个对应的参数；否则将返回运行时错误。将自动使用要被刷新的行中的主键值对参数进行填充。

下面是两个基于 SQL 的示例：

1.  由命令定义 **Recordset** ：

    ```sql
        SELECT * FROM Customers JOIN Orders ON 
        Customers.CustomerID = Orders.CustomerID
        WHERE city = Seattle
        ORDER BY CustomerID
    ```

    **Resync Command** 属性设置为：

    ```sql
     SELECT * FROM 
        (SELECT * FROM Customers JOIN Orders 
        ON Customers.CustomerID = Orders.CustomerID
        city = Seattle ORDER BY CustomerID)
     WHERE Orders.OrderID = ?"
    ```

    **Unique Table** 为 *Orders*（订单），其主键 *OrderID* 将被参数化。子选择提供了一种简单的方法，能以编程方式确保返回的列与原来命令中的列的数量和顺序都相同。

2. 由存储过程定义 **Recordset** ：

    ```sql
        CREATE PROC Custorders @CustomerID char(5) AS 
        SELECT * FROM Customers JOIN Orders ON 
        Customers.CustomerID = Orders.CustomerID 
        WHERE Customers.CustomerID = @CustomerID
    ```

    **Resync** 方法应执行以下存储过程：

    ```sql
        CREATE PROC CustordersResync @ordid int AS 
        SELECT * FROM Customers JOIN Orders ON 
        Customers.CustomerID = Orders.CustomerID
        WHERE Orders.ordid  = @ordid
    ```

    **Resync Command** 属性设置为：

    `"{call CustordersResync (?)}"`

同样，**Unique Table** 也是 *Orders*（订单），其主键 *OrderID* 将被参数化。

**Resync Command** 是一个动态属性，会在 **CursorLocation** 属性设置为 [adUseClient](properties-collection-ado.md) 时追加到 [Recordset](cursorlocation-property-ado.md) 对象的 **Properties** 集合中。

