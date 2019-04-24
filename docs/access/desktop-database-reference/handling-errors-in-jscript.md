---
title: 处理 JScript 中的错误
TOCTitle: Handling errors in JScript
ms:assetid: 2197b4b9-819f-43ff-3ac6-3823c62b40c6
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248993(v=office.15)
ms:contentKeyID: 48543684
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: f06584ef752e0be7f68b3f661fbdba50b52cd20e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32292039"
---
# <a name="handling-errors-in-jscript"></a><span data-ttu-id="48767-102">处理 JScript 中的错误</span><span class="sxs-lookup"><span data-stu-id="48767-102">Handling errors in JScript</span></span>


<span data-ttu-id="48767-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="48767-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="48767-p101">Microsoft JScript 代码必须检查 **Connection** 对象的 **Errors** 集合的 **Count** 属性。如果值大于 0，则迭代遍历集合，并以相应的其他任何语言打印这些值。</span><span class="sxs-lookup"><span data-stu-id="48767-p101">Your Microsoft JScript code must check the **Count** property of the **Connection** object's **Errors** collection. If the value is greater than 0, iterate through the collection and print the values as you would in any of the other languages.</span></span>

```javascript 
 
<!-- BeginErrorExampleJS --> 
<%@ Language=JScript %> 
<HTML> 
<HEAD> 
<title>Error Handling example (JScript)</title> 
</HEAD> 
<BODY> 
<h1>Error Handling example (JScript)</h1> 
<% 
 var cnn1 = Server.CreateObject("ADODB.Connection"); 
 var errLoop = Server.CreateObject("ADODB.Error"); 
 var strError = new String; 
 
 try 
 { 
 // Intentionally trigger an error. 
 cnn1.Open("nothing"); 
 } 
 catch(e) 
 { 
 Response.Write(e.message); 
 } 
%> 
 
</BODY> 
</HTML> 
<!-- EndErrorExampleJS --> 
```

