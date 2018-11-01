---
title: 步骤 2：调用服务器程序（RDS 教程）
TOCTitle: 'Step 2: Invoke the Server Program (RDS Tutorial)'
ms:assetid: 45429faa-c1e2-d448-a5b4-b2d77cb94377
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249211(v=office.15)
ms:contentKeyID: 48544549
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 53ad3306bf9e175566f0a3d02b1454872264d4b6
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25885477"
---
# <a name="step-2-invoke-the-server-program-rds-tutorial"></a><span data-ttu-id="bf3bd-102">步骤 2：调用服务器程序（RDS 教程）</span><span class="sxs-lookup"><span data-stu-id="bf3bd-102">Step 2: Invoke the Server Program (RDS Tutorial)</span></span>


<span data-ttu-id="bf3bd-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="bf3bd-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="bf3bd-p101">当调用客户端*代理*上的某种方法时，服务器上的实际程序将执行该方法。在该步骤中，将在服务器上执行查询。</span><span class="sxs-lookup"><span data-stu-id="bf3bd-p101">When you invoke a method on the client *proxy*, the actual program on the server executes the method. In this step, you'll execute a query on the server.</span></span>

<span data-ttu-id="bf3bd-106">**部分 A**如果您没有在本教程使用[RDSServer.DataFactory](datafactory-object-rdsserver.md) ，最方便的方式执行此步骤是使用[rds.DataControl](datacontrol-object-rds.md)对象。</span><span class="sxs-lookup"><span data-stu-id="bf3bd-106">**Part A**If you weren't using [RDSServer.DataFactory](datafactory-object-rdsserver.md) in this tutorial, the most convenient way to perform this step would be to use the [RDS.DataControl](datacontrol-object-rds.md) object.</span></span> <span data-ttu-id="bf3bd-107">**RDS.DataControl** 将该步骤与上一步（创建代理）合并，用于发出查询。</span><span class="sxs-lookup"><span data-stu-id="bf3bd-107">The **RDS.DataControl** combines the previous step of creating a proxy, with this step, issuing the query.</span></span>

<span data-ttu-id="bf3bd-p103">设置 **RDS.DataControl** 对象的 [Server](server-property-rds.md) 属性以标识服务器程序应当被实例化的位置；设置 [Connect](connect-property-rds.md) 属性以指定用来访问数据源的连接字符串；设置 [SQL](https://msdn.microsoft.com/library/jj248989\(v=office.15\)) 属性以指定查询命令文本。然后发出 [Refresh](refresh-method-rds.md) 方法使服务器程序与数据源相连接，检索该查询所指定的行，并将 **Recordset** 对象返回到客户端。</span><span class="sxs-lookup"><span data-stu-id="bf3bd-p103">Set the **RDS.DataControl** object [Server](server-property-rds.md) property to identify where the server program should be instantiated; the [Connect](connect-property-rds.md) property to specify the connect string to access the data source; and the [SQL](https://msdn.microsoft.com/library/jj248989\(v=office.15\)) property to specify the query command text. Then issue the [Refresh](refresh-method-rds.md) method to cause the server program to connect to the data source, retrieve rows specified by the query, and return a **Recordset** object to the client.</span></span>

<span data-ttu-id="bf3bd-110">本教程不使用 **RDS.DataControl** ，但在这里给出了它的形式：</span><span class="sxs-lookup"><span data-stu-id="bf3bd-110">This tutorial does not use the **RDS.DataControl**, but this is how it would look if it did:</span></span>

```vb 
 
Sub RDSTutorial2A() 
 Dim DC as New RDS.DataControl 
 DC.Server = "https://yourServer" 
 DC.Connect = "DSN=Pubs" 
 DC.SQL = "SELECT * FROM Authors" 
 DC.Refresh 
... 
```

<span data-ttu-id="bf3bd-111">本教程不使用 ADO 对象调用 RDS，但在这里给出了它的形式：</span><span class="sxs-lookup"><span data-stu-id="bf3bd-111">Nor does the tutorial invoke RDS with ADO objects, but this is how it would look if it did:</span></span>

```vb 
 
Dim rs as New ADODB.Recordset 
rs.Open "SELECT * FROM Authors","Provider=MS Remote;Data Source=Pubs;" & _ 
"Remote Server=https://yourServer;Remote Provider=SQLOLEDB;" 
```

<span data-ttu-id="bf3bd-112">**部分 B**执行此步骤的常规方法是调用**RDSServer.DataFactory**对象的[Query](query-method-rds.md)方法。</span><span class="sxs-lookup"><span data-stu-id="bf3bd-112">**Part B**The general method of performing this step is to invoke the **RDSServer.DataFactory** object [Query](query-method-rds.md) method.</span></span> <span data-ttu-id="bf3bd-113">该方法使用一个连接字符串（用来连接到数据源）和一个命令文本（用来指定要从数据源中返回的行）。</span><span class="sxs-lookup"><span data-stu-id="bf3bd-113">That method takes a connect string, which is used to connect to a data source, and a command text, which is used to specify the rows to be returned from the data source.</span></span>

<span data-ttu-id="bf3bd-114">本教程使用 **DataFactory** 对象的 **Query** 方法：</span><span class="sxs-lookup"><span data-stu-id="bf3bd-114">This tutorial uses the **DataFactory** object **Query** method:</span></span>

```vb 
 
Sub RDSTutorial2B() 
 Dim DS as New RDS.DataSpace 
 Dim DF 
 Dim RS as ADODB.Recordset 
 Set DF = DS.CreateObject("RDSServer.DataFactory", "https://yourServer") 
 Set RS = DF.Query ("DSN=Pubs", "SELECT * FROM Authors") 
... 
```

