---
title: 第 12 章： 远程数据服务 (RDS) 教程
TOCTitle: 'Chapter 12: RDS tutorial'
ms:assetid: fa44a5e8-e4df-dfdd-d7a1-a870ec3cabdd
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250277(v=office.15)
ms:contentKeyID: 48548837
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: fb29fd070a693b608cede1d21329b3749c18e852
ms.sourcegitcommit: 007141520d6479860f452371532f9267f33eb260
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/06/2018
ms.locfileid: "25999499"
---
# <a name="chapter-12-remote-data-service-rds-tutorial"></a><span data-ttu-id="0b8a1-102">第 12 章： 远程数据服务 (RDS) 教程</span><span class="sxs-lookup"><span data-stu-id="0b8a1-102">Chapter 12: Remote Data Service (RDS) tutorial</span></span>

<span data-ttu-id="0b8a1-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="0b8a1-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="0b8a1-104">本教程演示如何使用 RDS 编程模型查询和更新数据源</span><span class="sxs-lookup"><span data-stu-id="0b8a1-104">This tutorial illustrates using the RDS programming model to query and update a data source.</span></span> <span data-ttu-id="0b8a1-105">首先，它介绍完成此任务所需的步骤。</span><span class="sxs-lookup"><span data-stu-id="0b8a1-105">First, it describes the steps necessary to accomplish this task.</span></span> <span data-ttu-id="0b8a1-106">然后，可在 Microsoft Visual Basic Scripting Edition 和 Microsoft Visual J + + 中，其中 ADO for Windows Foundation Classes (ADO/WFC) 重复教程。</span><span class="sxs-lookup"><span data-stu-id="0b8a1-106">Then the tutorial is repeated in Microsoft Visual Basic Scripting Edition and Microsoft Visual J++, featuring ADO for Windows Foundation Classes (ADO/WFC).</span></span>

<span data-ttu-id="0b8a1-107">本教程使用不同语言的代码，主要有以下两个原因：</span><span class="sxs-lookup"><span data-stu-id="0b8a1-107">This tutorial is coded in different languages for two reasons:</span></span>

- <span data-ttu-id="0b8a1-p102">假设 RDS 文档的读者使用 Visual Basic 编码。这使得文档方便了 Visual Basic 编程人员，但对于使用其他语言的编程人员则没有多少用处。</span><span class="sxs-lookup"><span data-stu-id="0b8a1-p102">The documentation for RDS assumes the reader codes in Visual Basic. This makes the documentation convenient for Visual Basic programmers, but less useful for programmers who use other languages.</span></span>

- <span data-ttu-id="0b8a1-110">如果您不太熟悉具体的 RDS 功能，但对于其他语言有所了解，那么可以通过在其他语言中寻求相同的功能来解决问题。</span><span class="sxs-lookup"><span data-stu-id="0b8a1-110">If you are uncertain about a particular RDS feature and you know a little of another language, you might be able to resolve your question by looking for the same feature expressed in another language.</span></span>

<span data-ttu-id="0b8a1-p103">本教程基于 RDS 编程模型，并对该编程模型的每个步骤分别进行讨论，另外，还使用 Visual Basic 代码段举例讲述每个步骤。</span><span class="sxs-lookup"><span data-stu-id="0b8a1-p103">This tutorial is based on the RDS programming model. It discusses each step of the programming model individually. In addition, it illustrates each step with a fragment of Visual Basic code.</span></span>

<span data-ttu-id="0b8a1-p104">代码示例使用其他语言重复演示，但是对其很少进行讨论。在采用给定编程语言的教程中，每个步骤都以编程模型和说明性教程中的相应步骤来标记。请使用步骤编号来引用说明性教程中的讨论。</span><span class="sxs-lookup"><span data-stu-id="0b8a1-p104">The code example is repeated in other languages with minimal discussion. Each step in a given programming language tutorial is marked with the corresponding step in the programming model and descriptive tutorial. Use the number of the step to refer to the discussion in the descriptive tutorial.</span></span>

<span data-ttu-id="0b8a1-p105">下面对 RDS 编程模型进行了说明。在使用本教程时可将其作为路线图。</span><span class="sxs-lookup"><span data-stu-id="0b8a1-p105">The RDS programming model is stated below. Use it as a roadmap as you proceed through the tutorial.</span></span>

### <a name="rds-programming-model-with-objects"></a><span data-ttu-id="0b8a1-119">RDS 编程模型与对象</span><span class="sxs-lookup"><span data-stu-id="0b8a1-119">RDS programming model with objects</span></span>

