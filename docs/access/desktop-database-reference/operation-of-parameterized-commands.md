---
title: 参数化命令的操作
TOCTitle: Operation of parameterized commands
ms:assetid: 71edbd16-21db-7afa-356b-d8e7afb92b3a
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249456(v=office.15)
ms:contentKeyID: 48545596
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 145a2ee6c3d3c614eb9660350a0bb8a00d44d04c
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28717445"
---
# <a name="operation-of-parameterized-commands"></a>参数化命令的操作

**适用于**： Access 2013、 Office 2013

如果要使用大型子 **Recordset** （尤其是与父 **Recordset** 的大小相比较），但只需要访问少量子章节，则可能发现使用参数化命令会更有效。

*非参数化命令*检索整个父和子**Recordset**和追加章节列到父级，然后分配对每个父行的相关的子章节的引用。

*参数化的命令*检索整个父**记录集**，但访问的章节列时检索仅章**Recordset** 。 此检索策略差异可以产生极大的性能收益。

例如，可以指定以下内容：

```vb 
 
SHAPE {SELECT * FROM customer} 
 APPEND ({SELECT * FROM orders WHERE cust_id = ?} 
 RELATE cust_id TO PARAMETER 0) 
```

父和子表中常见，客户具有列名称\_*。* id *子命令*具有对建立关系子句所指的"?"占位符 (即"...参数 0"）。

> [!NOTE]
> [!注释] PARAMETER 子句仅仅属于 Shape 命令语法。它不与 ADO [Parameter](parameter-object-ado.md) 对象或 [Parameters](parameters-collection-ado.md) 集合关联。

执行参数化 Shape 命令时，将发生以下操作：

1.  *父命令*将执行，并从客户表返回父**Recordset** 。

2.  向父 **Recordset** 追加章节列。

3.  当访问父行的章节列时，使用 customer.cust 的值执行*子命令*\_id 作为参数的值。

4.  使用在步骤 3 中创建的数据提供程序行集的所有行来填充子 **Recordset** 。 在此示例中，该元素是在其中订单表中的所有行客户\_id 等于的 customer.cust 值\_id。 默认情况下的子**Recordset**s 将进行缓存在客户端上直到释放所有引用父**Recordset** 。 若要更改此行为，请将**Recordset** [动态属性](ado-dynamic-property-index.md)**缓存子行**设置为**False**。

5.  对所检索的子行的引用（即子 **Recordset** 的章节）将放在父 **Recordset** 的当前行的章节列中。

6.  在访问另一个行的章节列时，将重复步骤 3–5。

默认情况下， **Cache Child Rows** 动态属性设置为 **True** 。缓存行为因查询的参数值而异。在使用单个参数的查询中，在请求具有该值的子项的间隔期中，系统将缓存给定参数值的子 **Recordset** 。以下代码演示了这种情况：

```vb
... 
SCmd = "SHAPE {select * from customer} " & _ 
 "APPEND({select * from orders where cust_id = ?} " & _ 
 "RELATE cust_id TO PARAMETER 0) AS chpCustOrder" 
Rst1.Open sCmd, Cnn1 
Set RstChild = Rst1("chpCustOrder").Value 
Rst1.MoveNext ' Next cust_id passed to Param 0, & new rs fetched 
 ' into RstChild. 
Rst1.MovePrevious ' RstChild now holds cached rs, saving round trip. 
... 
```

在具有两个或更多个参数的查询中，只有当所有参数值都与缓存值匹配时，才会使用缓存的子项。

## <a name="parameterized-commands-and-complex-parent-child-relations"></a>参数化的命令和复杂的父子关系

除了使用参数化命令来改进 equi-join 类型层次结构的性能以外，还可以用参数化命令来支持更复杂的父子关系。 例如，考虑两个表少联盟的数据库： 一个包含团队 (团队\_id、 团队\_名称) 和其他的游戏 (日期，主\_团队，访问\_团队)。

如果使用非参数化层次结构，则无法通过让团队表和比赛表相关来使每个团队的子 **Recordset** 都包含它已完成的赛程。 可以创建包含主场赛程或客场赛程（但不同时包含这二者）的章节。 这是因为 RELATE 子句使您只能建立形式为 (pc1=cc1) AND (pc2=pc2) 的父子关系。 因此，如果您的命令包括"建立关系团队\_id 收件人主页\_团队、 团队\_id 与访问\_团队"，您将获取仅游戏团队已播放本身。 您需要的是"(团队\_id = 主页\_团队) 或者 (团队\_id = 访问\_团队)"，但形状提供程序不支持 OR 子句。

若要获得希望的结果，可以使用参数化命令。例如：

```vb 
 
SHAPE {SELECT * FROM teams} 
APPEND ({SELECT * FROM games WHERE home_team = ? OR visiting_team = ?} 
 RELATE team_id TO PARAMETER 0, 
 team_id TO PARAMETER 1) 
```

此示例利用 SQL WHERE 子句具有的更大灵活性来获得需要的结果。

