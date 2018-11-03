---
title: RDS 编程模型详细信息
TOCTitle: RDS Programming Model in Detail
ms:assetid: 133fc059-9b51-52e2-2e61-339716d8d965
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248906(v=office.15)
ms:contentKeyID: 48543364
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 8a34321df27b5270bd35844eaf28b0b335b0294e
ms.sourcegitcommit: 38d0db57580cc5f4a0231c27b1643f8db5431ca3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25937475"
---
# <a name="rds-programming-model-in-detail"></a><span data-ttu-id="eedba-102">RDS 编程模型详细信息</span><span class="sxs-lookup"><span data-stu-id="eedba-102">RDS Programming Model in Detail</span></span>


<span data-ttu-id="eedba-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="eedba-103">**Applies to**: Access 2013, Office 2013</span></span>



<span data-ttu-id="eedba-104">以下列出了 RDS 编程模型的主要组成部分：</span><span class="sxs-lookup"><span data-stu-id="eedba-104">The following are key elements of the RDS programming model:</span></span>

  - <span data-ttu-id="eedba-105">RDS.DataSpace</span><span class="sxs-lookup"><span data-stu-id="eedba-105">RDS.DataSpace</span></span>

  - <span data-ttu-id="eedba-106">RDSServer.DataFactory</span><span class="sxs-lookup"><span data-stu-id="eedba-106">RDSServer.DataFactory</span></span>

  - <span data-ttu-id="eedba-107">RDS.DataControl</span><span class="sxs-lookup"><span data-stu-id="eedba-107">RDS.DataControl</span></span>

  - <span data-ttu-id="eedba-108">事件</span><span class="sxs-lookup"><span data-stu-id="eedba-108">Event</span></span>

## <a name="rdsdataspace"></a><span data-ttu-id="eedba-109">RDS.DataSpace</span><span class="sxs-lookup"><span data-stu-id="eedba-109">RDS.DataSpace</span></span>

<span data-ttu-id="eedba-p101">客户端应用程序必须指定要调用的服务器和服务器程序。反过来，应用程序收到一个针对服务器程序的引用，该引用可以被视作服务器程序本身。</span><span class="sxs-lookup"><span data-stu-id="eedba-p101">Your client application must specify the server and the server program to invoke. In return, your application receives a reference to the server program and can treat the reference as if it were the server program itself.</span></span>

<span data-ttu-id="eedba-112">RDS 对象模型通过 [RDS.DataSpace](dataspace-object-rds.md) 对象来实现此功能。</span><span class="sxs-lookup"><span data-stu-id="eedba-112">The RDS object model embodies this functionality with the [RDS.DataSpace](dataspace-object-rds.md) object.</span></span>

<span data-ttu-id="eedba-p102">服务器程序用程序标识符或 *ProgID* 来指定。服务器使用 *ProgID* 以及服务器计算机的注册表来查找有关要初始化的实际程序的信息。</span><span class="sxs-lookup"><span data-stu-id="eedba-p102">The server program is specified with a program identifier, or *ProgID*. The server uses the *ProgID* and the server machine's registry to locate information about the actual program to initiate.</span></span>

<span data-ttu-id="eedba-p103">根据服务器程序是位于 Internet 或 Intranet 上的远程服务器上，还是位于局域网中的服务器上，还是根本不在服务器上而是位于本地动态链接库 (DLL) 上，RDS 将在内部区别对待。该区别决定了客户端与服务器之间的信息交换方式，并造成返回客户端应用程序的引用类型的切实不同。不过，从您的角度而言，这种区别并没有什么特殊意义，对于您而言，最重要的是收到一个可用的程序引用。</span><span class="sxs-lookup"><span data-stu-id="eedba-p103">RDS makes a distinction internally depending on whether the server program is on a remote server across the Internet or an intranet; a server on a local area network; or not on a server at all, but instead on a local dynamic-link library (DLL). This distinction determines how information is exchanged between the client and the server, and makes a tangible difference in the type of reference returned to your client application. However, from your point of view, this distinction has no special meaning. All that matters is that you receive a usable program reference.</span></span>

## <a name="rdsserverdatafactory"></a><span data-ttu-id="eedba-119">RDSServer.DataFactory</span><span class="sxs-lookup"><span data-stu-id="eedba-119">RDSServer.DataFactory</span></span>

<span data-ttu-id="eedba-120">RDS 提供了一个默认的服务器程序，该程序可以针对数据源执行 SQL 查询并返回 [Recordset](recordset-object-ado.md) 对象，还可以采用 **Recordset** 对象并更新数据源。</span><span class="sxs-lookup"><span data-stu-id="eedba-120">RDS provides a default server program that can either perform a SQL query against the data source and return a [Recordset](recordset-object-ado.md) object or take a **Recordset** object and update the data source.</span></span>

