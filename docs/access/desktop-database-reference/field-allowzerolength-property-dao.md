---
title: Field.AllowZeroLength Property (DAO)
TOCTitle: AllowZeroLength Property
ms:assetid: 5103a905-9258-e088-0210-857372f41c3c
ms:mtpsurl: https://msdn.microsoft.com/library/Ff193832(v=office.15)
ms:contentKeyID: 48544807
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1052962
f1_categories:
- Office.Version=v15
ms.openlocfilehash: cba5790ae557f7e5b29e8068d09d6fa7451cfb27
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467195"
---
# <a name="fieldallowzerolength-property-dao"></a><span data-ttu-id="4996e-102">Field.AllowZeroLength Property (DAO)</span><span class="sxs-lookup"><span data-stu-id="4996e-102">Field.AllowZeroLength Property (DAO)</span></span>

<span data-ttu-id="4996e-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="4996e-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="4996e-104">设置或返回一个值，该值指示零长度字符串 ("") 对于数据类型为"文本"或"备注"的 **[Field](field-value-property-dao.md)** 对象的 **[Value](field-object-dao.md)** 属性来说是否为有效设置（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="4996e-104">Sets or returns a value that indicates whether a zero-length string ("") is a valid setting for the **[Value](field-value-property-dao.md)** property of the **[Field](field-object-dao.md)** object with a Text or Memo data type (Microsoft Access workspaces only).</span></span>

## <a name="syntax"></a><span data-ttu-id="4996e-105">语法</span><span class="sxs-lookup"><span data-stu-id="4996e-105">Syntax</span></span>

<span data-ttu-id="4996e-106">*表达式*。AllowZeroLength</span><span class="sxs-lookup"><span data-stu-id="4996e-106">*expression* .AllowZeroLength</span></span>

<span data-ttu-id="4996e-107">*表达式*一个代表**Field**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="4996e-107">*expression* A variable that represents a **Field** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="4996e-108">注解</span><span class="sxs-lookup"><span data-stu-id="4996e-108">Remarks</span></span>

<span data-ttu-id="4996e-109">对于尚未追加到 **Fields** 集合中的对象，该属性是可读写的。</span><span class="sxs-lookup"><span data-stu-id="4996e-109">For an object not yet appended to the **Fields** collection, this property is read/write.</span></span>

<span data-ttu-id="4996e-110">将对象追加到 **Fields** 集合后， **AllowZeroLength** 属性的可用性将取决于包含 **Fields** 集合的对象，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="4996e-110">Once appended to a **Fields** collection, the availability of the **AllowZeroLength** property depends on the object that contains the **Fields** collection, as shown in the following table.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="4996e-111">如果 Fields 集合属于</span><span class="sxs-lookup"><span data-stu-id="4996e-111">If the Fields collection belongs to an</span></span></p></th>
<th><p><span data-ttu-id="4996e-112">则 AllowZeroLength</span><span class="sxs-lookup"><span data-stu-id="4996e-112">Then AllowZeroLength is</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4996e-113"><strong>Index</strong> 对象</span><span class="sxs-lookup"><span data-stu-id="4996e-113"><strong>Index</strong> object</span></span></p></td>
<td><p><span data-ttu-id="4996e-114">不支持</span><span class="sxs-lookup"><span data-stu-id="4996e-114">Not supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4996e-115"><strong>QueryDef</strong> 对象</span><span class="sxs-lookup"><span data-stu-id="4996e-115"><strong>QueryDef</strong> object</span></span></p></td>
<td><p><span data-ttu-id="4996e-116">只读</span><span class="sxs-lookup"><span data-stu-id="4996e-116">Read-only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4996e-117"><strong>Recordset</strong> 对象</span><span class="sxs-lookup"><span data-stu-id="4996e-117"><strong>Recordset</strong> object</span></span></p></td>
<td><p><span data-ttu-id="4996e-118">只读</span><span class="sxs-lookup"><span data-stu-id="4996e-118">Read-only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4996e-119"><strong>Relation</strong> 对象</span><span class="sxs-lookup"><span data-stu-id="4996e-119"><strong>Relation</strong> object</span></span></p></td>
<td><p><span data-ttu-id="4996e-120">不支持</span><span class="sxs-lookup"><span data-stu-id="4996e-120">Not supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4996e-121"><strong>TableDef</strong> 对象</span><span class="sxs-lookup"><span data-stu-id="4996e-121"><strong>TableDef</strong> object</span></span></p></td>
<td><p><span data-ttu-id="4996e-122">读/写</span><span class="sxs-lookup"><span data-stu-id="4996e-122">Read/write</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="4996e-123">可将该属性与 **[Required](field-required-property-dao.md)** 、 **[ValidateOnSet](field-validateonset-property-dao.md)** 或 **[ValidationRule](field-validationrule-property-dao.md)** 属性一起使用，以验证字段中的值。</span><span class="sxs-lookup"><span data-stu-id="4996e-123">You can use this property along with the **[Required](field-required-property-dao.md)**, **[ValidateOnSet](field-validateonset-property-dao.md)**, or **[ValidationRule](field-validationrule-property-dao.md)** property to validate a value in a field.</span></span>

