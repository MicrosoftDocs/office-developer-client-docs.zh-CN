---
title: 步骤 3：发送数据
TOCTitle: 'Step 3: Send the Data'
ms:assetid: d22ffe59-179b-fd1a-1211-be1a0d76b02f
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250049(v=office.15)
ms:contentKeyID: 48547878
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: ed3e6bfd6fe3b6727055eb264b1261b13d7a5a0b
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25465736"
---
# <a name="step-3-send-the-data"></a><span data-ttu-id="7996b-102">步骤 3：发送数据</span><span class="sxs-lookup"><span data-stu-id="7996b-102">Step 3: Send the Data</span></span>


<span data-ttu-id="7996b-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="7996b-103">**Applies to**: Access 2013 | Office 2013</span></span>

## <a name="step-3-send-the-data"></a><span data-ttu-id="7996b-104">步骤 3：发送数据</span><span class="sxs-lookup"><span data-stu-id="7996b-104">Step 3: Send the Data</span></span>

<span data-ttu-id="7996b-p101">现在您已经拥有一个 **Recordset** ，您将需要通过将它作为 XML 保存到 ASP **Response** 对象中来将其发送到客户端。请将以下代码添加到 XMLResponse.asp 的底部：</span><span class="sxs-lookup"><span data-stu-id="7996b-p101">Now that you have a **Recordset**, you need to send it to the client by saving it as XML to the ASP **Response** object. Add the following code to the bottom of XMLResponse.asp:</span></span>

```vb 
 
  Response.ContentType = "text/xml" 
  Response.Expires = 0 
  Response.Buffer = False 
 
 
  Response.Write "<?xml version='1.0'?>" & vbNewLine 
  adoRec.save Response, adPersistXML 
  adoRec.Close 
  Set adoRec=Nothing 
%> 
```

<span data-ttu-id="7996b-107">请注意，ASP**响应**对象的指定为**Recordset** [保存](save-method-ado.md)方法的目标。</span><span class="sxs-lookup"><span data-stu-id="7996b-107">Notice that the ASP **Response** object is specified as the destination for the **Recordset** [Save](save-method-ado.md) method.</span></span> <span data-ttu-id="7996b-108">**Save** 方法的目标可以是支持 **IStream** 接口的任何对象（如 ADO [Stream](stream-object-ado.md) 对象），也可以是包括要将 **Recordset** 保存到的完整路径的文件名。</span><span class="sxs-lookup"><span data-stu-id="7996b-108">The destination of the **Save** method can be any object that supports the **IStream** interface, such as an ADO [Stream](stream-object-ado.md) object, or a file name that includes the complete path to which the **Recordset** is to be saved.</span></span>

<span data-ttu-id="7996b-109">在转至下一步之前请保存并关闭 XMLResponse.asp。</span><span class="sxs-lookup"><span data-stu-id="7996b-109">Save and close XMLResponse.asp before going to the next step.</span></span> <span data-ttu-id="7996b-110">此外将 adovbs.inc 文件复制从 c:\\Program Files\\Common Files\\系统\\Ado 文件夹到了 XMLResponse.asp 文件的同一个文件夹。</span><span class="sxs-lookup"><span data-stu-id="7996b-110">Also copy the adovbs.inc file from C:\\Program Files\\Common Files\\System\\Ado folder to the same folder where you have the XMLResponse.asp file.</span></span>

<span data-ttu-id="7996b-111">**下一步**[步骤 4： 接收数据](step-4-receive-and-display-the-data.md)</span><span class="sxs-lookup"><span data-stu-id="7996b-111">**Next** [Step 4: Receive the Data](step-4-receive-and-display-the-data.md)</span></span>

