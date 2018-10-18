---
title: Open 方法 (ADO Connection)
TOCTitle: Open Method (ADO Connection)
ms:assetid: 1adaa17d-dfe1-22e0-3415-720516d138f8
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248951(v=office.15)
ms:contentKeyID: 48543525
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 78c20ce6da4c20385bd22488ce910312c737986e
ms.sourcegitcommit: a49b77f4c8cec69f90656a86f0872cf34c35968e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2018
ms.locfileid: "25606330"
---
# <a name="open-method-ado-connection"></a><span data-ttu-id="3fdc7-102">Open 方法 (ADO Connection)</span><span class="sxs-lookup"><span data-stu-id="3fdc7-102">Open Method (ADO Connection)</span></span>


<span data-ttu-id="3fdc7-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="3fdc7-103">**Applies to**: Access 2013 | Office 2013</span></span>
 

<span data-ttu-id="3fdc7-104">用于打开与数据源的连接。</span><span class="sxs-lookup"><span data-stu-id="3fdc7-104">Opens a connection to a data source.</span></span>

## <a name="syntax"></a><span data-ttu-id="3fdc7-105">语法</span><span class="sxs-lookup"><span data-stu-id="3fdc7-105">Syntax</span></span>

<span data-ttu-id="3fdc7-106">*连接*。打开*ConnectionString*、*用户 Id*、*密码*和*选项*</span><span class="sxs-lookup"><span data-stu-id="3fdc7-106">*connection*.Open*ConnectionString*, *UserID*, *Password*, *Options*</span></span>

## <a name="parameters"></a><span data-ttu-id="3fdc7-107">参数</span><span class="sxs-lookup"><span data-stu-id="3fdc7-107">Parameters</span></span>

  - <span data-ttu-id="3fdc7-108">*ConnectionString*</span><span class="sxs-lookup"><span data-stu-id="3fdc7-108">*ConnectionString*</span></span>

  - <span data-ttu-id="3fdc7-p101">可选。 **字符串** 值，包含连接信息。有关有效设置的详细信息，请参阅 [ConnectionString](connectionstring-property-ado.md) 属性。</span><span class="sxs-lookup"><span data-stu-id="3fdc7-p101">Optional. A **String** value that contains connection information. See the [ConnectionString](connectionstring-property-ado.md) property for details on valid settings.</span></span>

  - <span data-ttu-id="3fdc7-112">*用户 Id*</span><span class="sxs-lookup"><span data-stu-id="3fdc7-112">*UserID*</span></span>

  - <span data-ttu-id="3fdc7-p102">可选。 **字符串** 值，包含建立连接时所使用的用户名。</span><span class="sxs-lookup"><span data-stu-id="3fdc7-p102">Optional. A **String** value that contains a user name to use when establishing the connection.</span></span>

  - <span data-ttu-id="3fdc7-115">*Password*</span><span class="sxs-lookup"><span data-stu-id="3fdc7-115">*Password*</span></span>

  - <span data-ttu-id="3fdc7-p103">可选。 **字符串** 值，包含建立连接时所使用的密码。</span><span class="sxs-lookup"><span data-stu-id="3fdc7-p103">Optional. A **String** value that contains a password to use when establishing the connection.</span></span>

  - <span data-ttu-id="3fdc7-118">*Options*</span><span class="sxs-lookup"><span data-stu-id="3fdc7-118">*Options*</span></span>

  - <span data-ttu-id="3fdc7-p104">可选。一个 [ConnectOptionEnum](connectoptionenum.md) 值，用于确定此方法应在建立连接之后（同步）还是之前（异步）返回。</span><span class="sxs-lookup"><span data-stu-id="3fdc7-p104">Optional. A [ConnectOptionEnum](connectoptionenum.md) value that determines whether this method should return after (synchronously) or before (asynchronously) the connection is established.</span></span>

## <a name="remarks"></a><span data-ttu-id="3fdc7-121">说明</span><span class="sxs-lookup"><span data-stu-id="3fdc7-121">Remarks</span></span>

<span data-ttu-id="3fdc7-p105">如果对 **Connection** 对象使用 [Open](connection-object-ado.md) 方法，则将建立与数据源的物理连接。此方法成功完成之后，连接将激活，您可以针对它发布命令并处理结果。</span><span class="sxs-lookup"><span data-stu-id="3fdc7-p105">Using the **Open** method on a [Connection](connection-object-ado.md) object establishes the physical connection to a data source. After this method successfully completes, the connection is live and you can issue commands against it and process the results.</span></span>

