---
title: Recordset.Clone 方法 (DAO)
TOCTitle: Clone Method
ms:assetid: 50cbc011-7e72-4dee-488d-96e681618e8e
ms:mtpsurl: https://msdn.microsoft.com/library/Ff193824(v=office.15)
ms:contentKeyID: 48544802
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1052909
f1_categories:
- Office.Version=v15
localization_priority: Priority
ms.openlocfilehash: ecc5592893c1caee16f0a00687ce50f68b05e9c7
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32300656"
---
# <a name="recordsetclone-method-dao"></a><span data-ttu-id="91dcf-102">Recordset.Clone 方法 (DAO)</span><span class="sxs-lookup"><span data-stu-id="91dcf-102">Recordset.Clone method (DAO)</span></span>

<span data-ttu-id="91dcf-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="91dcf-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="91dcf-104">创建一个引用原始 **Recordset** 对象的重复 **[Recordset](recordset-object-dao.md)** 对象。</span><span class="sxs-lookup"><span data-stu-id="91dcf-104">Creates a duplicate [**Recordset**](recordset-object-dao.md) object that refers to the original **Recordset** object.</span></span>

## <a name="syntax"></a><span data-ttu-id="91dcf-105">语法</span><span class="sxs-lookup"><span data-stu-id="91dcf-105">Syntax</span></span>

<span data-ttu-id="91dcf-106">*表达式* .Clone</span><span class="sxs-lookup"><span data-stu-id="91dcf-106">expression  . Clone</span></span>

<span data-ttu-id="91dcf-107">*表达式* 一个表示 **Recordset** 对象的变量。</span><span class="sxs-lookup"><span data-stu-id="91dcf-107">*expression*  A variable that represents a **Recordset** object.</span></span>

## <a name="return-value"></a><span data-ttu-id="91dcf-108">返回值</span><span class="sxs-lookup"><span data-stu-id="91dcf-108">Return value</span></span>

<span data-ttu-id="91dcf-109">Recordset</span><span class="sxs-lookup"><span data-stu-id="91dcf-109">Recordset</span></span>

## <a name="remarks"></a><span data-ttu-id="91dcf-110">说明</span><span class="sxs-lookup"><span data-stu-id="91dcf-110">Remarks</span></span>

<span data-ttu-id="91dcf-p101">使用 **Clone** 方法可以创建多个重复的 **Recordset** 对象。每个 **Recordset** 都可以具有其自身的当前记录。使用 **Clone** 自身并不会更改对象中的数据或对象基础结构中的数据。使用 **Clone** 方法时，可以在两个或更多个 **Recordset** 对象之间共享书签，因为这些对象的书签是可以交换的。</span><span class="sxs-lookup"><span data-stu-id="91dcf-p101">Use the **Clone** method to create multiple, duplicate **Recordset** objects. Each **Recordset** can have its own current record. Using **Clone** by itself doesn't change the data in the objects or in their underlying structures. When you use the **Clone** method, you can share bookmarks between two or more **Recordset** objects because their bookmarks are interchangeable.</span></span>

<span data-ttu-id="91dcf-p102">如果要对需要多个当前记录的 **Recordset** 执行操作，可使用 **Clone** 方法。这样比打开第二个 **Recordset** 更加快速和高效。使用 **Clone** 方法创建了 **Recordset** 后，该记录集最初会缺少一个当前记录。若要在使用 **Recordset** 克隆之前使某记录成为当前记录，必须设置 **[Bookmark](recordset-bookmark-property-dao.md)** 属性，或使用 **[Move](recordset-movefirst-method-dao.md)** 方法之一、 **[Find](recordset-findfirst-method-dao.md)** 方法之一或 **[Seek](recordset-seek-method-dao.md)** 方法。</span><span class="sxs-lookup"><span data-stu-id="91dcf-p102">You can use the **Clone** method when you want to perform an operation on a **Recordset** that requires multiple current records. This is faster and more efficient than opening a second **Recordset**. When you create a **Recordset** with the **Clone** method, it initially lacks a current record. To make a record current before you use the **Recordset** clone, you must set the **[Bookmark](recordset-bookmark-property-dao.md)** property or use one of the **[Move](recordset-movefirst-method-dao.md)** methods, one of the **[Find](recordset-findfirst-method-dao.md)** methods, or the **[Seek](recordset-seek-method-dao.md)** method.</span></span>

