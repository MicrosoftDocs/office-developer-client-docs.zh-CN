---
title: Fields 集合
TOCTitle: The Fields Collection
ms:assetid: 3bda8e5d-eceb-9605-c4d7-c1f4cc00ce6b
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249154(v=office.15)
ms:contentKeyID: 48544297
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 0260954f9183e3d29b87369c17582c4cb6f9238f
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25465881"
---
# <a name="the-fields-collection"></a><span data-ttu-id="07a15-102">Fields 集合</span><span class="sxs-lookup"><span data-stu-id="07a15-102">The Fields Collection</span></span>


<span data-ttu-id="07a15-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="07a15-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="07a15-p101">**Fields** 集合是 ADO 的固有集合之一。集合是一组按顺序排列的、可以作为单元引用的项。</span><span class="sxs-lookup"><span data-stu-id="07a15-p101">The **Fields** collection is one of ADO's intrinsic collections. A collection is an ordered set of items that can be referred to as a unit.</span></span>

<span data-ttu-id="07a15-p102">**Fields** 集合包含与 **Recordset** 中的每个字段（列）对应的 **Field** 对象。像所有 ADO 集合一样，它有 **Count** 和 **Item** 属性，还有 **Append** 和 **Refresh** 方法。它还有 **CancelUpdate** 、 **Delete** 、 **Resync** 和 **Update** 方法（这些方法对其他 ADO 集合不可用）。</span><span class="sxs-lookup"><span data-stu-id="07a15-p102">The **Fields** collection contains a **Field** object for every field (column) in the **Recordset**. Like all ADO collections, it has **Count** and **Item** properties, as well as **Append** and **Refresh** methods. It also has **CancelUpdate**, **Delete**, **Resync**, and **Update** methods, which are not available to other ADO collections.</span></span>

## <a name="examining-the-fields-collection"></a><span data-ttu-id="07a15-109">检查 Fields 集合</span><span class="sxs-lookup"><span data-stu-id="07a15-109">Examining the Fields Collection</span></span>

<span data-ttu-id="07a15-p103">以本章引入的示例 **Recordset** 的 **Fields** 集合为例。示例 **Recordset** 是从以下 SQL 语句派生的：</span><span class="sxs-lookup"><span data-stu-id="07a15-p103">Consider the **Fields** collection of the sample **Recordset** introduced in this chapter. The sample **Recordset** was derived from the SQL statement</span></span>

```sql 
 
SELECT ProductID, ProductName, UnitPrice FROM Products WHERE CategoryID = 7 
```

<span data-ttu-id="07a15-112">因此，应当发现 **Recordset** **Fields** 集合包含三个字段。</span><span class="sxs-lookup"><span data-stu-id="07a15-112">Thus, you should find that the **Recordset** **Fields** collection contains three fields.</span></span>

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

<span data-ttu-id="07a15-p104">此代码仅使用 **Count** 属性来确定 **Fields** 集合中 **Field** 对象的个数，并循环遍历集合，同时返回每个 **Field** 对象的 **Name** 属性的值。可以使用更多 **Field** 属性来获得有关字段的信息。有关查询 **Field** 的详细信息，请参阅 [Field 对象](the-field-object.md)。</span><span class="sxs-lookup"><span data-stu-id="07a15-p104">This code simply determines the number of **Field** objects in the **Fields** collection using the **Count** property and loops through the collection, returning the value of the **Name** property for each **Field** object. You can use many more **Field** properties to get information about a field. For more information about querying a **Field**, see [The Field Object](the-field-object.md).</span></span>

## <a name="counting-columns"></a><span data-ttu-id="07a15-116">对列计数</span><span class="sxs-lookup"><span data-stu-id="07a15-116">Counting Columns</span></span>

<span data-ttu-id="07a15-p105">您可能已经想到， **Count** 属性返回 **Fields** 集合中 **Field** 对象的实际个数。由于集合成员的计数从零开始，因此循环代码应当始终从零成员开始，并以值 **Count** 属性减 1 结束。如果使用 Microsoft Visual Basic 并且要循环遍历集合成员而不检查 **Count** 属性，请使用 **For** **Each...Next** 命令。</span><span class="sxs-lookup"><span data-stu-id="07a15-p105">As you might expect, the **Count** property returns the actual number of **Field** objects in the **Fields** collection. Because numbering for members of a collection begins with zero, you should always code loops starting with the zero member and ending with the value of the **Count** property minus 1. If you are using Microsoft Visual Basic and want to loop through the members of a collection without checking the **Count** property, use the **For** **Each...Next** command.</span></span>

<span data-ttu-id="07a15-120">如果 **Count** 属性为零，则表明集合中没有对象。</span><span class="sxs-lookup"><span data-stu-id="07a15-120">If the **Count** property is zero, there are no objects in the collection.</span></span>

## <a name="getting-to-the-field"></a><span data-ttu-id="07a15-121">访问字段</span><span class="sxs-lookup"><span data-stu-id="07a15-121">Getting to the Field</span></span>

<span data-ttu-id="07a15-p106">与任何 ADO 集合一样， **Item** 属性是集合的默认属性。它返回按传递给它的名称或索引指定的单个 **Field** 对象。因此，以下语句是示例 **Recordset** 的等价语句：</span><span class="sxs-lookup"><span data-stu-id="07a15-p106">As with any ADO collection, the **Item** property is the default property of the collection. It returns the individual **Field** object specified by the name or index passed to it. Therefore, the following statements are equivalent for the sample **Recordset**:</span></span>

