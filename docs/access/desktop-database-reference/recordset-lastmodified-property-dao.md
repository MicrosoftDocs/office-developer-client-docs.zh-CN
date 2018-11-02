---
title: Recordset.LastModified 属性 (DAO)
TOCTitle: LastModified Property
ms:assetid: 7386f25b-bde1-a446-e980-640696a3bfec
ms:mtpsurl: https://msdn.microsoft.com/library/Ff195859(v=office.15)
ms:contentKeyID: 48545640
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1052898
f1_categories:
- Office.Version=v15
ms.openlocfilehash: be2e066801754c419b3c3b74e673af8f8034f2e7
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25920975"
---
# <a name="recordsetlastmodified-property-dao"></a><span data-ttu-id="e0736-102">Recordset.LastModified 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="e0736-102">Recordset.LastModified property (DAO)</span></span>


<span data-ttu-id="e0736-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="e0736-103">**Applies to**: Access 2013, Office 2013</span></span> 

<span data-ttu-id="e0736-104">返回一个书签，该书签指示最近添加或更改的记录。</span><span class="sxs-lookup"><span data-stu-id="e0736-104">Returns a bookmark indicating the most recently added or changed record.</span></span>

## <a name="syntax"></a><span data-ttu-id="e0736-105">语法</span><span class="sxs-lookup"><span data-stu-id="e0736-105">Syntax</span></span>

<span data-ttu-id="e0736-106">*表达式*。LastModified</span><span class="sxs-lookup"><span data-stu-id="e0736-106">*expression* .LastModified</span></span>

<span data-ttu-id="e0736-107">*表达式*一个表示**Recordset**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="e0736-107">*expression* A variable that represents a **Recordset** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="e0736-108">注解</span><span class="sxs-lookup"><span data-stu-id="e0736-108">Remarks</span></span>

<span data-ttu-id="e0736-p101">可以使用 **LastModified** 属性移动到最近添加或删除的记录。可以将 **LastModified** 属性用于表类型和动态集类型的 **[Recordset](recordset-object-dao.md)** 对象。必须在 **Recordset** 对象自身中添加或修改记录， **LastModified** 属性才能有值。</span><span class="sxs-lookup"><span data-stu-id="e0736-p101">You can use the **LastModified** property to move to the most recently added or updated record. Use the **LastModified** property with table- and dynaset-type **[Recordset](recordset-object-dao.md)** objects. A record must be added or modified in the **Recordset** object itself in order for the **LastModified** property to have a value.</span></span>

## <a name="example"></a><span data-ttu-id="e0736-112">示例</span><span class="sxs-lookup"><span data-stu-id="e0736-112">Example</span></span>

<span data-ttu-id="e0736-113">以下示例使用 **LastModified** 属性将当前记录指针移动到已修改的记录和新创建的记录。</span><span class="sxs-lookup"><span data-stu-id="e0736-113">This example uses the **LastModified** property to move the current record pointer to both a record that has been modified and a newly created record.</span></span>

```vb
    Sub LastModifiedX() 
     
     Dim dbsNorthwind As Database 
     Dim rstEmployees As Recordset 
     Dim strFirst As String 
     Dim strLast As String 
     
     Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
     Set rstEmployees = _ 
     dbsNorthwind.OpenRecordset("Employees", _ 
     dbOpenDynaset) 
     
     With rstEmployees 
     ' Store current data. 
     strFirst = !FirstName 
     strLast = !LastName 
     ' Change data in current record. 
     .Edit 
     !FirstName = "Julie" 
     !LastName = "Warren" 
     .Update 
     ' Move current record pointer to the most recently 
     ' changed or added record. 
     .Bookmark = .LastModified 
     Debug.Print _ 
     "Data in LastModified record after Edit: " & _ 
     !FirstName & " " & !LastName 
     
     ' Restore original data because this is a demonstration. 
     .Edit 
     !FirstName = strFirst 
     !LastName = strLast 
     .Update 
     
     ' Add new record. 
     .AddNew 
     !FirstName = "Roger" 
     !LastName = "Harui" 
     .Update 
     ' Move current record pointer to the most recently 
     ' changed or added record. 
     .Bookmark = .LastModified 
     Debug.Print _ 
     "Data in LastModified record after AddNew: " & _ 
     !FirstName & " " & !LastName 
     
     ' Delete new record because this is a demonstration. 
     .Delete 
     .Close 
     End With 
     
     dbsNorthwind.Close 
     
    End Sub 
```

<br/>

<span data-ttu-id="e0736-p102">以下示例使用 **AddNew** 方法创建一个具有指定名称的新记录。若要使该过程运行，需要使用 AddName 函数。</span><span class="sxs-lookup"><span data-stu-id="e0736-p102">This example uses the **AddNew** method to create a new record with the specified name. The AddName function is required for this procedure to run.</span></span>

```vb
    Sub AddNewX() 
     
     Dim dbsNorthwind As Database 
     Dim rstEmployees As Recordset 
     Dim strFirstName As String 
     Dim strLastName As String 
     
     Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
     Set rstEmployees = _ 
     dbsNorthwind.OpenRecordset("Employees", dbOpenDynaset) 
     
     ' Get data from the user. 
     strFirstName = Trim(InputBox( _ 
     "Enter first name:")) 
     strLastName = Trim(InputBox( _ 
     "Enter last name:")) 
     
     ' Proceed only if the user actually entered something 
     ' for both the first and last names. 
     If strFirstName <> "" and strLastName <> "" Then 
     
     ' Call the function that adds the record. 
     AddName rstEmployees, strFirstName, strLastName 
     
     ' Show the newly added data. 
     With rstEmployees 
     Debug.Print "New record: " & !FirstName & _ 
     " " & !LastName 
     ' Delete new record because this is a demonstration. 
     .Delete 
     End With 
     
     Else 
     Debug.Print _ 
     "You must input a string for first and last name!" 
     End If 
     
     rstEmployees.Close 
     dbsNorthwind.Close 
     
    End Sub 
     
    Function AddName(rstTemp As Recordset, _ 
     strFirst As String, strLast As String) 
     
     ' Adds a new record to a Recordset using the data passed 
     ' by the calling procedure. The new record is then made 
     ' the current record. 
     With rstTemp 
     .AddNew 
     !FirstName = strFirst 
     !LastName = strLast 
     .Update 
     .Bookmark = .LastModified 
     End With 
     
    End Function
```
