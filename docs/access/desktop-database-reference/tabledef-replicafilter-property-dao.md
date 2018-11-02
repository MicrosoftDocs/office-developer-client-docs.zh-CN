---
title: TableDef.ReplicaFilter 属性 (DAO)
TOCTitle: ReplicaFilter Property
ms:assetid: f44273de-2b6a-750f-cb7c-12c3ac2da503
ms:mtpsurl: https://msdn.microsoft.com/library/Ff836681(v=office.15)
ms:contentKeyID: 48548683
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1055548
f1_categories:
- Office.Version=v15
ms.openlocfilehash: dbd8ecc670742d6b9f88dd9c608d2304e26a8d09
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25929662"
---
# <a name="tabledefreplicafilter-property-dao"></a>TableDef.ReplicaFilter 属性 (DAO)


**适用于**： Access 2013、 Office 2013

设置或返回部分副本中的 **[TableDef](tabledef-object-dao.md)** 对象中的一个值，用于指示哪部分记录从完全副本复制到该表中（仅适用于 Microsoft Access 工作区）。

## <a name="syntax"></a>语法

*表达式*。ReplicaFilter

*表达式*一个代表**TableDef**对象的变量。

## <a name="remarks"></a>注解

设置或返回值是一个 **String** 或 **Boolean**，用于指示复制了哪部分记录，如下表所示：

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>值</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>字符串</p></td>
<td><p>为了从完全副本中复制，部分副本表中的记录所必须满足的条件。</p></td>
</tr>
<tr class="even">
<td><p><strong>True</strong></p></td>
<td><p>复制所有记录。</p></td>
</tr>
<tr class="odd">
<td><p><strong>False</strong></p></td>
<td><p>（默认）不复制任何记录。</p></td>
</tr>
</tbody>
</table>


该属性类似于 SQL WHERE 语句（不含 WHERE 一词），但是不能在条件中指定子查询、聚合函数（如 **Count**）或用户定义的函数。

只能在完全副本与部分副本之间同步数据。不能在两个部分副本之间同步数据。另外，对于部分复制，您可以设置关于复制哪些记录的限制，但是不能指出复制哪些字段。

通常，在想要复制另一组记录时重置副本筛选器。例如，当一个销售代表临时接替另一个销售代表所负责的区域时，数据库应用程序可以临时复制这两个区域的数据，然后恢复使用上一个筛选器。在这种情况下，应用程序重置 **ReplicaFilter** 属性，然后重新填充部分副本。

如果应用程序更改了副本筛选器，您应当执行下列步骤：

1.  使用 **[Synchronize](database-synchronize-method-dao.md)** 方法将完全副本与更改了筛选器的部分副本同步。

2.  使用 **ReplicaFilter** 属性对副本筛选器进行必要的更改。

3.  使用 **[PopulatePartial](database-populatepartial-method-dao.md)** 方法删除部分副本中的所有记录，然后从完全副本传输所有符合新副本筛选条件的记录。

若要删除筛选器，请将 **ReplicaFilter** 属性设置为 **False**。如果删除所有筛选器并调用 **PopulatePartial** 方法，则部分副本中的所有已复制表中都不会显示任何记录。


> [!NOTE]
> <P>[!注释] 如果副本筛选器已更改，并且在未首先调用 <STRONG>PopulatePartial</STRONG> 的情况下调用了 <STRONG>Synchronize</STRONG> 方法，则会发生可捕获的错误。</P>



## <a name="example"></a>示例

以下示例使用 **ReplicaFilter** 属性来仅复制加利福尼亚地区的客户记录。

```vb 
Sub ReplicaFilterX() 
 
 ' This example assumes the current open database 
 ' is the replica. 
 Dim tdfCustomers As TableDef 
 Dim strFilter As String 
 Dim dbsTemp As Database 
 
 Set dbsTemp = OpenDatabase("Northwind.mdb") 
 Set tdfCustomers = dbsTemp.TableDefs("Customers") 
 
 ' Synchronize with full replica 
 ' before setting replica filter. 
 dbsTemp.Synchronize "C:\SALES\FY96.MDB" 
 
 strFilter = "Region = 'CA'" 
 tdfCustomers.ReplicaFilter = strFilter 
 dbsTemp.PopulatePartial "C:\SALES\FY96.MDB" 
 
 ' Now remove the replica filter (for example purposes 
 ' only). 
 tdfCustomers.ReplicaFilter = False 
 ' Repopulate the database. 
 dbsTemp.PopulatePartial "C:\SALES\DATA96.MDB" 
 
End Sub 
 
```

