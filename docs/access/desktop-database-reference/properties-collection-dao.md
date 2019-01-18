---
title: Properties 集合 (DAO)
TOCTitle: Properties collection
ms:assetid: cd07184a-a261-29c9-542f-bc2eff6f4af6
ms:mtpsurl: https://msdn.microsoft.com/library/Ff834455(v=office.15)
ms:contentKeyID: 48547753
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 515d28f0d7d99359c36df79cf3b8769d8f71e06d
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28715513"
---
# <a name="properties-collection-dao"></a><span data-ttu-id="510d2-102">Properties 集合 (DAO)</span><span class="sxs-lookup"><span data-stu-id="510d2-102">Properties collection (DAO)</span></span>

<span data-ttu-id="510d2-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="510d2-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="510d2-104">**Properties** 集合包含对象的特定实例的所有 **[Property](property-object-dao.md)** 对象。</span><span class="sxs-lookup"><span data-stu-id="510d2-104">A **Properties** collection contains all the **[Property](property-object-dao.md)** objects for a specific instance of an object.</span></span>

## <a name="remarks"></a><span data-ttu-id="510d2-105">注解</span><span class="sxs-lookup"><span data-stu-id="510d2-105">Remarks</span></span>

<span data-ttu-id="510d2-p101">每个 DAO 对象（ **Connection** 和 **Error** 对象除外）都包含一个 **Properties** 集合，该集合具有某些内置的 **Property** 对象。这些 **Property** 对象（通常就称为属性）唯一地描述了对象的该实例。</span><span class="sxs-lookup"><span data-stu-id="510d2-p101">Every DAO object except the **Connection** and **Error** objects contains a **Properties** collection, which has certain built-in **Property** objects. These **Property** objects (which are often just called properties) uniquely characterize that instance of the object.</span></span>

<span data-ttu-id="510d2-p102">除了内部属性，还可以创建并添加您自己的用户定义的属性。若要向对象的现有实例添加用户定义的属性，请首先使用 **CreateProperty** 方法定义该实例的特征，然后使用 **Append** 方法将该实例添加到集合中。如果引用尚未追加到 **Properties** 集合的用户定义的 **Property** 对象，则会发生错误；如果将用户定义的 **Property** 对象追加到包含同名 **Property** 对象的 **Properties** 集合中，也会发生错误。</span><span class="sxs-lookup"><span data-stu-id="510d2-p102">In addition to the built-in properties, you can also create and add your own user-defined properties. To add a user-defined property to an existing instance of an object, first define its characteristics with the **CreateProperty** method, then add it to the collection with the **Append** method. Referencing a user-defined **Property** object that has not yet been appended to a **Properties** collection will cause an error, as will appending a user-defined **Property** object to a **Properties** collection containing a **Property** object of the same name.</span></span>

<span data-ttu-id="510d2-111">可以使用 **Delete** 方法从 **Properties** 集合中删除用户定义的属性，但不能删除内置属性。</span><span class="sxs-lookup"><span data-stu-id="510d2-111">You can use the **Delete** method to remove user-defined properties from the **Properties** collection, but you can't remove built-in properties.</span></span>

> [!NOTE]
> <span data-ttu-id="510d2-p103">[!注释] 一个用户定义的 **Property** 对象只与一个对象的特定实例相关联。属性并不是为选定类型的对象的所有实例定义的。</span><span class="sxs-lookup"><span data-stu-id="510d2-p103">A user-defined **Property** object is associated only with the specific instance of an object. The property isn't defined for all instances of objects of the selected type.</span></span>

<span data-ttu-id="510d2-114">若要按照序号或 **Name** 属性设置来引用集合中的内置 **Property** 对象，可以使用下列任何一种语法形式：</span><span class="sxs-lookup"><span data-stu-id="510d2-114">To refer to a built-in **Property** object in a collection by its ordinal number or by its **Name** property setting, use any of the following syntax forms:</span></span>

- <span data-ttu-id="510d2-115">对象。**属性**(0)</span><span class="sxs-lookup"><span data-stu-id="510d2-115">object.**Properties**(0)</span></span>

- <span data-ttu-id="510d2-116">对象。**属性**("name")</span><span class="sxs-lookup"><span data-stu-id="510d2-116">object.**Properties**("name")</span></span>

- <span data-ttu-id="510d2-117">对象。**属性**\!\[名称\]</span><span class="sxs-lookup"><span data-stu-id="510d2-117">object.**Properties**\!\[name\]</span></span>

<span data-ttu-id="510d2-118">对于内置属性，还可以使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="510d2-118">For a built-in property, you can also use this syntax:</span></span>

- <span data-ttu-id="510d2-119">object.name</span><span class="sxs-lookup"><span data-stu-id="510d2-119">object.name</span></span>

