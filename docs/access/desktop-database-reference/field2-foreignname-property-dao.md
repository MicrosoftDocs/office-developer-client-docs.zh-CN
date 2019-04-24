---
title: ForeignName 属性 (DAO)
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
localization_priority: Normal
ms.openlocfilehash: a8368165f73fc52c51cf1503da9c2cc02e969bf4
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32292809"
---
# <a name="field2foreignname-property-dao"></a><span data-ttu-id="d0ad5-102">ForeignName 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="d0ad5-102">Field2.ForeignName property (DAO)</span></span>


<span data-ttu-id="d0ad5-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="d0ad5-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="d0ad5-104">设置或返回一个值，该值指定某个外表中的 **Field2** 对象的名称，而该外表对应于某个关系的主表中的字段（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="d0ad5-104">Sets or returns a value that specifies the name of the **Field2** object in a foreign table that corresponds to a field in a primary table for a relationship (Microsoft Access workspaces only).</span></span>

## <a name="syntax"></a><span data-ttu-id="d0ad5-105">语法</span><span class="sxs-lookup"><span data-stu-id="d0ad5-105">Syntax</span></span>

<span data-ttu-id="d0ad5-106">*表达式*。ForeignName</span><span class="sxs-lookup"><span data-stu-id="d0ad5-106">*expression* .ForeignName</span></span>

<span data-ttu-id="d0ad5-107">*表达式*一个代表**Field2**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="d0ad5-107">*expression* A variable that represents a **Field2** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="d0ad5-108">注解</span><span class="sxs-lookup"><span data-stu-id="d0ad5-108">Remarks</span></span>

<span data-ttu-id="d0ad5-p101">如果 **[Relation](relation-object-dao.md)** 对象未追加到 **[Database](database-object-dao.md)** ，但是 **Field2** 已追加到 **Relation** 对象，则 **ForeignName** 属性是可读写的。将 **Relation** 对象追加到数据库后， **ForeignName** 属性是只读的。</span><span class="sxs-lookup"><span data-stu-id="d0ad5-p101">If the **[Relation](relation-object-dao.md)** object isn't appended to the **[Database](database-object-dao.md)**, but the **Field2** is appended to the **Relation** object, the **ForeignName** property is read/write. Once the **Relation** object is appended to the database, the **ForeignName** property is read-only.</span></span>

<span data-ttu-id="d0ad5-111">只有属于 **Relation** 对象 **Fields** 集合的 **Field2** 对象才能支持 **ForeignName** 属性。</span><span class="sxs-lookup"><span data-stu-id="d0ad5-111">Only a **Field2** object that belongs to the **Fields** collection of a **Relation** object can support the **ForeignName** property.</span></span>

<span data-ttu-id="d0ad5-112">**Field2**对象的**[Name](connection-name-property-dao.md)** 和**ForeignName**属性设置指定关系的主表和外表中相应字段的名称。</span><span class="sxs-lookup"><span data-stu-id="d0ad5-112">The **[Name](connection-name-property-dao.md)** and **ForeignName** property settings for a **Field2** object specify the names of the corresponding fields in the primary and foreign tables of a relationship.</span></span> <span data-ttu-id="d0ad5-113">**Relation**对象的**[Table](relation-table-property-dao.md)** 和**[ForeignTable](relation-foreigntable-property-dao.md)** 属性设置决定了关系的主表和外表。</span><span class="sxs-lookup"><span data-stu-id="d0ad5-113">The **[Table](relation-table-property-dao.md)** and **[ForeignTable](relation-foreigntable-property-dao.md)** property settings for a **Relation** object determine the primary and foreign tables of a relationship.</span></span>

<span data-ttu-id="d0ad5-114">例如，如果您有一个存储在 ValidParts 表中的有效部件代码列表（这些代码存储在名为 PartNo 的字段中），则可以与 OrderItem 表建立关系，这样的话，如果部件代码输入到 OrderItem 表中，它就会出现在 ValidParts 表中。</span><span class="sxs-lookup"><span data-stu-id="d0ad5-114">For example, if you had a list of valid part codes (in a field named PartNo) stored in a ValidParts table, you could establish a relationship with an OrderItem table such that if a part code were entered into the OrderItem table, it would have to already exist in the ValidParts table.</span></span> <span data-ttu-id="d0ad5-115">如果部分代码在 ValidParts 表中不存在, 并且您没有将**Relation**对象的**[Attributes](field-attributes-property-dao.md)** 属性设置为**dbRelationDontEnforce**, 则会发生可捕获的错误。</span><span class="sxs-lookup"><span data-stu-id="d0ad5-115">If the part code didn't exist in the ValidParts table and you had not set the **[Attributes](field-attributes-property-dao.md)** property of the **Relation** object to **dbRelationDontEnforce**, a trappable error would occur.</span></span>

<span data-ttu-id="d0ad5-p104">在这种情况下，ValidParts 表将是外表，因此 **Relation** 对象的 **ForeignTable** 属性将设置为 ValidParts， **Relation** 对象的 **Table** 属性将设置为 OrderItem。 **Relation** 对象的 **Fields** 集合中的 **Field2** 对象的 **Name** 和 **ForeignName** 属性将设置为 PartNo。</span><span class="sxs-lookup"><span data-stu-id="d0ad5-p104">In this case, the ValidParts table is the foreign table, so the **ForeignTable** property of the **Relation** object would be set to ValidParts and the **Table** property of the **Relation** object would be set to OrderItem. The **Name** and **ForeignName** properties of the **Field2** object in the **Relation** object's **Fields** collection would be set to PartNo.</span></span>

## <a name="example"></a><span data-ttu-id="d0ad5-118">示例</span><span class="sxs-lookup"><span data-stu-id="d0ad5-118">Example</span></span>

<span data-ttu-id="d0ad5-119">以下示例演示 **Table**、 **ForeignTable** 和 **ForeignName** 属性如何定义两个表之间的 **Relation** 条件。</span><span class="sxs-lookup"><span data-stu-id="d0ad5-119">This example shows how the **Table**, **ForeignTable**, and **ForeignName** properties define the terms of a **Relation** between two tables.</span></span>

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