```vb 
 
objField = objRecordset.Fields.Item("ProductID") 
objField = objRecordset.Fields("ProductID") 
objField = objRecordset.Fields.Item(0) 
objField = objRecordset.Fields(0) 
```

<span data-ttu-id="07a15-p107">如果这些方法是等价的，那么哪个是最佳的？这要视情况而定。使用索引从集合检索 **Field** 速度更快，这是因为它直接访问 **Field** 而不必执行字符串查找。另一方面，在集合中 **Fields** 的顺序必须是已知的，如果顺序更改，则在发生更改的地方对 **Field** 索引的引用也必须更改。尽管速度稍微慢点，但使用 **Field** 名称更灵活，因为它不依赖于 **Fields** 在集合中的顺序。</span><span class="sxs-lookup"><span data-stu-id="07a15-p107">If these methods are equivalent, which is best? It depends. Using an index to retrieve a **Field** from the collection is faster because it accesses the **Field** directly without having to perform a string lookup. On the other hand, the order of **Fields** within the collection must be known, and if the order changes, the reference to the **Field's** index will have to be changed wherever it occurs. Although slightly slower, using the name of the **Field** is more flexible because it doesn't depend on the order of the **Fields** in the collection.</span></span>

## <a name="using-the-refresh-method"></a><span data-ttu-id="07a15-130">使用 Refresh 方法</span><span class="sxs-lookup"><span data-stu-id="07a15-130">Using the Refresh Method</span></span>

<span data-ttu-id="07a15-p108">与某些其他 ADO 集合不同，使用 **Fields** 集合的 **Refresh** 方法没有可见的效果。若要从基础数据库结构检索更改，必须使用 **Requery** 方法，或如果 **Recordset** 对象不支持书签，则使用 **MoveFirst** 方法，而这将导致再次对提供程序执行命令。</span><span class="sxs-lookup"><span data-stu-id="07a15-p108">Unlike some other ADO collections, using the **Refresh** method on the **Fields** collection has no visible effect. To retrieve changes from the underlying database structure, you must use either the **Requery** method, or if the **Recordset** object does not support bookmarks, the **MoveFirst** method, which will cause the command to be executed against the provider again.</span></span>

## <a name="adding-fields-to-a-recordset"></a><span data-ttu-id="07a15-133">向记录集添加字段</span><span class="sxs-lookup"><span data-stu-id="07a15-133">Adding Fields to a Recordset</span></span>

<span data-ttu-id="07a15-134">**Append** 方法用来向 **Recordset** 添加字段。</span><span class="sxs-lookup"><span data-stu-id="07a15-134">The **Append** method is used to add fields to a **Recordset**.</span></span>

<span data-ttu-id="07a15-p109">可以使用 **Append** 方法通过编程来构造 **Recordset** ，而不用打开与数据源的连接。如果对打开的 **Recordset** 的 **Fields** 集合或已设置 **ActiveConnection** 属性的 **Recordset** 调用 **Append** 方法，将发生运行时错误。可以将字段只追加到没有打开并且尚未连接到数据源的 **Recordset** 。但是，若要为新追加的 **Fields** 指定值，必须首先打开 **Recordset** 。</span><span class="sxs-lookup"><span data-stu-id="07a15-p109">You can use the **Append** method to fabricate a **Recordset** programmatically without opening a connection to a data source. A run-time error will occur if the **Append** method is called on the **Fields** collection of an open **Recordset** or on a **Recordset** where the **ActiveConnection** property has been set. You can append fields only to a **Recordset** that is not open and has not yet been connected to a data source. However, to specify values for the newly appended **Fields**, the **Recordset** must first be opened.</span></span>

<span data-ttu-id="07a15-p110">开发人员通常需要一个地方来临时存储某些数据，或者想让某些数据好像来自服务器，以使这些数据可以在用户界面中参与数据绑定。ADO（与 [Microsoft Cursor Service for OLE DB](microsoft-cursor-service-for-ole-db-ado-service-component.md) 结合）使开发人员能够通过指定列信息并调用 **Open** 来生成空的 **Recordset** 对象。以下示例将三个新字段追加到新 **Recordset** 对象。然后打开 **Recordset** ，添加两个新记录，并将 **Recordset** 持久化到文件（有关 **Recordset** 持久化的详细信息，请参阅 [第 5 章：更新和持久化数据](chapter-5-updating-and-persisting-data.md)）。</span><span class="sxs-lookup"><span data-stu-id="07a15-p110">Developers often need a place to temporarily store some data, or want some data to act as if it came from a server so it can participate in data binding in a user interface. ADO (in conjunction with the [Microsoft Cursor Service for OLE DB](microsoft-cursor-service-for-ole-db-ado-service-component.md)) enables the developer to build an empty **Recordset** object by specifying column information and calling **Open**. In the following example, three new fields are appended to a new **Recordset** object. Then the **Recordset** is opened, two new records are added, and the **Recordset** is persisted to a file. (For more information about **Recordset** persistence, see [Chapter 5: Updating and Persisting Data](chapter-5-updating-and-persisting-data.md).)</span></span>

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

<span data-ttu-id="07a15-p111">对于 **Recordset** 对象和 **Record** 对象，二者的 **Fields** **Append** 方法的用法不同。有关 **Record** 对象的详细信息，请参阅 [第 10 章：记录和流](chapter-10-records-and-streams.md)。</span><span class="sxs-lookup"><span data-stu-id="07a15-p111">The usage of the **Fields** **Append** method differs between the **Recordset** object and the **Record** object. For more information about the **Record** object, see [Chapter 10: Records and Streams](chapter-10-records-and-streams.md).</span></span>

