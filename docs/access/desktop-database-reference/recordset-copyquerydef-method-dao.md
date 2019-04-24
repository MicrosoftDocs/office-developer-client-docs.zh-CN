---
title: CopyQueryDef 方法 (DAO)
TOCTitle: CopyQueryDef Method
ms:assetid: fee8c2fe-500e-dfb3-21ce-211e54ff334b
ms:mtpsurl: https://msdn.microsoft.com/library/Ff837296(v=office.15)
ms:contentKeyID: 48548950
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: aa6c5aab5f357eef8c62c63c6fca873e64031411
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32300558"
---
# <a name="recordsetcopyquerydef-method-dao"></a><span data-ttu-id="f282c-102">CopyQueryDef 方法 (DAO)</span><span class="sxs-lookup"><span data-stu-id="f282c-102">Recordset.CopyQueryDef method (DAO)</span></span>


<span data-ttu-id="f282c-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="f282c-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="f282c-104">返回一个**[querydef](querydef-object-dao.md)** 对象, 该对象是用于创建 recordset 占位符表示的**[recordset](recordset-object-dao.md)** 对象的**querydef**副本 (仅适用于 Microsoft Access 工作区)。</span><span class="sxs-lookup"><span data-stu-id="f282c-104">Returns a **[QueryDef](querydef-object-dao.md)** object that is a copy of the **QueryDef** used to create the **[Recordset](recordset-object-dao.md)** object represented by the recordset placeholder (Microsoft Access workspaces only).</span></span> <span data-ttu-id="f282c-105">.</span><span class="sxs-lookup"><span data-stu-id="f282c-105"></span></span>

## <a name="syntax"></a><span data-ttu-id="f282c-106">语法</span><span class="sxs-lookup"><span data-stu-id="f282c-106">Syntax</span></span>

<span data-ttu-id="f282c-107">*表达式*。CopyQueryDef</span><span class="sxs-lookup"><span data-stu-id="f282c-107">*expression* .CopyQueryDef</span></span>

<span data-ttu-id="f282c-108">*表达式*一个代表**Recordset**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="f282c-108">*expression* A variable that represents a **Recordset** object.</span></span>

## <a name="return-value"></a><span data-ttu-id="f282c-109">返回值</span><span class="sxs-lookup"><span data-stu-id="f282c-109">Return value</span></span>

<span data-ttu-id="f282c-110">QueryDef</span><span class="sxs-lookup"><span data-stu-id="f282c-110">QueryDef</span></span>

## <a name="remarks"></a><span data-ttu-id="f282c-111">注解</span><span class="sxs-lookup"><span data-stu-id="f282c-111">Remarks</span></span>

<span data-ttu-id="f282c-112">可以使用 **CopyQueryDef** 方法创建一个新的 **QueryDef**，该对象是用于创建 **Recordset** 的 **QueryDef** 的副本。</span><span class="sxs-lookup"><span data-stu-id="f282c-112">You can use the **CopyQueryDef** method to create a new **QueryDef** that is a duplicate of the **QueryDef** used to create the **Recordset**.</span></span>

<span data-ttu-id="f282c-p102">如果没有使用 **QueryDef** 创建此 **Recordset**，将会发生错误。使用 **CopyQueryDef** 方法之前，必须首先使用 **OpenRecordset** 方法打开 **Recordset**。</span><span class="sxs-lookup"><span data-stu-id="f282c-p102">If a **QueryDef** wasn't used to create this **Recordset**, an error occurs. You must first open a **Recordset** with the **OpenRecordset** method before using the **CopyQueryDef** method.</span></span>

<span data-ttu-id="f282c-115">如果从 **QueryDef** 创建了一个 **Recordset** 对象，然后将 **Recordset** 传递给了一个函数，则使用此方法十分有用，函数必须重新创建查询的 SQL 等效项，例如，以某种方式对它进行修改。</span><span class="sxs-lookup"><span data-stu-id="f282c-115">This method is useful when you create a **Recordset** object from a **QueryDef**, and pass the **Recordset** to a function, and the function must re-create the SQL equivalent of the query, for example, to modify it in some way.</span></span>

