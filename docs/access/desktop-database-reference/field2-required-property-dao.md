---
title: Field2.Required 属性 (DAO)
TOCTitle: Required Property
ms:assetid: 7d14dfd7-a50d-6044-469e-1511c74c148d
ms:mtpsurl: https://msdn.microsoft.com/library/Ff196390(v=office.15)
ms:contentKeyID: 48545848
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 2bb7735bf2c19da3cf82ffcb10d3d5b99b1a01c1
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25928787"
---
# <a name="field2required-property-dao"></a><span data-ttu-id="fd635-102">Field2.Required 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="fd635-102">Field2.Required property (DAO)</span></span>


<span data-ttu-id="fd635-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="fd635-103">**Applies to**: Access 2013, Office 2013</span></span>


<span data-ttu-id="fd635-104">设置或返回一个值，该值指示 **Field2** 对象是否需要非 Null 值。</span><span class="sxs-lookup"><span data-stu-id="fd635-104">Sets or returns a value that indicates whether a **Field2** object requires a non-Null value.</span></span>

## <a name="syntax"></a><span data-ttu-id="fd635-105">语法</span><span class="sxs-lookup"><span data-stu-id="fd635-105">Syntax</span></span>

<span data-ttu-id="fd635-106">*表达式*。必填</span><span class="sxs-lookup"><span data-stu-id="fd635-106">*expression* .Required</span></span>

<span data-ttu-id="fd635-107">*表达式*一个代表**Field2**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="fd635-107">*expression* A variable that represents a **Field2** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="fd635-108">注解</span><span class="sxs-lookup"><span data-stu-id="fd635-108">Remarks</span></span>

<span data-ttu-id="fd635-109">对于尚未追加到 **Fields** 集合中的 **Field2**，该属性是可读写的。</span><span class="sxs-lookup"><span data-stu-id="fd635-109">For a **Field2** not yet appended to the **Fields** collection, this property is read/write.</span></span>

<span data-ttu-id="fd635-110">**Required** 属性的可用性取决于包含 **[Fields](fields-collection-dao.md)** 集合的对象，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="fd635-110">The availability of the **Required** property depends on the object that contains the **[Fields](fields-collection-dao.md)** collection, as shown in the following table.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="fd635-111">如果 Fields 集合属于</span><span class="sxs-lookup"><span data-stu-id="fd635-111">If the Fields collection belongs to a</span></span></p></th>
<th><p><span data-ttu-id="fd635-112">则 Required</span><span class="sxs-lookup"><span data-stu-id="fd635-112">Then Required is</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fd635-113"><strong>Index</strong> 对象</span><span class="sxs-lookup"><span data-stu-id="fd635-113"><strong>Index</strong> object</span></span></p></td>
<td><p><span data-ttu-id="fd635-114">不支持</span><span class="sxs-lookup"><span data-stu-id="fd635-114">Not supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd635-115"><strong>QueryDef</strong>对象</span><span class="sxs-lookup"><span data-stu-id="fd635-115"><strong>QueryDef</strong> object</span></span></p></td>
<td><p><span data-ttu-id="fd635-116">只读</span><span class="sxs-lookup"><span data-stu-id="fd635-116">Read-only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd635-117"><strong>Recordset</strong>对象</span><span class="sxs-lookup"><span data-stu-id="fd635-117"><strong>Recordset</strong> object</span></span></p></td>
<td><p><span data-ttu-id="fd635-118">只读</span><span class="sxs-lookup"><span data-stu-id="fd635-118">Read-only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd635-119"><strong>Relation</strong>对象</span><span class="sxs-lookup"><span data-stu-id="fd635-119"><strong>Relation</strong> object</span></span></p></td>
<td><p><span data-ttu-id="fd635-120">不支持</span><span class="sxs-lookup"><span data-stu-id="fd635-120">Not supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd635-121"><strong>TableDef</strong>对象</span><span class="sxs-lookup"><span data-stu-id="fd635-121"><strong>TableDef</strong> object</span></span></p></td>
<td><p><span data-ttu-id="fd635-122">读/写</span><span class="sxs-lookup"><span data-stu-id="fd635-122">Read/write</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="fd635-p101">可以将 **Required** 属性与 **AllowZeroLength**、 **ValidateOnSet** 或 **ValidationRule** 属性一起使用，以确定该 **Field2** 对象的 **Value** 属性设置的有效性。如果 **Required** 属性设置为 **False**，则该字段可以包含 **null** 值以及满足 **AllowZeroLength** 和 **ValidationRule** 属性设置所指定的条件的值。</span><span class="sxs-lookup"><span data-stu-id="fd635-p101">You can use the **Required** property along with the **AllowZeroLength**, **ValidateOnSet**, or **ValidationRule** property to determine the validity of the **Value** property setting for that **Field2** object. If the **Required** property is set to **False**, the field can contain **null** values as well as values that meet the conditions specified by the **AllowZeroLength** and **ValidationRule** property settings.</span></span>


> [!NOTE]
> <P><span data-ttu-id="fd635-p102">[!注释] 在您可以为 <STRONG>Index</STRONG> 对象或 <STRONG>Field2</STRONG> 对象设置该属性时，请为 <STRONG>Field2</STRONG> 对象设置该属性。这是因为需要先检查 <STRONG>Field2</STRONG> 对象属性设置的有效性，然后检查 <STRONG>Index</STRONG> 对象属性设置的有效性。</span><span class="sxs-lookup"><span data-stu-id="fd635-p102">When you can set this property for either an <STRONG>Index</STRONG> object or a <STRONG>Field2</STRONG> object, set it for the <STRONG>Field2</STRONG> object. The validity of the property setting for a <STRONG>Field2</STRONG> object is checked before that of an <STRONG>Index</STRONG> object.</span></span></P>



## <a name="example"></a><span data-ttu-id="fd635-127">示例</span><span class="sxs-lookup"><span data-stu-id="fd635-127">Example</span></span>

<span data-ttu-id="fd635-p103">以下示例使用 **Required** 属性报告为了添加新记录，三个不同表中的哪些字段必须包含数据。若要使该过程运行，需要使用 RequiredOutput 过程。</span><span class="sxs-lookup"><span data-stu-id="fd635-p103">This example uses the **Required** property to report which fields in three different tables must contain data in order for a new record to be added. The RequiredOutput procedure is required for this procedure to run.</span></span>

```vb 
Sub RequiredX() 
 
 Dim dbsNorthwind As Database 
 Dim tdfloop As TableDef 
 
 Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
 
 With dbsNorthwind 
 ' Show which fields are required in the Fields 
 ' collections of three different TableDef objects. 
 RequiredOutput .TableDefs("Categories") 
 RequiredOutput .TableDefs("Customers") 
 RequiredOutput .TableDefs("Employees") 
 .Close 
 End With 
 
End Sub 
 
Sub RequiredOutput(tdfTemp As TableDef) 
 
 Dim fldLoop As Field2 
 
 ' Enumerate Fields collection of the specified TableDef 
 ' and show the Required property. 
 Debug.Print "Fields in " & tdfTemp.Name & ":" 
 For Each fldLoop In tdfTemp.Fields 
 Debug.Print , fldLoop.Name & ", Required = " & _ 
 fldLoop.Required 
 Next fldLoop 
 
End Sub 
 
```

