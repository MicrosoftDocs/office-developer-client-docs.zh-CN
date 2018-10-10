---
title: VBScript ADO 编程
TOCTitle: VBScript ADO Programming
ms:assetid: 24be1c70-8813-ed98-c3e5-fb33a68e7b41
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249019(v=office.15)
ms:contentKeyID: 48543764
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: d6336819b759e7ced832e993f72b05ebc2108587
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468501"
---
# <a name="vbscript-ado-programming"></a><span data-ttu-id="e70d4-102">VBScript ADO 编程</span><span class="sxs-lookup"><span data-stu-id="e70d4-102">VBScript ADO Programming</span></span>


<span data-ttu-id="e70d4-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="e70d4-103">**Applies to**: Access 2013 | Office 2013</span></span> 

## <a name="creating-an-ado-project"></a><span data-ttu-id="e70d4-104">创建 ADO 项目</span><span class="sxs-lookup"><span data-stu-id="e70d4-104">Creating an ADO Project</span></span>

<span data-ttu-id="e70d4-p101">Microsoft Visual Basic Scripting Edition 不支持类型库，所以不需要在项目中引用 ADO。因此，不支持命令行完成等关联功能。而且，在默认情况下，VBScript 中没有定义 ADO 枚举常量。</span><span class="sxs-lookup"><span data-stu-id="e70d4-p101">Microsoft Visual Basic, Scripting Edition does not support type libraries, so you do not need to reference ADO in your project. Consequently, no associated features such as command line completion are supported. Also, by default, ADO enumerated constants are not defined in VBScript.</span></span>

<span data-ttu-id="e70d4-108">但是，ADO 提供了两个包含文件，其中包含要用于 VBScript 的以下定义：</span><span class="sxs-lookup"><span data-stu-id="e70d4-108">However, ADO provides you with two include files containing the following definitions to be used with VBScript:</span></span>

  - <span data-ttu-id="e70d4-109">对于服务器端脚本，请使用 Adovbs.inc，该文件安装中的 c:\\Program Files\\Common Files\\系统\\ado\\默认情况下的文件夹。</span><span class="sxs-lookup"><span data-stu-id="e70d4-109">For server-side scripting use Adovbs.inc, which is installed in the c:\\Program Files\\Common Files\\System\\ado\\ folder by default.</span></span>

  - <span data-ttu-id="e70d4-110">客户端脚本，请使用 Adcvbs.inc，其安装在 c:\\Program Files\\Common Files\\系统\\msdac\\默认情况下的文件夹。</span><span class="sxs-lookup"><span data-stu-id="e70d4-110">For client-side scripting use Adcvbs.inc, which is installed in the c:\\Program Files\\Common Files\\System\\msdac\\ folder by default.</span></span>

<span data-ttu-id="e70d4-111">您可以复制和将常量定义从这些文件粘贴到 ASP 页中，或时，如果您正在执行服务器端脚本，Adovbs.inc 将文件复制到文件夹在您的网站和引用从 ASP 页如下所示：</span><span class="sxs-lookup"><span data-stu-id="e70d4-111">You can either copy and paste constant definitions from these files into your ASP pages, or, if you are doing server-side scripting, copy Adovbs.inc file to a folder on your website and referencing it from your ASP page like this:</span></span>

```vb 
 
<!--#include File="adovbs.inc"--> 
```

## <a name="creating-ado-objects-in-vbscript"></a><span data-ttu-id="e70d4-112">在 VBScript 中创建 ADO 对象</span><span class="sxs-lookup"><span data-stu-id="e70d4-112">Creating ADO Objects in VBScript</span></span>