<span data-ttu-id="eedba-121">RDS 对象模型通过 [RDSServer.DataFactory](datafactory-object-rdsserver.md) 对象来实现此功能。</span><span class="sxs-lookup"><span data-stu-id="eedba-121">The RDS object model embodies this functionality with the [RDSServer.DataFactory](datafactory-object-rdsserver.md) object.</span></span>

<span data-ttu-id="eedba-122">此外，此对象包含用于创建您可以编程方式填充的空**Recordset**对象的方法 ([CreateRecordset](createrecordset-method-rds.md))，和用于将**Recordset**对象转换为文本字符串来构建网页 ([的另一种方法ConvertToString](converttostring-method-rds.md))。</span><span class="sxs-lookup"><span data-stu-id="eedba-122">In addition, this object has a method for creating an empty **Recordset** object that you can fill programmatically ([CreateRecordset](createrecordset-method-rds.md)), and another method for converting a **Recordset** object into a text string to build a webpage ([ConvertToString](converttostring-method-rds.md)).</span></span>

<span data-ttu-id="eedba-123">通过 ADO，可以用 **DataFactory** 处理程序和包含连接、命令和安全参数的自定义文件替代 **RDSServer.DataFactory** 的某些标准连接和命令行为。</span><span class="sxs-lookup"><span data-stu-id="eedba-123">With ADO, you can override some of the standard connection and command behavior of the **RDSServer.DataFactory** with a **DataFactory** handler and a customization file that contains connection, command, and security parameters.</span></span>

<span data-ttu-id="eedba-p104">服务器程序有时也称为*业务对象*。您可以编写自定义的业务对象，用于执行复杂的数据访问、有效性检查等。即使是在编写自定义业务对象时，您也可以创建 **RDSServer.DataFactory** 对象的实例并使用该对象的某些方法来完成您自己的任务。</span><span class="sxs-lookup"><span data-stu-id="eedba-p104">The server program is sometimes called a *business object*. You can write your own custom business object that can perform complicated data access, validity checks, and so on. Even when writing a custom business object, you can create an instance of an **RDSServer.DataFactory** object and use some of its methods to accomplish your own tasks.</span></span>

## <a name="rdsdatacontrol"></a><span data-ttu-id="eedba-127">RDS.DataControl</span><span class="sxs-lookup"><span data-stu-id="eedba-127">RDS.DataControl</span></span>

<span data-ttu-id="eedba-p105">可以通过 RDS 提供的方法，将 **RDS.DataSpace** 和 **RDSServer.DataFactory** 的功能结合在一起，并启用可视控件，以轻松地使用查询从数据源返回的 **Recordset** 对象。最常见的情况是，RDS 会尽可能地自动获取有关服务器的信息的访问权，并将信息显示在可视控件中。</span><span class="sxs-lookup"><span data-stu-id="eedba-p105">RDS provides a means to combine the functionality of the **RDS.DataSpace** and **RDSServer.DataFactory**, and also enable visual controls to easily use the **Recordset** object returned by a query from a data source. RDS attempts, for the most common case, to do as much as possible to automatically gain access to information on a server and display it in a visual control.</span></span>

<span data-ttu-id="eedba-130">RDS 对象模型通过 [RDS.DataControl](datacontrol-object-rds.md) 对象来实现此功能。</span><span class="sxs-lookup"><span data-stu-id="eedba-130">The RDS object model embodies this functionality with the [RDS.DataControl](datacontrol-object-rds.md) object.</span></span>

<span data-ttu-id="eedba-p106">**RDS.DataControl** 具有两个方面。其中一个方面关系到数据源。如果使用 **RDS.DataControl** 的 **Connect** 和 **SQL** 属性设置命令和连接信息，则它将自动使用 **RDS.DataSpace** 创建针对默认 **RDSServer.DataFactory** 对象的引用。随后， **RDSServer.DataFactory** 将使用 **Connect** 属性值连接到数据源，使用 **SQL** 属性值从数据源获取 **Recordset** ，并将 **Recordset** 对象返回给 **RDS.DataControl** 。</span><span class="sxs-lookup"><span data-stu-id="eedba-p106">The **RDS.DataControl** has two aspects. One aspect pertains to the data source. If you set the command and connection information using the **Connect** and **SQL** properties of the **RDS.DataControl**, it will automatically use the **RDS.DataSpace** to create a reference to the default **RDSServer.DataFactory** object. Then the **RDSServer.DataFactory** will use the **Connect** property value to connect to the data source, use the **SQL** property value to obtain a **Recordset** from the data source, and return the **Recordset** object to the **RDS.DataControl**.</span></span>

