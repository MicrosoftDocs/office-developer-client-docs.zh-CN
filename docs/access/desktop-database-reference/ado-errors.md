---
title: ActiveX 数据对象 (ADO) 错误
TOCTitle: ADO Errors
ms:assetid: 02fcf563-ce2d-9ef7-b8ae-2795f667335a
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248796(v=office.15)
ms:contentKeyID: 48542972
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: ee87da91086a010066ba94b294955eebdff7b636
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25465944"
---
# <a name="ado-errors"></a><span data-ttu-id="c9cf5-102">ADO 错误</span><span class="sxs-lookup"><span data-stu-id="c9cf5-102">ADO Errors</span></span>


<span data-ttu-id="c9cf5-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="c9cf5-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="c9cf5-104">ADO 错误作为运行时错误报告给您的程序。</span><span class="sxs-lookup"><span data-stu-id="c9cf5-104">ADO Errors are reported to your program as run-time errors.</span></span> <span data-ttu-id="c9cf5-105">您可以使用编程语言的错误捕获机制来捕获并处理它们。</span><span class="sxs-lookup"><span data-stu-id="c9cf5-105">You can use the error-trapping mechanism of your programming language to trap and handle them.</span></span> <span data-ttu-id="c9cf5-106">例如，在 Visual Basic 中，使用 **On Error** 语句。</span><span class="sxs-lookup"><span data-stu-id="c9cf5-106">For example, in Visual Basic, use the **On Error** statement.</span></span> <span data-ttu-id="c9cf5-107">在 Visual J++ 中，使用 **try-catch** 块。</span><span class="sxs-lookup"><span data-stu-id="c9cf5-107">In Visual J++, use a **try-catch** block.</span></span> <span data-ttu-id="c9cf5-108">在 Visual C++ 中，错误捕获机制取决于您用于访问 ADO 库的方法。</span><span class="sxs-lookup"><span data-stu-id="c9cf5-108">In Visual C++, it depends on the method you are using to access the ADO libraries.</span></span> <span data-ttu-id="c9cf5-109">使用\#导入，请使用**try-catch**块。</span><span class="sxs-lookup"><span data-stu-id="c9cf5-109">With \#import, use a **try-catch** block.</span></span> <span data-ttu-id="c9cf5-110">否则，C++ 程序员需要通过调用 **GetErrorInfo** 显式检索该错误对象。</span><span class="sxs-lookup"><span data-stu-id="c9cf5-110">Otherwise, C++ programmers need to explicitly retrieve the error object by calling **GetErrorInfo**.</span></span> <span data-ttu-id="c9cf5-111">以下 Visual Basic 子程序演示了如何捕获 ADO 错误：</span><span class="sxs-lookup"><span data-stu-id="c9cf5-111">The following Visual Basic sub procedure demonstrates trapping an ADO error:</span></span>

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

<span data-ttu-id="c9cf5-112">这**窗体\_负载**事件过程有意通过尝试两次打开相同的**Connection**对象创建一个错误。</span><span class="sxs-lookup"><span data-stu-id="c9cf5-112">This **Form\_Load** event procedure intentionally creates an error by trying to open the same **Connection** object twice.</span></span> <span data-ttu-id="c9cf5-113">第二次调用 **Open** 方法时，会激活错误处理程序。</span><span class="sxs-lookup"><span data-stu-id="c9cf5-113">The second time the **Open** method is called, the error handler is activated.</span></span> <span data-ttu-id="c9cf5-114">在这种情况下，该错误类型是 **adErrObjectOpen** ，因此在继续执行程序之前，该错误处理程序显示以下消息：</span><span class="sxs-lookup"><span data-stu-id="c9cf5-114">In this case the error is of type **adErrObjectOpen**, so the error handler displays the following message before resuming program execution:</span></span>

```vb 
Error #3705: Operation is not allowed when the object is open. 
Error reported by: ADODB.Connection 
Help File: E:\WINNT\HELP\ADO260.CHM Topic ID: 1003705 
```

<span data-ttu-id="c9cf5-p103">该错误消息包括由 Visual Basic **Err** 对象提供的每条信息， **LastDLLError** 值除外（此值不适合这种情况）。错误号会告知您发生了哪个错误。如果您不想亲自处理错误，该说明会很有用。您只需将其传递给用户。尽管通常希望使用为应用程序自定义的消息，但您无法预见每个错误；该说明可以提供关于出错原因的一些线索。在示例代码中，错误是由 **Connection** 对象报告的。在此处您将看到对象类型或程序 ID（而不是变量名）。</span><span class="sxs-lookup"><span data-stu-id="c9cf5-p103">The error message includes each piece of information provided by the Visual Basic **Err** object except for the **LastDLLError** value, which does not apply here. The error number tells you which error has occurred. The description is useful in cases in which you do not want to handle the error yourself. You can simply pass it along to the user. Although you will usually want to use messages customized for your application, you cannot anticipate every error; the description gives some clue as to what went wrong. In the sample code, the error was reported by the **Connection** object. You will see the object's type or programmatic ID here — not a variable name.</span></span>


> [!NOTE]
> <P><span data-ttu-id="c9cf5-p104">[!注释] Visual Basic <STRONG>Err</STRONG> 对象仅包含有关最近发生的错误的信息。对于由最近的 ADO 操作引起的每个错误， <STRONG>Connection</STRONG> 对象的 ADO <STRONG>Errors</STRONG> 集合都包含一个 <STRONG>Error</STRONG> 对象。请使用 <STRONG>Errors</STRONG> 集合而不是 <STRONG>Err</STRONG> 对象来处理多个错误。有关 <STRONG>Errors</STRONG> 集合的详细信息，请参阅 <A href="provider-errors.md">提供程序错误</A>。但是，如果不存在有效的 <STRONG>Connection</STRONG> 对象， <STRONG>Err</STRONG> 对象就是有关 ADO 错误的唯一信息源。</span><span class="sxs-lookup"><span data-stu-id="c9cf5-p104">The Visual Basic <STRONG>Err</STRONG> object only contains information about the most recent error. The ADO <STRONG>Errors</STRONG> collection of the <STRONG>Connection</STRONG> object contains one <STRONG>Error</STRONG> object for each error raised by the most recent ADO operation. Use the <STRONG>Errors</STRONG> collection rather than the <STRONG>Err</STRONG> object to handle multiple errors. For more information about the <STRONG>Errors</STRONG> collection, see <A href="provider-errors.md">Provider Errors</A>. However, if there is no valid <STRONG>Connection</STRONG> object, the <STRONG>Err</STRONG> object is the only source for information about ADO errors.</span></span></P>



<span data-ttu-id="c9cf5-p105">哪种操作有可能导致 ADO 错误呢？常见的 ADO 错误有，打开 **Connection** 或 **Recordset** 等对象，试图更新数据，或者调用提供程序不支持的方法或属性。</span><span class="sxs-lookup"><span data-stu-id="c9cf5-p105">What kinds of operations are likely to cause ADO errors? Common ADO errors can involve opening an object such as a **Connection** or **Recordset**, attempting to update data, or calling a method or property that is not supported by your provider.</span></span>

<span data-ttu-id="c9cf5-p106">OLE DB 错误还可以作为 **Errors** 集合中的运行时错误传递到您的应用程序中。有关 OLE DB 错误号的详细信息，请参阅《OLE DB 程序员参考》的第 16 章。</span><span class="sxs-lookup"><span data-stu-id="c9cf5-p106">OLE DB errors can also be passed to your application as run-time errors in the **Errors** collection. For more information about OLE DB error numbers, see Chapter 16 of the OLE DB Programmer's Reference.</span></span>
