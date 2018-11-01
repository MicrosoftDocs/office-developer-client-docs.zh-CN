---
title: Field2.IsComplex Property (DAO)
TOCTitle: IsComplex Property
ms:assetid: ffc90e6e-e3ee-4f9b-ca6b-615199300d45
ms:mtpsurl: https://msdn.microsoft.com/library/Ff837318(v=office.15)
ms:contentKeyID: 48548970
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 5109b7f512782a8038cd197b74cc669dc5256569
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25871393"
---
# <a name="field2iscomplex-property-dao"></a><span data-ttu-id="4e723-102">Field2.IsComplex Property (DAO)</span><span class="sxs-lookup"><span data-stu-id="4e723-102">Field2.IsComplex Property (DAO)</span></span>

<span data-ttu-id="4e723-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="4e723-103">**Applies to**: Access 2013, Office 2013</span></span> 

<span data-ttu-id="4e723-p101">返回 **Boolean** 类型的值，该值指示指定字段是否是多值数据类型。只读。</span><span class="sxs-lookup"><span data-stu-id="4e723-p101">Returns **Boolean** that indicates whether the specified field is a multi-valued data type. Read-only.</span></span>

## <a name="version-information"></a><span data-ttu-id="4e723-106">版本信息</span><span class="sxs-lookup"><span data-stu-id="4e723-106">Version information</span></span>

<span data-ttu-id="4e723-107">添加的版本： Access 2007</span><span class="sxs-lookup"><span data-stu-id="4e723-107">Version Added: Access 2007</span></span>

## <a name="syntax"></a><span data-ttu-id="4e723-108">语法</span><span class="sxs-lookup"><span data-stu-id="4e723-108">Syntax</span></span>

<span data-ttu-id="4e723-109">*表达式*。IsComplex</span><span class="sxs-lookup"><span data-stu-id="4e723-109">*expression* .IsComplex</span></span>

<span data-ttu-id="4e723-110">*表达式*一个代表**Field2**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="4e723-110">*expression* A variable that represents a **Field2** object.</span></span>

## <a name="example"></a><span data-ttu-id="4e723-111">示例</span><span class="sxs-lookup"><span data-stu-id="4e723-111">Example</span></span>

<span data-ttu-id="4e723-112">下面的示例演示如何导航记录集包含一个多值字段。</span><span class="sxs-lookup"><span data-stu-id="4e723-112">The following example shows how to navigate a Recordset that contains a multi-value field.</span></span>

<span data-ttu-id="4e723-113">**示例代码提供者** [Microsoft Access 2010 Programmer's Reference](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125)。</span><span class="sxs-lookup"><span data-stu-id="4e723-113">**Sample code provided by** the [Microsoft Access 2010 Programmer’s Reference](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125).</span></span>

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
