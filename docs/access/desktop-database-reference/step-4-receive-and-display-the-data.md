---
title: 步骤 4：接收和显示数据
TOCTitle: 'Step 4: Receive and Display the Data'
ms:assetid: a27cc1d8-0ee0-95a5-ad70-88c454c10485
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249749(v=office.15)
ms:contentKeyID: 48546764
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: d2a447b68b8c0eeb18d18050ba8dbbb6f09786ab
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468222"
---
# <a name="step-4-receive-and-display-the-data"></a><span data-ttu-id="d987c-102">步骤 4：接收和显示数据</span><span class="sxs-lookup"><span data-stu-id="d987c-102">Step 4: Receive and Display the Data</span></span>


<span data-ttu-id="d987c-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="d987c-103">**Applies to**: Access 2013 | Office 2013</span></span>

## <a name="step-4-receive-and-display-the-data"></a><span data-ttu-id="d987c-104">步骤 4：接收和显示数据</span><span class="sxs-lookup"><span data-stu-id="d987c-104">Step 4: Receive and Display the Data</span></span>

<span data-ttu-id="d987c-p101">在该步骤中，您将用嵌入的 [RDS.DataControl](datacontrol-object-rds.md) 对象（该对象指向 XMLResponse.asp 文件）创建一个 HTML 文件，以获取 **Recordset** 。用文本编辑器（如 Windows 记事本）打开 default.htm，并添加以下代码。将该 URL 中的"sqlserver"替换为您的服务器计算机的名称。</span><span class="sxs-lookup"><span data-stu-id="d987c-p101">In this step you will create an HTML file with an embedded [RDS.DataControl](datacontrol-object-rds.md) object that points at the XMLResponse.asp file to get the **Recordset**. Open default.htm with a text editor, such as Windows Notepad, and add the code below. Replace "sqlserver" in the URL with the name of your server computer.</span></span>

```html 
 
<HTML> 
<HEAD><TITLE>ADO Recordset Persistence Sample</TITLE></HEAD> 
<BODY> 
 
<TABLE DATASRC="#RDC1" border="1"> 
  <TR> 
<TD><SPAN DATAFLD="title"></SPAN></TD> 
<TD><SPAN DATAFLD="price"></SPAN></TD> 
  </TR> 
</TABLE> 

<OBJECT CLASSID="clsid:BD96C556-65A3-11D0-983A-00C04FC29E33" ID="RDC1"> 
   <PARAM NAME="URL" VALUE="XMLResponse.asp"> 
</OBJECT> 
 
</BODY> 
</HTML> 
```

<span data-ttu-id="d987c-108">关闭 default.htm 文件并将其保存到 XMLResponse.asp 所在的同一文件夹中。</span><span class="sxs-lookup"><span data-stu-id="d987c-108">Close the default.htm file and save it to the same folder where you saved XMLResponse.asp.</span></span> <span data-ttu-id="d987c-109">使用 Internet Explorer 4.0 或更高版本，打开 URL https://*sqlserver*/XMLPersist/default.htm，并观察结果。</span><span class="sxs-lookup"><span data-stu-id="d987c-109">Using Internet Explorer 4.0 or later, open the URL https://*sqlserver*/XMLPersist/default.htm and observe the results.</span></span> <span data-ttu-id="d987c-110">数据将显示在绑定的 DHTML 表中。</span><span class="sxs-lookup"><span data-stu-id="d987c-110">The data is displayed in a bound DHTML table.</span></span> <span data-ttu-id="d987c-111">立即打开 URL https://*sqlserver*/XMLPersist/XMLResponse.asp，并观察结果。</span><span class="sxs-lookup"><span data-stu-id="d987c-111">Now open the URL https://*sqlserver*/XMLPersist/XMLResponse.asp and observe the results.</span></span> <span data-ttu-id="d987c-112">此时将显示 XML。</span><span class="sxs-lookup"><span data-stu-id="d987c-112">The XML is displayed.</span></span>

