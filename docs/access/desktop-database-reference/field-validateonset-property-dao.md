---
title: Field.ValidateOnSet 属性 (DAO)
TOCTitle: ValidateOnSet Property
ms:assetid: 00245a8a-a78f-b0a8-3eb3-11dd27873984
ms:mtpsurl: https://msdn.microsoft.com/library/Ff844720(v=office.15)
ms:contentKeyID: 48542898
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1052929
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 1c8892236410005d556dbe7f9322303a23d411d8
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25925182"
---
# <a name="fieldvalidateonset-property-dao"></a><span data-ttu-id="1b6e9-102">Field.ValidateOnSet 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="1b6e9-102">Field.ValidateOnSet property (DAO)</span></span>


<span data-ttu-id="1b6e9-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="1b6e9-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="1b6e9-104">设置或返回一个值，该值指定当设置 **[Field](field-object-dao.md)** 对象的 **[Value](field-value-property-dao.md)** 属性时是否立即验证该对象的值（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="1b6e9-104">Sets or returns a value that specifies whether or not the value of a **[Field](field-object-dao.md)** object is immediately validated when the object's **[Value](field-value-property-dao.md)** property is set (Microsoft Access workspaces only).</span></span>

## <a name="syntax"></a><span data-ttu-id="1b6e9-105">语法</span><span class="sxs-lookup"><span data-stu-id="1b6e9-105">Syntax</span></span>

<span data-ttu-id="1b6e9-106">*表达式*。ValidateOnSet</span><span class="sxs-lookup"><span data-stu-id="1b6e9-106">*expression* .ValidateOnSet</span></span>

<span data-ttu-id="1b6e9-107">*表达式*一个代表**Field**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="1b6e9-107">*expression* A variable that represents a **Field** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="1b6e9-108">注解</span><span class="sxs-lookup"><span data-stu-id="1b6e9-108">Remarks</span></span>

<span data-ttu-id="1b6e9-109">只有 [**Recordset**](recordset-object-dao.md) 对象中的 **Field** 对象才支持可读写的 **ValidateOnSet** 属性。</span><span class="sxs-lookup"><span data-stu-id="1b6e9-109">Only **Field** objects in **[Recordset](recordset-object-dao.md)** objects support the **ValidateOnSet** property as read/write.</span></span>

<span data-ttu-id="1b6e9-p101">当用户输入包含大量备注数据的记录时，将 **ValidateOnSet** 属性设置为 **True** 非常有用。如果 **[Update](recordset-update-method-dao.md)** 调用由于另一字段违反验证规则而显示数据无效，则等待该调用验证数据会将时间浪费在将冗长的备注数据写入数据库上。</span><span class="sxs-lookup"><span data-stu-id="1b6e9-p101">Setting the **ValidateOnSet** property to **True** can be useful in a situation when a user is entering records that include substantial Memo data. Waiting until the **[Update](recordset-update-method-dao.md)** call to validate the data can result in unnecessary time spent writing the lengthy Memo data to the database if it turns out that the data was invalid anyway because a validation rule was broken in another field.</span></span>

## <a name="example"></a><span data-ttu-id="1b6e9-112">示例</span><span class="sxs-lookup"><span data-stu-id="1b6e9-112">Example</span></span>

<span data-ttu-id="1b6e9-p102">以下示例使用 **ValidateOnSet** 属性演示在数据输入过程中如何捕获错误。若要使该过程运行，需要使用 ValidateData 函数。</span><span class="sxs-lookup"><span data-stu-id="1b6e9-p102">This example uses the **ValidateOnSet** property to demonstrate how one might trap for errors during data entry. The ValidateData function is required for this procedure to run.</span></span>

```vb
    Sub ValidateOnSetX() 
     
     Dim dbsNorthwind As Database 
     Dim fldDays As Field 
     Dim rstEmployees As Recordset 
     
     Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
     
     ' Create and append a new Field object to the Fields 
     ' collection of the Employees table. 
     Set fldDays = _ 
     dbsNorthwind.TableDefs!Employees.CreateField( _ 
     "DaysOfVacation", dbInteger, 2) 
     fldDays.ValidationRule = "BETWEEN 1 AND 20" 
     fldDays.ValidationText = _ 
     "Number must be between 1 and 20!" 
     dbsNorthwind.TableDefs!Employees.Fields.Append fldDays 
     
     Set rstEmployees = _ 
     dbsNorthwind.OpenRecordset("Employees") 
     
     With rstEmployees 
     
     Do While True 
     ' Add new record. 
     .AddNew 
     
     ' Get user input for three fields. Verify that the 
     ' data do not violate the validation rules for any 
     ' of the fields. 
     If ValidateData(!FirstName, _ 
     "Enter first name.") = False Then Exit Do 
     If ValidateData(!LastName, _ 
     "Enter last name.") = False Then Exit Do 
     If ValidateData(!DaysOfVacation, _ 
     "Enter days of vacation.") = False Then Exit Do 
     
     .Update 
     .Bookmark = .LastModified 
     Debug.Print !FirstName & " " & !LastName & _ 
     " - " & "DaysOfVacation = " & !DaysOfVacation 
     
     ' Delete new record because this is a demonstration. 
     .Delete 
     Exit Do 
     Loop 
     
     ' Cancel AddNew method if any of the validation rules 
     ' were broken. 
     If .EditMode <> dbEditNone Then .CancelUpdate 
     .Close 
     End With 
     
     ' Delete new field because this is a demonstration. 
     dbsNorthwind.TableDefs!Employees.Fields.Delete _ 
     fldDays.Name 
     dbsNorthwind.Close 
     
    End Sub 
     
    Function ValidateData(fldTemp As Field, _ 
     strMessage As String) As Boolean 
     
     Dim strInput As String 
     Dim errLoop As Error 
     
     ValidateData = True 
     ' ValidateOnSet is only read/write for Field objects in 
     ' Recordset objects. 
     fldTemp.ValidateOnSet = True 
     
     Do While True 
     strInput = InputBox(strMessage) 
     If strInput = "" Then Exit Do 
     ' Trap for errors when setting the Field value. 
     On Error GoTo Err_Data 
     If fldTemp.Type = dbInteger Then 
     fldTemp = Val(strInput) 
     Else 
     fldTemp = strInput 
     End If 
     On Error GoTo 0 
     If Not IsNull(fldTemp) Then Exit Do 
     Loop 
     
     If strInput = "" Then ValidateData = False 
     
     Exit Function 
     
    Err_Data: 
     
     If DBEngine.Errors.Count > 0 Then 
     ' Enumerate the Errors collection. The description 
     ' property of the last Error object will be set to 
     ' the ValidationText property of the relevant 
     ' field. 
     For Each errLoop In DBEngine.Errors 
     MsgBox "Error number: " & errLoop.Number & _ 
     vbCr & errLoop.Description 
     Next errLoop 
     End If 
     
     Resume Next 
     
    End Function
```