<span data-ttu-id="3fdc7-124">使用可选的*ConnectionString*参数指定包含一系列并用分号或文件的*参数* *= value*语句或标识与 URL 目录资源的连接字符串。</span><span class="sxs-lookup"><span data-stu-id="3fdc7-124">Use the optional *ConnectionString* argument to specify either a connection string containing a series of *argument* *= value* statements separated by semicolons, or a file or directory resource identified with a URL.</span></span> <span data-ttu-id="3fdc7-125">**ConnectionString**属性自动继承的*ConnectionString*参数使用的值。</span><span class="sxs-lookup"><span data-stu-id="3fdc7-125">The **ConnectionString** property automatically inherits the value used for the *ConnectionString* argument.</span></span> <span data-ttu-id="3fdc7-126">因此，您可以将**Connection**对象的**ConnectionString**属性设置然后再打开它，或使用的*ConnectionString*参数设置或**Open**方法调用期间重写当前的连接参数.</span><span class="sxs-lookup"><span data-stu-id="3fdc7-126">Therefore, you can either set the **ConnectionString** property of the **Connection** object before opening it, or use the *ConnectionString* argument to set or override the current connection parameters during the **Open** method call.</span></span>

<span data-ttu-id="3fdc7-127">如果同时在 *ConnectionString* 参数和可选的 *UserID* 与 *Password* 参数中传递用户和密码信息，则 *UserID* 和 *Password* 参数将替代在 *ConnectionString* 中指定的值。</span><span class="sxs-lookup"><span data-stu-id="3fdc7-127">If you pass user and password information both in the *ConnectionString* argument and in the optional *UserID* and *Password* arguments, the *UserID* and *Password* arguments will override the values specified in *ConnectionString*.</span></span>

<span data-ttu-id="3fdc7-p107">结束对打开的 **Connection** 执行的操作之后，可使用 [Close](close-method-ado.md) 方法释放任何关联的系统资源。关闭对象不会将其从内存中删除，您可以更改其属性设置，稍后使用 **Open** 方法再次打开它。若要从内存中完全消除对象，请将对象变量设置为 *Nothing*。</span><span class="sxs-lookup"><span data-stu-id="3fdc7-p107">When you have concluded your operations over an open **Connection**, use the [Close](close-method-ado.md) method to free any associated system resources. Closing an object does not remove it from memory; you can change its property settings and use the **Open** method to open it again later. To completely eliminate an object from memory, set the object variable to *Nothing*.</span></span>

<span data-ttu-id="3fdc7-131">**远程数据服务用法**当客户端**Connection**对象上使用， **Open**方法实际上不会建立连接到服务器的直到在**Connection**对象上打开[Recordset](recordset-object-ado.md) 。</span><span class="sxs-lookup"><span data-stu-id="3fdc7-131">**Remote Data Service Usage**When used on a client-side **Connection** object, the **Open** method doesn't actually establish a connection to the server until a [Recordset](recordset-object-ado.md) is opened on the **Connection** object.</span></span>


> [!NOTE]
<span data-ttu-id="3fdc7-132"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="3fdc7-132"><<<<<<< HEAD</span></span>
> <P><span data-ttu-id="3fdc7-p108">[!注释] 使用 HTTP 架构的 URL 将自动调用 <A href="microsoft-ole-db-provider-for-internet-publishing.md">Microsoft OLE DB Provider for Internet Publishing</A>。有关详细信息，请参阅<A href="absolute-and-relative-urls.md">绝对 URL 和相对 URL</A>。</span><span class="sxs-lookup"><span data-stu-id="3fdc7-p108">URLs using the http scheme will automatically invoke the <A href="microsoft-ole-db-provider-for-internet-publishing.md">Microsoft OLE DB Provider for Internet Publishing</A>. For more information, see <A href="absolute-and-relative-urls.md">Absolute and Relative URLs</A>.</span></span></P>
=======
> <span data-ttu-id="3fdc7-135">[!注释] 使用 HTTP 架构的 URL 将自动调用 [Microsoft OLE DB Provider for Internet Publishing](microsoft-ole-db-provider-for-internet-publishing.md)。</span><span class="sxs-lookup"><span data-stu-id="3fdc7-135">URLs using the http scheme will automatically invoke the [Microsoft OLE DB Provider for Internet Publishing](microsoft-ole-db-provider-for-internet-publishing.md).</span></span> <span data-ttu-id="3fdc7-136">有关详细信息，请参阅[绝对和相对 Url](absolute-and-relative-urls.md)。</span><span class="sxs-lookup"><span data-stu-id="3fdc7-136">For more information, see [Absolute and relative URLs](absolute-and-relative-urls.md).</span></span>
>>>>>>> <span data-ttu-id="3fdc7-137">master</span><span class="sxs-lookup"><span data-stu-id="3fdc7-137">master</span></span>


