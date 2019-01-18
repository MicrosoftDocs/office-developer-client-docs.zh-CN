---
title: Field2.IsComplex 属性 (DAO)
TOCTitle: IsComplex Property
ms:assetid: ffc90e6e-e3ee-4f9b-ca6b-615199300d45
ms:mtpsurl: https://msdn.microsoft.com/library/Ff837318(v=office.15)
ms:contentKeyID: 48548970
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: d24229a0fc3122cc8a9fb20b041fc9fadc5ccb0a
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28713152"
---
# <a name="field2iscomplex-property-dao"></a><span data-ttu-id="913ef-102">Field2.IsComplex 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="913ef-102">Field2.IsComplex property (DAO)</span></span>

<span data-ttu-id="913ef-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="913ef-103">**Applies to**: Access 2013, Office 2013</span></span> 

<span data-ttu-id="913ef-p101">返回 **Boolean** 类型的值，该值指示指定字段是否是多值数据类型。只读。</span><span class="sxs-lookup"><span data-stu-id="913ef-p101">Returns **Boolean** that indicates whether the specified field is a multi-valued data type. Read-only.</span></span>

## <a name="version-information"></a><span data-ttu-id="913ef-106">版本信息</span><span class="sxs-lookup"><span data-stu-id="913ef-106">Version information</span></span>

<span data-ttu-id="913ef-107">添加的版本： Access 2007</span><span class="sxs-lookup"><span data-stu-id="913ef-107">Version added: Access 2007</span></span>

## <a name="syntax"></a><span data-ttu-id="913ef-108">语法</span><span class="sxs-lookup"><span data-stu-id="913ef-108">Syntax</span></span>

<span data-ttu-id="913ef-109">*表达式*。IsComplex</span><span class="sxs-lookup"><span data-stu-id="913ef-109">*expression* .IsComplex</span></span>

<span data-ttu-id="913ef-110">*表达式*一个代表**Field2**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="913ef-110">*expression* A variable that represents a **Field2** object.</span></span>

## <a name="example"></a><span data-ttu-id="913ef-111">示例</span><span class="sxs-lookup"><span data-stu-id="913ef-111">Example</span></span>

<span data-ttu-id="913ef-112">下面的示例演示如何导航记录集包含一个多值字段。</span><span class="sxs-lookup"><span data-stu-id="913ef-112">The following example shows how to navigate a Recordset that contains a multi-value field.</span></span>

<span data-ttu-id="913ef-113">**示例代码提供者** [Microsoft Access 2010 Programmer's Reference](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125)。</span><span class="sxs-lookup"><span data-stu-id="913ef-113">**Sample code provided by** the [Microsoft Access 2010 Programmer’s Reference](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125).</span></span>

```vb
    Sub PrintStudentsAndClasses()
        Dim dbs As DAO.Database
        Dim rsStudents As DAO.Recordset2  'Recordset for students
        Dim rsClasses As DAO.Recordset2  'Recordset for classes
        Dim fld As DAO.Field2
    
        'open the database
        Set dbs = CurrentDb()
    
        'get the table of students
        Set rsStudents = dbs.OpenRecordset("tblStudents")
    
        'loop through the students
        Do While Not rsStudents.EOF
            
            'get the classes field
            Set fld = rsStudents("Classes")
    
            'get the classes Recordset
            'make sure the field is a multi-valued field before
            'getting a Recordset object
            If fld.IsComplex Then
                Set rsClasses = fld.Value
            End If
    
            'access all records in the Recordset
            If Not (rsClasses.BOF And rsClasses.EOF) Then
                rsClasses.MoveLast
                rsClasses.MoveFirst
            End If
    
            'print the student and number of classes
            Debug.Print rsStudents("FirstName") & " " & rsStudents("LastName"), _
                "Number of classes: " & rsClasses.RecordCount
    
            'print the classes for this student
            Do While Not rsClasses.EOF
                Debug.Print , rsClasses("Value")
                rsClasses.MoveNext
            Loop
    
            'close the Classes Recordset
            rsClasses.Close
    
            'get the next student
            rsStudents.MoveNext
    
        Loop
        
        'cleanup
        rsStudents.Close
    
        Set fld = Nothing
        Set rsStudents = Nothing
        Set dbs = Nothing
    
    End Sub
```
