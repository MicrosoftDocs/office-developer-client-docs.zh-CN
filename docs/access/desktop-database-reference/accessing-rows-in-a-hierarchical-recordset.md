---
title: 访问层次记录集中的行
TOCTitle: Accessing rows in a hierarchical Recordset
ms:assetid: db59b152-b780-539c-17ef-462e8adfb26e
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250106(v=office.15)
ms:contentKeyID: 48548104
ms.date: 10/17/2018
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: a80b089fa72ef01eb1b4b2f1dae494e002c6a6fb
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28698237"
---
# <a name="accessing-rows-in-a-hierarchical-recordset"></a><span data-ttu-id="fe889-102">访问层次记录集中的行</span><span class="sxs-lookup"><span data-stu-id="fe889-102">Accessing rows in a hierarchical Recordset</span></span>

<span data-ttu-id="fe889-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="fe889-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="fe889-104">以下示例演示访问分层 [Recordset](recordset-object-ado.md) 中的行所必需的步骤：</span><span class="sxs-lookup"><span data-stu-id="fe889-104">The following example shows the steps necessary to access rows in a hierarchical [Recordset](recordset-object-ado.md):</span></span>

1. <span data-ttu-id="fe889-105">authors（作者）和 titleauthor（标题作者）表中的 **Recordset** 对象通过作者 ID 进行关联。</span><span class="sxs-lookup"><span data-stu-id="fe889-105">**Recordset** objects from the authors and titleauthor tables are related by author ID.</span></span>

2. <span data-ttu-id="fe889-106">外部循环显示每个作者的姓名、省/市/自治区和身份。</span><span class="sxs-lookup"><span data-stu-id="fe889-106">The outer loop displays each author's first and last name, state, and identification.</span></span>

3. <span data-ttu-id="fe889-107">每行所追加的 **Recordset** 都从 **Fields** 集合进行检索并分配给 *rstTitleAuthor*。</span><span class="sxs-lookup"><span data-stu-id="fe889-107">The appended **Recordset** for each row is retrieved from the **Fields** collection and assigned to *rstTitleAuthor*.</span></span>

4. <span data-ttu-id="fe889-108">内循环显示追加的 **Recordset** 中每行的四个字段。</span><span class="sxs-lookup"><span data-stu-id="fe889-108">The inner loop displays four fields from each row in the appended **Recordset**.</span></span>

> [!NOTE] 
> <span data-ttu-id="fe889-109">[StayInSync](stayinsync-property-ado.md)属性是设置为 FALSE 的图中，为了，以便您可以看到的外部循环每次迭代中明确更改一章。</span><span class="sxs-lookup"><span data-stu-id="fe889-109">The [StayInSync](stayinsync-property-ado.md) property is set to FALSE for purposes of illustration, so you can see the chapter change explicitly in each iteration of the outer loop.</span></span> <span data-ttu-id="fe889-110">但是，该示例将更高效，如果在步骤 2 中的第一行之前移动步骤 3 中的工作分配，以便仅执行一次执行工作分配。</span><span class="sxs-lookup"><span data-stu-id="fe889-110">However, the example will be more efficient if the assignment in step 3 is moved before the first line in step 2, so that the assignment is performed only once.</span></span> <span data-ttu-id="fe889-111">**StayInSync**属性设置为 true，则，以便*rstTitleAuthor*将隐式和自动更改为相应章只要*rst*移动到新行。</span><span class="sxs-lookup"><span data-stu-id="fe889-111">Set the **StayInSync** property to TRUE, so that *rstTitleAuthor* will implicitly and automatically change to the corresponding chapter whenever *rst* moves to a new row.</span></span>

<span data-ttu-id="fe889-112">**示例**</span><span class="sxs-lookup"><span data-stu-id="fe889-112">**Example**</span></span>

```vb 
 
Sub datashape() 
 Dim cnn As New ADODB.Connection 
 Dim rst As New ADODB.Recordset 
 Dim rstTitleAuthor As New ADODB.Recordset 
 
 cnn.Provider = "MSDataShape" 
 cnn.Open "Data Provider=MSDASQL;" & _ 
 "Data Source=SRV;" & _ 
 "User Id=MyUserName;Password=MyPassword;Database=Pubs" 
' STEP 1 
 rst.StayInSync = FALSE 
 rst.Open "SHAPE {select * from authors} " & _ 
 "APPEND ({select * from titleauthor} " & _ 
 "RELATE au_id TO au_id) AS chapTitleAuthor", _ 
 cnn 
' STEP 2 
 While Not rst.EOF 
 Debug.Print rst("au_fname"), rst("au_lname"), _ 
 rst("state"), rst("au_id") 
' STEP 3 
 Set rstTitleAuthor = rst("chapTitleAuthor").Value 
' STEP 4 
 While Not rstTitleAuthor.EOF 
 Debug.Print rstTitleAuthor(0), rstTitleAuthor(1), _ 
 rstTitleAuthor(2), rstTitleAuthor(3) 
 rstTitleAuthor.MoveNext 
 Wend 
 rst.MoveNext 
 Wend 
End Sub 
```