> [!NOTE]
> <span data-ttu-id="510d2-120">对于用户定义的属性，您必须使用完整的对象。**属性**("name") 语法。</span><span class="sxs-lookup"><span data-stu-id="510d2-120">For a user-defined property, you must use the full object.**Properties**("name") syntax.</span></span>

<span data-ttu-id="510d2-p104">使用同样的语法格式，还可以引用 **Property** 对象的 **Value** 属性。引用的上下文将确定是引用 **Property** 对象自身，还是引用 **Property** 对象的 **Value** 属性。</span><span class="sxs-lookup"><span data-stu-id="510d2-p104">With the same syntax forms, you can also refer to the **Value** property of a **Property** object. The context of the reference will determine whether you are referring to the **Property** object itself or the **Value** property of the **Property** object.</span></span>

## <a name="example"></a><span data-ttu-id="510d2-123">示例</span><span class="sxs-lookup"><span data-stu-id="510d2-123">Example</span></span>

<span data-ttu-id="510d2-p105">以下示例为当前数据库创建用户定义的属性，设置该属性的 **Type** 和 **Value** 属性，并将该属性追加到数据库的 **Properties** 集合中。然后，该示例枚举数据库中的所有属性。</span><span class="sxs-lookup"><span data-stu-id="510d2-p105">This example creates a user-defined property for the current database, sets its **Type** and **Value** properties, and appends it to the **Properties** collection of the database. Then the example enumerates all properties in the database.</span></span>

```vb
    Sub PropertyX() 
     
     Dim dbsNorthwind As Database 
     Dim prpNew As Property 
     Dim prpLoop As Property 
     
     Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
     
     With dbsNorthwind 
     ' Create and append user-defined property. 
     Set prpNew = .CreateProperty() 
     prpNew.Name = "UserDefined" 
     prpNew.Type = dbText 
     prpNew.Value = "This is a user-defined property." 
     .Properties.Append prpNew 
     
     ' Enumerate all properties of current database. 
     Debug.Print "Properties of " & .Name 
     For Each prpLoop In .Properties 
     With prpLoop 
     Debug.Print " " & .Name 
     Debug.Print " Type: " & .Type 
     Debug.Print " Value: " & .Value 
     Debug.Print " Inherited: " & _ 
     .Inherited 
     End With 
     Next prpLoop 
     
     ' Delete new property because this is a 
     ' demonstration. 
     .Properties.Delete "UserDefined" 
     End With 
     
    End Sub 
```

<br/>

<span data-ttu-id="510d2-p106">以下示例尝试设置用户定义的属性的值。如果该属性不存在，则使用 **CreateProperty** 方法创建一个新属性并设置其值。若要使该过程运行，需要使用 SetProperty 过程。</span><span class="sxs-lookup"><span data-stu-id="510d2-p106">This example tries to set the value of a user-defined property. If the property doesn't exist, it uses the **CreateProperty** method to create and set the value of the new property. The SetProperty procedure is required for this procedure to run.</span></span>

```vb
    Sub CreatePropertyX() 
     
     Dim dbsNorthwind As Database 
     Dim prpLoop As Property 
     
     Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
     
     ' Set the Archive property to True. 
     SetProperty dbsNorthwind, "Archive", True 
     
     With dbsNorthwind 
     Debug.Print "Properties of " & .Name 
     
     ' Enumerate Properties collection of the Northwind 
     ' database. 
     For Each prpLoop In .Properties 
     If prpLoop <> "" Then Debug.Print " " & _ 
     prpLoop.Name & " = " & prpLoop 
     Next prpLoop 
     
     ' Delete the new property since this is a 
     ' demonstration. 
     .Properties.Delete "Archive" 
     
     .Close 
     End With 
     
    End Sub 
     
    Sub SetProperty(dbsTemp As Database, strName As String, _ 
     booTemp As Boolean) 
     
     Dim prpNew As Property 
     Dim errLoop As Error 
     
     ' Attempt to set the specified property. 
     On Error GoTo Err_Property 
     dbsTemp.Properties("strName") = booTemp 
     On Error GoTo 0 
     
     Exit Sub 
     
    Err_Property: 
     
     ' Error 3270 means that the property was not found. 
     If DBEngine.Errors(0).Number = 3270 Then 
     ' Create property, set its value, and append it to the 
     ' Properties collection. 
     Set prpNew = dbsTemp.CreateProperty(strName, _ 
     dbBoolean, booTemp) 
     dbsTemp.Properties.Append prpNew 
     Resume Next 
     Else 
     ' If different error has occurred, display message. 
     For Each errLoop In DBEngine.Errors 
     MsgBox "Error number: " & errLoop.Number & vbCr & _ 
     errLoop.Description 
     Next errLoop 
     End 
     End If 
     
    End Sub
```