- <span data-ttu-id="0b8a1-120">指定要在服务器上调用的程序，并获取从客户端引用它的方法（代理）。</span><span class="sxs-lookup"><span data-stu-id="0b8a1-120">Specify the program to be invoked on the server, and obtain a way (proxy) to refer to it from the client.</span></span>

- <span data-ttu-id="0b8a1-p106">调用服务器程序，将参数传递给标识数据源和所发命令的服务器程序。</span><span class="sxs-lookup"><span data-stu-id="0b8a1-p106">Invoke the server program. Pass parameters to the server program that identifies the data source and the command to issue.</span></span>

- <span data-ttu-id="0b8a1-p107">服务器程序通常是通过使用 ADO 从数据源获取 [Recordset](recordset-object-ado.md) 对象。可以选择在服务器上处理 **Recordset** 对象。</span><span class="sxs-lookup"><span data-stu-id="0b8a1-p107">The server program obtains a [Recordset](recordset-object-ado.md) object from the data source, typically by using ADO. Optionally, the **Recordset** object is processed on the server.</span></span>

- <span data-ttu-id="0b8a1-125">服务器程序将最终的 **Recordset** 对象返回给客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="0b8a1-125">The server program returns the final **Recordset** object to the client application.</span></span>

- <span data-ttu-id="0b8a1-126">在客户端上，可以选择将 **Recordset** 对象置为便于可视控件使用的形式。</span><span class="sxs-lookup"><span data-stu-id="0b8a1-126">On the client, the **Recordset** object is optionally put into a form that can be easily used by visual controls.</span></span>

- <span data-ttu-id="0b8a1-127">将对于 **Recordset** 对象进行的更改发回到服务器并将其用于更新数据源。</span><span class="sxs-lookup"><span data-stu-id="0b8a1-127">Changes to the **Recordset** object are sent back to the server and used to update the data source.</span></span>

## <a name="step-1-specify-a-server-program"></a><span data-ttu-id="0b8a1-128">步骤 1： 指定服务器程序</span><span class="sxs-lookup"><span data-stu-id="0b8a1-128">Step 1: Specify a server program</span></span>

<span data-ttu-id="0b8a1-p108">在大多数情况下，使用 [RDS.DataSpace](dataspace-object-rds.md) 对象的 [CreateObject](createobject-method-rds.md) 方法指定默认服务器程序 [RDSServer.DataFactory](datafactory-object-rdsserver.md) 或自定义服务器程序（业务对象）。服务器程序在服务器上实例化，返回的是对服务器程序的引用（即*代理*）。</span><span class="sxs-lookup"><span data-stu-id="0b8a1-p108">In the most general case, use the [RDS.DataSpace](dataspace-object-rds.md) object [CreateObject](createobject-method-rds.md) method to specify the default server program, [RDSServer.DataFactory](datafactory-object-rdsserver.md), or your own custom server program (business object). A server program is instantiated on the server, and a reference to the server program, or *proxy*, is returned.</span></span>

<span data-ttu-id="0b8a1-131">本教程使用默认服务器程序：</span><span class="sxs-lookup"><span data-stu-id="0b8a1-131">This tutorial uses the default server program:</span></span>

```vb 
 
Sub RDSTutorial1() 
 Dim DS as New RDS.DataSpace 
 Dim DF as Object 
 Set DF = DS.CreateObject("RDSServer.DataFactory", "https://yourServer") 
... 
``` 

## <a name="step-2-invoke-the-server-program"></a><span data-ttu-id="0b8a1-132">步骤 2： 调用服务器程序</span><span class="sxs-lookup"><span data-stu-id="0b8a1-132">Step 2: Invoke the server program</span></span> 

<span data-ttu-id="0b8a1-p109">当调用客户端*代理*上的某种方法时，服务器上的实际程序将执行该方法。在该步骤中，将在服务器上执行查询。</span><span class="sxs-lookup"><span data-stu-id="0b8a1-p109">When you invoke a method on the client *proxy*, the actual program on the server executes the method. In this step, you'll execute a query on the server.</span></span>

### <a name="part-a"></a><span data-ttu-id="0b8a1-135">部分 A</span><span class="sxs-lookup"><span data-stu-id="0b8a1-135">Part A</span></span>

