---
title: JScript ADO 编程
TOCTitle: JScript ADO programming
ms:assetid: 2254f111-e6c2-1ad7-eb65-ee0550056d89
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249002(v=office.15)
ms:contentKeyID: 48543706
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 88a84f6fa3604286ca27651cefc999c96ff41d0e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32290889"
---
# <a name="jscript-ado-programming"></a>JScript ADO 编程


**适用于**：Access 2013、Office 2013


## <a name="creating-an-ado-project"></a>创建 ADO 项目

Microsoft JScript 不支持类型库，所以不需要在项目中引用 ADO。因此，不支持命令行完成等关联功能。而且，默认情况下，JScript 中没有定义 ADO 枚举常量。

但是，ADO 提供了两个包含文件，其中包含要用于 JScript 的以下定义：

- 对于服务器端脚本, 请使用 adojavas.inc, 它在默认情况下安装在 c\\: Program\\files 常见\\文件\\系统\\ ado 文件夹中。

- 对于客户端脚本, 请使用 Adcjavas, 它在默认情况下安装在 c\\: Program\\files Common\\files\\System\\ msdac 文件夹中。

您可以将常量定义从这些文件复制并粘贴到 ASP 页中, 或者, 如果您正在执行服务器端脚本, 请将 adojavas.inc 文件复制到网站上的文件夹中, 并从 ASP 页引用它, 如下所示:

```javascript  
 
<!--#include File="adojavas.inc"--> 
```

## <a name="creating-ado-objects-in-jscript"></a>在 JScript 中创建 ADO 对象

必须改为使用 **CreateObject** 函数调用：

```javascript  
 
var Rs1; 
Rs1 = Server.CreateObject("ADODB.Recordset"); 
```

## <a name="jscript-example"></a>JScript 示例

以下代码是在一个用于打开 **Recordset** 对象的 Active Server Page (ASP) 文件中进行 JScript 服务器端编程的一般示例：

```javascript 
 
<%  @LANGUAGE="JScript" %> 
<!--#include File="adojavas.inc"--> 
<HTML> 
<BODY BGCOLOR="White" topmargin="10" leftmargin="10"> 
<% 
var Source = "SELECT * FROM Authors"; 
var Connect =  "Provider=sqloledb;Data Source=srv;" + 
    "Initial Catalog=Pubs;Integrated Security=SSPI;" 
var Rs1 = Server.CreateObject( "ADODB.Recordset.2.5" ); 
Rs1.Open(Source,Connect,adOpenForwardOnly); 
Response.Write("Success!"); 
%> 
</BODY> 
</HTML> 
```

