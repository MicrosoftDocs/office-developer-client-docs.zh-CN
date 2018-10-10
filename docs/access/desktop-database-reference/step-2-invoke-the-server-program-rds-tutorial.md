---
title: 步骤 2：调用服务器程序（RDS 教程）
TOCTitle: 'Step 2: Invoke the Server Program (RDS Tutorial)'
ms:assetid: 45429faa-c1e2-d448-a5b4-b2d77cb94377
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249211(v=office.15)
ms:contentKeyID: 48544549
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: edd9f8561e6275e3b8eb33e86be745345d7c797a
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468557"
---
# <a name="step-2-invoke-the-server-program-rds-tutorial"></a>步骤 2：调用服务器程序（RDS 教程）


**适用于**： Access 2013 |Office 2013

当调用客户端*代理*上的某种方法时，服务器上的实际程序将执行该方法。在该步骤中，将在服务器上执行查询。

**部分 A**如果您没有在本教程使用[RDSServer.DataFactory](datafactory-object-rdsserver.md) ，最方便的方式执行此步骤是使用[rds.DataControl](datacontrol-object-rds.md)对象。 **RDS.DataControl** 将该步骤与上一步（创建代理）合并，用于发出查询。

设置 **RDS.DataControl** 对象的 [Server](server-property-rds.md) 属性以标识服务器程序应当被实例化的位置；设置 [Connect](connect-property-rds.md) 属性以指定用来访问数据源的连接字符串；设置 [SQL](https://msdn.microsoft.com/library/jj248989\(v=office.15\)) 属性以指定查询命令文本。然后发出 [Refresh](refresh-method-rds.md) 方法使服务器程序与数据源相连接，检索该查询所指定的行，并将 **Recordset** 对象返回到客户端。

本教程不使用 **RDS.DataControl** ，但在这里给出了它的形式：

```vb 
 
Sub RDSTutorial2A() 
 Dim DC as New RDS.DataControl 
 DC.Server = "https://yourServer" 
 DC.Connect = "DSN=Pubs" 
 DC.SQL = "SELECT * FROM Authors" 
 DC.Refresh 
... 
```

本教程不使用 ADO 对象调用 RDS，但在这里给出了它的形式：

```vb 
 
Dim rs as New ADODB.Recordset 
rs.Open "SELECT * FROM Authors","Provider=MS Remote;Data Source=Pubs;" & _ 
"Remote Server=https://yourServer;Remote Provider=SQLOLEDB;" 
```

**部分 B**执行此步骤的常规方法是调用**RDSServer.DataFactory**对象的[Query](query-method-rds.md)方法。 该方法使用一个连接字符串（用来连接到数据源）和一个命令文本（用来指定要从数据源中返回的行）。

本教程使用 **DataFactory** 对象的 **Query** 方法：

```vb 
 
Sub RDSTutorial2B() 
 Dim DS as New RDS.DataSpace 
 Dim DF 
 Dim RS as ADODB.Recordset 
 Set DF = DS.CreateObject("RDSServer.DataFactory", "https://yourServer") 
 Set RS = DF.Query ("DSN=Pubs", "SELECT * FROM Authors") 
... 
```

