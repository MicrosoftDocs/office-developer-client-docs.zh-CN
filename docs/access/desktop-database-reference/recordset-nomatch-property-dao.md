---
title: Recordset.NoMatch 属性 (DAO)
TOCTitle: NoMatch Property
ms:assetid: 47d03575-f570-89b5-a20f-a3bd8b8b5c6d
ms:mtpsurl: https://msdn.microsoft.com/library/Ff193226(v=office.15)
ms:contentKeyID: 48544606
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1052889
f1_categories:
- Office.Version=v15
localization_priority: Priority
ms.openlocfilehash: e54f8c51787e51785bdaacaecd28a8d24e2cb5b1
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32300425"
---
# <a name="recordsetnomatch-property-dao"></a><span data-ttu-id="18cdb-102">Recordset.NoMatch 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="18cdb-102">Recordset.NoMatch property (DAO)</span></span>

<span data-ttu-id="18cdb-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="18cdb-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="18cdb-104">指示特定记录是通过使用 **[Seek](recordset-seek-method-dao.md)** 方法还是 **[Find](recordset-findfirst-method-dao.md)** 方法找到的（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="18cdb-104">Indicates whether a particular record was found by using the **[Seek](recordset-seek-method-dao.md)** method or one of the **[Find](recordset-findfirst-method-dao.md)** methods (Microsoft Access workspaces only).</span></span>

## <a name="syntax"></a><span data-ttu-id="18cdb-105">语法</span><span class="sxs-lookup"><span data-stu-id="18cdb-105">Syntax</span></span>

<span data-ttu-id="18cdb-106">*表达式* .NoMatch</span><span class="sxs-lookup"><span data-stu-id="18cdb-106">expression  . NoMatch</span></span>

<span data-ttu-id="18cdb-107">*表达式* 一个表示 **Recordset** 对象的变量。</span><span class="sxs-lookup"><span data-stu-id="18cdb-107">*expression*  A variable that represents a **Recordset** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="18cdb-108">说明</span><span class="sxs-lookup"><span data-stu-id="18cdb-108">Remarks</span></span>

<span data-ttu-id="18cdb-109">打开或创建 **[Recordset](recordset-object-dao.md)** 对象时，其 **NoMatch** 属性设置为 **False**。</span><span class="sxs-lookup"><span data-stu-id="18cdb-109">When you open or create a **[Recordset](recordset-object-dao.md)** object, its **NoMatch** property is set to **False**.</span></span>

<span data-ttu-id="18cdb-p101">若要定位记录，请对表类型的 **Recordset** 对象使用 **Seek** 方法，或者对动态集类型或快照类型的 **Recordset** 对象使用 **Find** 方法之一。检查 **NoMatch** 属性设置以查看是否找到了该记录。</span><span class="sxs-lookup"><span data-stu-id="18cdb-p101">To locate a record, use the **Seek** method on a table-type **Recordset** object or one of the **Find** methods on a dynaset- or snapshot-type **Recordset** object. Check the **NoMatch** property setting to see whether the record was found.</span></span>

<span data-ttu-id="18cdb-p102">如果 **Seek** 或 **Find** 方法不成功，且 **NoMatch** 属性为 **True**，则当前记录将不再有效。如果需要返回到当前记录，请在使用 **Seek** 方法或 **Find** 方法之前获取当前记录的书签。</span><span class="sxs-lookup"><span data-stu-id="18cdb-p102">If the **Seek** or **Find** method is unsuccessful and the **NoMatch** property is **True**, the current record will no longer be valid. Be sure to obtain the current record's bookmark before using the **Seek** method or a **Find** method if you'll need to return to that record.</span></span>


> [!NOTE]
> <span data-ttu-id="18cdb-114">对 **Recordset** 对象使用任何 **[Move](recordset-movefirst-method-dao.md)** 方法将不会影响其 **NoMatch** 属性设置。</span><span class="sxs-lookup"><span data-stu-id="18cdb-114">Using any of the [**Move**](recordset-movefirst-method-dao.md) methods on a **Recordset** object won't affect its **NoMatch** property setting.</span></span>


## <a name="example"></a><span data-ttu-id="18cdb-115">示例</span><span class="sxs-lookup"><span data-stu-id="18cdb-115">Example</span></span>

<span data-ttu-id="18cdb-p103">以下示例使用 **NoMatch** 属性确定 **Seek** 和 **FindFirst** 是否成功，如果未成功，则提供相应的反馈。若要使该过程运行，需要使用 SeekMatch 和 FindMatch 过程。</span><span class="sxs-lookup"><span data-stu-id="18cdb-p103">This example uses the **NoMatch** property to determine whether a **Seek** and a **FindFirst** were successful, and if not, to give appropriate feedback. The SeekMatch and FindMatch procedures are required for this procedure to run.</span></span>

