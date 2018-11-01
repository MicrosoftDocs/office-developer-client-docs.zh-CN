---
title: Relation.Attributes Property (DAO)
TOCTitle: Attributes Property
ms:assetid: db19d2ad-5965-214c-211d-9a8eb9c3c522
ms:mtpsurl: https://msdn.microsoft.com/library/Ff835337(v=office.15)
ms:contentKeyID: 48548098
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: b33d9ce16982caebc5c21f304735088b6340c96a
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25867795"
---
# <a name="relationattributes-property-dao"></a><span data-ttu-id="52039-102">Relation.Attributes Property (DAO)</span><span class="sxs-lookup"><span data-stu-id="52039-102">Relation.Attributes Property (DAO)</span></span>


<span data-ttu-id="52039-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="52039-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="52039-p101">设置或返回一个值，该值指示 **Relation** 对象的一个或多个特征。可读写 **Long**。</span><span class="sxs-lookup"><span data-stu-id="52039-p101">Sets or returns a value that indicates one or more characteristics of a **Relation** object. Read/write **Long**.</span></span>

## <a name="syntax"></a><span data-ttu-id="52039-106">语法</span><span class="sxs-lookup"><span data-stu-id="52039-106">Syntax</span></span>

<span data-ttu-id="52039-107">*表达式*。属性</span><span class="sxs-lookup"><span data-stu-id="52039-107">*expression* .Attributes</span></span>

<span data-ttu-id="52039-108">*表达式*一个代表**Relation**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="52039-108">*expression* A variable that represents a **Relation** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="52039-109">注解</span><span class="sxs-lookup"><span data-stu-id="52039-109">Remarks</span></span>

<span data-ttu-id="52039-110">对于尚未追加到集合中的对象，该属性是可读写的。</span><span class="sxs-lookup"><span data-stu-id="52039-110">For an object not yet appended to a collection, this property is read/write.</span></span>

## <a name="example"></a><span data-ttu-id="52039-111">示例</span><span class="sxs-lookup"><span data-stu-id="52039-111">Example</span></span>

<span data-ttu-id="52039-112">以下示例显示 Northwind 数据库中 **Field**、 **Relation** 和 **TableDef** 对象的 **Attributes** 属性。</span><span class="sxs-lookup"><span data-stu-id="52039-112">This example displays the **Attributes** property for **Field**, **Relation**, and **TableDef** objects in the Northwind database.</span></span>

```vb 
Sub AttributesX() 
 
 Dim dbsNorthwind As Database 
 Dim fldLoop As Field 
 Dim relLoop As Relation 
 Dim tdfloop As TableDef 
 
 Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
 
 With dbsNorthwind 
 
 ' Display the attributes of a TableDef object's 
 ' fields. 
 Debug.Print "Attributes of fields in " & _ 
 .TableDefs(0).Name & " table:" 
 For Each fldLoop In .TableDefs(0).Fields 
 Debug.Print " " & fldLoop.Name & " = " & _ 
 fldLoop.Attributes 
 Next fldLoop 
 
 ' Display the attributes of the Northwind database's 
 ' relations. 
 Debug.Print "Attributes of relations in " & _ 
 .Name & ":" 
 For Each relLoop In .Relations 
 Debug.Print " " & relLoop.Name & " = " & _ 
 relLoop.Attributes 
 Next relLoop 
 
 ' Display the attributes of the Northwind database's 
 ' tables. 
 Debug.Print "Attributes of tables in " & .Name & ":" 
 For Each tdfloop In .TableDefs 
 Debug.Print " " & tdfloop.Name & " = " & _ 
 tdfloop.Attributes 
 Next tdfloop 
 
 .Close 
 End With 
 
End Sub 
 
```

