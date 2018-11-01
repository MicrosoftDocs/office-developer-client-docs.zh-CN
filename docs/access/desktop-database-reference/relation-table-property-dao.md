---
title: Relation.Table Property (DAO)
TOCTitle: Table Property
ms:assetid: cc4f64ef-c4e9-1a14-9263-5f8220d89840
ms:mtpsurl: https://msdn.microsoft.com/library/Ff834423(v=office.15)
ms:contentKeyID: 48547736
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1053068
f1_categories:
- Office.Version=v15
ms.openlocfilehash: bdc58837cea3f54e46a3e805523e77c27cb21e7c
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25870826"
---
# <a name="relationtable-property-dao"></a><span data-ttu-id="e9261-102">Relation.Table Property (DAO)</span><span class="sxs-lookup"><span data-stu-id="e9261-102">Relation.Table Property (DAO)</span></span>


<span data-ttu-id="e9261-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="e9261-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="e9261-p101">指示 **[Relation](relation-object-dao.md)** 对象的主表的名称。该属性应当等同于 **[TableDef](connection-name-property-dao.md)** 或 **[QueryDef](tabledef-object-dao.md)** 对象的 **[Name](querydef-object-dao.md)** 属性设置（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="e9261-p101">Indicates the name of a **[Relation](relation-object-dao.md)** object's primary table. This should be equal to the **[Name](connection-name-property-dao.md)** property setting of a **[TableDef](tabledef-object-dao.md)** or **[QueryDef](querydef-object-dao.md)** object (Microsoft Access workspaces only).</span></span>

## <a name="syntax"></a><span data-ttu-id="e9261-106">语法</span><span class="sxs-lookup"><span data-stu-id="e9261-106">Syntax</span></span>

<span data-ttu-id="e9261-107">*表达式*。表</span><span class="sxs-lookup"><span data-stu-id="e9261-107">*expression* .Table</span></span>

<span data-ttu-id="e9261-108">*表达式*一个代表**Relation**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="e9261-108">*expression* A variable that represents a **Relation** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="e9261-109">注解</span><span class="sxs-lookup"><span data-stu-id="e9261-109">Remarks</span></span>

<span data-ttu-id="e9261-110">对于新的尚未追加到集合中的 **Relation** 对象， **Table** 属性设置是可读写的；对于 [**Relations**](relations-collection-dao.md) 集合中的现有 **Relation** 对象，该属性设置是只读的。</span><span class="sxs-lookup"><span data-stu-id="e9261-110">The **Table** property setting is read/write for a new **Relation** object not yet appended to a collection and read-only for an existing **Relation** object in a **[Relations](relations-collection-dao.md)** collection.</span></span>

<span data-ttu-id="e9261-p102">将 **Table** 属性与 **[ForeignTable](relation-foreigntable-property-dao.md)** 属性一起使用，可以定义 **Relation** 对象（该对象表示两个表或查询中的字段间的关系）。将 **Table** 属性设置为主 **TableDef** 或 **QueryDef** 对象的 **Name** 属性设置，将 **ForeignTable** 属性设置为外部（引用） **TableDef** 或 **QueryDef** 对象的 **Name** 属性设置。 **[Attributes](field-attributes-property-dao.md)** 属性决定了两个对象之间的关系类型。</span><span class="sxs-lookup"><span data-stu-id="e9261-p102">Use the **Table** property with the **[ForeignTable](relation-foreigntable-property-dao.md)** property to define a **Relation** object, which represents the relationship between fields in two tables or queries. Set the **Table** property to the **Name** property setting of the primary **TableDef** or **QueryDef** object, and set the **ForeignTable** property to the **Name** property setting of the foreign (referencing) **TableDef** or **QueryDef** object. The **[Attributes](field-attributes-property-dao.md)** property determines the type of relationship between the two objects.</span></span>

<span data-ttu-id="e9261-p103">例如，如果您有一个存储在 ValidParts 表中的有效部件代码列表（这些代码存储在名为 PartNo 的字段中），则可以与 OrderItem 表建立一对多关系，这样一来，如果部件代码输入到 OrderItem 表中，它就会出现在 ValidParts 表中。如果部件代码不存在于 ValidParts 表中，并且您未将 **Relation** 对象的 **Attributes** 属性设置为 **dbRelationDontEnforce**，就会发生可捕获的错误。</span><span class="sxs-lookup"><span data-stu-id="e9261-p103">For example, if you had a list of valid part codes (in a field named PartNo) stored in a ValidParts table, you could establish a one-to-many relationship with an OrderItem table such that if a part code were entered into the OrderItem table, it would have to already be in the ValidParts table. If the part code didn't exist in the ValidParts table and you had not set the **Attributes** property of the **Relation** object to **dbRelationDontEnforce**, a trappable error would occur.</span></span>

<span data-ttu-id="e9261-p104">在本例中，ValidParts 表是主表，所以 **Relation** 对象的 **Table** 属性将设置为 ValidParts， **Relation** 对象的 **ForeignTable** 属性将设置为 OrderItem。 **Relation** 对象的 [**Fields**](field-object-dao.md) 集合中的 \*\*\*\*Field\*\*\*\* 对象的 [Name](fields-collection-dao.md) 和 **ForeignName** 属性将设置为 PartNo。</span><span class="sxs-lookup"><span data-stu-id="e9261-p104">In this case, the ValidParts table is the primary table, so the **Table** property of the **Relation** object would be set to ValidParts and the **ForeignTable** property of the **Relation** object would be set to OrderItem. The **Name** and **ForeignName** properties of the **[Field](field-object-dao.md)** object in the **Relation** object's **[Fields](fields-collection-dao.md)** collection would be set to PartNo.</span></span>

## <a name="example"></a><span data-ttu-id="e9261-118">示例</span><span class="sxs-lookup"><span data-stu-id="e9261-118">Example</span></span>

<span data-ttu-id="e9261-119">以下示例演示 **Table**、 **ForeignTable** 和 **ForeignName** 属性如何定义两个表之间的 **Relation** 条件。</span><span class="sxs-lookup"><span data-stu-id="e9261-119">This example shows how the **Table**, **ForeignTable**, and **ForeignName** properties define the terms of a **Relation** between two tables.</span></span>

```vb
    Sub ForeignNameX() 
     
     Dim dbsNorthwind As Database 
     Dim relLoop As Relation 
     
     Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
     
     Debug.Print "Relation" 
     Debug.Print " Table - Field" 
     Debug.Print " Primary (One) "; 
     Debug.Print ".Table - .Fields(0).Name" 
     Debug.Print " Foreign (Many) "; 
     Debug.Print ".ForeignTable - .Fields(0).ForeignName" 
     
     ' Enumerate the Relations collection of the Northwind 
     ' database to report on the property values of 
     ' the Relation objects and their Field objects. 
     For Each relLoop In dbsNorthwind.Relations 
     With relLoop 
     Debug.Print 
     Debug.Print .Name & " Relation" 
     Debug.Print " Table - Field" 
     Debug.Print " Primary (One) "; 
     Debug.Print .Table & " - " & .Fields(0).Name 
     Debug.Print " Foreign (Many) "; 
     Debug.Print .ForeignTable & " - " & _ 
     .Fields(0).ForeignName 
     End With 
     Next relLoop 
     
     dbsNorthwind.Close 
     
    End Sub
```
