---
title: RDS 教程 (VBScript)
TOCTitle: RDS Tutorial (VBScript)
ms:assetid: 7a6596fd-00b9-a637-7d00-fb55a621305f
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249506(v=office.15)
ms:contentKeyID: 48545792
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: d87dc84217b716505302464825a1857fecf67669
ms.sourcegitcommit: a49b77f4c8cec69f90656a86f0872cf34c35968e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2018
ms.locfileid: "25606820"
---
# <a name="rds-tutorial-vbscript"></a><span data-ttu-id="ac8e7-102">RDS 教程 (VBScript)</span><span class="sxs-lookup"><span data-stu-id="ac8e7-102">RDS Tutorial (VBScript)</span></span>


<span data-ttu-id="ac8e7-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="ac8e7-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="ac8e7-p101">这是用 Microsoft Visual Basic Scripting Edition 编写的 RDS 教程。有关本教程目的的说明，请参阅 [RDS 教程](chapter-12-rds-tutorial.md)。</span><span class="sxs-lookup"><span data-stu-id="ac8e7-p101">This is the RDS Tutorial, written in Microsoft Visual Basic Scripting Edition. For a description of the purpose of this tutorial, see the [RDS Tutorial](chapter-12-rds-tutorial.md).</span></span>

<span data-ttu-id="ac8e7-106">在本教程中， [rds.DataControl](datacontrol-object-rds.md)和[rds.DataSpace](dataspace-object-rds.md)在设计时创建 — 即，与 object 标记，如下所示定义:。</span><span class="sxs-lookup"><span data-stu-id="ac8e7-106">In this tutorial, [RDS.DataControl](datacontrol-object-rds.md) and [RDS.DataSpace](dataspace-object-rds.md) are created at design time — that is, they are defined with object tags, like this: .</span></span> <span data-ttu-id="ac8e7-107">另外，它们也可以在运行时通过 **Server.CreateObject** 方法创建。</span><span class="sxs-lookup"><span data-stu-id="ac8e7-107">Alternatively, they could be created at run time with the **Server.CreateObject** method.</span></span> <span data-ttu-id="ac8e7-108">例如， **RDS.DataControl** 对象可以按如下方式创建：</span><span class="sxs-lookup"><span data-stu-id="ac8e7-108">For example, the **RDS.DataControl** object could be created like this:</span></span>

```vb
    Set DC = Server.CreateObject("RDS.DataControl") 
     <!-- RDS.DataControl --> 
     <OBJECT 
     ID="DC1" CLASSID="CLSID:BD96C556-65A3-11D0-983A-00C04FC29E33"> 
     </OBJECT> 
     
     <!-- RDS.DataSpace --> 
     <OBJECT 
     ID="DS1" WIDTH=1 HEIGHT=1 
     CLASSID="CLSID:BD96C556-65A3-11D0-983A-00C04FC29E36"> 
     </OBJECT> 
     
     <SCRIPT LANGUAGE="VBScript"> 
     
     Sub RDSTutorial() 
     Dim DF1 
```

<span data-ttu-id="ac8e7-109">**步骤 1 - 指定服务器程序**</span><span class="sxs-lookup"><span data-stu-id="ac8e7-109">**Step 1 — Specify a server program**</span></span>

<span data-ttu-id="ac8e7-110"><<<<<<< 标头 VBScript 可以发现通过访问供 Active Server Pages 的 VBScript **Request.ServerVariables**方法运行的 IIS Web 服务器的名称: === VBScript 可以发现的 IIS web 名称服务器上运行它通过访问供 Active Server Pages 的 VBScript **Request.ServerVariables**方法：</span><span class="sxs-lookup"><span data-stu-id="ac8e7-110"><<<<<<< HEAD VBScript can discover the name of the IIS Web server it is running on by accessing the VBScript **Request.ServerVariables** method available to Active Server Pages: ======= VBScript can discover the name of the IIS web server it is running on by accessing the VBScript **Request.ServerVariables** method available to Active Server Pages:</span></span>
>>>>>>> <span data-ttu-id="ac8e7-111">master</span><span class="sxs-lookup"><span data-stu-id="ac8e7-111">master</span></span>

```vb 
 
"https://<%=Request.ServerVariables("SERVER_NAME")%>" 
```

<span data-ttu-id="ac8e7-112">但是，本教程将使用虚构服务器"yourServer"。</span><span class="sxs-lookup"><span data-stu-id="ac8e7-112">However, for this tutorial, use the imaginary server, "yourServer".</span></span>


> [!NOTE]
> <P><span data-ttu-id="ac8e7-p103">[!注释] 请留意 <STRONG>ByRef</STRONG> 参数的数据类型。VBScript 不允许指定变量类型，因此必须始终传递变量。使用 HTTP 时，如果您用 <STRONG>RDS.DataSpace</STRONG> 对象的 <A href="createobject-method-rds.md">CreateObject</A> 方法调用服务器程序，RDS 将允许您向应该使用非变量的方法传递变量。在使用 DCOM 或进程内服务器时，必须使客户端与服务器端的参数类型相匹配，否则将会产生"类型不匹配"错误。</span><span class="sxs-lookup"><span data-stu-id="ac8e7-p103">Pay attention to the data type of <STRONG>ByRef</STRONG> arguments. VBScript does not let you specify the variable type, so you must always pass a Variant. When using HTTP, RDS will allow you to pass a Variant to a method that expects a non-Variant if you invoke it with the <STRONG>RDS.DataSpace</STRONG> object <A href="createobject-method-rds.md">CreateObject</A> method. When using DCOM or an in-process server, match the parameter types on the client and server sides or you will receive a "Type Mismatch" error.</span></span></P>

