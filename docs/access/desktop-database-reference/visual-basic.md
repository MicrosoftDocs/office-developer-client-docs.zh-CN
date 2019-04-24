---
title: Visual Basic (Access 桌面数据库参考)
TOCTitle: Visual Basic
ms:assetid: 9d153b6c-c860-7350-cb3c-b9bd08f75ba8
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249714(v=office.15)
ms:contentKeyID: 48546616
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 3045cf3861409d2909f31536670a27c282eb2cdc
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32312136"
---
# <a name="visual-basic"></a><span data-ttu-id="e50cf-102">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e50cf-102">Visual Basic</span></span>


<span data-ttu-id="e50cf-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="e50cf-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="e50cf-p101">为了在 Microsoft Visual Basic 中处理 ADO 事件，必须使用 **WithEvents** 关键字声明模块级变量。该变量只能声明为类模块的一部分，并且必须在模块级别声明。但是，它所受限制并非看起来那样大，因为 Visual Basic **Form** 对象也是类。处理 ADO 事件的最简单方式是使用 **WithEvents** 声明变量。以下示例将处理 **Connection** 对象的 **ConnectComplete** 事件：</span><span class="sxs-lookup"><span data-stu-id="e50cf-p101">In order to handle ADO events in Microsoft Visual Basic, you must declare a module-level variable using the **WithEvents** keyword. The variable can be declared only as part of a class module and must be declared at the module level. This is not as restrictive as it seems, however, because Visual Basic **Form** objects are also classes. The simplest way to handle ADO events is to declare a variable using **WithEvents**. The following example handles the **ConnectComplete** event for a **Connection** object:</span></span>

```vb 
 
' BeginEventExampleVB02 
Dim WithEvents connEvent As Connection 
Attribute connEvent.VB_VarHelpID = -1 
Dim strMsg As String 
 
Private Sub Form_Load() 
 On Error GoTo ErrHandler: 
 
 Dim strConn As String 
 
 ' Create a new object with event 
 ' handling enabled. 
 strConn = "Provider='sqloledb';" & _ 
 "Data Source='MySqlServer';" & _ 
 "Initial Catalog='Northwind';" & _ 
 "Integrated Security='SSPI';" 
 Set connEvent = New ADODB.Connection 
 connEvent.Open strConn 
 
 Exit Sub 
 
ErrHandler: 
 MsgBox strMsg 
End Sub 
 
Private Sub connEvent_ConnectComplete(ByVal pError As ADODB.Error, _ 
 adStatus As ADODB.EventStatusEnum, _ 
 ByVal pConnection As ADODB.Connection) 
 
 If adStatus = adStatusErrorsOccurred Then 
 If Not pError Is Nothing Then 
 Select Case pError.Number 
 Case adErrOperationCancelled 
 ' The operation was cancelled in the 
 ' Will event. Notify the user and exit. 
 strMsg = "I'm sorry you can't connect right now." & vbCrLf 
 strMsg = strMsg & " Click OK to exit." 
 Unload Me 
 Case Else 
 strMsg = "Error " & Format(pError.Number) & vbCrLf 
 strMsg = strMsg & pError.Description 
 strMsg = strMsg & " Click OK to exit." 
 Unload Me 
 End Select 
 Else 
 strMsg = "Error occured. Click OK to exit." 
 Unload Me 
 End If 
 End If 
 'frmWait.btnOK.Enabled = True 
End Sub 
' EndEventExampleVB02 
```

<span data-ttu-id="e50cf-109">**Connection** 对象声明于 **Form** 级别，并使用 **WithEvents** 关键字来启用事件处理。</span><span class="sxs-lookup"><span data-stu-id="e50cf-109">The **Connection** object is declared at the **Form** level using the **WithEvents** keyword to enable event handling.</span></span> <span data-ttu-id="e50cf-110">表单\_加载事件处理程序实际上通过将一个新的**connection**对象分配给*connEvent*来创建对象, 然后打开该连接。</span><span class="sxs-lookup"><span data-stu-id="e50cf-110">The Form\_Load event handler actually creates the object by assigning a new **Connection** object to *connEvent* and then opens the connection.</span></span> <span data-ttu-id="e50cf-111">当然, 实际应用程序在表单\_加载事件处理程序中执行的处理会比此处显示的更多。</span><span class="sxs-lookup"><span data-stu-id="e50cf-111">Of course, a real application would do more processing in the Form\_Load event handler than is shown here.</span></span>

