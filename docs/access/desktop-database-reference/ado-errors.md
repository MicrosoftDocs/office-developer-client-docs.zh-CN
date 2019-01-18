---
title: ActiveX 数据对象 (ADO) 错误
TOCTitle: ADO errors
ms:assetid: 02fcf563-ce2d-9ef7-b8ae-2795f667335a
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248796(v=office.15)
ms:contentKeyID: 48542972
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 5a25dc0d1d5e621a610b34ca1875c3fd76ba56eb
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28720854"
---
# <a name="ado-errors"></a>ADO 错误

**适用于**： Access 2013、 Office 2013

ADO 错误作为运行时错误报告给您的程序。 您可以使用编程语言的错误捕获机制来捕获并处理它们。 例如，在 Visual Basic 中，使用 **On Error** 语句。 在 Visual J++ 中，使用 **try-catch** 块。 在 Visual C++ 中，错误捕获机制取决于您用于访问 ADO 库的方法。 使用\#导入，请使用**try-catch**块。 否则，C++ 程序员需要通过调用 **GetErrorInfo** 显式检索该错误对象。 以下 Visual Basic 子程序演示了如何捕获 ADO 错误：

```vb 
 
' BeginErrorHandlingVB01 
Private Sub Form_Load() 
 ' Turn on error handling 
 On Error GoTo FormLoadError 
 
 'Open the database and the recordset for processing. 
 ' 
 Dim strCnn As String 
 strCnn = "Provider='sqloledb';" & _ 
 "Data Source='MySqlServer';" & _ 
 "Initial Catalog='Northwind';Integrated Security='SSPI';" 
 
 ' cnn is a Public Connection Object because 
 ' it was defined WithEvents 
 Set cnn = New ADODB.Connection 
 cnn.Open strCnn 
 
 ' The next line of code intentionally causes 
 ' an error by trying to open a connection 
 ' that has already been opened. 
 cnn.Open strCnn 
 
 ' rst is a Public Recordset because it 
 ' was defined WithEvents 
 Set rst = New ADODB.Recordset 
 rst.Open "Customers", cnn 
 
 Exit Sub 
 
' Error handler 
FormLoadError: 
 Dim strErr As String 
 Select Case Err 
 Case adErrObjectOpen 
 strErr = "Error #" & Err.Number & ": " & Err.Description & vbCrLf 
 strErr = strErr & "Error reported by: " & Err.Source & vbCrLf 
 strErr = strErr & "Help File: " & Err.HelpFile & vbCrLf 
 strErr = strErr & "Topic ID: " & Err.HelpContext 
 MsgBox strErr 
 Debug.Print strErr 
 Err.Clear 
 Resume Next 
 ' If some other error occurs that 
 ' has nothing to do with ADO, show 
 ' the number and description and exit. 
 Case Else 
 strErr = "Error #" & Err.Number & ": " & Err.Description & vbCrLf 
 MsgBox strErr 
 Debug.Print strErr 
 Unload Me 
 End Select 
End Sub 
' EndErrorHandlingVB01 
```

这**窗体\_负载**事件过程有意通过尝试两次打开相同的**Connection**对象创建一个错误。 第二次调用 **Open** 方法时，会激活错误处理程序。 在这种情况下，该错误类型是 **adErrObjectOpen** ，因此在继续执行程序之前，该错误处理程序显示以下消息：

```vb 
Error #3705: Operation is not allowed when the object is open. 
Error reported by: ADODB.Connection 
Help File: E:\WINNT\HELP\ADO260.CHM Topic ID: 1003705 
```

该错误消息包括由 Visual Basic **Err** 对象提供的每条信息， **LastDLLError** 值除外（此值不适合这种情况）。错误号会告知您发生了哪个错误。如果您不想亲自处理错误，该说明会很有用。您只需将其传递给用户。尽管通常希望使用为应用程序自定义的消息，但您无法预见每个错误；该说明可以提供关于出错原因的一些线索。在示例代码中，错误是由 **Connection** 对象报告的。在此处您将看到对象类型或程序 ID（而不是变量名）。


> [!NOTE]
> [!注释] Visual Basic **Err** 对象仅包含有关最近发生的错误的信息。对于由最近的 ADO 操作引起的每个错误， **Connection** 对象的 ADO **Errors** 集合都包含一个 **Error** 对象。请使用 **Errors** 集合而不是 **Err** 对象来处理多个错误。有关 **Errors** 集合的详细信息，请参阅 <A href="provider-errors.md">提供程序错误</A>。但是，如果不存在有效的 **Connection** 对象， **Err** 对象就是有关 ADO 错误的唯一信息源。

哪种操作有可能导致 ADO 错误呢？常见的 ADO 错误有，打开 **Connection** 或 **Recordset** 等对象，试图更新数据，或者调用提供程序不支持的方法或属性。

OLE DB 错误还可以作为 **Errors** 集合中的运行时错误传递到您的应用程序中。有关 OLE DB 错误号的详细信息，请参阅《OLE DB 程序员参考》的第 16 章。

