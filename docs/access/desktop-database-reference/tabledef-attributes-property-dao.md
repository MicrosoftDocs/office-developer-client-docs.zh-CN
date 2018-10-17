---
title: TableDef.Attributes Property (DAO)
TOCTitle: Attributes Property
ms:assetid: d01588c3-e94e-06bd-6568-974873411f2d
ms:mtpsurl: https://msdn.microsoft.com/library/Ff834701(v=office.15)
ms:contentKeyID: 48547828
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 10c0c3211fe76b169f9c2ed634f8adb61c767cfc
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468662"
---
# <a name="tabledefattributes-property-dao"></a><span data-ttu-id="39935-102">TableDef.Attributes Property (DAO)</span><span class="sxs-lookup"><span data-stu-id="39935-102">TableDef.Attributes Property (DAO)</span></span>


<span data-ttu-id="39935-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="39935-103">**Applies to**: Access 2013 | Office 2013</span></span>


<span data-ttu-id="39935-p101">设置或返回一个值，该值指示 **TableDef** 对象的一个或多个特征。 **Long** 类型，可读写。</span><span class="sxs-lookup"><span data-stu-id="39935-p101">Sets or returns a value that indicates one or more characteristics of a **TableDef** object. Read/write **Long**.</span></span>

## <a name="syntax"></a><span data-ttu-id="39935-106">语法</span><span class="sxs-lookup"><span data-stu-id="39935-106">Syntax</span></span>

<span data-ttu-id="39935-107">*表达式*。属性</span><span class="sxs-lookup"><span data-stu-id="39935-107">*expression* .Attributes</span></span>

<span data-ttu-id="39935-108">*表达式*一个代表**TableDef**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="39935-108">*expression* A variable that represents a **TableDef** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="39935-109">注解</span><span class="sxs-lookup"><span data-stu-id="39935-109">Remarks</span></span>

<span data-ttu-id="39935-110">对于尚未追加到集合中的对象，该属性是可读写的。</span><span class="sxs-lookup"><span data-stu-id="39935-110">For an object not yet appended to a collection, this property is read/write.</span></span>

## <a name="example"></a><span data-ttu-id="39935-111">示例</span><span class="sxs-lookup"><span data-stu-id="39935-111">Example</span></span>

<span data-ttu-id="39935-112">以下示例显示 Northwind 数据库中 **Field**、 **Relation** 和 **TableDef** 对象的 **Attributes** 属性。</span><span class="sxs-lookup"><span data-stu-id="39935-112">This example displays the **Attributes** property for **Field**, **Relation**, and **TableDef** objects in the Northwind database.</span></span>

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
