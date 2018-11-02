---
title: Property.Inherited 属性 (DAO)
TOCTitle: Inherited Property
ms:assetid: 10e624db-2301-b9be-beca-6e8caccf7274
ms:mtpsurl: https://msdn.microsoft.com/library/Ff845349(v=office.15)
ms:contentKeyID: 48543304
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1052991
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 56f0153748a6d5cc7dd8e6b15dbae93fb638a381
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25927156"
---
# <a name="propertyinherited-property-dao"></a><span data-ttu-id="6dc69-102">Property.Inherited 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="6dc69-102">Property.Inherited property (DAO)</span></span>


<span data-ttu-id="6dc69-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="6dc69-103">**Applies to**: Access 2013, Office 2013</span></span> 

<span data-ttu-id="6dc69-104">返回一个值，该值指示某个 **[Property](property-object-dao.md)** 对象是否是从基础对象中继承的。</span><span class="sxs-lookup"><span data-stu-id="6dc69-104">Returns a value that indicates whether a **[Property](property-object-dao.md)** object is inherited from an underlying object.</span></span>

## <a name="syntax"></a><span data-ttu-id="6dc69-105">语法</span><span class="sxs-lookup"><span data-stu-id="6dc69-105">Syntax</span></span>

<span data-ttu-id="6dc69-106">*表达式*。继承</span><span class="sxs-lookup"><span data-stu-id="6dc69-106">*expression* .Inherited</span></span>

<span data-ttu-id="6dc69-107">*表达式*一个代表**Property**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="6dc69-107">*expression* A variable that represents a **Property** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="6dc69-108">注解</span><span class="sxs-lookup"><span data-stu-id="6dc69-108">Remarks</span></span>

<span data-ttu-id="6dc69-109">对于代表预定义属性的内置 **Property** 对象，唯一可能的返回值是 **False**。</span><span class="sxs-lookup"><span data-stu-id="6dc69-109">For built-in **Property** objects that represent predefined properties, the only possible return value is **False**.</span></span>

<span data-ttu-id="6dc69-p101">可以使用 **Inherited** 属性确定某个用户定义的 **Property** 是否是为其应用到的对象创建的，或者 **Property** 是否是从另一个对象继承的。例如，假设您为 [**QueryDef**](querydef-object-dao.md) 对象创建了一个新的 **Property**，然后从 [QueryDef](recordset-object-dao.md) 对象打开了一个 \*\*\*\*Recordset\*\*\*\* 对象。此新的 **Property** 将是 **Recordset** 对象的 **[Properties](properties-collection-dao.md)** 集合的一部分，并且其 **Inherited** 属性将设置为 **True**，这是因为该属性是为 **QueryDef** 对象（而不是为 **Recordset** 对象）创建的。</span><span class="sxs-lookup"><span data-stu-id="6dc69-p101">You can use the **Inherited** property to determine whether a user-defined **Property** was created for the object it applies to, or whether the **Property** was inherited from another object. For example, suppose you create a new **Property** for a **[QueryDef](querydef-object-dao.md)** object and then open a **[Recordset](recordset-object-dao.md)** object from the **QueryDef** object. This new **Property** will be part of the **Recordset** object's **[Properties](properties-collection-dao.md)** collection, and its **Inherited** property will be set to **True** because the property was created for the **QueryDef** object, not the **Recordset** object.</span></span>

## <a name="example"></a><span data-ttu-id="6dc69-113">示例</span><span class="sxs-lookup"><span data-stu-id="6dc69-113">Example</span></span>

<span data-ttu-id="6dc69-114">以下示例使用 **Inherited** 属性确定用户定义的 **Property** 对象是为 **Recordset** 对象创建的，还是为某个基础对象创建的。</span><span class="sxs-lookup"><span data-stu-id="6dc69-114">This example use the **Inherited** property to determine if a user-defined **Property** object was created for a **Recordset** object or for some underlying object.</span></span>

```vb 
Sub InheritedX() 
 
 Dim dbsNorthwind As Database 
 Dim tdfTest As TableDef 
 Dim rstTest As Recordset 
 Dim prpNew As Property 
 Dim prpLoop As Property 
 
 ' Create a new property for a saved TableDef object, then 
 ' open a recordset from that TableDef object. 
 Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
 Set tdfTest = dbsNorthwind.TableDefs(0) 
 Set prpNew = tdfTest.CreateProperty("NewProperty", _ 
 dbBoolean, True) 
 tdfTest.Properties.Append prpNew 
 Set rstTest = tdfTest.OpenRecordset(dbOpenForwardOnly) 
 
 ' Show Name and Inherited property of the new Property 
 ' object in the TableDef. 
 Debug.Print "NewProperty of " & tdfTest.Name & _ 
 " TableDef:" 
 Debug.Print " Inherited = " & _ 
 tdfTest.Properties("NewProperty").Inherited 
 
 ' Show Name and Inherited property of the new Property 
 ' object in the Recordset. 
 Debug.Print "NewProperty of " & rstTest.Name & _ 
 " Recordset:" 
 Debug.Print " Inherited = " & _ 
 rstTest.Properties("NewProperty").Inherited 
 
 ' Delete new TableDef because this is a demonstration. 
 tdfTest.Properties.Delete prpNew.Name 
 dbsNorthwind.Close 
 
End Sub 
 
```

