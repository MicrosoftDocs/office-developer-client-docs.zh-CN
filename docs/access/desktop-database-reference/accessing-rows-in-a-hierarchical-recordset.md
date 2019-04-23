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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32281954"
---
# <a name="accessing-rows-in-a-hierarchical-recordset"></a><span data-ttu-id="c97f0-102">访问层次记录集中的行</span><span class="sxs-lookup"><span data-stu-id="c97f0-102">Accessing rows in a hierarchical Recordset</span></span>

<span data-ttu-id="c97f0-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="c97f0-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="c97f0-104">以下示例演示访问分层 [Recordset](recordset-object-ado.md) 中的行所必需的步骤：</span><span class="sxs-lookup"><span data-stu-id="c97f0-104">The following example shows the steps necessary to access rows in a hierarchical [Recordset](recordset-object-ado.md):</span></span>

1. <span data-ttu-id="c97f0-105">authors（作者）和 titleauthor（标题作者）表中的 **Recordset** 对象通过作者 ID 进行关联。</span><span class="sxs-lookup"><span data-stu-id="c97f0-105">**Recordset** objects from the authors and titleauthor tables are related by author ID.</span></span>

2. <span data-ttu-id="c97f0-106">外部循环显示每个作者的姓名、省/市/自治区和身份。</span><span class="sxs-lookup"><span data-stu-id="c97f0-106">The outer loop displays each author's first and last name, state, and identification.</span></span>

3. <span data-ttu-id="c97f0-107">每行所追加的 **Recordset** 都从 **Fields** 集合进行检索并分配给 *rstTitleAuthor*。</span><span class="sxs-lookup"><span data-stu-id="c97f0-107">The appended **Recordset** for each row is retrieved from the **Fields** collection and assigned to *rstTitleAuthor*.</span></span>

4. <span data-ttu-id="c97f0-108">内循环显示追加的 **Recordset** 中每行的四个字段。</span><span class="sxs-lookup"><span data-stu-id="c97f0-108">The inner loop displays four fields from each row in the appended **Recordset**.</span></span>

> [!NOTE] 
> <span data-ttu-id="c97f0-109">将[StayInSync](stayinsync-property-ado.md)属性设置为 FALSE 以进行说明, 以便您可以在外部循环的每个迭代中明确地看到章节更改。</span><span class="sxs-lookup"><span data-stu-id="c97f0-109">The [StayInSync](stayinsync-property-ado.md) property is set to FALSE for purposes of illustration, so you can see the chapter change explicitly in each iteration of the outer loop.</span></span> <span data-ttu-id="c97f0-110">但是, 如果在步骤3中的工作分配移到了步骤2中的第一行之前, 则该示例将更高效, 以便仅执行一次该工作分配。</span><span class="sxs-lookup"><span data-stu-id="c97f0-110">However, the example will be more efficient if the assignment in step 3 is moved before the first line in step 2, so that the assignment is performed only once.</span></span> <span data-ttu-id="c97f0-111">将**StayInSync**属性设置为 TRUE, 以便在*rst*移动到新行时*rstTitleAuthor*将隐式和自动更改为相应的章节。</span><span class="sxs-lookup"><span data-stu-id="c97f0-111">Set the **StayInSync** property to TRUE, so that *rstTitleAuthor* will implicitly and automatically change to the corresponding chapter whenever *rst* moves to a new row.</span></span>

<span data-ttu-id="c97f0-112">**示例**</span><span class="sxs-lookup"><span data-stu-id="c97f0-112">**Example**</span></span>

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

