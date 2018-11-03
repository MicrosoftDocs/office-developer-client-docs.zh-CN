---
title: Field.Required 属性 (DAO)
TOCTitle: Required Property
ms:assetid: 2f1dbdeb-a37a-59b2-fdc2-f16c7ae1a575
ms:mtpsurl: https://msdn.microsoft.com/library/Ff192247(v=office.15)
ms:contentKeyID: 48543999
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 6fbf95e02c9945558d70fff35f12a73ce0dee45e
ms.sourcegitcommit: 38d0db57580cc5f4a0231c27b1643f8db5431ca3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25937314"
---
# <a name="fieldrequired-property-dao"></a><span data-ttu-id="9fd31-102">Field.Required 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="9fd31-102">Field.Required property (DAO)</span></span>


<span data-ttu-id="9fd31-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="9fd31-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="9fd31-104">设置或返回一个值，该值指示 **[Field](field-object-dao.md)** 对象是否需要一个非 Null 值。</span><span class="sxs-lookup"><span data-stu-id="9fd31-104">Sets or returns a value that indicates whether a **[Field](field-object-dao.md)** object requires a non-Null value.</span></span>

## <a name="syntax"></a><span data-ttu-id="9fd31-105">语法</span><span class="sxs-lookup"><span data-stu-id="9fd31-105">Syntax</span></span>

<span data-ttu-id="9fd31-106">*表达式*。必填</span><span class="sxs-lookup"><span data-stu-id="9fd31-106">*expression* .Required</span></span>

<span data-ttu-id="9fd31-107">*表达式*一个代表**Field**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="9fd31-107">*expression* A variable that represents a **Field** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="9fd31-108">注解</span><span class="sxs-lookup"><span data-stu-id="9fd31-108">Remarks</span></span>

<span data-ttu-id="9fd31-109">对于尚未追加到 **Fields** 集合中的 **Field**，该属性是可读写的。</span><span class="sxs-lookup"><span data-stu-id="9fd31-109">For a **Field** not yet appended to the **Fields** collection, this property is read/write.</span></span>

<span data-ttu-id="9fd31-110">**Required** 属性的可用性取决于包含 [Fields](fields-collection-dao.md) 集合的对象，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="9fd31-110">The availability of the **Required** property depends on the object that contains the [Fields](fields-collection-dao.md) collection, as shown in the following table.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="9fd31-111">如果 Fields 集合属于</span><span class="sxs-lookup"><span data-stu-id="9fd31-111">If the Fields collection belongs to a</span></span></p></th>
<th><p><span data-ttu-id="9fd31-112">则 Required</span><span class="sxs-lookup"><span data-stu-id="9fd31-112">Then Required is</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9fd31-113"><strong>Index</strong> 对象</span><span class="sxs-lookup"><span data-stu-id="9fd31-113"><strong>Index</strong> object</span></span></p></td>
<td><p><span data-ttu-id="9fd31-114">不支持</span><span class="sxs-lookup"><span data-stu-id="9fd31-114">Not supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fd31-115"><strong>QueryDef</strong>对象</span><span class="sxs-lookup"><span data-stu-id="9fd31-115"><strong>QueryDef</strong> object</span></span></p></td>
<td><p><span data-ttu-id="9fd31-116">只读</span><span class="sxs-lookup"><span data-stu-id="9fd31-116">Read-only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fd31-117"><strong>Recordset</strong>对象</span><span class="sxs-lookup"><span data-stu-id="9fd31-117"><strong>Recordset</strong> object</span></span></p></td>
<td><p><span data-ttu-id="9fd31-118">只读</span><span class="sxs-lookup"><span data-stu-id="9fd31-118">Read-only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fd31-119"><strong>Relation</strong>对象</span><span class="sxs-lookup"><span data-stu-id="9fd31-119"><strong>Relation</strong> object</span></span></p></td>
<td><p><span data-ttu-id="9fd31-120">不支持</span><span class="sxs-lookup"><span data-stu-id="9fd31-120">Not supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fd31-121"><strong>TableDef</strong>对象</span><span class="sxs-lookup"><span data-stu-id="9fd31-121"><strong>TableDef</strong> object</span></span></p></td>
<td><p><span data-ttu-id="9fd31-122">读/写</span><span class="sxs-lookup"><span data-stu-id="9fd31-122">Read/write</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="9fd31-p101">可以将 **Required** 属性与 **[AllowZeroLength](field-allowzerolength-property-dao.md)** 、 **[ValidateOnSet](field-validateonset-property-dao.md)** 或 **[ValidationRule](field-validationrule-property-dao.md)** 属性一起使用，以确定该 [Field](field-value-property-dao.md) 对象的 \*\*\*\*Value\*\*\*\* 属性设置的有效性。如果 **Required** 属性设置为 **False**，则该字段可以包含 **null** 值以及满足 **AllowZeroLength** 和 **ValidationRule** 属性设置所指定的条件的值。</span><span class="sxs-lookup"><span data-stu-id="9fd31-p101">You can use the **Required** property along with the **[AllowZeroLength](field-allowzerolength-property-dao.md)**, **[ValidateOnSet](field-validateonset-property-dao.md)**, or **[ValidationRule](field-validationrule-property-dao.md)** property to determine the validity of the **[Value](field-value-property-dao.md)** property setting for that **Field** object. If the **Required** property is set to **False**, the field can contain **null** values as well as values that meet the conditions specified by the **AllowZeroLength** and **ValidationRule** property settings.</span></span>


> [!NOTE]
> <span data-ttu-id="9fd31-p102">[!注释] 在您可以为 **Index** 对象或 **Field** 对象设置该属性时，请为 **Field** 对象设置该属性。这是因为需要先检查 **Field** 对象属性设置的有效性，然后检查 **Index** 对象属性设置的有效性。</span><span class="sxs-lookup"><span data-stu-id="9fd31-p102">When you can set this property for either an **Index** object or a **Field** object, set it for the **Field** object. The validity of the property setting for a **Field** object is checked before that of an **Index** object.</span></span>



## <a name="example"></a><span data-ttu-id="9fd31-127">示例</span><span class="sxs-lookup"><span data-stu-id="9fd31-127">Example</span></span>

<span data-ttu-id="9fd31-p103">以下示例使用 **Required** 属性报告为了添加新记录，三个不同表中的哪些字段必须包含数据。若要使该过程运行，需要使用 RequiredOutput 过程。</span><span class="sxs-lookup"><span data-stu-id="9fd31-p103">This example uses the **Required** property to report which fields in three different tables must contain data in order for a new record to be added. The RequiredOutput procedure is required for this procedure to run.</span></span>

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
 
 Dim fldLoop As Field 
 
 ' Enumerate Fields collection of the specified TableDef 
 ' and show the Required property. 
 Debug.Print "Fields in " & tdfTemp.Name & ":" 
 For Each fldLoop In tdfTemp.Fields 
 Debug.Print , fldLoop.Name & ", Required = " & _ 
 fldLoop.Required 
 Next fldLoop 
 
End Sub 
 
```