<span data-ttu-id="0b8a1-136">如果您没有在本教程使用[RDSServer.DataFactory](datafactory-object-rdsserver.md) ，最方便的方式执行此步骤是使用[rds.DataControl](datacontrol-object-rds.md)对象。</span><span class="sxs-lookup"><span data-stu-id="0b8a1-136">If you weren't using [RDSServer.DataFactory](datafactory-object-rdsserver.md) in this tutorial, the most convenient way to perform this step would be to use the [RDS.DataControl](datacontrol-object-rds.md) object.</span></span> <span data-ttu-id="0b8a1-137">**RDS.DataControl** 将该步骤与上一步（创建代理）合并，用于发出查询。</span><span class="sxs-lookup"><span data-stu-id="0b8a1-137">The **RDS.DataControl** combines the previous step of creating a proxy, with this step, issuing the query.</span></span>

1. <span data-ttu-id="0b8a1-138">设置**rds.DataControl**对象[服务器](server-property-rds.md)属性来确定应实例化服务器程序。</span><span class="sxs-lookup"><span data-stu-id="0b8a1-138">Set the **RDS.DataControl** object [Server](server-property-rds.md) property to identify where the server program should be instantiated.</span></span>

2. <span data-ttu-id="0b8a1-139">设置[Connect](connect-property-rds.md)属性来指定要访问数据源的连接字符串。</span><span class="sxs-lookup"><span data-stu-id="0b8a1-139">Set the [Connect](connect-property-rds.md) property to specify the connect string to access the data source.</span></span>

3. <span data-ttu-id="0b8a1-140">设置[SQL](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/sql-property-ado)属性指定的查询命令文本。</span><span class="sxs-lookup"><span data-stu-id="0b8a1-140">Set the [SQL](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/sql-property-ado) property to specify the query command text.</span></span> 

4. <span data-ttu-id="0b8a1-141">问题的[Refresh](refresh-method-rds.md)方法会导致服务器程序连接到数据源，检索指定的查询中的行，并返回到客户端**Recordset**对象。</span><span class="sxs-lookup"><span data-stu-id="0b8a1-141">Issue the [Refresh](refresh-method-rds.md) method to cause the server program to connect to the data source, retrieve rows specified by the query, and return a **Recordset** object to the client.</span></span>

<span data-ttu-id="0b8a1-142">本教程不使用 **RDS.DataControl** ，但在这里给出了它的形式：</span><span class="sxs-lookup"><span data-stu-id="0b8a1-142">This tutorial does not use the **RDS.DataControl**, but this is how it would look if it did:</span></span>

```vb 
 
Sub RDSTutorial2A() 
 Dim DC as New RDS.DataControl 
 DC.Server = "https://yourServer" 
 DC.Connect = "DSN=Pubs" 
 DC.SQL = "SELECT * FROM Authors" 
 DC.Refresh 
... 
```

<br/>

<span data-ttu-id="0b8a1-143">本教程不使用 ADO 对象调用 RDS，但在这里给出了它的形式：</span><span class="sxs-lookup"><span data-stu-id="0b8a1-143">Nor does the tutorial invoke RDS with ADO objects, but this is how it would look if it did:</span></span>

```vb 
 
Dim rs as New ADODB.Recordset 
rs.Open "SELECT * FROM Authors","Provider=MS Remote;Data Source=Pubs;" & _ 
"Remote Server=https://yourServer;Remote Provider=SQLOLEDB;" 
```

### <a name="part-b"></a><span data-ttu-id="0b8a1-144">部分 B</span><span class="sxs-lookup"><span data-stu-id="0b8a1-144">Part B</span></span>

<span data-ttu-id="0b8a1-145">执行此步骤的常规方法是调用**RDSServer.DataFactory**对象的[Query](query-method-rds.md)方法。</span><span class="sxs-lookup"><span data-stu-id="0b8a1-145">The general method of performing this step is to invoke the **RDSServer.DataFactory** object [Query](query-method-rds.md) method.</span></span> <span data-ttu-id="0b8a1-146">该方法使用一个连接字符串（用来连接到数据源）和一个命令文本（用来指定要从数据源中返回的行）。</span><span class="sxs-lookup"><span data-stu-id="0b8a1-146">That method takes a connect string, which is used to connect to a data source, and a command text, which is used to specify the rows to be returned from the data source.</span></span>

<span data-ttu-id="0b8a1-147">本教程使用 **DataFactory** 对象的 **Query** 方法：</span><span class="sxs-lookup"><span data-stu-id="0b8a1-147">This tutorial uses the **DataFactory** object **Query** method:</span></span>

