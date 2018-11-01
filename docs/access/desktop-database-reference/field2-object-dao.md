---
title: Field2 Object (DAO)
TOCTitle: Field2 Object
ms:assetid: 585aa163-402b-2c2b-d8d7-733a6d55d104
ms:mtpsurl: https://msdn.microsoft.com/library/Ff194326(v=office.15)
ms:contentKeyID: 48544994
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 7b092007ed2ba0dc3f2b6e53cc059e2382a064e9
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25870371"
---
# <a name="field2-object-dao"></a><span data-ttu-id="1ce6b-102">Field2 Object (DAO)</span><span class="sxs-lookup"><span data-stu-id="1ce6b-102">Field2 Object (DAO)</span></span>

<span data-ttu-id="1ce6b-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="1ce6b-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="1ce6b-104">**Field2** 对象代表具有普通数据类型和普通属性集的数据列。</span><span class="sxs-lookup"><span data-stu-id="1ce6b-104">A **Field2** object represents a column of data with a common data type and a common set of properties.</span></span>

## <a name="remarks"></a><span data-ttu-id="1ce6b-105">注解</span><span class="sxs-lookup"><span data-stu-id="1ce6b-105">Remarks</span></span>

<span data-ttu-id="1ce6b-p101">**Field2** 对象包含与 **[Field](field-object-dao.md)** 对象相同的所有属性和方法，并且 **Field2** 对象还包含几个支持多值字段类型的新增属性和方法。这几个新属性和方法是：</span><span class="sxs-lookup"><span data-stu-id="1ce6b-p101">A **Field2** object is contains all of the same properties and methods as the **[Field](field-object-dao.md)** object. The **Field2** object contains several new properties and methods that support multi-valued field types. The new properties and methods are:</span></span>

- <span data-ttu-id="1ce6b-109">**[AppendOnly](field2-appendonly-property-dao.md)** 属性</span><span class="sxs-lookup"><span data-stu-id="1ce6b-109">**[AppendOnly](field2-appendonly-property-dao.md)** property</span></span>

- <span data-ttu-id="1ce6b-110">**[ComplexType](field2-complextype-property-dao.md)** 属性</span><span class="sxs-lookup"><span data-stu-id="1ce6b-110">**[ComplexType](field2-complextype-property-dao.md)** property</span></span>

- <span data-ttu-id="1ce6b-111">**[IsComplex](field2-iscomplex-property-dao.md)** 属性</span><span class="sxs-lookup"><span data-stu-id="1ce6b-111">**[IsComplex](field2-iscomplex-property-dao.md)** property</span></span>

- <span data-ttu-id="1ce6b-112">**[LoadFromFile](field2-loadfromfile-method-dao.md)** 方法</span><span class="sxs-lookup"><span data-stu-id="1ce6b-112">**[LoadFromFile](field2-loadfromfile-method-dao.md)** method</span></span>

- <span data-ttu-id="1ce6b-113">**[SaveToFile](field2-savetofile-method-dao.md)** 方法</span><span class="sxs-lookup"><span data-stu-id="1ce6b-113">**[SaveToFile](field2-savetofile-method-dao.md)** method</span></span>

<span data-ttu-id="1ce6b-114">若要按照序号或 **Name** 属性设置来引用集合中的 **Field2** 对象，可以使用下列任何一种语法形式：</span><span class="sxs-lookup"><span data-stu-id="1ce6b-114">To refer to a **Field2** object in a collection by its ordinal number or by its **Name** property setting, use any of the following syntax forms:</span></span>

<span data-ttu-id="1ce6b-115">**Fields**(0)</span><span class="sxs-lookup"><span data-stu-id="1ce6b-115">**Fields**(0)</span></span>

<span data-ttu-id="1ce6b-116">**字段**("name")</span><span class="sxs-lookup"><span data-stu-id="1ce6b-116">**Fields**("name")</span></span>

<span data-ttu-id="1ce6b-117">**字段**\!\[名称\]</span><span class="sxs-lookup"><span data-stu-id="1ce6b-117">**Fields**\!\[name\]</span></span>