```vb
    Sub NoMatchX() 
     
       Dim dbsNorthwind As Database 
       Dim rstProducts As Recordset 
       Dim rstCustomers As Recordset 
       Dim strMessage As String 
       Dim strSeek As String 
       Dim strCountry As String 
       Dim varBookmark As Variant 
     
       Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
       ' Default is dbOpenTable; required if Index property will  
       ' be used. 
       Set rstProducts = dbsNorthwind.OpenRecordset("Products") 
     
       With rstProducts 
          .Index = "PrimaryKey" 
     
          Do While True 
             ' Show current record information; ask user for  
             ' input. 
             strMessage = "NoMatch with Seek method" & vbCr & _ 
                "Product ID: " & !ProductID & vbCr & _ 
                "Product Name: " & !ProductName & vbCr & _ 
                "NoMatch = " & .NoMatch & vbCr & vbCr & _ 
                "Enter a product ID." 
             strSeek = InputBox(strMessage) 
             If strSeek = "" Then Exit Do 
     
             ' Call procedure that seeks for a record based on  
             ' the ID number supplied by the user. 
             SeekMatch rstProducts, Val(strSeek) 
          Loop 
     
          .Close 
       End With 
     
       Set rstCustomers = dbsNorthwind.OpenRecordset( _ 
          "SELECT CompanyName, Country FROM Customers " & _ 
          "ORDER BY CompanyName", dbOpenSnapshot) 
     
       With rstCustomers 
     
          Do While True 
             ' Show current record information; ask user for  
             ' input. 
             strMessage = "NoMatch with FindFirst method" & _ 
                vbCr & "Customer Name: " & !CompanyName & _ 
                vbCr & "Country: " & !Country & vbCr & _ 
                "NoMatch = " & .NoMatch & vbCr & vbCr & _ 
                "Enter country on which to search." 
             strCountry = Trim(InputBox(strMessage)) 
             If strCountry = "" Then Exit Do 
     
             ' Call procedure that finds a record based on  
             ' the country name supplied by the user. 
             FindMatch rstCustomers, _ 
                "Country = '" & strCountry & "'" 
          Loop 
     
          .Close 
       End With 
     
       dbsNorthwind.Close 
     
    End Sub 
     
    Sub SeekMatch(rstTemp As Recordset, _ 
       intSeek As Integer) 
     
       Dim varBookmark As Variant 
       Dim strMessage As String 
     
       With rstTemp 
          ' Store current record location. 
          varBookmark = .Bookmark 
          .Seek "=", intSeek 
     
          ' If Seek method fails, notify user and return to the  
          ' last current record. 
          If .NoMatch Then 
             strMessage = _ 
                "Not found! Returning to current record." & _ 
                vbCr & vbCr & "NoMatch = " & .NoMatch 
             MsgBox strMessage 
             .Bookmark = varBookmark 
          End If 
     
       End With 
     
    End Sub 
     
    Sub FindMatch(rstTemp As Recordset, _ 
       strFind As String) 
     
       Dim varBookmark As Variant 
       Dim strMessage As String 
     
       With rstTemp 
          ' Store current record location. 
          varBookmark = .Bookmark 
          .FindFirst strFind 
     
          ' If Find method fails, notify user and return to the  
          ' last current record. 
          If .NoMatch Then 
             strMessage = _ 
                "Not found! Returning to current record." & _ 
                vbCr & vbCr & "NoMatch = " & .NoMatch 
             MsgBox strMessage 
             .Bookmark = varBookmark 
          End If 
     
       End With 
     
    End Sub 
```

<br/>

<span data-ttu-id="18cdb-118">以下示例说明如何使用 Seek 方法在链接的表中查找记录。</span><span class="sxs-lookup"><span data-stu-id="18cdb-118">The following example shows how to use the Seek method to find a record in a linked table.</span></span>

<span data-ttu-id="18cdb-119">**示例代码提供方：**[Microsoft Access 2010 程序员参考](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125)。</span><span class="sxs-lookup"><span data-stu-id="18cdb-119">**Sample code provided by** the [Microsoft Access 2010 Programmer’s Reference](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125).</span></span>

```vb
    Sub TestSeek()
        ' Get the path to the external database that contains
        ' the tblCustomers table we're going to search.
        Dim strMyExternalDatabase
        Dim dbs    As DAO.Database
        Dim dbsExt As DAO.Database
        Dim rst    As DAO.Recordset
        Dim tdf    As DAO.TableDef
        
        Set dbs = CurrentDb()
        Set tdf = dbs.TableDefs("tblCustomers")
        strMyExternalDatabase = Mid(tdf.Connect, 11)
        
        'Open the database that contains the table that is linked
        Set dbsExt = OpenDatabase(strMyExternalDatabase)
        
        'Open a table-type recordset against the external table
        Set rst = dbsExt.OpenRecordset("tblCustomers", dbOpenTable)
        
        'Specify which index to search on
        rst.Index = "PrimaryKey"
        
        'Specify the criteria
        rst.Seek "=", 123
        
        'Check the result
        If rst.NoMatch Then
            MsgBox "Record not found."
        Else
            MsgBox "Customer name: " & rst!CustName
        End If
        
        rst.Close
        dbs.Close
        dbsExt.Close
        Set rst = Nothing
        Set tdf = Nothing
        Set dbs = Nothing
        
        
    End Sub
```
