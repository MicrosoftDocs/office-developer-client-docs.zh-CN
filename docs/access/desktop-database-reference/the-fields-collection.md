---
title: Fields 集合
TOCTitle: The Fields Collection
ms:assetid: 3bda8e5d-eceb-9605-c4d7-c1f4cc00ce6b
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249154(v=office.15)
ms:contentKeyID: 48544297
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 67f16c9c4dd27fdbd57a2c082580ead0606298e9
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25874872"
---
# <a name="the-fields-collection"></a>Fields 集合


**适用于**： Access 2013、 Office 2013

**Fields** 集合是 ADO 的固有集合之一。集合是一组按顺序排列的、可以作为单元引用的项。

**Fields** 集合包含与 **Recordset** 中的每个字段（列）对应的 **Field** 对象。像所有 ADO 集合一样，它有 **Count** 和 **Item** 属性，还有 **Append** 和 **Refresh** 方法。它还有 **CancelUpdate** 、 **Delete** 、 **Resync** 和 **Update** 方法（这些方法对其他 ADO 集合不可用）。

## <a name="examining-the-fields-collection"></a>检查 Fields 集合

以本章引入的示例 **Recordset** 的 **Fields** 集合为例。示例 **Recordset** 是从以下 SQL 语句派生的：

```sql 
 
SELECT ProductID, ProductName, UnitPrice FROM Products WHERE CategoryID = 7 
```

因此，应当发现 **Recordset** **Fields** 集合包含三个字段。

```vb 
 
'BeginWalkFields 
 Dim objFields As ADODB.Fields 
 
 objRs.Open strSQL, strConnStr, adOpenForwardOnly, adLockReadOnly, adCmdText 
 
 Set objFields = objRs.Fields 
 
 For intLoop = 0 To (objFields.Count - 1) 
 Debug.Print objFields.Item(intLoop).Name 
 Next 
'EndWalkFields 
```

此代码仅使用 **Count** 属性来确定 **Fields** 集合中 **Field** 对象的个数，并循环遍历集合，同时返回每个 **Field** 对象的 **Name** 属性的值。可以使用更多 **Field** 属性来获得有关字段的信息。有关查询 **Field** 的详细信息，请参阅 [Field 对象](the-field-object.md)。

## <a name="counting-columns"></a>对列计数

您可能已经想到， **Count** 属性返回 **Fields** 集合中 **Field** 对象的实际个数。由于集合成员的计数从零开始，因此循环代码应当始终从零成员开始，并以值 **Count** 属性减 1 结束。如果使用 Microsoft Visual Basic 并且要循环遍历集合成员而不检查 **Count** 属性，请使用 **For** **Each...Next** 命令。

如果 **Count** 属性为零，则表明集合中没有对象。

## <a name="getting-to-the-field"></a>访问字段

与任何 ADO 集合一样， **Item** 属性是集合的默认属性。它返回按传递给它的名称或索引指定的单个 **Field** 对象。因此，以下语句是示例 **Recordset** 的等价语句：

```vb 
 
objField = objRecordset.Fields.Item("ProductID") 
objField = objRecordset.Fields("ProductID") 
objField = objRecordset.Fields.Item(0) 
objField = objRecordset.Fields(0) 
```

如果这些方法是等价的，那么哪个是最佳的？这要视情况而定。使用索引从集合检索 **Field** 速度更快，这是因为它直接访问 **Field** 而不必执行字符串查找。另一方面，在集合中 **Fields** 的顺序必须是已知的，如果顺序更改，则在发生更改的地方对 **Field** 索引的引用也必须更改。尽管速度稍微慢点，但使用 **Field** 名称更灵活，因为它不依赖于 **Fields** 在集合中的顺序。

## <a name="using-the-refresh-method"></a>使用 Refresh 方法

与某些其他 ADO 集合不同，使用 **Fields** 集合的 **Refresh** 方法没有可见的效果。若要从基础数据库结构检索更改，必须使用 **Requery** 方法，或如果 **Recordset** 对象不支持书签，则使用 **MoveFirst** 方法，而这将导致再次对提供程序执行命令。

## <a name="adding-fields-to-a-recordset"></a>向记录集添加字段

**Append** 方法用来向 **Recordset** 添加字段。

可以使用 **Append** 方法通过编程来构造 **Recordset** ，而不用打开与数据源的连接。如果对打开的 **Recordset** 的 **Fields** 集合或已设置 **ActiveConnection** 属性的 **Recordset** 调用 **Append** 方法，将发生运行时错误。可以将字段只追加到没有打开并且尚未连接到数据源的 **Recordset** 。但是，若要为新追加的 **Fields** 指定值，必须首先打开 **Recordset** 。

开发人员通常需要一个地方来临时存储某些数据，或者想让某些数据好像来自服务器，以使这些数据可以在用户界面中参与数据绑定。ADO（与 [Microsoft Cursor Service for OLE DB](microsoft-cursor-service-for-ole-db-ado-service-component.md) 结合）使开发人员能够通过指定列信息并调用 **Open** 来生成空的 **Recordset** 对象。以下示例将三个新字段追加到新 **Recordset** 对象。然后打开 **Recordset** ，添加两个新记录，并将 **Recordset** 持久化到文件（有关 **Recordset** 持久化的详细信息，请参阅 [第 5 章：更新和持久化数据](chapter-5-updating-and-persisting-data.md)）。

```vb 
 
 'BeginFabricate 
 Dim objRs As New ADODB.Recordset 
 
 With objRs.Fields 
 .Append "StudentID", adChar, 11, adFldUpdatable 
 .Append "FullName", adVarChar, 50, adFldUpdatable 
 .Append "PhoneNmbr", adVarChar, 20, adFldUpdatable 
 End With 
 
 With objRs 
 .Open 
 
 .AddNew 
 .Fields(0) = "123-45-6789" 
 .Fields(1) = "John Doe" 
 .Fields(2) = "(425) 555-5555" 
 .Update 
 
 .AddNew 
 .Fields(0) = "123-45-6780" 
 .Fields(1) = "Jane Doe" 
 .Fields(2) = "(615) 555-1212" 
 .Update 
 End With 
 
 objRs.Save App.Path & "\FabriTest.adtg", adPersistADTG 
 
 objRs.Close 
 'EndFabricate 
```

对于 **Recordset** 对象和 **Record** 对象，二者的 **Fields** **Append** 方法的用法不同。有关 **Record** 对象的详细信息，请参阅 [第 10 章：记录和流](chapter-10-records-and-streams.md)。

