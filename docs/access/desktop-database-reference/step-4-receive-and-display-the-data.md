---
title: 步骤 4：接收和显示数据
TOCTitle: 'Step 4: Receive and Display the Data'
ms:assetid: a27cc1d8-0ee0-95a5-ad70-88c454c10485
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249749(v=office.15)
ms:contentKeyID: 48546764
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 03a089e600799e1ac5fa85886ee6a16e1dd86026
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25869076"
---
# <a name="step-4-receive-and-display-the-data"></a><span data-ttu-id="61423-102">步骤 4：接收和显示数据</span><span class="sxs-lookup"><span data-stu-id="61423-102">Step 4: Receive and Display the Data</span></span>


<span data-ttu-id="61423-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="61423-103">**Applies to**: Access 2013, Office 2013</span></span>

## <a name="step-4-receive-and-display-the-data"></a><span data-ttu-id="61423-104">步骤 4：接收并显示数据</span><span class="sxs-lookup"><span data-stu-id="61423-104">Step 4: Receive and Display the Data</span></span>

<span data-ttu-id="61423-p101">在该步骤中，您将用嵌入的 [RDS.DataControl](datacontrol-object-rds.md) 对象（该对象指向 XMLResponse.asp 文件）创建一个 HTML 文件，以获取 **Recordset** 。用文本编辑器（如 Windows 记事本）打开 default.htm，并添加以下代码。将该 URL 中的"sqlserver"替换为您的服务器计算机的名称。</span><span class="sxs-lookup"><span data-stu-id="61423-p101">In this step you will create an HTML file with an embedded [RDS.DataControl](datacontrol-object-rds.md) object that points at the XMLResponse.asp file to get the **Recordset**. Open default.htm with a text editor, such as Windows Notepad, and add the code below. Replace "sqlserver" in the URL with the name of your server computer.</span></span>

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

<span data-ttu-id="61423-108">关闭 default.htm 文件并将其保存到 XMLResponse.asp 所在的同一文件夹中。</span><span class="sxs-lookup"><span data-stu-id="61423-108">Close the default.htm file and save it to the same folder where you saved XMLResponse.asp.</span></span> <span data-ttu-id="61423-109">使用 Internet Explorer 4.0 或更高版本，打开 URL https://*sqlserver*/XMLPersist/default.htm，并观察结果。</span><span class="sxs-lookup"><span data-stu-id="61423-109">Using Internet Explorer 4.0 or later, open the URL https://*sqlserver*/XMLPersist/default.htm and observe the results.</span></span> <span data-ttu-id="61423-110">数据将显示在绑定的 DHTML 表中。</span><span class="sxs-lookup"><span data-stu-id="61423-110">The data is displayed in a bound DHTML table.</span></span> <span data-ttu-id="61423-111">立即打开 URL https://*sqlserver*/XMLPersist/XMLResponse.asp，并观察结果。</span><span class="sxs-lookup"><span data-stu-id="61423-111">Now open the URL https://*sqlserver*/XMLPersist/XMLResponse.asp and observe the results.</span></span> <span data-ttu-id="61423-112">此时将显示 XML。</span><span class="sxs-lookup"><span data-stu-id="61423-112">The XML is displayed.</span></span>