```vb 
 
Sub RDSTutorial2B() 
 Dim DS as New RDS.DataSpace 
 Dim DF 
 Dim RS as ADODB.Recordset 
 Set DF = DS.CreateObject("RDSServer.DataFactory", "https://yourServer") 
 Set RS = DF.Query ("DSN=Pubs", "SELECT * FROM Authors") 
... 
```

## <a name="step-3-server-obtains-a-recordset"></a><span data-ttu-id="0b8a1-148">步骤 3： 服务器获取 Recordset</span><span class="sxs-lookup"><span data-stu-id="0b8a1-148">Step 3: Server obtains a Recordset</span></span> 

<span data-ttu-id="0b8a1-p112">服务器程序使用连接字符串和命令文本在数据源中查询所需的行。尽管也可以使用其他 Microsoft 数据访问接口（如 OLE DB），但通常使用 ADO 来检索该 **Recordset** 。</span><span class="sxs-lookup"><span data-stu-id="0b8a1-p112">The server program uses the connect string and command text to query the data source for the desired rows. ADO is typically used to retrieve this **Recordset**, although other Microsoft data access interfaces, such as OLE DB, could be used.</span></span>

<span data-ttu-id="0b8a1-151">自定义服务器程序的形式可以类似如下：</span><span class="sxs-lookup"><span data-stu-id="0b8a1-151">A custom server program might look like this:</span></span>

```vb 
 
Public Function ServerProgram(cn as String, qry as String) as Object 
Dim rs as New ADODB.Recordset 
 rs.CursorLocation = adUseClient 
 rs.Open qry, cn 
 rs.ActiveConnection = Nothing 
 Set ServerProgram = rs 
End Function 
```

## <a name="step-4-server-returns-the-recordset"></a><span data-ttu-id="0b8a1-152">步骤 4： 服务器返回 Recordset</span><span class="sxs-lookup"><span data-stu-id="0b8a1-152">Step 4: Server returns the Recordset</span></span> 

<span data-ttu-id="0b8a1-p113">RDS 将检索到的 **Recordset** 对象转换为可以发回到客户端的形式（即，它\*封送 \***Recordset**）。转换的确切形式及其发送方式取决于服务器是位于 Internet、Intranet 还是局域网上，或者服务器是否为动态链接库。但是，该细节并不是关键；RDS 将 **Recordset** 发回到客户端才是关键。</span><span class="sxs-lookup"><span data-stu-id="0b8a1-p113">RDS converts the retrieved **Recordset** object to a form that can be sent back to the client (that is, it *marshals* the **Recordset**). The exact form of the conversion and how it is sent depends on whether the server is on the Internet or an intranet, a local area network, or is a dynamic-link library. However, this detail is not critical; all that matters is that RDS sends the **Recordset** back to the client.</span></span>

<span data-ttu-id="0b8a1-156">在客户端上， **Recordset** 对象返回，并被分配给本地变量。</span><span class="sxs-lookup"><span data-stu-id="0b8a1-156">On the client side, a **Recordset** object is returned and assigned to a local variable.</span></span>

```vb 
 
Sub RDSTutorial4() 
 Dim DS as New RDS.DataSpace 
 Dim RS as ADODB.Recordset 
 Dim DF as Object 
 Set DF = DS.CreateObject("RDSServer.DataFactory", "https://yourServer") 
 Set RS = DF.Query("DSN=Pubs", "SELECT * FROM Authors") 
... 
```

## <a name="step-5-datacontrol-is-made-usable"></a><span data-ttu-id="0b8a1-157">步骤 5: DataControl 由可用</span><span class="sxs-lookup"><span data-stu-id="0b8a1-157">Step 5: DataControl is made usable</span></span> 

<span data-ttu-id="0b8a1-p114">所返回的 **Recordset** 对象已经可以使用。可以像对任何其他 **Recordset** 一样检查、定位或编辑该对象。对 **Recordset** 可以执行的操作取决于相应的环境。Visual Basic 和 Visual C++ 具有一些可视控件，这些控件可以直接或通过启用数据控件间接使用 **Recordset** 。</span><span class="sxs-lookup"><span data-stu-id="0b8a1-p114">The returned **Recordset** object is available for use. You can examine, navigate, or edit it as you would any other **Recordset**. What you can do with the **Recordset** depends on your environment. Visual Basic and Visual C++ have visual controls that can use a **Recordset** directly or indirectly with the aid of an enabling data control.</span></span>

