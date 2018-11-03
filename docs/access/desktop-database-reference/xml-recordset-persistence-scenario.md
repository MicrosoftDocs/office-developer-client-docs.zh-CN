---
title: XML Recordset 持久化方案
TOCTitle: XML Recordset persistence scenario
ms:assetid: 08f464da-10ba-b649-7571-766a40da2e04
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248825(v=office.15)
ms:contentKeyID: 48543107
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 4840b59f8f145b17b45a9732443d3f844b336868
ms.sourcegitcommit: 558d09fad81f8d80b5ad0edd21934fc09c098f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25945486"
---
# <a name="xml-recordset-persistence-scenario"></a>XML Recordset 持久化方案

**适用于**： Access 2013、 Office 2013

在该方案中，您将创建一个 Active Server Pages (ASP) 应用程序，该应用程序将 **Recordset** 对象的内容直接保存到 ASP **Response** 对象中。

> [!NOTE]
> [!注释] 该方案要求您的服务器上装有 Internet Information Server 5.0 (IIS) 或更高版本。

返回的 **Recordset** 使用 [RDS.DataControl](datacontrol-object-rds.md) 显示在 Internet Explorer 中。

下列步骤是创建该方案所必需的步骤：

1.  设置应用程序。
2.  获取数据。
3.  发送数据。
4.  接收和显示数据。

## <a name="step-1-set-up-the-application"></a>步骤 1： 设置应用程序

1. 创建名为脚本权限**XMLPersist**的 IIS 虚拟目录。 

2. 在向其虚拟目录点，一个命名的**XMLResponse.asp**，另一个名为**Default.htm**的文件夹中创建两个新的文本文件。


## <a name="step-2-get-the-data"></a>步骤 2： 获取数据

在该步骤中，您将编写用来打开 ADO **Recordset** 的代码，并准备将其发送到客户端。 

1. 用文本编辑器（如 Windows 记事本）打开 XMLResponse.asp 文件，并插入以下代码：

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

2. 请务必 strCon 中的数据源参数值更改为 Microsoft SQL Server 计算机的名称。

3. 使该文件保持打开状态并转至下一步。

## <a name="step-3-send-the-data"></a>步骤 3： 发送数据

现在您已经拥有一个 **Recordset** ，您将需要通过将它作为 XML 保存到 ASP **Response** 对象中来将其发送到客户端。 

1. 请将以下代码添加到 XMLResponse.asp 的底部：

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

2. 在转至下一步之前请保存并关闭 XMLResponse.asp。 此外将 adovbs.inc 文件复制从 c:\\Program Files\\Common Files\\系统\\Ado 文件夹到了 XMLResponse.asp 文件的同一个文件夹。

## <a name="step-4-receive-and-display-the-data"></a>步骤 4： 接收和显示数据

在此步骤中，将 HTML 文件创建与嵌入[rds.DataControl](datacontrol-object-rds.md)对象的 points XMLResponse.asp 文件以获取**记录集**。 

1. 使用 Windows 记事本等文本编辑器，打开 default.htm 并添加以下代码。 将该 URL 中的"sqlserver"替换为您的服务器计算机的名称。

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

2. 关闭 default.htm 文件并将其保存到 XMLResponse.asp 所在的同一文件夹中。 

3. 使用 Internet Explorer 4.0 或更高版本，打开 URL`https://<sqlserver>/XMLPersist/default.htm`并观察结果。 数据将显示在绑定的 DHTML 表中。 

4. 现在打开 URL`https://<sqlserver>/XMLPersist/XMLResponse.asp`并观察结果。 此时将显示 XML。




