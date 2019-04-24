---
title: LoadFromFile 方法 (DAO)
TOCTitle: LoadFromFile Method
ms:assetid: 8ffe4636-d4da-0579-f4b5-14f423647562
ms:mtpsurl: https://msdn.microsoft.com/library/Ff197396(v=office.15)
ms:contentKeyID: 48546314
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1101190
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: bdb1ba92c4a0f4fbee7204b2f4fee8a96c87cc1b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32292788"
---
# <a name="field2loadfromfile-method-dao"></a><span data-ttu-id="fac5a-102">LoadFromFile 方法 (DAO)</span><span class="sxs-lookup"><span data-stu-id="fac5a-102">Field2.LoadFromFile method (DAO)</span></span>

<span data-ttu-id="fac5a-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="fac5a-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="fac5a-104">从磁盘加载指定文件。</span><span class="sxs-lookup"><span data-stu-id="fac5a-104">Loads the specified file from disk.</span></span>

## <a name="version-information"></a><span data-ttu-id="fac5a-105">版本信息</span><span class="sxs-lookup"><span data-stu-id="fac5a-105">Version information</span></span>

<span data-ttu-id="fac5a-106">添加的版本: Access 2007</span><span class="sxs-lookup"><span data-stu-id="fac5a-106">Version added: Access 2007</span></span>

## <a name="syntax"></a><span data-ttu-id="fac5a-107">语法</span><span class="sxs-lookup"><span data-stu-id="fac5a-107">Syntax</span></span>

<span data-ttu-id="fac5a-108">*表达式*。LoadFromFile (***FileName***)</span><span class="sxs-lookup"><span data-stu-id="fac5a-108">*expression* .LoadFromFile(***FileName***)</span></span>

<span data-ttu-id="fac5a-109">*表达式*一个代表**Field2**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="fac5a-109">*expression* A variable that represents a **Field2** object.</span></span>

## <a name="parameters"></a><span data-ttu-id="fac5a-110">参数</span><span class="sxs-lookup"><span data-stu-id="fac5a-110">Parameters</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="fac5a-111">名称</span><span class="sxs-lookup"><span data-stu-id="fac5a-111">Name</span></span></p></th>
<th><p><span data-ttu-id="fac5a-112">必需/可选</span><span class="sxs-lookup"><span data-stu-id="fac5a-112">Required/optional</span></span></p></th>
<th><p><span data-ttu-id="fac5a-113">数据类型</span><span class="sxs-lookup"><span data-stu-id="fac5a-113">Data type</span></span></p></th>
<th><p><span data-ttu-id="fac5a-114">说明</span><span class="sxs-lookup"><span data-stu-id="fac5a-114">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fac5a-115"><em>FileName</em></span><span class="sxs-lookup"><span data-stu-id="fac5a-115"><em>FileName</em></span></span></p></td>
<td><p><span data-ttu-id="fac5a-116">必需</span><span class="sxs-lookup"><span data-stu-id="fac5a-116">Required</span></span></p></td>
<td><p><span data-ttu-id="fac5a-117"><strong>String</strong></span><span class="sxs-lookup"><span data-stu-id="fac5a-117"><strong>String</strong></span></span></p></td>
<td><p><span data-ttu-id="fac5a-118">要加载的文件的完全限定路径。</span><span class="sxs-lookup"><span data-stu-id="fac5a-118">The fully qualified path of the file to that you want to load.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="example"></a><span data-ttu-id="fac5a-119">示例</span><span class="sxs-lookup"><span data-stu-id="fac5a-119">Example</span></span>

<span data-ttu-id="fac5a-120">以下代码段使用 **LoadFromFile** 方法从磁盘加载雇员的图片。</span><span class="sxs-lookup"><span data-stu-id="fac5a-120">The following code snippet uses the **LoadFromFile** method to load an employee's picture from disk.</span></span>

```vb 
   '  Instantiate the parent recordset.  
   Set rsEmployees = db.OpenRecordset("Employees") 
  
   … Code to move to desired employee 
  
   ' Activate edit mode. 
   rsEmployees.Edit 
  
   ' Instantiate the child recordset. 
   Set rsPictures = rsEmployees.Fields("Pictures").Value  
  
   ' Add a new attachment. 
   rsPictures.AddNew 
   rsPictures.Fields("FileData").LoadFromFile "EmpPhoto39392.jpg" 
   rsPictures.Update 
  
   ' Update the parent record 
   rsEmployees.Update 
```

<br/>

<span data-ttu-id="fac5a-121">下面的示例演示如何将文件从指定的文件夹路径添加到附件字段。</span><span class="sxs-lookup"><span data-stu-id="fac5a-121">The following example shows how to add files from a specified folder path to an attachment field.</span></span>

<span data-ttu-id="fac5a-122">**示例代码提供方：**[Microsoft Access 2010 程序员参考](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125)。</span><span class="sxs-lookup"><span data-stu-id="fac5a-122">**Sample code provided by** the [Microsoft Access 2010 Programmer’s Reference](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125).</span></span>

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
