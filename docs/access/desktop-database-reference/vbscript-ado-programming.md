---
title: VBScript ADO 编程
TOCTitle: VBScript ADO Programming
ms:assetid: 24be1c70-8813-ed98-c3e5-fb33a68e7b41
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249019(v=office.15)
ms:contentKeyID: 48543764
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 4aff2c8b3394321367851ad82e4e7efe98badff8
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32306025"
---
# <a name="vbscript-ado-programming"></a>VBScript ADO 编程


**适用于**：Access 2013、Office 2013 

## <a name="creating-an-ado-project"></a>创建 ADO 项目

Microsoft Visual Basic Scripting Edition 不支持类型库，所以不需要在项目中引用 ADO。因此，不支持命令行完成等关联功能。而且，在默认情况下，VBScript 中没有定义 ADO 枚举常量。

但是，ADO 提供了两个包含文件，其中包含要用于 VBScript 的以下定义：

  - 对于服务器端脚本, 请使用 adovbs.inc, 它在默认情况下安装在 c\\: Program\\files 常见\\文件\\系统\\ ado 文件夹中。

  - 对于客户端脚本, 请使用 adcvbs.inc, 它在默认情况下安装在 c\\: Program\\files Common\\files\\System\\ msdac 文件夹中。

您可以将常量定义从这些文件复制并粘贴到 ASP 页中, 或者, 如果您正在执行服务器端脚本, 请将 adovbs.inc 文件复制到网站上的文件夹中, 并从 ASP 页引用它, 如下所示:

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

ADO 文档中附带了更多特定的 VBScript 示例。 有关详细信息, 请参阅[Microsoft Visual Basic 脚本版中的 ADO 代码示例](ado-code-examples-in-microsoft-visual-basic-scripting-edition.md)。

## <a name="differences-between-vbscript-and-visual-basic"></a>VBScript 和 Visual Basic 之间的差异

在 VBScript 中使用 ADO 与在 Visual Basic 中使用 ADO 有很多相似之处，包括语法的使用方式。但是，还存在某些重要的差异：

- VBScript 只支持变量型数据类型，该数据类型可以包含不同类型的数据。可以将需要的数据存储在变量型数据类型中，由于 VBScript 将执行相应的转换，这些数据将适当地发挥作用。VBScript 可以识别 ADO 需要的类型，并相应地转换变量型中的值。

- 不能在`on error goto <label>` VBScript 中使用。

- VBScript 支持某些内置的 Visual Basic 函数，例如 **Msgbox** 、 **Date** 和 **IsNumeric** 。但是，由于 VBScript 是 Visual Basic 的子集，它仅支持部分内置函数。例如，VBScript 不支持 **Format** 函数和文件 I/O 函数。

