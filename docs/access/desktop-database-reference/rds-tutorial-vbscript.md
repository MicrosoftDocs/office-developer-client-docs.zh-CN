---
title: RDS 教程 (VBScript)
TOCTitle: RDS Tutorial (VBScript)
ms:assetid: 7a6596fd-00b9-a637-7d00-fb55a621305f
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249506(v=office.15)
ms:contentKeyID: 48545792
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 8d8bc6d0bb2b2f5402a10a690bb0003170357b21
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467321"
---
# <a name="rds-tutorial-vbscript"></a>RDS 教程 (VBScript)


**适用于**： Access 2013 |Office 2013

这是用 Microsoft Visual Basic Scripting Edition 编写的 RDS 教程。有关本教程目的的说明，请参阅 [RDS 教程](chapter-12-rds-tutorial.md)。

在本教程中， [rds.DataControl](datacontrol-object-rds.md)和[rds.DataSpace](dataspace-object-rds.md)在设计时创建 — 即，与 object 标记，如下所示定义:。 另外，它们也可以在运行时通过 **Server.CreateObject** 方法创建。 例如， **RDS.DataControl** 对象可以按如下方式创建：

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

**步骤 1 - 指定服务器程序**

VBScript 可以发现它运行其上的 IIS Web 服务器的名称，方法是访问可用于 Active Server Pages 的 VBScript **Request.ServerVariables** 方法：

```vb 
 
"https://<%=Request.ServerVariables("SERVER_NAME")%>" 
```

但是，本教程将使用虚构服务器"yourServer"。


> [!NOTE]
> <P>[!注释] 请留意 <STRONG>ByRef</STRONG> 参数的数据类型。VBScript 不允许指定变量类型，因此必须始终传递变量。使用 HTTP 时，如果您用 <STRONG>RDS.DataSpace</STRONG> 对象的 <A href="createobject-method-rds.md">CreateObject</A> 方法调用服务器程序，RDS 将允许您向应该使用非变量的方法传递变量。在使用 DCOM 或进程内服务器时，必须使客户端与服务器端的参数类型相匹配，否则将会产生"类型不匹配"错误。</P>

```vb
 
Set DF1 = DS1.CreateObject("RDSServer.DataFactory", "https://yourServer") 
```

**步骤 2a - 使用 RDS.DataControl 调用服务器程序**

以下示例只是注释，演示 **RDS.DataControl** 的默认行为是执行指定的查询。

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

**步骤 2b - 使用 RDSServer.DataFactory 调用服务器程序**

**步骤 3 - 服务器获取 Recordset**

**步骤 4 - 服务器返回 Recordset**

```vb
 
Set RS = DF1.Query("DSN=Pubs;", "SELECT * FROM Authors") 
```

**步骤 5 - 使 DataControl 能被可视控件使用**

```vb
 
' Assign the returned recordset to the DataControl. 
 
DC1.SourceRecordset = RS 
```

**步骤 6a - 用 RDS.DataControl 将所做的更改发送到服务器**

以下示例只是一个注释，演示 **RDS.DataControl** 如何执行更新。

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

**步骤 6b - 使用 RDSServer.DataFactory 将所做的更改发送到服务器**

```vb
 
DF.SubmitChanges"DSN=Pubs", RS 
 
End Sub 
</SCRIPT> 
</BODY> 
</HTML> 
```

**本教程到此结束。**

