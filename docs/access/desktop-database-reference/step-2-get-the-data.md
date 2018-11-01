---
title: 步骤 2：获取数据
TOCTitle: 'Step 2: Get the Data'
ms:assetid: e6be8801-6e57-d287-e8d2-348963706edc
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250171(v=office.15)
ms:contentKeyID: 48548387
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: eb206d003f0f5dc6714f00c54368e493856eed1f
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25872247"
---
# <a name="step-2-get-the-data"></a>步骤 2：获取数据


**适用于**： Access 2013、 Office 2013

## <a name="step-2-get-the-data"></a>步骤 2：获取数据

在该步骤中，您将编写用来打开 ADO **Recordset** 的代码，并准备将其发送到客户端。用文本编辑器（如 Windows 记事本）打开 XMLResponse.asp 文件，并插入以下代码：

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

请务必中 strCon 参数中的数据源参数值更改为 Microsoft SQL Server 计算机的名称。

使该文件保持打开状态并转至下一步。

### <a name="next-step"></a>后续步骤

[步骤 3：发送数据](step-3-send-the-data.md)