## <a name="example"></a><span data-ttu-id="f282c-116">示例</span><span class="sxs-lookup"><span data-stu-id="f282c-116">Example</span></span>

<span data-ttu-id="f282c-p103">以下示例使用 **CopyQueryDef** 方法从现有的 **Recordset** 创建 **QueryDef** 的副本，然后通过向 SQL 属性添加子句，对副本进行修改。创建了永久的 **QueryDef** 后，可以向 SQL 属性添加空格、分号或换行符。只有在删除这些额外的字符之后，才可以将任何新子句附加到 SQL 语句。</span><span class="sxs-lookup"><span data-stu-id="f282c-p103">This example uses the **CopyQueryDef** method to create a copy of a **QueryDef** from an existing **Recordset** and modifies the copy by adding a clause to the SQL property. When you create a permanent **QueryDef**, spaces, semicolons, or linefeeds may be added to the SQL property; these extra characters must be stripped before any new clauses can be attached to the SQL statement.</span></span>

```vb
    Function CopyQueryNew(rstTemp As Recordset, _ 
     strAdd As String) As QueryDef 
     
     Dim strSQL As String 
     Dim strRightSQL As String 
     
     Set CopyQueryNew = rstTemp.CopyQueryDef 
     With CopyQueryNew 
     ' Strip extra characters. 
     strSQL = .SQL 
     strRightSQL = Right(strSQL, 1) 
     Do While strRightSQL = " " Or strRightSQL = ";" Or _ 
     strRightSQL = Chr(10) Or strRightSQL = vbCr 
     strSQL = Left(strSQL, Len(strSQL) - 1) 
     strRightSQL = Right(strSQL, 1) 
     Loop 
     .SQL = strSQL & strAdd 
     End With 
     
    End Function 
```

<br/>

<span data-ttu-id="f282c-119">以下示例演示 CopyQueryNew() 可能的用法。</span><span class="sxs-lookup"><span data-stu-id="f282c-119">This example shows a possible use of CopyQueryNew().</span></span>

```vb 
Sub CopyQueryDefX() 
 
 Dim dbsNorthwind As Database 
 Dim qdfEmployees As QueryDef 
 Dim rstEmployees As Recordset 
 Dim intCommand As Integer 
 Dim strOrderBy As String 
 Dim qdfCopy As QueryDef 
 Dim rstCopy As Recordset 
 
 Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
 Set qdfEmployees = dbsNorthwind.CreateQueryDef( _ 
 "NewQueryDef", "SELECT FirstName, LastName, " & _ 
 "BirthDate FROM Employees") 
 Set rstEmployees = qdfEmployees.OpenRecordset( _ 
 dbOpenForwardOnly) 
 
 Do While True 
 intCommand = Val(InputBox( _ 
 "Choose field on which to order a new " & _ 
 "Recordset:" & vbCr & "1 - FirstName" & vbCr & _ 
 "2 - LastName" & vbCr & "3 - BirthDate" & vbCr & _ 
 "[Cancel - exit]")) 
 Select Case intCommand 
 Case 1 
 strOrderBy = " ORDER BY FirstName" 
 Case 2 
 strOrderBy = " ORDER BY LastName" 
 Case 3 
 strOrderBy = " ORDER BY BirthDate" 
 Case Else 
 Exit Do 
 End Select 
 Set qdfCopy = CopyQueryNew(rstEmployees, strOrderBy) 
 Set rstCopy = qdfCopy.OpenRecordset(dbOpenSnapshot, _ 
 dbForwardOnly) 
 With rstCopy 
 Do While Not .EOF 
 Debug.Print !LastName & ", " & !FirstName & _ 
 " - " & !BirthDate 
 .MoveNext 
 Loop 
 .Close 
 End With 
 Exit Do 
 Loop 
 
 rstEmployees.Close 
 ' Delete new QueryDef because this is a demonstration. 
 dbsNorthwind.QueryDefs.Delete qdfEmployees.Name 
 dbsNorthwind.Close 
 
End Sub 
 
```

