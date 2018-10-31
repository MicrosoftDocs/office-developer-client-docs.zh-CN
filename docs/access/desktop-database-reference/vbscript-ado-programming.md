---
title: VBScript ADO 编程
TOCTitle: VBScript ADO Programming
ms:assetid: 24be1c70-8813-ed98-c3e5-fb33a68e7b41
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249019(v=office.15)
ms:contentKeyID: 48543764
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: e94f4d313a9c43d08c9786c6f27fd49624709249
ms.sourcegitcommit: 801b1b54786f7b0e5b0d35466e7ae8d1e840b26f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25863064"
---
# <a name="vbscript-ado-programming"></a>VBScript ADO 编程


**适用于**： Access 2013 |Office 2013 

## <a name="creating-an-ado-project"></a>创建 ADO 项目

Microsoft Visual Basic Scripting Edition 不支持类型库，所以不需要在项目中引用 ADO。因此，不支持命令行完成等关联功能。而且，在默认情况下，VBScript 中没有定义 ADO 枚举常量。

但是，ADO 提供了两个包含文件，其中包含要用于 VBScript 的以下定义：

  - 对于服务器端脚本，请使用 Adovbs.inc，该文件安装中的 c:\\Program Files\\Common Files\\系统\\ado\\默认情况下的文件夹。

  - 客户端脚本，请使用 Adcvbs.inc，其安装在 c:\\Program Files\\Common Files\\系统\\msdac\\默认情况下的文件夹。

您可以复制和将常量定义从这些文件粘贴到 ASP 页中，或时，如果您正在执行服务器端脚本，Adovbs.inc 将文件复制到文件夹在您的网站和引用从 ASP 页如下所示：

```vb 
 
<!--#include File="adovbs.inc"--> 
```

## <a name="creating-ado-objects-in-vbscript"></a>在 VBScript 中创建 ADO 对象

在 VBScript 中，无法使用 **Dim** 语句将对象赋给特定类型。而且，在 VBScript 中不支持在 Basic for Applications 中与 **Dim** 语句一起使用的 **New** 语法。必须改用使用 **CreateObject** 函数调用：

```vb 
 
Dim Rs1 
Set Rs1 = Server.CreateObject( "ADODB.Recordset" ) 
```

## <a name="vbscript-examples"></a>VBScript 示例

以下代码是在 Active Server Page (ASP) 文件中进行 VBScript 服务器端编程的一般示例：

```vb 
 
<%  @LANGUAGE="VBSCRIPT" %> 
<%  Option Explicit %> 
<!--#include File="adovbs.inc"--> 
<HTML> 
    <BODY BGCOLOR="White" topmargin="10" leftmargin="10"> 
 
    <!-- Your ASP Code goes here --> 
<% 
Dim Source 
Dim Connect 
Dim Rs1 
     
Source = "SELECT * FROM Authors" 
Connect = "Provider=sqloledb;Data Source=srv;" & _ 
    "Initial Catalog=Pubs;Integrated Security=SSPI;" 
 
Set Rs1 = Server.CreateObject( "ADODB.Recordset" ) 
Rs1.Open Source, Connect, adOpenForwardOnly 
Response.Write("Success!") 
%> 
    </BODY> 
</HTML> 
```

ADO 文档中附带了更多特定的 VBScript 示例。 有关详细信息，请参阅[在 Microsoft Visual Basic Scripting Edition 中的 ADO 代码示例](ado-code-examples-in-microsoft-visual-basic-scripting-edition.md)。

## <a name="differences-between-vbscript-and-visual-basic"></a>VBScript 和 Visual Basic 之间的差异

在 VBScript 中使用 ADO 与在 Visual Basic 中使用 ADO 有很多相似之处，包括语法的使用方式。但是，还存在某些重要的差异：

- VBScript 只支持变量型数据类型，该数据类型可以包含不同类型的数据。可以将需要的数据存储在变量型数据类型中，由于 VBScript 将执行相应的转换，这些数据将适当地发挥作用。VBScript 可以识别 ADO 需要的类型，并相应地转换变量型中的值。

- 不能使用`on error goto <label>`VBScript 中。

- VBScript 支持某些内置的 Visual Basic 函数，例如 **Msgbox** 、 **Date** 和 **IsNumeric** 。但是，由于 VBScript 是 Visual Basic 的子集，它仅支持部分内置函数。例如，VBScript 不支持 **Format** 函数和文件 I/O 函数。

