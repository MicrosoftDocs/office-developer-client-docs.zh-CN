---
title: Database.PopulatePartial 方法 (DAO)
TOCTitle: PopulatePartial Method
ms:assetid: fa3227a2-c961-6a98-32b3-5b6e5329a21d
ms:mtpsurl: https://msdn.microsoft.com/library/Ff837034(v=office.15)
ms:contentKeyID: 48548834
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1101186
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 2d90d82db89060894eda1e58442cb6f9d52f124e
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25919488"
---
# <a name="databasepopulatepartial-method-dao"></a>Database.PopulatePartial 方法 (DAO)


**适用于**： Access 2013、 Office 2013


将部分副本中的任何更改与完全副本同步，清除部分副本中的所有记录，然后根据当前副本筛选器重新填充部分副本。（仅适用于 Microsoft Access 数据库引擎数据库。）

## <a name="syntax"></a>语法

*表达式*。PopulatePartial (***DbPathName***)

*表达式*一个代表**Database**对象的变量。

### <a name="parameters"></a>参数

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p>名称</p></th>
<th><p>必需/可选</p></th>
<th><p>数据类型</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DbPathName</p></td>
<td><p>必需</p></td>
<td><p><strong>字符串</strong></p></td>
<td><p>要使用其中的数据填充记录的完全副本的路径和名称。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>注解

当您将部分副本与完全副本同步时，有可能在部分副本中创建"孤立"的记录。 例如，假设客户表具有其**[ReplicaFilter](tabledef-replicafilter-property-dao.md)** 设置为"区域 = 'CA'"。 如果用户在部分副本中将客户的区域由 CA 更改为 NY，然后通过 **[Synchronize](database-synchronize-method-dao.md)** 方法发生同步，更改将传播到完全副本，但是部分副本中包含 NY 的记录会变为孤立的，因为它现在不满足副本筛选器条件。

若要解决孤立记录的问题，可以使用 **PopulatePartial** 方法。 **PopulatePartial** 方法类似于 **Synchronize** 方法，但是它将任何更改与完全副本同步，再删除部分副本中的所有记录，然后基于当前的副本筛选器重新填充部分副本。即使未更改副本筛选器， **PopulatePartial** 也始终清除部分副本中的所有记录，然后基于当前筛选器重新填充部分副本。

一般而言，在创建部分副本时，以及无论何时更改副本筛选器时，都应该使用 **PopulatePartial** 方法。如果应用程序更改了副本筛选器，应遵循以下步骤：

1.  将完全副本与其中更改了筛选器的部分副本同步。

2.  使用 **ReplicaFilter** 和 **[PartialReplica](relation-partialreplica-property-dao.md)** 属性对副本筛选器执行所需的更改。

3.  调用 **PopulatePartial** 方法可从部分副本中删除所有记录，并从完全副本中传输符合新的副本筛选条件的所有记录。

如果副本筛选器已更改，并且在未首先调用 **PopulatePartial** 的情况下调用了 **Synchronize** 方法，则会发生可捕获的错误。

只能对已打开以便进行独占访问的部分副本调用 **PopulatePartial** 方法。此外，不能从运行于部分副本自身内的代码调用 **PopulatePartial** 方法，而应当从完全副本或另一个数据库以独占方式打开部分副本，然后调用 **PopulatePartial**。


> [!NOTE]
> [!注释] 尽管 **PopulatePartial** 在清除和重新填充部分副本之前执行单向同步，但是，最好是仍然在调用 **PopulatePartial** 之前调用 **Synchronize**。这是因为如果调用 **Synchronize** 失败，将发生可捕获的错误。可以使用此错误决定是否继续 **PopulatePartial** 方法（此方法将删除部分副本中的所有记录）。如果 **PopulatePartial** 由其自身调用，并且在同步记录时出错，则仍然会清除部分副本中的记录，这可能是不希望得到的结果。



## <a name="example"></a>示例

以下示例在更改副本筛选器后使用 **PopulatePartial** 方法。

```vb 
Sub PopulatePartialX() 
 
 Dim tdfCustomers As TableDef 
 Dim strFilter As String 
 Dim dbsTemp As Database 
 
 ' Open the partial replica in exclusive mode. 
 Set dbsTemp = OpenDatabase("F:\SALES\FY96CA.MDB", True) 
 
 With dbsTemp 
 Set tdfCustomers = .TableDefs("Customers") 
 
 ' Synchronize with full replica 
 ' before setting replica filter. 
 .Synchronize "C:\SALES\FY96.MDB" 
 
 strFilter = "Region = 'CA'" 
 tdfCustomers.ReplicaFilter = strFilter 
 
 ' Populate records from the full replica. 
 .PopulatePartial "C:\SALES\FY96.MDB" 
 
 .Close 
 End With 
 
End Sub 
 
```