```vb
 
Set DF1 = DS1.CreateObject("RDSServer.DataFactory", "https://yourServer") 
```

<span data-ttu-id="ac8e7-117">**步骤 2a - 使用 RDS.DataControl 调用服务器程序**</span><span class="sxs-lookup"><span data-stu-id="ac8e7-117">**Step 2a — Invoke the server program with RDS.DataControl**</span></span>

<span data-ttu-id="ac8e7-118">以下示例只是注释，演示 **RDS.DataControl** 的默认行为是执行指定的查询。</span><span class="sxs-lookup"><span data-stu-id="ac8e7-118">This example is merely a comment demonstrating that the default behavior of the **RDS.DataControl** is to perform the specified query.</span></span>

```vb
 
<OBJECT CLASSID="clsid:BD96C556-65A3-11D0-983A-00C04FC29E33" ID="DC1"> 
 <PARAM NAME="SQL" VALUE="SELECT * FROM Authors"> 
 <PARAM NAME="Connect" VALUE="DSN=Pubs;"> 
 <PARAM NAME="Server" VALUE="https://yourServer/"> 
</OBJECT> 
... 
<SCRIPT LANGUAGE="VBScript"> 
 
Sub RDSTutorial2A() 
 Dim RS 
 DC1.Refresh 
 Set RS = DC1.Recordset 
... 
```

<span data-ttu-id="ac8e7-119">**步骤 2b - 使用 RDSServer.DataFactory 调用服务器程序**</span><span class="sxs-lookup"><span data-stu-id="ac8e7-119">**Step 2b — Invoke the server program with RDSServer.DataFactory**</span></span>

<span data-ttu-id="ac8e7-120">**步骤 3 - 服务器获取 Recordset**</span><span class="sxs-lookup"><span data-stu-id="ac8e7-120">**Step 3 — Server obtains a Recordset**</span></span>

<span data-ttu-id="ac8e7-121">**步骤 4 - 服务器返回 Recordset**</span><span class="sxs-lookup"><span data-stu-id="ac8e7-121">**Step 4 — Server returns the Recordset**</span></span>

```vb
 
Set RS = DF1.Query("DSN=Pubs;", "SELECT * FROM Authors") 
```

<span data-ttu-id="ac8e7-122">**步骤 5 - 使 DataControl 能被可视控件使用**</span><span class="sxs-lookup"><span data-stu-id="ac8e7-122">**Step 5 — DataControl is made usable by visual controls**</span></span>

```vb
 
' Assign the returned recordset to the DataControl. 
 
DC1.SourceRecordset = RS 
```

<span data-ttu-id="ac8e7-123">**步骤 6a - 用 RDS.DataControl 将所做的更改发送到服务器**</span><span class="sxs-lookup"><span data-stu-id="ac8e7-123">**Step 6a — Changes are sent to the server with RDS.DataControl**</span></span>

<span data-ttu-id="ac8e7-124">以下示例只是一个注释，演示 **RDS.DataControl** 如何执行更新。</span><span class="sxs-lookup"><span data-stu-id="ac8e7-124">This example is merely a comment demonstrating how the **RDS.DataControl** performs updates.</span></span>

```vb
 
<OBJECT CLASSID="clsid:BD96C556-65A3-11D0-983A-00C04FC29E33" ID="DC1"> 
 <PARAM NAME="SQL" VALUE="SELECT * FROM Authors"> 
 <PARAM NAME="Connect" VALUE="DSN=Pubs;"> 
 <PARAM NAME="Server" VALUE="https://yourServer/"> 
</OBJECT> 
... 
<SCRIPT LANGUAGE="VBScript"> 
 
Sub RDSTutorial6A() 
Dim RS 
DC1.Refresh 
... 
Set RS = DC1.Recordset 
' Edit the Recordset object... 
' The SERVER and CONNECT properties are already set from Step 2A. 
Set DC1.SourceRecordset = RS 
... 
DC1.SubmitChanges 
```

<span data-ttu-id="ac8e7-125">**步骤 6b - 使用 RDSServer.DataFactory 将所做的更改发送到服务器**</span><span class="sxs-lookup"><span data-stu-id="ac8e7-125">**Step 6b — Changes are sent to the server with RDSServer.DataFactory**</span></span>

```vb
 
DF.SubmitChanges"DSN=Pubs", RS 
 
End Sub 
</SCRIPT> 
</BODY> 
</HTML> 
```

<span data-ttu-id="ac8e7-126">**本教程到此结束。**</span><span class="sxs-lookup"><span data-stu-id="ac8e7-126">**This is the end of the tutorial.**</span></span>