<span data-ttu-id="0b8a1-162">例如，如果您要显示在 Internet Explorer 中的网页，您可能想要在可视控件中显示的**Recordset**对象的数据。</span><span class="sxs-lookup"><span data-stu-id="0b8a1-162">For example, if you are displaying a webpage in Internet Explorer, you might want to display the **Recordset** object data in a visual control.</span></span> <span data-ttu-id="0b8a1-163">网页上的可视控件不能直接访问**Recordset**对象。</span><span class="sxs-lookup"><span data-stu-id="0b8a1-163">Visual controls on a webpage cannot access a **Recordset** object directly.</span></span> <span data-ttu-id="0b8a1-164">但是，它们可以通过 **RDS.DataControl** 访问 [Recordset](datacontrol-object-rds.md) 对象。</span><span class="sxs-lookup"><span data-stu-id="0b8a1-164">However, they can access the **Recordset** object through the [RDS.DataControl](datacontrol-object-rds.md).</span></span> <span data-ttu-id="0b8a1-165">当 **RDS.DataControl** 的 [SourceRecordset](recordset-sourcerecordset-properties-rds.md) 属性设置为 **Recordset** 对象时，RDS.DataControl 便可被可视控件使用。</span><span class="sxs-lookup"><span data-stu-id="0b8a1-165">The **RDS.DataControl** becomes usable by a visual control when its [SourceRecordset](recordset-sourcerecordset-properties-rds.md) property is set to the **Recordset** object.</span></span>

<span data-ttu-id="0b8a1-166">可视控件对象的 **DATASRC** 参数必须设置为 **RDS.DataControl** ，它的 **DATAFLD** 属性必须设置为 **Recordset** 对象字段（列）。</span><span class="sxs-lookup"><span data-stu-id="0b8a1-166">The visual control object must have its **DATASRC** parameter set to the **RDS.DataControl**, and its **DATAFLD** property set to a **Recordset** object field (column).</span></span>

<span data-ttu-id="0b8a1-167">在本教程中，设置 **SourceRecordset** 属性：</span><span class="sxs-lookup"><span data-stu-id="0b8a1-167">In this tutorial, set the **SourceRecordset** property:</span></span>

```vb 
 
Sub RDSTutorial5() 
 Dim DS as New RDS.DataSpace 
 Dim RS as ADODB.Recordset 
 Dim DC as New RDS.DataControl 
 Dim DF as Object 
 Set DF = DS.CreateObject("RDSServer.DataFactory", "https://yourServer") 
 Set RS = DF.Query ("DSN=Pubs", "SELECT * FROM Authors") 
 DC.SourceRecordset = RS ' Visual controls can now bind to DC. 
... 
```

## <a name="step-6-changes-are-sent-to-the-server"></a><span data-ttu-id="0b8a1-168">步骤 6： 将更改发送到服务器</span><span class="sxs-lookup"><span data-stu-id="0b8a1-168">Step 6: Changes are sent to the server</span></span>

<span data-ttu-id="0b8a1-169">如果对 **Recordset** 对象进行编辑，则可以将任何更改（即，对行进行地添加、更改或删除）发回到服务器。</span><span class="sxs-lookup"><span data-stu-id="0b8a1-169">If the **Recordset** object is edited, any changes (that is, rows that are added, changed, or deleted) can be sent back to the server.</span></span>

<span data-ttu-id="0b8a1-170">[!注释] RDS 的默认行为可通过 ADO 对象和 Microsoft OLE DB Remoting Provider 隐式调用。</span><span class="sxs-lookup"><span data-stu-id="0b8a1-170">The default behavior of RDS can be invoked implicitly with ADO objects and the Microsoft OLE DB Remoting Provider.</span></span> <span data-ttu-id="0b8a1-171">查询可以返回**记录集**，并将已编辑的**记录集**可以更新数据源。</span><span class="sxs-lookup"><span data-stu-id="0b8a1-171">Queries can return **Recordsets**, and edited **Recordsets** can update the data source.</span></span> <span data-ttu-id="0b8a1-172">本教程不通过 ADO 对象调用 RDS，但在这里给出了它的形式：</span><span class="sxs-lookup"><span data-stu-id="0b8a1-172">This tutorial does not invoke RDS with ADO objects, but this is how it would look if it did:</span></span>

```vb 
 
Dim rs as New ADODB.Recordset 
rs.Open "SELECT * FROM Authors","Provider=MS Remote;Data Source=Pubs;" & _ 
 "Remote Server=https://yourServer;Remote Provider=SQLOLEDB;" 
... ' Edit the Recordset. 
rs.UpdateBatch ' The equivalent of SubmitChanges. 
... 
```

