---
title: 步骤 6：将更改发送到服务器（RDS 教程）
TOCTitle: 'Step 6: Changes are Sent to the Server (RDS Tutorial)'
ms:assetid: c5915d89-77b6-bb3f-a962-49378160751f
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249965(v=office.15)
ms:contentKeyID: 48547611
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: e125837b8f3d16e012d89374650182653f98a728
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25870413"
---
# <a name="step-6-changes-are-sent-to-the-server-rds-tutorial"></a>步骤 6：将更改发送到服务器（RDS 教程）


**适用于**： Access 2013、 Office 2013

如果对 **Recordset** 对象进行编辑，则可以将任何更改（即，对行进行地添加、更改或删除）发回到服务器。


> [!NOTE]
> <P>RDS 的默认行为可通过 ADO 对象和 Microsoft OLE DB Remoting Provider 隐式调用。查询可返回 <STRONG>Recordset</STRONG>，经过编辑的 <STRONG>Recordset</STRONG> 则可以更新数据源。本教程不通过 ADO 对象调用 RDS，但在这里给出了它的形式：</P>



```vb 
 
Dim rs as New ADODB.Recordset 
rs.Open "SELECT * FROM Authors","Provider=MS Remote;Data Source=Pubs;" & _ 
 "Remote Server=https://yourServer;Remote Provider=SQLOLEDB;" 
... ' Edit the Recordset. 
rs.UpdateBatch ' The equivalent of SubmitChanges. 
... 
```

**部分 A** 

假设这种情况下，仅使用[rds.DataControl](datacontrol-object-rds.md)和**Recordset**对象是否立即与**rds.DataControl**。 如果 [Server](submitchanges-method-rds.md) 和 **Connect** 属性已设置， [SubmitChanges](server-property-rds.md) 方法将用对 [Recordset](connect-property-rds.md) 对象进行的任何更改来更新数据源。

```vb 
 
Sub RDSTutorial6A() 
Dim DC as New RDS.DataControl 
Dim RS as ADODB.Recordset 
DC.Server = "https://yourServer" 
DC.Connect = "DSN=Pubs" 
DC.SQL = "SELECT * FROM Authors" 
DC.Refresh 
... 
Set RS = DC.Recordset 
 ' Edit the Recordset. 
... 
DC.SubmitChanges 
... 
```

**部分 B** 

此外，您无法使用[RDSServer.DataFactory](datafactory-object-rdsserver.md)对象，指定连接和**Recordset**对象更新服务器。

```vb 
 
Sub RDSTutorial6B() 
Dim DS As New RDS.DataSpace 
Dim RS As ADODB.Recordset 
Dim DC As New RDS.DataControl 
Dim DF As Object 
Dim blnStatus As Boolean 
Set DF = DS.CreateObject("RDSServer.DataFactory", "https://yourServer") 
Set RS = DF.Query ("DSN=Pubs", "SELECT * FROM Authors") 
DC.SourceRecordset = RS ' Visual controls can now bind to DC. 
 ' Edit the Recordset. 
blnStatus = DF.SubmitChanges "DSN=Pubs", RS 
End Sub 
```

**本教程到此结束。**

