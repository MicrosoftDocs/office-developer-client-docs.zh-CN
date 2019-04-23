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
# <a name="accessing-rows-in-a-hierarchical-recordset"></a>访问层次记录集中的行

**适用于**：Access 2013、Office 2013

以下示例演示访问分层 [Recordset](recordset-object-ado.md) 中的行所必需的步骤：

1. authors（作者）和 titleauthor（标题作者）表中的 **Recordset** 对象通过作者 ID 进行关联。

2. 外部循环显示每个作者的姓名、省/市/自治区和身份。

3. 每行所追加的 **Recordset** 都从 **Fields** 集合进行检索并分配给 *rstTitleAuthor*。

4. 内循环显示追加的 **Recordset** 中每行的四个字段。

> [!NOTE] 
> 将[StayInSync](stayinsync-property-ado.md)属性设置为 FALSE 以进行说明, 以便您可以在外部循环的每个迭代中明确地看到章节更改。 但是, 如果在步骤3中的工作分配移到了步骤2中的第一行之前, 则该示例将更高效, 以便仅执行一次该工作分配。 将**StayInSync**属性设置为 TRUE, 以便在*rst*移动到新行时*rstTitleAuthor*将隐式和自动更改为相应的章节。

**示例**

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

