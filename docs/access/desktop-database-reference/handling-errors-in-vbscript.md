---
title: 在 VBScript 中处理错误
TOCTitle: Handling Errors in VBScript
ms:assetid: df8f96d5-b917-ddac-d274-6345b2499bf1
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250135(v=office.15)
ms:contentKeyID: 48548222
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: b361291914b952b458fc4fc587b5b0461464c1fb
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466845"
---
# <a name="handling-errors-in-vbscript"></a><span data-ttu-id="8df86-102">在 VBScript 中处理错误</span><span class="sxs-lookup"><span data-stu-id="8df86-102">Handling Errors in VBScript</span></span>


<span data-ttu-id="8df86-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="8df86-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="8df86-104">在 Visual Basic 中与在 VBScript 中所使用的方法几乎没有差异。</span><span class="sxs-lookup"><span data-stu-id="8df86-104">There is little difference between the methods used in Visual Basic and those used with VBScript.</span></span> <span data-ttu-id="8df86-105">主要的差异是，VBScript 不支持错误处理的概念，而是在一个标签位置继续执行。</span><span class="sxs-lookup"><span data-stu-id="8df86-105">The primary difference is that VBScript does not support the concept of error handling by continuing execution at a label.</span></span> <span data-ttu-id="8df86-106">换句话说，不能在 VBScript 中使用 On Error GoTo。</span><span class="sxs-lookup"><span data-stu-id="8df86-106">In other words, you cannot use On Error GoTo in VBScript.</span></span> <span data-ttu-id="8df86-107">在 VBScript 中，而是使用。</span><span class="sxs-lookup"><span data-stu-id="8df86-107">Instead, use in VBScript.</span></span> <span data-ttu-id="8df86-108">而使用上错误继续下一步，然后检查**Err.Number**和**Count**属性， **Errors**集合，如下面的示例中所示：</span><span class="sxs-lookup"><span data-stu-id="8df86-108">Instead, use On Error Resume Next and then check both **Err.Number** and the **Count** property of the **Errors** collection, as shown in the following example:</span></span>

```vb 
 
<!-- BeginErrorExampleVBS --> 
<HTML> 
<HEAD> 
<META NAME="GENERATOR" Content="Microsoft Visual Studio 6.0"> 
<TITLE>Error Handling Example (VBScript)</TITLE> 
</HEAD> 
<BODY> 
 
<h1>Error Handling Example (VBScript)</h1> 
 
<% 
 Dim errLoop 
 Dim strError 
 
 On Error Resume Next 
 
 ' Intentionally trigger an error. 
 Set cnn1 = Server.CreateObject("ADODB.Connection") 
 cnn1.Open "nothing" 
 
 If cnn1.Errors.Count > 0 Then 
 ' Enumerate Errors collection and display 
 ' properties of each Error object. 
 For Each errLoop In cnn1.Errors 
 strError = "Error #" & errLoop.Number & "<br>" & _ 
 " " & errLoop.Description & "<br>" & _ 
 " (Source: " & errLoop.Source & ")" & "<br>" & _ 
 " (SQL State: " & errLoop.SQLState & ")" & "<br>" & _ 
 " (NativeError: " & errLoop.NativeError & ")" & "<br>" 
 If errLoop.HelpFile = "" Then 
 strError = strError & _ 
 " No Help file available" & _ 
 "<br><br>" 
 Else 
 strError = strError & _ 
 " (HelpFile: " & errLoop.HelpFile & ")" & "<br>" & _ 
 " (HelpContext: " & errLoop.HelpContext & ")" & _ 
 "<br><br>" 
 End If 
 Response.Write ("<p>" & strError & "</p>") 
 Next 
 End If 
%> 
 
</BODY> 
</HTML> 
<!-- EndErrorExampleVBS --> 
```
