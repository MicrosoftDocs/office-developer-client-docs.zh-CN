---
title: Field2.SaveToFile 方法 (DAO)
TOCTitle: SaveToFile Method
ms:assetid: 250f9596-1a03-471d-96f9-718cd57dc94f
ms:mtpsurl: https://msdn.microsoft.com/library/Ff191852(v=office.15)
ms:contentKeyID: 48543776
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1101191
f1_categories:
- Office.Version=v15
localization_priority: Priority
ms.openlocfilehash: 78b08575b1fde304dc47b8219c1143cda265baf8
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28706980"
---
# <a name="field2savetofile-method-dao"></a><span data-ttu-id="49368-102">Field2.SaveToFile 方法 (DAO)</span><span class="sxs-lookup"><span data-stu-id="49368-102">Field2.SaveToFile method (DAO)</span></span>

<span data-ttu-id="49368-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="49368-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="49368-104">将保存到磁盘上的附件。</span><span class="sxs-lookup"><span data-stu-id="49368-104">Saves an attachment to disk.</span></span>

## <a name="version-information"></a><span data-ttu-id="49368-105">版本信息</span><span class="sxs-lookup"><span data-stu-id="49368-105">Version information</span></span>

<span data-ttu-id="49368-106">添加的版本： Access 2007</span><span class="sxs-lookup"><span data-stu-id="49368-106">Version added: Access 2007</span></span>

## <a name="syntax"></a><span data-ttu-id="49368-107">语法</span><span class="sxs-lookup"><span data-stu-id="49368-107">Syntax</span></span>

<span data-ttu-id="49368-108">*表达式*。SaveToFile (***文件名***)</span><span class="sxs-lookup"><span data-stu-id="49368-108">*expression* .SaveToFile(***FileName***)</span></span>

<span data-ttu-id="49368-109">*表达式*一个代表**Field2**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="49368-109">*expression* A variable that represents a **Field2** object.</span></span>

## <a name="parameters"></a><span data-ttu-id="49368-110">Parameters</span><span class="sxs-lookup"><span data-stu-id="49368-110">Parameters</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="49368-111">Name</span><span class="sxs-lookup"><span data-stu-id="49368-111">Name</span></span></p></th>
<th><p><span data-ttu-id="49368-112">必需/可选</span><span class="sxs-lookup"><span data-stu-id="49368-112">Required/optional</span></span></p></th>
<th><p><span data-ttu-id="49368-113">数据类型</span><span class="sxs-lookup"><span data-stu-id="49368-113">Data type</span></span></p></th>
<th><p><span data-ttu-id="49368-114">说明</span><span class="sxs-lookup"><span data-stu-id="49368-114">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="49368-115"><em>FileName</em></span><span class="sxs-lookup"><span data-stu-id="49368-115"><em>FileName</em></span></span></p></td>
<td><p><span data-ttu-id="49368-116">必需</span><span class="sxs-lookup"><span data-stu-id="49368-116">Required</span></span></p></td>
<td><p><span data-ttu-id="49368-117"><strong>String</strong></span><span class="sxs-lookup"><span data-stu-id="49368-117"><strong>String</strong></span></span></p></td>
<td><p><span data-ttu-id="49368-118">附件要保存到的文件的完全限定路径。</span><span class="sxs-lookup"><span data-stu-id="49368-118">The fully qualified path of the file to which you want to save the attachment.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="example"></a><span data-ttu-id="49368-119">示例</span><span class="sxs-lookup"><span data-stu-id="49368-119">Example</span></span>

<span data-ttu-id="49368-120">下面的代码段说明了如何使用 **SaveToFile** 方法将指定员工的所有附件保存到磁盘上。</span><span class="sxs-lookup"><span data-stu-id="49368-120">The following code snippet illustrates how to use the **SaveToFile** method to save all of the attachments for a specific employee to disk.</span></span>

```vb
    '  Instantiate the parent recordset.  
       Set rsEmployees = db.OpenRecordset("Employees") 
      
       … Code to move to desired employee 
      
       ' Instantiate the child recordset. 
       Set rsPictures = rsEmployees.Fields("Pictures").Value  
     
       '  Loop through the attachments. 
       While Not rsPictures.EOF 
      
          '  Save current attachment to disk in the "My Documents" folder. 
          rsPictures.Fields("FileData").SaveToFile _ 
                      "C:\Documents and Settings\Username\My Documents" 
          rsPictures.MoveNext 
       Wend 
```

<br/>

<span data-ttu-id="49368-121">下面的示例演示如何将保存到指定的文件夹路径附件字段中存储的文件。</span><span class="sxs-lookup"><span data-stu-id="49368-121">The following example shows how to save the files stored in an attachment field to the specified folder path.</span></span>

<span data-ttu-id="49368-122">**示例代码提供者** [Microsoft Access 2010 Programmer's Reference](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125)。</span><span class="sxs-lookup"><span data-stu-id="49368-122">**Sample code provided by** the [Microsoft Access 2010 Programmer’s Reference](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125).</span></span>

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
