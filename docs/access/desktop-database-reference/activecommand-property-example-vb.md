---
title: ActiveCommand 属性示例 (VB)
TOCTitle: ActiveCommand property example (VB)
ms:assetid: 831032cb-d557-aa98-5637-07bad65f924a
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249569(v=office.15)
ms:contentKeyID: 48545999
ms.date: 10/17/2018
mtps_version: v=office.15
ms.openlocfilehash: 46338c801bbdf1e4faaef5a3f6ff1c10d28ab544
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25870000"
---
# <a name="activecommand-property-example-vb"></a><span data-ttu-id="a7fbe-102">ActiveCommand 属性示例 (VB)</span><span class="sxs-lookup"><span data-stu-id="a7fbe-102">ActiveCommand property example (VB)</span></span>


<span data-ttu-id="a7fbe-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="a7fbe-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="a7fbe-104">此示例演示 [ActiveCommand](activecommand-property-ado.md) 属性。</span><span class="sxs-lookup"><span data-stu-id="a7fbe-104">This example demonstrates the [ActiveCommand](activecommand-property-ado.md) property.</span></span>

<span data-ttu-id="a7fbe-105">将向子例程提供一个 [Recordset](recordset-object-ado.md) 对象，该对象的 **ActiveCommand** 属性用于显示创建 **Recordset** 的命令文本和参数。</span><span class="sxs-lookup"><span data-stu-id="a7fbe-105">A subroutine is given a [Recordset](recordset-object-ado.md) object whose **ActiveCommand** property is used to display the command text and parameter that created the **Recordset**.</span></span>

```vb 
 
'BeginActiveCommandVB 
 
 'To integrate this code 
 'replace the data source and initial catalog values 
 'in the connection string 
 
Public Sub Main() 
 On Error GoTo ErrorHandler 
 
 'recordset and connection variables 
 Dim cmd As ADODB.Command 
 Dim rst As ADODB.Recordset 
 Dim Cnxn As ADODB.Connection 
 Dim strCnxn As String 
 'record variables 
 Dim strPrompt As String 
 Dim strName As String 
 
 Set Cnxn = New ADODB.Connection 
 Set cmd = New ADODB.Command 
 
 strPrompt = "Enter an author's name (e.g., Ringer): " 
 strName = Trim(InputBox(strPrompt, "ActiveCommandX Example")) 
 strCnxn = "Provider='sqloledb';Data Source='MySqlServer';" & _ 
 "Initial Catalog='Pubs';Integrated Security='SSPI';" 
 
 'create SQL command string 
 cmd.CommandText = "SELECT * FROM Authors WHERE au_lname = ?" 
 cmd.Parameters.Append cmd.CreateParameter("LastName", adChar, adParamInput, 20, strName) 
 
 Cnxn.Open strCnxn 
 cmd.ActiveConnection = Cnxn 
 
 'create the recordset by executing command string 
 Set rst = cmd.Execute(, , adCmdText) 
 'see the results 
 Call ActiveCommandXprint(rst) 
 
 ' clean up 
 Cnxn.Close 
 Set rst = Nothing 
 Set Cnxn = Nothing 
 Exit Sub 
 
ErrorHandler: 
 ' clean up 
 If Not rst Is Nothing Then 
 If rst.State = adStateOpen Then rst.Close 
 End If 
 Set rst = Nothing 
 
 If Not Cnxn Is Nothing Then 
 If Cnxn.State = adStateOpen Then Cnxn.Close 
 End If 
 Set Cnxn = Nothing 
 
 If Err <> 0 Then 
 MsgBox Err.Source & "-->" & Err.Description, , "Error" 
 End If 
End Sub 
'EndActiveCommandVB 
```

<span data-ttu-id="a7fbe-p101">仅为 **ActiveCommandXprint** 例程提供一个 **Recordset** 对象，不过它必须输出创建 **Recordset** 的命令文本和参数。因为 **Recordset** 对象的 **ActiveCommand** 属性将生成关联的 [Command](command-object-ado.md) 对象，因此可以完成此操作。</span><span class="sxs-lookup"><span data-stu-id="a7fbe-p101">The **ActiveCommandXprint** routine is given only a **Recordset** object, yet it must print the command text and parameter that created the **Recordset**. This can be done because the **Recordset** object's **ActiveCommand** property yields the associated [Command](command-object-ado.md) object.</span></span>

<span data-ttu-id="a7fbe-p102">**Command** 对象的 [CommandText](commandtext-property-ado.md) 属性将生成创建 **Recordset** 的参数化命令。**Command** 对象的 [Parameters](parameters-collection-ado.md) 集合将生成替代命令的参数占位符（“**?**”）的值。</span><span class="sxs-lookup"><span data-stu-id="a7fbe-p102">The **Command** object's [CommandText](commandtext-property-ado.md) property yields the parameterized command that created the **Recordset**. The **Command** object's [Parameters](parameters-collection-ado.md) collection yields the value that was substituted for the command's parameter placeholder ("**?**").</span></span>

<span data-ttu-id="a7fbe-110">最后，将输出一条错误消息或作者的姓名和 ID。</span><span class="sxs-lookup"><span data-stu-id="a7fbe-110">Finally, an error message or the author's name and ID are printed.</span></span>

```vb 
 
'BeginActiveCommandPrintVB 
Public Sub ActiveCommandXprint(rstp As ADODB.Recordset) 
 
 Dim strName As String 
 
 strName = rstp.ActiveCommand.Parameters.Item("LastName").Value 
 
 Debug.Print "Command text = '"; rstp.ActiveCommand.CommandText; "'" 
 Debug.Print "Parameter = '"; strName; "'" 
 
 If rstp.BOF = True Then 
 Debug.Print "Name = '"; strName; "', not found." 
 Else 
 Debug.Print "Name = '"; rstp!au_fname; " "; rstp!au_lname; _ 
 "', author ID = '"; rstp!au_id; "'" 
 End If 
 
 rstp.Close 
 Set rstp = Nothing 
End Sub 
'EndActiveCommandPrintVB 
```