<span data-ttu-id="1ce6b-p102">还可以使用相同的语法形式，引用创建并追加到 **Fields** 集合中的 **Field2** 对象的 **Value** 属性。字段引用的上下文将确定引用的是 **Field2** 对象还是 **Field** 对象的 **Value** 属性。</span><span class="sxs-lookup"><span data-stu-id="1ce6b-p102">With the same syntax forms, you can also refer to the **Value** property of a **Field2** object that you create and append to a **Fields** collection. The context of the field reference will determine whether you are referring to the **Field2** object or the **Value** property of the **Field** object.</span></span>

## <a name="example"></a><span data-ttu-id="1ce6b-120">示例</span><span class="sxs-lookup"><span data-stu-id="1ce6b-120">Example</span></span>

<span data-ttu-id="1ce6b-121">下面的示例演示如何导航记录集包含一个多值字段。</span><span class="sxs-lookup"><span data-stu-id="1ce6b-121">The following example shows how to navigate a Recordset that contains a multi-value field.</span></span>

<span data-ttu-id="1ce6b-122">**示例代码提供者** [Microsoft Access 2010 Programmer's Reference](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125)。</span><span class="sxs-lookup"><span data-stu-id="1ce6b-122">**Sample code provided by** the [Microsoft Access 2010 Programmer’s Reference](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125).</span></span>

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

<br/>

<span data-ttu-id="1ce6b-123">下面的示例演示如何导航附件字段中的文件。</span><span class="sxs-lookup"><span data-stu-id="1ce6b-123">The following example shows how to navigate the files in an attachment field.</span></span> <span data-ttu-id="1ce6b-124">在即时窗口中打印的文件类型和每个附件的文件名。</span><span class="sxs-lookup"><span data-stu-id="1ce6b-124">The file type and filename of each attachment is printed in the Immediate window.</span></span>

```vb
    Sub ListAttachments()
        Dim dbs As DAO.Database
        Dim rst As DAO.Recordset2
        Dim rsA As DAO.Recordset2
        Dim fld As DAO.Field2
        
        'Get the database, recordset, and attachment field
        Set dbs = CurrentDb
        Set rst = dbs.OpenRecordset("tblAttachments")
        Set fld = rst("Attachments")
        
        'Navigate through the table
        Do While Not rst.EOF
        
            'Print the first and last name
            Debug.Print rst("FirstName") & " " & rst("LastName")
            
            'Get the recordset for the Attachments field
            Set rsA = fld.Value
            
            'Print all attachments in the field
            Do While Not rsA.EOF
                Debug.Print , rsA("FileType"), rsA("FileName")
                
                'Next attachment
                rsA.MoveNext
            Loop
            
            rsA.Close
            
            'Next record
            rst.MoveNext
        Loop
        
            
        rst.Close
        dbs.Close
        
        Set fld = Nothing
        Set rsA = Nothing
        Set rst = Nothing
        Set dbs = Nothing
    End Sub
```

<br/>

<span data-ttu-id="1ce6b-125">下面的示例演示如何将文件从指定的文件夹路径添加到附件字段。</span><span class="sxs-lookup"><span data-stu-id="1ce6b-125">The following example shows how to add files from a specified folder path to an attachment field.</span></span>

```vb
    Public Function LoadAttachments(strPath As String, Optional strPattern As String = "*.*") As Long
        Dim dbs As DAO.Database
        Dim rst As DAO.Recordset2
        Dim rsA As DAO.Recordset2
        Dim fld  As DAO.Field2
        Dim strFile As String
        
        'Get the database, recordset, and attachment field
        Set dbs = CurrentDb
        Set rst = dbs.OpenRecordset("tblAttachments")
        Set fld = rst("Attachments")
        
        'Navigate through the table
        Do While Not rst.EOF
        
            'Get the recordset for the Attachments field
            Set rsA = fld.Value
            
            'Load all attachments in the specified directory
            strFile = Dir(strPath & "\*.*")
            
            rst.Edit
            Do While Len(strFile) > 0
                'Add a new attachment that matches the pattern.
                'Pass "" to match all files.
                If strFile Like strPattern Then
                    rsA.AddNew
                    rsA("FileData").LoadFromFile strPath & "\" & strFile
                    rsA.Update
                    
                    'Increment the number of files added
                    LoadAttachments = LoadAttachments + 1
                End If
                strFile = Dir
            Loop
            rsA.Close
            
            rst.Update
            'Next record
            rst.MoveNext
        Loop
        
        rst.Close
        dbs.Close
        
        Set fld = Nothing
        Set rsA = Nothing
        Set rst = Nothing
        Set dbs = Nothing
    End Function
```

<br/>

<span data-ttu-id="1ce6b-126">下面的示例演示如何将保存到指定的文件夹路径附件字段中存储的文件。</span><span class="sxs-lookup"><span data-stu-id="1ce6b-126">The following example shows how to save the files stored in an attachment field to the specified folder path.</span></span>

```vb
    Public Function SaveAttachments(strPath As String, Optional strPattern As String = "*.*") As Long
        Dim dbs As DAO.Database
        Dim rst As DAO.Recordset2
        Dim rsA As DAO.Recordset2
        Dim fld As DAO.Field2
        Dim strFullPath As String
        
        'Get the database, recordset, and attachment field
        Set dbs = CurrentDb
        Set rst = dbs.OpenRecordset("tblAttachments")
        Set fld = rst("Attachments")
        
        'Navigate through the table
        Do While Not rst.EOF
        
            'Get the recordset for the Attachments field
            Set rsA = fld.Value
            
            'Save all attachments in the field
            Do While Not rsA.EOF
                If rsA("FileName") Like strPattern Then
                    strFullPath = strPath & "\" & rsA("FileName")
                    
                    'Make sure the file does not exist and save
                    If Dir(strFullPath) = "" Then
                        rsA("FileData").SaveToFile strFullPath
                    End If
                    
                    'Increment the number of files saved
                    SaveAttachments = SaveAttachments + 1
                End If
                
                'Next attachment
                rsA.MoveNext
            Loop
            rsA.Close
            
            'Next record
            rst.MoveNext
        Loop
        
        rst.Close
        dbs.Close
        
        Set fld = Nothing
        Set rsA = Nothing
        Set rst = Nothing
        Set dbs = Nothing
    End Function
```

<br/>

<span data-ttu-id="1ce6b-127">下面的示例演示如何删除附件字段中存储的文件。</span><span class="sxs-lookup"><span data-stu-id="1ce6b-127">The following example shows how to delete a file stored in an attachment field.</span></span>

```vb
    Function RemoveAttachment(strRemoveFile As String, Optional strFilter As String) As Long
        Dim dbs As DAO.Database
        Dim rst As DAO.Recordset2
        Dim rsA As DAO.Recordset2
        Dim fld As DAO.Field2
        
        'Get the database
        Set dbs = CurrentDb
        
        'Open the recordset. If the strFilter is supplied, add it to the WHERE
        'clause for the recordset. Otherwise, any files matching strFileName
        'will be deleted
        If Len(strFilter) > 0 Then
            Set rst = dbs.OpenRecordset("SELECT * FROM tblAttachments WHERE " & strFilter)
        Else
            Set rst = dbs.OpenRecordset("tblAttachments")
        End If
        
        'Get the Attachment field
        Set fld = rst("Attachments")
        
        'Navigate through the recordset
        Do While Not rst.EOF
        
            'Get the recordset for the Attachments field
            Set rsA = fld.Value
            
            'Walk the attachments and look for the file name to remove
            Do While Not rsA.EOF
                If rsA("FileName") Like strRemoveFile Then
                    rsA.Delete
                    
                    'Increment the number of files removed
                    RemoveAttachment = RemoveAttachment + 1
                End If
                rsA.MoveNext
            Loop
                    
            'Cleanup the Attachments recordset
            rsA.Close
            Set rsA = Nothing
            
            'Next record
            rst.MoveNext
        Loop
        
        rst.Close
        dbs.Close
        Set fld = Nothing
        Set rst = Nothing
        Set dbs = Nothing
    End Function
```
