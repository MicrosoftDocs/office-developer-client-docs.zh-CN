---
title: "Resync Command 属性 \x97 动态 (ADO)"
TOCTitle: Resync Command Property--Dynamic (ADO)
ms:assetid: 5c0c0819-620a-6eb0-a217-69113ec8d094
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249322(v=office.15)
ms:contentKeyID: 48545081
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 8fc64a51044f219d4daae44a9c684506cd7bd5c6
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466449"
---
# <a name="resync-command-property--dynamic-ado"></a><span data-ttu-id="0ff8a-102">Resync Command 属性  动态 (ADO)</span><span class="sxs-lookup"><span data-stu-id="0ff8a-102">Resync Command Property--Dynamic (ADO)</span></span>

<span data-ttu-id="0ff8a-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="0ff8a-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="0ff8a-104">指定一个用户提供的命令字符串，[Resync](resync-method-ado.md) 方法会发出此命令字符串以刷新 [Unique Table](unique-table-unique-schema-unique-catalog-properties-dynamic-ado.md) 动态属性中指定的表中的数据。</span><span class="sxs-lookup"><span data-stu-id="0ff8a-104">Specifies a user-supplied command string that the [Resync](resync-method-ado.md) method issues to refresh the data in the table named in the [Unique Table](unique-table-unique-schema-unique-catalog-properties-dynamic-ado.md) dynamic property.</span></span>

## <a name="settings-and-return-values"></a><span data-ttu-id="0ff8a-105">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="0ff8a-105">Settings and Return Values</span></span>

<span data-ttu-id="0ff8a-106">设置或返回一个 **String** 值，该值为一个命令字符串。</span><span class="sxs-lookup"><span data-stu-id="0ff8a-106">Sets or returns a **String** value which is a command string.</span></span>

## <a name="remarks"></a><span data-ttu-id="0ff8a-107">备注</span><span class="sxs-lookup"><span data-stu-id="0ff8a-107">Remarks</span></span>

<span data-ttu-id="0ff8a-108">[Recordset](recordset-object-ado.md) 对象是在多个基表上执行的 JOIN 操作的结果。</span><span class="sxs-lookup"><span data-stu-id="0ff8a-108">The [Recordset](recordset-object-ado.md) object is the result of a JOIN operation executed on multiple base tables.</span></span> <span data-ttu-id="0ff8a-109">受影响的行取决于[Resync](resync-method-ado.md)方法的*AffectRecords*参数。</span><span class="sxs-lookup"><span data-stu-id="0ff8a-109">The rows affected depend on the *AffectRecords* parameter of the [Resync](resync-method-ado.md) method.</span></span> <span data-ttu-id="0ff8a-110">如果未设置 **Unique Table** 和 [Resync Command](unique-table-unique-schema-unique-catalog-properties-dynamic-ado.md) 属性，则将执行标准 **Resync** 方法。</span><span class="sxs-lookup"><span data-stu-id="0ff8a-110">The standard **Resync** method is executed if the [Unique Table](unique-table-unique-schema-unique-catalog-properties-dynamic-ado.md) and **Resync Command** properties are not set.</span></span>

<span data-ttu-id="0ff8a-p102">**Resync Command** 属性的命令字符串是唯一标识要刷新的行的参数化命令或存储过程，并返回单个行，其中包含的列与要被刷新的行中的列的数量和顺序都相同。对于 **Unique Table** 中的每个主键列，命令字符串都应包含一个对应的参数；否则将返回运行时错误。将自动使用要被刷新的行中的主键值对参数进行填充。</span><span class="sxs-lookup"><span data-stu-id="0ff8a-p102">The command string of the **Resync Command** property is a parameterized command or stored procedure that uniquely identifies the row being refreshed, and returns a single row containing the same number and order of columns as the row to be refreshed. The command string contains a parameter for each primary key column in the **Unique Table**; otherwise, a run-time error is returned. The parameters are automatically filled in with primary key values from the row to be refreshed.</span></span>

<span data-ttu-id="0ff8a-114">下面是两个基于 SQL 的示例：</span><span class="sxs-lookup"><span data-stu-id="0ff8a-114">Here are two examples based on SQL:</span></span>

1.  <span data-ttu-id="0ff8a-115">由命令定义 **Recordset** ：</span><span class="sxs-lookup"><span data-stu-id="0ff8a-115">The **Recordset** is defined by a command:</span></span>

    ```sql
        SELECT * FROM Customers JOIN Orders ON 
        Customers.CustomerID = Orders.CustomerID
        WHERE city = Seattle
        ORDER BY CustomerID
    ```

    <span data-ttu-id="0ff8a-116">**Resync Command** 属性设置为：</span><span class="sxs-lookup"><span data-stu-id="0ff8a-116">The **Resync Command** property is set to:</span></span>

    ```sql
     SELECT * FROM 
        (SELECT * FROM Customers JOIN Orders 
        ON Customers.CustomerID = Orders.CustomerID
        city = Seattle ORDER BY CustomerID)
     WHERE Orders.OrderID = ?"
    ```

    <span data-ttu-id="0ff8a-p103">**Unique Table** 为 *Orders*（订单），其主键 *OrderID* 将被参数化。子选择提供了一种简单的方法，能以编程方式确保返回的列与原来命令中的列的数量和顺序都相同。</span><span class="sxs-lookup"><span data-stu-id="0ff8a-p103">The **Unique Table** is *Orders* and its primary key, *OrderID*, is parameterized. The sub-select provides a simple way to programmatically ensure that the same number and order of columns are returned as by the original command.</span></span>

2. <span data-ttu-id="0ff8a-119">由存储过程定义 **Recordset** ：</span><span class="sxs-lookup"><span data-stu-id="0ff8a-119">The **Recordset** is defined by a stored procedure:</span></span>

    ```sql
        CREATE PROC Custorders @CustomerID char(5) AS 
        SELECT * FROM Customers JOIN Orders ON 
        Customers.CustomerID = Orders.CustomerID 
        WHERE Customers.CustomerID = @CustomerID
    ```

    <span data-ttu-id="0ff8a-120">**Resync** 方法应执行以下存储过程：</span><span class="sxs-lookup"><span data-stu-id="0ff8a-120">The **Resync** method should execute the following stored procedure:</span></span>

    ```sql
        CREATE PROC CustordersResync @ordid int AS 
        SELECT * FROM Customers JOIN Orders ON 
        Customers.CustomerID = Orders.CustomerID
        WHERE Orders.ordid  = @ordid
    ```

    <span data-ttu-id="0ff8a-121">**Resync Command** 属性设置为：</span><span class="sxs-lookup"><span data-stu-id="0ff8a-121">The **Resync Command** property is set to:</span></span>

    `"{call CustordersResync (?)}"`

<span data-ttu-id="0ff8a-122">同样，**Unique Table** 也是 *Orders*（订单），其主键 *OrderID* 将被参数化。</span><span class="sxs-lookup"><span data-stu-id="0ff8a-122">Once again, the **Unique Table** is *Orders* and its primary key, *OrderID*, is parameterized.</span></span>

<span data-ttu-id="0ff8a-123">**Resync Command** 是一个动态属性，会在 **CursorLocation** 属性设置为 [adUseClient](properties-collection-ado.md) 时追加到 [Recordset](cursorlocation-property-ado.md) 对象的 **Properties** 集合中。</span><span class="sxs-lookup"><span data-stu-id="0ff8a-123">**Resync Command** is a dynamic property appended to the **Recordset** object [Properties](properties-collection-ado.md) collection when the [CursorLocation](cursorlocation-property-ado.md) property is set to **adUseClient**.</span></span>
