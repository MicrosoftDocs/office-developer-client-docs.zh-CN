---
title: 步骤 3：发送数据
TOCTitle: 'Step 3: Send the Data'
ms:assetid: d22ffe59-179b-fd1a-1211-be1a0d76b02f
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250049(v=office.15)
ms:contentKeyID: 48547878
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 5af9b24ac7edb77ceb6dea9ceb5ae8e628fa5e3b
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25889705"
---
# <a name="step-3-send-the-data"></a>步骤 3：发送数据


**适用于**： Access 2013、 Office 2013

## <a name="step-3-send-the-data"></a>步骤 3：发送数据

现在您已经拥有一个 **Recordset** ，您将需要通过将它作为 XML 保存到 ASP **Response** 对象中来将其发送到客户端。请将以下代码添加到 XMLResponse.asp 的底部：

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

请注意，ASP**响应**对象的指定为**Recordset** [保存](save-method-ado.md)方法的目标。 **Save** 方法的目标可以是支持 **IStream** 接口的任何对象（如 ADO [Stream](stream-object-ado.md) 对象），也可以是包括要将 **Recordset** 保存到的完整路径的文件名。

在转至下一步之前请保存并关闭 XMLResponse.asp。 此外将 adovbs.inc 文件复制从 c:\\Program Files\\Common Files\\系统\\Ado 文件夹到了 XMLResponse.asp 文件的同一个文件夹。

### <a name="next-step"></a>后续步骤

[步骤 4： 接收数据](step-4-receive-and-display-the-data.md)