## <a name="example"></a><span data-ttu-id="4996e-124">示例</span><span class="sxs-lookup"><span data-stu-id="4996e-124">Example</span></span>

<span data-ttu-id="4996e-p101">在以下示例中， **AllowZeroLength** 属性允许用户将 **Field** 的值设置为空字符串。在这种情况下，用户可区分数据未知的记录和未应用数据的记录。</span><span class="sxs-lookup"><span data-stu-id="4996e-p101">In this example, the **AllowZeroLength** property allows the user to set the value of a **Field** to an empty string. In this situation, the user can distinguish between a record where data is not known and a record where the data does not apply.</span></span>

```vb
    Sub AllowZeroLengthX() 
     
     Dim dbsNorthwind As Database 
     Dim tdfEmployees As TableDef 
     Dim fldTemp As Field 
     Dim rstEmployees As Recordset 
     Dim strMessage As String 
     Dim strInput As String 
     
     Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
     Set tdfEmployees = dbsNorthwind.TableDefs("Employees") 
     ' Create a new Field object and append it to the Fields 
     ' collection of the Employees table. 
     Set fldTemp = tdfEmployees.CreateField("FaxPhone", _ 
     dbText, 24) 
     fldTemp.AllowZeroLength = True 
     tdfEmployees.Fields.Append fldTemp 
     
     Set rstEmployees = _ 
     dbsNorthwind.OpenRecordset("Employees") 
     
     With rstEmployees 
     ' Get user input. 
     .Edit 
     strMessage = "Enter fax number for " & _ 
     !FirstName & " " & !LastName & "." & vbCr & _ 
     "[? - unknown, X - has no fax]" 
     strInput = UCase(InputBox(strMessage)) 
     If strInput <> "" Then 
     Select Case strInput 
     Case "?" 
     !FaxPhone = Null 
     Case "X" 
     !FaxPhone = "" 
     Case Else 
     !FaxPhone = strInput 
     End Select 
     
     .Update 
     
     ' Print report. 
     Debug.Print "Name - Fax number" 
     Debug.Print !FirstName & " " & !LastName & " - "; 
     
     If IsNull(!FaxPhone) Then 
     Debug.Print "[Unknown]" 
     Else 
     If !FaxPhone = "" Then 
     Debug.Print "[Has no fax]" 
     Else 
     Debug.Print !FaxPhone 
     End If 
     End If 
     
     Else 
     .CancelUpdate 
     End If 
     
     .Close 
     End With 
     
     ' Delete new field because this is a demonstration. 
     tdfEmployees.Fields.Delete fldTemp.Name 
     dbsNorthwind.Close 
     
    End Sub
```
