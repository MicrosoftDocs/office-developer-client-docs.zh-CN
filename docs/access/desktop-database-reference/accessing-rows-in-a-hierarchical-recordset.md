---
title: 访问分层记录集中的行
TOCTitle: Accessing rows in a hierarchical Recordset
ms:assetid: db59b152-b780-539c-17ef-462e8adfb26e
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250106(v=office.15)
ms:contentKeyID: 48548104
ms.date: 10/17/2018
mtps_version: v=office.15
ms.openlocfilehash: 3041aa1486f9630a36383dde4ad675c50c799339
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25870028"
---
# <a name="accessing-rows-in-a-hierarchical-recordset"></a>访问分层记录集中的行

**适用于**： Access 2013、 Office 2013

以下示例演示访问分层 [Recordset](recordset-object-ado.md) 中的行所必需的步骤：

1. authors（作者）和 titleauthor（标题作者）表中的 **Recordset** 对象通过作者 ID 进行关联。

2. 外部循环显示每个作者的姓名、省/市/自治区和身份。

3. 每行所追加的 **Recordset** 都从 **Fields** 集合进行检索并分配给 *rstTitleAuthor*。

4. 内循环显示追加的 **Recordset** 中每行的四个字段。

> [!NOTE] 
> [StayInSync](stayinsync-property-ado.md)属性是设置为 FALSE 的图中，为了，以便您可以看到的外部循环每次迭代中明确更改一章。 但是，该示例将更高效，如果在步骤 2 中的第一行之前移动步骤 3 中的工作分配，以便仅执行一次执行工作分配。 **StayInSync**属性设置为 true，则，以便*rstTitleAuthor*将隐式和自动更改为相应章只要*rst*移动到新行。

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

