---
title: 步骤 2：获取数据
TOCTitle: 'Step 2: Get the Data'
ms:assetid: e6be8801-6e57-d287-e8d2-348963706edc
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250171(v=office.15)
ms:contentKeyID: 48548387
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 5e4b93eb3e3679fdbc235f4406b0480ad2597d25
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25465786"
---
# <a name="step-2-get-the-data"></a><span data-ttu-id="ee097-102">步骤 2：获取数据</span><span class="sxs-lookup"><span data-stu-id="ee097-102">Step 2: Get the Data</span></span>


<span data-ttu-id="ee097-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="ee097-103">**Applies to**: Access 2013 | Office 2013</span></span>

## <a name="step-2-get-the-data"></a><span data-ttu-id="ee097-104">步骤 2：获取数据</span><span class="sxs-lookup"><span data-stu-id="ee097-104">Step 2: Get the Data</span></span>

<span data-ttu-id="ee097-p101">在该步骤中，您将编写用来打开 ADO **Recordset** 的代码，并准备将其发送到客户端。用文本编辑器（如 Windows 记事本）打开 XMLResponse.asp 文件，并插入以下代码：</span><span class="sxs-lookup"><span data-stu-id="ee097-p101">In this step, you will write the code to open an ADO **Recordset** and prepare to send it to the client. Open the file XMLResponse.asp with a text editor, such as Windows Notepad, and insert the following code:</span></span>

```vb 
 
<%@ language="VBScript" %> 
 
<!-- #include file='adovbs.inc' --> 
 
<% 
  Dim strSQL, strCon 
  Dim adoRec  
  Dim adoCon  
  Dim xmlDoc  
 
  ' You will need to change "slqServer" below to the name of the SQL  
  ' server machine to which you want to connect. 
  strCon = "Provider=sqloledb;Data Source=sqlServer;Initial Catalog=Pubs;Integrated Security=SSPI;" 
  Set adoCon = server.createObject("ADODB.Connection") 
  adoCon.Open strCon 
 
  strSQL = "SELECT Title, Price FROM Titles ORDER BY Price" 
  Set adoRec = Server.CreateObject("ADODB.Recordset") 
  adoRec.Open strSQL, adoCon, adOpenStatic, adLockOptimistic, adCmdText 
```

<span data-ttu-id="ee097-107">请务必中 strCon 参数中的数据源参数值更改为 Microsoft SQL Server 计算机的名称。</span><span class="sxs-lookup"><span data-stu-id="ee097-107">Be sure to change the value of the Data Source parameter in parameter in strCon to the name of your Microsoft SQL Server computer.</span></span>

<span data-ttu-id="ee097-108">使该文件保持打开状态并转至下一步。</span><span class="sxs-lookup"><span data-stu-id="ee097-108">Keep the file open and go on to the next step.</span></span>

<span data-ttu-id="ee097-109">**下一步**[步骤 3： 发送数据](step-3-send-the-data.md)</span><span class="sxs-lookup"><span data-stu-id="ee097-109">**Next** [Step 3: Send the Data](step-3-send-the-data.md)</span></span>