### <a name="part-a"></a><span data-ttu-id="0b8a1-173">部分 A</span><span class="sxs-lookup"><span data-stu-id="0b8a1-173">Part A</span></span>

<span data-ttu-id="0b8a1-174">假设这种情况下，仅使用[rds.DataControl](datacontrol-object-rds.md)和**Recordset**对象是否立即与**rds.DataControl**。</span><span class="sxs-lookup"><span data-stu-id="0b8a1-174">Assume for this case that you have only used the [RDS.DataControl](datacontrol-object-rds.md) and that a **Recordset** object is now associated with the **RDS.DataControl**.</span></span> <span data-ttu-id="0b8a1-175">如果 [Server](submitchanges-method-rds.md) 和 **Connect** 属性已设置， [SubmitChanges](server-property-rds.md) 方法将用对 [Recordset](connect-property-rds.md) 对象进行的任何更改来更新数据源。</span><span class="sxs-lookup"><span data-stu-id="0b8a1-175">The [SubmitChanges](submitchanges-method-rds.md) method updates the data source with any changes to the **Recordset** object if the [Server](server-property-rds.md) and [Connect](connect-property-rds.md) properties are still set.</span></span>

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

### <a name="part-b"></a><span data-ttu-id="0b8a1-176">部分 B</span><span class="sxs-lookup"><span data-stu-id="0b8a1-176">Part B</span></span>

<span data-ttu-id="0b8a1-177">此外，您无法使用[RDSServer.DataFactory](datafactory-object-rdsserver.md)对象，指定连接和**Recordset**对象更新服务器。</span><span class="sxs-lookup"><span data-stu-id="0b8a1-177">Alternatively, you could update the server with the [RDSServer.DataFactory](datafactory-object-rdsserver.md) object, specifying a connection and a **Recordset** object.</span></span>

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


## <a name="appendix-a-rds-tutorial-vbscript"></a><span data-ttu-id="0b8a1-178">附录 a: RDS 教程 (VBScript)</span><span class="sxs-lookup"><span data-stu-id="0b8a1-178">Appendix A: RDS tutorial (VBScript)</span></span>

<span data-ttu-id="0b8a1-179">这是在 Microsoft Visual Basic Scripting Edition 编写的 RDS 教程。</span><span class="sxs-lookup"><span data-stu-id="0b8a1-179">This is the RDS tutorial, written in Microsoft Visual Basic Scripting Edition.</span></span> <span data-ttu-id="0b8a1-180">本教程的用途的说明，请参阅本主题介绍。</span><span class="sxs-lookup"><span data-stu-id="0b8a1-180">For a description of the purpose of this tutorial, see the introduction to this topic.</span></span>

<span data-ttu-id="0b8a1-181">在本教程中， [rds.DataControl](datacontrol-object-rds.md)和[rds.DataSpace](dataspace-object-rds.md)在设计时; 创建即是与 object 标记中定义的。</span><span class="sxs-lookup"><span data-stu-id="0b8a1-181">In this tutorial, [RDS.DataControl](datacontrol-object-rds.md) and [RDS.DataSpace](dataspace-object-rds.md) are created at design time; that is, they are defined with object tags.</span></span> <span data-ttu-id="0b8a1-182">另外，它们也可以在运行时通过 **Server.CreateObject** 方法创建。</span><span class="sxs-lookup"><span data-stu-id="0b8a1-182">Alternatively, they could be created at run time with the **Server.CreateObject** method.</span></span> 

<span data-ttu-id="0b8a1-183">例如， **RDS.DataControl** 对象可以按如下方式创建：</span><span class="sxs-lookup"><span data-stu-id="0b8a1-183">For example, the **RDS.DataControl** object could be created like this:</span></span>

```vb
    Set DC = Server.CreateObject("RDS.DataControl") 
     <!-- RDS.DataControl --> 
     <OBJECT 
     ID="DC1" CLASSID="CLSID:BD96C556-65A3-11D0-983A-00C04FC29E33"> 
     </OBJECT> 
     
     <!-- RDS.DataSpace --> 
     <OBJECT 
     ID="DS1" WIDTH=1 HEIGHT=1 
     CLASSID="CLSID:BD96C556-65A3-11D0-983A-00C04FC29E36"> 
     </OBJECT> 
     
     <SCRIPT LANGUAGE="VBScript"> 
     
     Sub RDSTutorial() 
     Dim DF1 
```

### <a name="step-1-specify-a-server-program"></a><span data-ttu-id="0b8a1-184">步骤 1： 指定服务器程序</span><span class="sxs-lookup"><span data-stu-id="0b8a1-184">Step 1: Specify a server program</span></span>