<span data-ttu-id="e70d4-p102">在 VBScript 中，无法使用 **Dim** 语句将对象赋给特定类型。而且，在 VBScript 中不支持在 Basic for Applications 中与 **Dim** 语句一起使用的 **New** 语法。必须改用使用 **CreateObject** 函数调用：</span><span class="sxs-lookup"><span data-stu-id="e70d4-p102">You cannot use the **Dim** statement to assign objects to a specific type in VBScript. Also, VBScript does not support the **New** syntax used with the **Dim** statement in Visual Basic for Applications. You must instead use the **CreateObject** function call:</span></span>

```vb 
 
Dim Rs1 
Set Rs1 = Server.CreateObject( "ADODB.Recordset" ) 
```

## <a name="vbscript-examples"></a><span data-ttu-id="e70d4-116">VBScript 示例</span><span class="sxs-lookup"><span data-stu-id="e70d4-116">VBScript Examples</span></span>

<span data-ttu-id="e70d4-117">以下代码是在 Active Server Page (ASP) 文件中进行 VBScript 服务器端编程的一般示例：</span><span class="sxs-lookup"><span data-stu-id="e70d4-117">The following code is a generic example of VBScript server-side programming in an Active Server Page (ASP) file:</span></span>

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

<span data-ttu-id="e70d4-p103">ADO 文档中附带了更多特定的 VBScript 示例。有关详细信息，请参阅 [Microsoft Visual Basic Scripting Edition 中的 ADO 代码示例](ado-code-examples-in-microsoft-visual-basic-scripting-edition.md)。</span><span class="sxs-lookup"><span data-stu-id="e70d4-p103">More specific VBScript examples are included with the ADO documentation. For more information, see [ADO Code Examples in Microsoft Visual Basic Scripting Edition](ado-code-examples-in-microsoft-visual-basic-scripting-edition.md).</span></span>

## <a name="differences-between-vbscript-and-visual-basic"></a><span data-ttu-id="e70d4-120">VBScript 和 Visual Basic 之间的差异</span><span class="sxs-lookup"><span data-stu-id="e70d4-120">Differences Between VBScript and Visual Basic</span></span>

<span data-ttu-id="e70d4-p104">在 VBScript 中使用 ADO 与在 Visual Basic 中使用 ADO 有很多相似之处，包括语法的使用方式。但是，还存在某些重要的差异：</span><span class="sxs-lookup"><span data-stu-id="e70d4-p104">Using ADO with VBScript is similar to using ADO with Visual Basic in many ways, including how syntax is used. However, some significant differences exist:</span></span>

- <span data-ttu-id="e70d4-p105">VBScript 只支持变量型数据类型，该数据类型可以包含不同类型的数据。可以将需要的数据存储在变量型数据类型中，由于 VBScript 将执行相应的转换，这些数据将适当地发挥作用。VBScript 可以识别 ADO 需要的类型，并相应地转换变量型中的值。</span><span class="sxs-lookup"><span data-stu-id="e70d4-p105">VBScript supports only the Variant data type, which can hold different types of data. You can store the data you need in a Variant data type, and the data will function appropriately due to casting performed by VBScript. It recognizes the type required by ADO, and converts the value in the Variant accordingly.</span></span>

- <span data-ttu-id="e70d4-126">不能使用`on error goto <label>`VBScript 中。</span><span class="sxs-lookup"><span data-stu-id="e70d4-126">You cannot use `on error goto <label>` within VBScript.</span></span>

- <span data-ttu-id="e70d4-p106">VBScript 支持某些内置的 Visual Basic 函数，例如 **Msgbox** 、 **Date** 和 **IsNumeric** 。但是，由于 VBScript 是 Visual Basic 的子集，它仅支持部分内置函数。例如，VBScript 不支持 **Format** 函数和文件 I/O 函数。</span><span class="sxs-lookup"><span data-stu-id="e70d4-p106">VBScript supports some of the built-in Visual Basic functions such as **Msgbox**, **Date**, and **IsNumeric**. However, because VBScript is a subset of Visual Basic, not all built-in functions are supported. For example, VBScript does not support the **Format** function and the file I/O functions.</span></span>