<span data-ttu-id="eedba-135">另一个方面关系到可视控件中返回的 **Recordset** 信息的显示。</span><span class="sxs-lookup"><span data-stu-id="eedba-135">The second aspect pertains to the display of returned **Recordset** information in a visual control.</span></span> <span data-ttu-id="eedba-136">您可以将可视控件与 rds.**相关联DataControl** （称为绑定的过程） 中并访问关联的**Recordset**对象，Microsoft Internet Explorer 中的网页上显示查询结果中的信息。</span><span class="sxs-lookup"><span data-stu-id="eedba-136">You can associate a visual control with the **RDS.DataControl** (in a process called binding) and gain access to the information in the associated **Recordset** object, displaying query results on a webpage in Microsoft Internet Explorer.</span></span> <span data-ttu-id="eedba-137">每个 **RDS.DataControl** 对象将一个表示单个查询结果的 **Recordset** 对象绑定到一个或多个可视控件（如文本框、组合框、网格控件等）。</span><span class="sxs-lookup"><span data-stu-id="eedba-137">Each **RDS.DataControl** object binds one **Recordset** object, representing the results of a single query, to one or more visual controls (for example, a text box, combo box, grid control, and so forth).</span></span> <span data-ttu-id="eedba-138">每个页面上可能有多个 **RDS.DataControl** 对象。</span><span class="sxs-lookup"><span data-stu-id="eedba-138">There may be more than one **RDS.DataControl** object on each page.</span></span> <span data-ttu-id="eedba-139">每个 **RDS.DataControl** 对象可以连接到不同的数据源，并包含不同查询的结果。</span><span class="sxs-lookup"><span data-stu-id="eedba-139">Each **RDS.DataControl** object can be connected to a different data source and contain the results of a separate query.</span></span>

<span data-ttu-id="eedba-p108">对于关联的 **Recordset** 对象的行， **RDS.DataControl** 对象还有自己的导航、排序和筛选方法。这些方法与 ADO **Recordset** 对象的方法很类似，但不尽相同。</span><span class="sxs-lookup"><span data-stu-id="eedba-p108">The **RDS.DataControl** object also has its own methods for navigating, sorting, and filtering the rows of the associated **Recordset** object. These methods are similar, but not the same as the methods on the ADO **Recordset** object.</span></span>

## <a name="events"></a><span data-ttu-id="eedba-142">事件</span><span class="sxs-lookup"><span data-stu-id="eedba-142">Events</span></span>

<span data-ttu-id="eedba-143">RDS 支持自己的两个事件，这些事件独立于 ADO 事件模型。</span><span class="sxs-lookup"><span data-stu-id="eedba-143">RDS supports two of its own events, which are independent of the ADO event model.</span></span> <span data-ttu-id="eedba-144">会调用[onReadyStateChange](onreadystatechange-event-rds.md)事件只要**rds.DataControl** [ReadyState](readystate-property-rds.md)属性更改，因此在异步操作已成功完成，通知您终止，或遇到错误。</span><span class="sxs-lookup"><span data-stu-id="eedba-144">The [onReadyStateChange](onreadystatechange-event-rds.md) event is called whenever the **RDS.DataControl** [ReadyState](readystate-property-rds.md) property changes, thus notifying you when an asynchronous operation has successfully completed, terminated, or experienced an error.</span></span> <span data-ttu-id="eedba-145">只要发生错误，便调用 [onError](onerror-event-rds.md) 事件，即使该错误发生于异步操作过程中也不例外。</span><span class="sxs-lookup"><span data-stu-id="eedba-145">The [onError](onerror-event-rds.md) event is called whenever an error occurs, even if the error occurs during an asynchronous operation.</span></span>


> [!NOTE]
> <P><span data-ttu-id="eedba-146">[!注释] Microsoft Internet Explorer 为 RDS 提供了其他两个事件： <STRONG>onDataSetChanged</STRONG> （ <STRONG>Recordset</STRONG> 可用但仍在检索行）和 <STRONG>onDataSetComplete</STRONG> （ <STRONG>Recordset</STRONG> 已完成行的检索）。</span><span class="sxs-lookup"><span data-stu-id="eedba-146">Microsoft Internet Explorer provides two additional events to RDS — <STRONG>onDataSetChanged</STRONG> (the <STRONG>Recordset</STRONG> is functional but still retrieving rows) and <STRONG>onDataSetComplete</STRONG> (the <STRONG>Recordset</STRONG> has finished retrieving rows).</span></span></P>


