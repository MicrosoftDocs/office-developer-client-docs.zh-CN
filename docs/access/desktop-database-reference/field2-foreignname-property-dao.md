---
title: Field2.ForeignName 属性 (DAO)
TOCTitle: ForeignName Property
ms:assetid: 76da233a-efb4-63cd-a2a2-d18d9e2fb2fb
ms:mtpsurl: https://msdn.microsoft.com/library/Ff196027(v=office.15)
ms:contentKeyID: 48545708
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1052932
f1_categories:
- Office.Version=v15
ms.openlocfilehash: f95839ac7b8832e22f69b31914f42de4f4adad06
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25929233"
---
# <a name="field2foreignname-property-dao"></a><span data-ttu-id="55863-102">Field2.ForeignName 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="55863-102">Field2.ForeignName property (DAO)</span></span>


<span data-ttu-id="55863-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="55863-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="55863-104">设置或返回一个值，该值指定某个外表中的 **Field2** 对象的名称，而该外表对应于某个关系的主表中的字段（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="55863-104">Sets or returns a value that specifies the name of the **Field2** object in a foreign table that corresponds to a field in a primary table for a relationship (Microsoft Access workspaces only).</span></span>

## <a name="syntax"></a><span data-ttu-id="55863-105">语法</span><span class="sxs-lookup"><span data-stu-id="55863-105">Syntax</span></span>

<span data-ttu-id="55863-106">*表达式*。ForeignName</span><span class="sxs-lookup"><span data-stu-id="55863-106">*expression* .ForeignName</span></span>

<span data-ttu-id="55863-107">*表达式*一个代表**Field2**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="55863-107">*expression* A variable that represents a **Field2** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="55863-108">注解</span><span class="sxs-lookup"><span data-stu-id="55863-108">Remarks</span></span>

<span data-ttu-id="55863-p101">如果 **[Relation](relation-object-dao.md)** 对象未追加到 **[Database](database-object-dao.md)** ，但是 **Field2** 已追加到 **Relation** 对象，则 **ForeignName** 属性是可读写的。将 **Relation** 对象追加到数据库后， **ForeignName** 属性是只读的。</span><span class="sxs-lookup"><span data-stu-id="55863-p101">If the **[Relation](relation-object-dao.md)** object isn't appended to the **[Database](database-object-dao.md)**, but the **Field2** is appended to the **Relation** object, the **ForeignName** property is read/write. Once the **Relation** object is appended to the database, the **ForeignName** property is read-only.</span></span>

<span data-ttu-id="55863-111">只有属于 **Relation** 对象 **Fields** 集合的 **Field2** 对象才能支持 **ForeignName** 属性。</span><span class="sxs-lookup"><span data-stu-id="55863-111">Only a **Field2** object that belongs to the **Fields** collection of a **Relation** object can support the **ForeignName** property.</span></span>

<span data-ttu-id="55863-p102">[Field2](connection-name-property-dao.md) 对象的 \*\*\*\*Name\*\*\*\* 和 **ForeignName** 属性设置指定关系的主表和外表中相应字段的名称。 [Relation](relation-table-property-dao.md) 对象的 [**Table**](relation-foreigntable-property-dao.md) 和 \*\*\*\*ForeignTable\*\*\*\* 属性设置确定关系的主表和外表。</span><span class="sxs-lookup"><span data-stu-id="55863-p102">The **[Name](connection-name-property-dao.md)** and **ForeignName** property settings for a **Field2** object specify the names of the corresponding fields in the primary and foreign tables of a relationship. The **[Table](relation-table-property-dao.md)** and **[ForeignTable](relation-foreigntable-property-dao.md)** property settings for a **Relation** object determine the primary and foreign tables of a relationship.</span></span>

<span data-ttu-id="55863-p103">例如，如果您有一个存储在 ValidParts 表中的有效部件代码列表（这些代码存储在名为 PartNo 的字段中），则可以与 OrderItem 表建立关系，这样的话，如果部件代码输入到 OrderItem 表中，它就会出现在 ValidParts 表中。如果部件代码在 ValidParts 表中不存在，并且您未将 [Relation](field-attributes-property-dao.md) 对象的 \*\*\*\*Attributes\*\*\*\* 属性设置为 **dbRelationDontEnforce**，则会发生可捕获的错误。</span><span class="sxs-lookup"><span data-stu-id="55863-p103">For example, if you had a list of valid part codes (in a field named PartNo) stored in a ValidParts table, you could establish a relationship with an OrderItem table such that if a part code were entered into the OrderItem table, it would have to already exist in the ValidParts table. If the part code didn't exist in the ValidParts table and you had not set the **[Attributes](field-attributes-property-dao.md)** property of the **Relation** object to **dbRelationDontEnforce**, a trappable error would occur.</span></span>

<span data-ttu-id="55863-p104">在这种情况下，ValidParts 表将是外表，因此 **Relation** 对象的 **ForeignTable** 属性将设置为 ValidParts， **Relation** 对象的 **Table** 属性将设置为 OrderItem。 **Relation** 对象的 **Fields** 集合中的 **Field2** 对象的 **Name** 和 **ForeignName** 属性将设置为 PartNo。</span><span class="sxs-lookup"><span data-stu-id="55863-p104">In this case, the ValidParts table is the foreign table, so the **ForeignTable** property of the **Relation** object would be set to ValidParts and the **Table** property of the **Relation** object would be set to OrderItem. The **Name** and **ForeignName** properties of the **Field2** object in the **Relation** object's **Fields** collection would be set to PartNo.</span></span>

## <a name="example"></a><span data-ttu-id="55863-118">示例</span><span class="sxs-lookup"><span data-stu-id="55863-118">Example</span></span>

<span data-ttu-id="55863-119">以下示例演示 **Table**、 **ForeignTable** 和 **ForeignName** 属性如何定义两个表之间的 **Relation** 条件。</span><span class="sxs-lookup"><span data-stu-id="55863-119">This example shows how the **Table**, **ForeignTable**, and **ForeignName** properties define the terms of a **Relation** between two tables.</span></span>

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