<span data-ttu-id="91dcf-p103">无论是对原始对象还是对复制对象使用 **[Close](connection-close-method-dao.md)** 方法，都不会影响其他对象。例如，对原始 **Recordset** 使用 **Close** 不会关闭克隆。</span><span class="sxs-lookup"><span data-stu-id="91dcf-p103">Using the **[Close](connection-close-method-dao.md)** method on either the original or duplicate object doesn't affect the other object. For example, using **Close** on the original **Recordset** doesn't close the clone.</span></span>

> [!NOTE]
> - <span data-ttu-id="91dcf-121">在待定事务中关闭克隆 Recordset 将导致隐式 **Rollback** 操作。</span><span class="sxs-lookup"><span data-stu-id="91dcf-121">Closing a clone recordset within a pending transaction will cause an implicit **Rollback** operation.</span></span>
> - <span data-ttu-id="91dcf-p104">在 Microsoft Access 工作区中克隆表类型的 **Recordset** 对象时，不会将 **[Index](recordset2-index-property-dao.md)** 属性设置克隆到 Recordset 的新副本上。必须手动复制 **Index** 属性设置。</span><span class="sxs-lookup"><span data-stu-id="91dcf-p104">When you clone a table-type **Recordset** object in a Microsoft Access workspace, the **[Index](recordset2-index-property-dao.md)** property setting is not cloned on the new copy of the recordset. You must copy the **Index** property setting manually.</span></span>

## <a name="example"></a><span data-ttu-id="91dcf-124">示例</span><span class="sxs-lookup"><span data-stu-id="91dcf-124">Example</span></span>

<span data-ttu-id="91dcf-125">以下示例使用 **Clone** 方法创建 **Recordset** 的副本，然后让用户单独定位每个副本的记录指针。</span><span class="sxs-lookup"><span data-stu-id="91dcf-125">This example uses the **Clone** method to create copies of a **Recordset** and then lets the user position the record pointer of each copy independently.</span></span>

```vb
    Sub CloneX() 
     
       Dim dbsNorthwind As Database 
       Dim arstProducts(1 To 3) As Recordset 
       Dim intLoop As Integer 
       Dim strMessage As String 
       Dim strFind As String 
     
       Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
     
       ' If the following SQL statement will be used often,  
       ' creating a permanent QueryDef will result in better 
       ' performance. 
       Set arstProducts(1) = dbsNorthwind.OpenRecordset( _ 
          "SELECT ProductName FROM Products " & _ 
          "ORDER BY ProductName", dbOpenSnapshot) 
     
       ' Create two clones of the original Recordset. 
       Set arstProducts(2) = arstProducts(1).Clone 
       Set arstProducts(3) = arstProducts(1).Clone 
     
       Do While True 
     
          ' Loop through the array so that on each pass, the  
          ' user is searching a different copy of the same  
          ' Recordset. 
          For intLoop = 1 To 3 
     
             ' Ask for search string while showing where the 
             ' current record pointer is for each Recordset. 
             strMessage = _ 
                "Recordsets from Products table:" & vbCr & _ 
                "  1 - Original - Record pointer at " & _ 
                arstProducts(1)!ProductName & vbCr & _ 
                "  2 - Clone - Record pointer at " & _ 
                arstProducts(2)!ProductName & vbCr & _ 
                "  3 - Clone - Record pointer at " & _ 
                arstProducts(3)!ProductName & vbCr & _ 
                "Enter search string for #" & intLoop & ":" 
             strFind = Trim(InputBox(strMessage)) 
             If strFind = "" Then Exit Do 
     
             ' Find the search string; if there's no match, jump 
             ' to the last record. 
             With arstProducts(intLoop) 
                .FindFirst "ProductName >= '" & strFind & "'" 
                If .NoMatch Then .MoveLast 
             End With 
     
          Next intLoop 
     
       Loop 
     
       arstProducts(1).Close 
       arstProducts(2).Close 
       arstProducts(3).Close 
       dbsNorthwind.Close 
     
    End Sub
```
