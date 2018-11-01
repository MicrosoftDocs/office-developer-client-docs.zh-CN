---
title: JScript ADO 编程
TOCTitle: JScript ADO Programming
ms:assetid: 2254f111-e6c2-1ad7-eb65-ee0550056d89
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249002(v=office.15)
ms:contentKeyID: 48543706
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: dd470482c8e4a2e9228247c5eea4512367ca6483
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25867235"
---
# <a name="jscript-ado-programming"></a><span data-ttu-id="d8c41-102">JScript ADO 编程</span><span class="sxs-lookup"><span data-stu-id="d8c41-102">JScript ADO Programming</span></span>


<span data-ttu-id="d8c41-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="d8c41-103">**Applies to**: Access 2013, Office 2013</span></span>


## <a name="creating-an-ado-project"></a><span data-ttu-id="d8c41-104">创建 ADO 项目</span><span class="sxs-lookup"><span data-stu-id="d8c41-104">Creating an ADO Project</span></span>

<span data-ttu-id="d8c41-p101">Microsoft JScript 不支持类型库，所以不需要在项目中引用 ADO。因此，不支持命令行完成等关联功能。而且，默认情况下，JScript 中没有定义 ADO 枚举常量。</span><span class="sxs-lookup"><span data-stu-id="d8c41-p101">Microsoft JScript does not support type libraries, so you do not need to reference ADO in your project. Consequently, no associated features such as command line completion are supported. Also, by default, ADO enumerated constants are not defined in JScript.</span></span>

<span data-ttu-id="d8c41-108">但是，ADO 提供了两个包含文件，其中包含要用于 JScript 的以下定义：</span><span class="sxs-lookup"><span data-stu-id="d8c41-108">However, ADO provides you with two include files containing the following definitions to be used with JScript:</span></span>

- <span data-ttu-id="d8c41-109">对于服务器端脚本，请使用 Adojavas.inc，该文件安装中的 c:\\Program Files\\Common Files\\系统\\ado\\默认情况下的文件夹。</span><span class="sxs-lookup"><span data-stu-id="d8c41-109">For server-side scripting use Adojavas.inc, which is installed in the c:\\Program Files\\Common Files\\System\\ado\\ folder by default.</span></span>

- <span data-ttu-id="d8c41-110">客户端脚本，请使用 Adcjavas.inc，其安装在 c:\\Program Files\\Common Files\\系统\\msdac\\默认情况下的文件夹。</span><span class="sxs-lookup"><span data-stu-id="d8c41-110">For client-side scripting use Adcjavas.inc, which is installed in the c:\\Program Files\\Common Files\\System\\msdac\\ folder by default.</span></span>

<span data-ttu-id="d8c41-111">您可以复制和粘贴 ASP 页中，从这些文件常量定义或者，如果执行服务器端脚本，将 Adojavas.inc 文件复制到您的网站上的文件夹和引用从 ASP 页如下所示：</span><span class="sxs-lookup"><span data-stu-id="d8c41-111">You can either copy and paste constant definitions from these files into your ASP pages, or, if you are doing server-side scripting, copy Adojavas.inc file to a folder on your website and references it from your ASP page like this:</span></span>

```javascript  
 
<!--#include File="adojavas.inc"--> 
```

## <a name="creating-ado-objects-in-jscript"></a><span data-ttu-id="d8c41-112">在 JScript 中创建 ADO 对象</span><span class="sxs-lookup"><span data-stu-id="d8c41-112">Creating ADO Objects in JScript</span></span>

<span data-ttu-id="d8c41-113">必须改为使用 **CreateObject** 函数调用：</span><span class="sxs-lookup"><span data-stu-id="d8c41-113">You must instead use the **CreateObject** function call:</span></span>

```javascript  
 
var Rs1; 
Rs1 = Server.CreateObject("ADODB.Recordset"); 
```

## <a name="jscript-example"></a><span data-ttu-id="d8c41-114">JScript 示例</span><span class="sxs-lookup"><span data-stu-id="d8c41-114">JScript Example</span></span>

<span data-ttu-id="d8c41-115">以下代码是在一个用于打开 **Recordset** 对象的 Active Server Page (ASP) 文件中进行 JScript 服务器端编程的一般示例：</span><span class="sxs-lookup"><span data-stu-id="d8c41-115">The following code is a generic example of JScript server-side programming in an Active Server Page (ASP) file that opens a **Recordset** object:</span></span>

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

