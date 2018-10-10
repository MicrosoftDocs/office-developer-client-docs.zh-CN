---
title: 步骤 6：将更改发送到服务器（RDS 教程）
TOCTitle: 'Step 6: Changes are Sent to the Server (RDS Tutorial)'
ms:assetid: c5915d89-77b6-bb3f-a962-49378160751f
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249965(v=office.15)
ms:contentKeyID: 48547611
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: d26ca621ba7102dc0f9c6219ba3a16b28138770f
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467002"
---
# <a name="step-6-changes-are-sent-to-the-server-rds-tutorial"></a><span data-ttu-id="e97df-102">步骤 6：将更改发送到服务器（RDS 教程）</span><span class="sxs-lookup"><span data-stu-id="e97df-102">Step 6: Changes are Sent to the Server (RDS Tutorial)</span></span>


<span data-ttu-id="e97df-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="e97df-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="e97df-104">如果对 **Recordset** 对象进行编辑，则可以将任何更改（即，对行进行地添加、更改或删除）发回到服务器。</span><span class="sxs-lookup"><span data-stu-id="e97df-104">If the **Recordset** object is edited, any changes (that is, rows that are added, changed, or deleted) can be sent back to the server.</span></span>


> [!NOTE]
> <P><span data-ttu-id="e97df-p101">RDS 的默认行为可通过 ADO 对象和 Microsoft OLE DB Remoting Provider 隐式调用。查询可返回 <STRONG>Recordset</STRONG>，经过编辑的 <STRONG>Recordset</STRONG> 则可以更新数据源。本教程不通过 ADO 对象调用 RDS，但在这里给出了它的形式：</span><span class="sxs-lookup"><span data-stu-id="e97df-p101">The default behavior of RDS can be invoked implicitly with ADO objects and the Microsoft OLE DB Remoting Provider. Queries can return <STRONG>Recordset</STRONG>s, and edited <STRONG>Recordset</STRONG>s can update the data source. This tutorial does not invoke RDS with ADO objects, but this is how it would look if it did:</span></span></P>



```vb 
 
Dim rs as New ADODB.Recordset 
rs.Open "SELECT * FROM Authors","Provider=MS Remote;Data Source=Pubs;" & _ 
 "Remote Server=https://yourServer;Remote Provider=SQLOLEDB;" 
... ' Edit the Recordset. 
rs.UpdateBatch ' The equivalent of SubmitChanges. 
... 
```

<span data-ttu-id="e97df-108">**部分 A**</span><span class="sxs-lookup"><span data-stu-id="e97df-108">**Part A**</span></span> 

<span data-ttu-id="e97df-109">假设这种情况下，仅使用[rds.DataControl](datacontrol-object-rds.md)和**Recordset**对象是否立即与**rds.DataControl**。</span><span class="sxs-lookup"><span data-stu-id="e97df-109">Assume for this case that you have only used the [RDS.DataControl](datacontrol-object-rds.md) and that a **Recordset** object is now associated with the **RDS.DataControl**.</span></span> <span data-ttu-id="e97df-110">如果 [Server](submitchanges-method-rds.md) 和 **Connect** 属性已设置， [SubmitChanges](server-property-rds.md) 方法将用对 [Recordset](connect-property-rds.md) 对象进行的任何更改来更新数据源。</span><span class="sxs-lookup"><span data-stu-id="e97df-110">The [SubmitChanges](submitchanges-method-rds.md) method updates the data source with any changes to the **Recordset** object if the [Server](server-property-rds.md) and [Connect](connect-property-rds.md) properties are still set.</span></span>

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

<span data-ttu-id="e97df-111">**部分 B**</span><span class="sxs-lookup"><span data-stu-id="e97df-111">**Part B**</span></span> 

<span data-ttu-id="e97df-112">此外，您无法使用[RDSServer.DataFactory](datafactory-object-rdsserver.md)对象，指定连接和**Recordset**对象更新服务器。</span><span class="sxs-lookup"><span data-stu-id="e97df-112">Alternatively, you could update the server with the [RDSServer.DataFactory](datafactory-object-rdsserver.md) object, specifying a connection and a **Recordset** object.</span></span>

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

<span data-ttu-id="e97df-113">**本教程到此结束。**</span><span class="sxs-lookup"><span data-stu-id="e97df-113">**This is the end of the tutorial.**</span></span>