<span data-ttu-id="0b8a1-185">VBScript 可以发现 IIS web 服务器通过访问供 Active Server Pages 的 VBScript **Request.ServerVariables**方法运行的名称：</span><span class="sxs-lookup"><span data-stu-id="0b8a1-185">VBScript can discover the name of the IIS web server it is running on by accessing the VBScript **Request.ServerVariables** method available to Active Server Pages:</span></span>

```vb 
 
"https://<%=Request.ServerVariables("SERVER_NAME")%>" 
```

<span data-ttu-id="0b8a1-186">但是，本教程使用虚构服务器"yourServer"。</span><span class="sxs-lookup"><span data-stu-id="0b8a1-186">However, for this tutorial, use the imaginary server, "yourServer."</span></span>

> [!NOTE]
> <span data-ttu-id="0b8a1-p120">[!注释] 请留意 **ByRef** 参数的数据类型。VBScript 不允许指定变量类型，因此必须始终传递变量。使用 HTTP 时，如果您用 **RDS.DataSpace** 对象的 [CreateObject](createobject-method-rds.md) 方法调用服务器程序，RDS 将允许您向应该使用非变量的方法传递变量。在使用 DCOM 或进程内服务器时，必须使客户端与服务器端的参数类型相匹配，否则将会产生"类型不匹配"错误。</span><span class="sxs-lookup"><span data-stu-id="0b8a1-p120">Pay attention to the data type of **ByRef** arguments. VBScript does not let you specify the variable type, so you must always pass a Variant. When using HTTP, RDS will allow you to pass a Variant to a method that expects a non-Variant if you invoke it with the **RDS.DataSpace** object [CreateObject](createobject-method-rds.md) method. When using DCOM or an in-process server, match the parameter types on the client and server sides or you will receive a "Type Mismatch" error.</span></span>

```vb
 
Set DF1 = DS1.CreateObject("RDSServer.DataFactory", "https://yourServer") 
```

### <a name="step-2-part-a-invoke-the-server-program-with-rdsdatacontrol"></a><span data-ttu-id="0b8a1-191">步骤 2，部件答： 调用服务器程序与 rds.DataControl</span><span class="sxs-lookup"><span data-stu-id="0b8a1-191">Step 2, Part A: Invoke the server program with RDS.DataControl</span></span>

<span data-ttu-id="0b8a1-192">以下示例只是注释，演示 **RDS.DataControl** 的默认行为是执行指定的查询。</span><span class="sxs-lookup"><span data-stu-id="0b8a1-192">This example is merely a comment demonstrating that the default behavior of the **RDS.DataControl** is to perform the specified query.</span></span>

```vb
 
<OBJECT CLASSID="clsid:BD96C556-65A3-11D0-983A-00C04FC29E33" ID="DC1"> 
 <PARAM NAME="SQL" VALUE="SELECT * FROM Authors"> 
 <PARAM NAME="Connect" VALUE="DSN=Pubs;"> 
 <PARAM NAME="Server" VALUE="https://yourServer/"> 
</OBJECT> 
... 
<SCRIPT LANGUAGE="VBScript"> 
 
Sub RDSTutorial2A() 
 Dim RS 
 DC1.Refresh 
 Set RS = DC1.Recordset 
... 
```

<span data-ttu-id="0b8a1-193">跳到下面的步骤。</span><span class="sxs-lookup"><span data-stu-id="0b8a1-193">Skip to the following step.</span></span>

### <a name="step-4-server-returns-the-recordset"></a><span data-ttu-id="0b8a1-194">步骤 4： 服务器返回 Recordset</span><span class="sxs-lookup"><span data-stu-id="0b8a1-194">Step 4: Server returns the Recordset</span></span>

```vb
 
Set RS = DF1.Query("DSN=Pubs;", "SELECT * FROM Authors") 
```

### <a name="step-5-datacontrol-is-made-usable-by-visual-controls"></a><span data-ttu-id="0b8a1-195">步骤 5: DataControl 进行可用可视控件</span><span class="sxs-lookup"><span data-stu-id="0b8a1-195">Step 5: DataControl is made usable by visual controls</span></span>

```vb
 
' Assign the returned recordset to the DataControl. 
 
DC1.SourceRecordset = RS 
```

