---
title: 在 JScript 中处理错误
TOCTitle: Handling Errors in JScript
ms:assetid: 2197b4b9-819f-43ff-3ac6-3823c62b40c6
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248993(v=office.15)
ms:contentKeyID: 48543684
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 1c264d4fb4eae460934fcd056e371607c5c0138e
ms.sourcegitcommit: 801b1b54786f7b0e5b0d35466e7ae8d1e840b26f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25860208"
---
# <a name="handling-errors-in-jscript"></a><span data-ttu-id="b4bd4-102">在 JScript 中处理错误</span><span class="sxs-lookup"><span data-stu-id="b4bd4-102">Handling Errors in JScript</span></span>


<span data-ttu-id="b4bd4-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="b4bd4-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="b4bd4-p101">Microsoft JScript 代码必须检查 **Connection** 对象的 **Errors** 集合的 **Count** 属性。如果值大于 0，则迭代遍历集合，并以相应的其他任何语言打印这些值。</span><span class="sxs-lookup"><span data-stu-id="b4bd4-p101">Your Microsoft JScript code must check the **Count** property of the **Connection** object's **Errors** collection. If the value is greater than 0, iterate through the collection and print the values as you would in any of the other languages.</span></span>

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