### <a name="step-6-part-a-changes-are-sent-to-the-server-with-rdsdatacontrol"></a><span data-ttu-id="0b8a1-196">步骤 6，部件答： 更改发送到的服务器与 rds.DataControl</span><span class="sxs-lookup"><span data-stu-id="0b8a1-196">Step 6, Part A: Changes are sent to the server with RDS.DataControl</span></span>

<span data-ttu-id="0b8a1-197">以下示例只是一个注释，演示 **RDS.DataControl** 如何执行更新。</span><span class="sxs-lookup"><span data-stu-id="0b8a1-197">This example is merely a comment demonstrating how the **RDS.DataControl** performs updates.</span></span>

```vb
 
<OBJECT CLASSID="clsid:BD96C556-65A3-11D0-983A-00C04FC29E33" ID="DC1"> 
 <PARAM NAME="SQL" VALUE="SELECT * FROM Authors"> 
 <PARAM NAME="Connect" VALUE="DSN=Pubs;"> 
 <PARAM NAME="Server" VALUE="https://yourServer/"> 
</OBJECT> 
... 
<SCRIPT LANGUAGE="VBScript"> 
 
Sub RDSTutorial6A() 
Dim RS 
DC1.Refresh 
... 
Set RS = DC1.Recordset 
' Edit the Recordset object... 
' The SERVER and CONNECT properties are already set from Step 2A. 
Set DC1.SourceRecordset = RS 
... 
DC1.SubmitChanges 
```

### <a name="step-6-part-b-changes-are-sent-to-the-server-with-rdsserverdatafactory"></a><span data-ttu-id="0b8a1-198">步骤 6，部件 b： 将更改发送到使用 RDSServer.DataFactory 服务器</span><span class="sxs-lookup"><span data-stu-id="0b8a1-198">Step 6, Part B: Changes are sent to the server with RDSServer.DataFactory</span></span>

```vb
 
DF.SubmitChanges"DSN=Pubs", RS 
 
End Sub 
</SCRIPT> 
</BODY> 
</HTML> 
```

## <a name="appendix-b-rds-tutorial-visual-j"></a><span data-ttu-id="0b8a1-199">附录 b: RDS 教程 （Visual J + +）</span><span class="sxs-lookup"><span data-stu-id="0b8a1-199">Appendix B: RDS tutorial (Visual J++)</span></span>

<span data-ttu-id="0b8a1-p121">ADO/WFC 不完全遵循 RDS 对象模型，因为它不实现 [RDS.DataControl](datacontrol-object-rds.md) 对象。ADO/WFC 仅实现客户端类 [RDS.DataSpace](dataspace-object-rds.md)。</span><span class="sxs-lookup"><span data-stu-id="0b8a1-p121">ADO/WFC does not completely follow the RDS object model in that it does not implement the [RDS.DataControl](datacontrol-object-rds.md) object. ADO/WFC only implements the client-side class, [RDS.DataSpace](dataspace-object-rds.md).</span></span>

<span data-ttu-id="0b8a1-p122">**DataSpace** 类实现 [CreateObject](createobject-method-rds.md) 方法，该方法返回 [ObjectProxy](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/objectproxy-ado-wfc-syntax) 对象。 **DataSpace** 类还实现 [InternetTimeout](internettimeout-property-rds.md) 属性。</span><span class="sxs-lookup"><span data-stu-id="0b8a1-p122">The **DataSpace** class implements one method, [CreateObject](createobject-method-rds.md), which returns an [ObjectProxy](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/objectproxy-ado-wfc-syntax) object. The **DataSpace** class also implements the [InternetTimeout](internettimeout-property-rds.md) property.</span></span>

<span data-ttu-id="0b8a1-204">**ObjectProxy** 类实现 call 方法，该方法可以调用任何服务器端业务对象。</span><span class="sxs-lookup"><span data-stu-id="0b8a1-204">The **ObjectProxy** class implements one method, call, which can invoke any server-side business object.</span></span>

```java 
 
import com.ms.wfc.data.*; 
public class RDSTutorial 
{ 
 public void tutorial() 
 { 
// Step 1: Specify a server program. 
 ObjectProxy obj = 
 DataSpace.createObject( 
 "RDSServer.DataFactory", 
 "https://YourServer"); 
 
// Step 2: Server returns a Recordset. 
 Recordset rs = (Recordset) obj.call( 
 "Query", 
 new Object[] {"DSN=Pubs;", "SELECT * FROM Authors"}); 
 
// Step 3: Changes are sent to the server. 
 ... // Edit Recordset. 
 obj.call( 
 "SubmitChanges", 
 new Object[] {"DSN=Pubs;", rs}); 
 return; 
 } 
} 
```



