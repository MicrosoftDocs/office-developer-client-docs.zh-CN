---
title: 将 RDS 与 ODBC 连接池结合使用
TOCTitle: Using RDS with ODBC Connection Pooling
ms:assetid: 6e8b023a-d211-44cb-10af-d43174a5d4bc
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249437(v=office.15)
ms:contentKeyID: 48545513
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 35a4327a76ff34f503c988e8d51f5aa73d6c454b
ms.sourcegitcommit: 558d09fad81f8d80b5ad0edd21934fc09c098f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25946718"
---
# <a name="using-rds-with-odbc-connection-pooling"></a><span data-ttu-id="112ac-102">使用 RDS 与 ODBC 连接池</span><span class="sxs-lookup"><span data-stu-id="112ac-102">Using RDS with ODBC connection pooling</span></span>


<span data-ttu-id="112ac-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="112ac-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="112ac-p101">如果您使用的是 ODBC 数据源，则可以在 Internet 信息服务 (IIS) 中使用连接池选项来实现对客户端负载的高性能处理。连接池是用于连接的资源管理器，可维护常用连接的打开状态。</span><span class="sxs-lookup"><span data-stu-id="112ac-p101">If you're using an ODBC data source, you can use the connection pooling option in Internet Information Services (IIS) to achieve high performance handling of client load. Connection pooling is a resource manager for connections, maintaining the open state on frequently used connections.</span></span>

<span data-ttu-id="112ac-106">若要启用连接池，请参考 Internet 信息服务文档。</span><span class="sxs-lookup"><span data-stu-id="112ac-106">To enable connection pooling, refer to the Internet Information Services documentation.</span></span>

<span data-ttu-id="112ac-107">请注意，启用连接池可能会使 web 服务器受到其他限制，如 Microsoft Internet 信息服务文档中所述。</span><span class="sxs-lookup"><span data-stu-id="112ac-107">Please note that enabling connection pooling may subject the web server to other restrictions, as noted in the Microsoft Internet Information Services documentation.</span></span>

<span data-ttu-id="112ac-108">为了确保连接池稳定且提供额外的性能提升，必须将 Microsoft SQL Server 配置为使用 TCP/IP 套接字网络库。</span><span class="sxs-lookup"><span data-stu-id="112ac-108">To ensure that connection pooling is stable and provides additional performance gains, you must configure Microsoft SQL Server to use the TCP/IP Socket network library.</span></span>

<span data-ttu-id="112ac-109">为此，您需要执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="112ac-109">To do this, you need to:</span></span>

  - <span data-ttu-id="112ac-110">将 SQL Server 计算机配置为使用 TCP/IP 套接字。</span><span class="sxs-lookup"><span data-stu-id="112ac-110">Configure the SQL Server computer to use TCP/IP Sockets.</span></span>

  - <span data-ttu-id="112ac-111">Web 服务器配置为使用 TCP/IP 套接字。</span><span class="sxs-lookup"><span data-stu-id="112ac-111">Configure the web server to use TCP/IP Sockets.</span></span>

## <a name="configuring-the-sql-server-computer-to-use-tcpip-sockets"></a><span data-ttu-id="112ac-112">将 SQL Server 计算机配置为使用 TCP/IP 套接字</span><span class="sxs-lookup"><span data-stu-id="112ac-112">Configuring the SQL Server Computer to Use TCP/IP Sockets</span></span>

<span data-ttu-id="112ac-113">在 SQL Server 计算机上运行 SQL Server 安装程序，以便与数据源交互时使用 TCP/IP 套接字网络库。</span><span class="sxs-lookup"><span data-stu-id="112ac-113">On the SQL Server computer, run the SQL Server Setup program so that interactions with the data source use the TCP/IP Socket network library.</span></span>

<span data-ttu-id="112ac-114">**在 SQL Server 计算机上指定 TCP/IP 套接字网络库**</span><span class="sxs-lookup"><span data-stu-id="112ac-114">**To specify the TCP/IP Socket network library on the SQL Server computer**</span></span>

<span data-ttu-id="112ac-115">**在 Microsoft SQL Server 6.5 中：**</span><span class="sxs-lookup"><span data-stu-id="112ac-115">**In Microsoft SQL Server 6.5:**</span></span>

1.  <span data-ttu-id="112ac-116">从**开始**菜单上，指向**程序**，指向**Microsoft SQL Server 6.5**，，然后单击**SQL Setup**。</span><span class="sxs-lookup"><span data-stu-id="112ac-116">From the **Start** menu, point to **Programs**, point to **Microsoft SQL Server 6.5**, and then click **SQL Setup**.</span></span>

2.  <span data-ttu-id="112ac-117">单击**继续**两次。</span><span class="sxs-lookup"><span data-stu-id="112ac-117">Click **Continue** twice.</span></span>

3.  <span data-ttu-id="112ac-118">在**Microsoft SQL Server — 选项**对话框中，选择**更改网络支持**，然后单击**继续**。</span><span class="sxs-lookup"><span data-stu-id="112ac-118">In the **Microsoft SQL Server — Options** dialog box, select **Change Network Support**, and then click **Continue**.</span></span>

4.  <span data-ttu-id="112ac-119">请确保选择了**TCP/IP 套接字**复选框，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="112ac-119">Make sure the **TCP/IP Sockets** check box is selected, and click **OK**.</span></span>

5.  <span data-ttu-id="112ac-120">单击**继续**以完成，然后退出安装程序。</span><span class="sxs-lookup"><span data-stu-id="112ac-120">Click **Continue** to finish, and exit setup.</span></span>

<span data-ttu-id="112ac-121">**在 Microsoft SQL Server 7.0 中：**</span><span class="sxs-lookup"><span data-stu-id="112ac-121">**In Microsoft SQL Server 7.0:**</span></span>

1.  <span data-ttu-id="112ac-122">从**开始**菜单上，指向**程序**，指向**Microsoft SQL Server 7.0**，，然后单击**服务器网络实用工具**。</span><span class="sxs-lookup"><span data-stu-id="112ac-122">From the **Start** menu, point to **Programs**, point to **Microsoft SQL Server 7.0**, and then click **Server Network Utility**.</span></span>

2.  <span data-ttu-id="112ac-123">在对话框的**常规**选项卡上，单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="112ac-123">On the **General** tab of the dialog box, click **Add**.</span></span>

3.  <span data-ttu-id="112ac-124">在**添加网络库配置**对话框中，单击**TCP/IP**。</span><span class="sxs-lookup"><span data-stu-id="112ac-124">In the **Add Network Library Configuration** dialog box, click **TCP/IP**.</span></span>

4.  <span data-ttu-id="112ac-125">在**端口号**和**代理服务器地址**框中，输入网络管理员提供的端口号和代理地址。</span><span class="sxs-lookup"><span data-stu-id="112ac-125">In the **Port number** and **Proxy address** boxes, enter the port number and proxy address provided by your network administrator.</span></span>

5.  <span data-ttu-id="112ac-126">单击**确定**完成，然后退出安装程序。</span><span class="sxs-lookup"><span data-stu-id="112ac-126">Click **OK** to finish, and exit setup.</span></span>

## <a name="configuring-the-web-server-to-use-tcpip-sockets"></a><span data-ttu-id="112ac-127">配置 web 服务器添加到使用 TCP/IP 套接字</span><span class="sxs-lookup"><span data-stu-id="112ac-127">Configuring the web Server to Use TCP/IP Sockets</span></span>

<span data-ttu-id="112ac-128">有两个选项的 web 服务器配置为使用 TCP/IP 套接字。</span><span class="sxs-lookup"><span data-stu-id="112ac-128">There are two options for configuring the web server to use TCP/IP Sockets.</span></span> <span data-ttu-id="112ac-129">执行哪些操作取决于是否所有的 SQL Server 访问来自 web 服务器，或仅特定的 SQL Server 访问来自 web 服务器。</span><span class="sxs-lookup"><span data-stu-id="112ac-129">What you do depends on whether all SQL Servers are accessed from the web server, or only a specific SQL Server is accessed from the web server.</span></span>

<span data-ttu-id="112ac-130">如果所有的 SQL Server 访问来自 web 服务器，您需要在 web 服务器计算机上运行 SQL Server 客户端配置实用工具。</span><span class="sxs-lookup"><span data-stu-id="112ac-130">If all SQL Servers are accessed from the web server, you need to run the SQL Server Client Configuration Utility on the web server computer.</span></span> <span data-ttu-id="112ac-131">以下步骤更改为使用 TCP/IP 套接字网络库通过此 IIS web 服务器所做的所有 SQL Server 连接的默认网络库。</span><span class="sxs-lookup"><span data-stu-id="112ac-131">The following steps change the default network library for all SQL Server connections made from this IIS web server to use the TCP/IP Sockets network library.</span></span>

<span data-ttu-id="112ac-132">**配置 web 服务器 (所有的 SQL Server)**</span><span class="sxs-lookup"><span data-stu-id="112ac-132">**To configure the web server (all SQL Servers)**</span></span>

<span data-ttu-id="112ac-133">**在 Microsoft SQL Server 6.5 中：**</span><span class="sxs-lookup"><span data-stu-id="112ac-133">**For Microsoft SQL Server 6.5:**</span></span>

1.  <span data-ttu-id="112ac-134">从**开始**菜单上，指向**程序**，指向**Microsoft SQL Server 6.5**，，然后单击**SQL 客户端配置实用工具**。</span><span class="sxs-lookup"><span data-stu-id="112ac-134">From the **Start** menu, point to **Programs**, point to **Microsoft SQL Server 6.5**, and then click **SQL Client Configuration Utility**.</span></span>

2.  <span data-ttu-id="112ac-135">单击**网络库**选项卡。</span><span class="sxs-lookup"><span data-stu-id="112ac-135">Click the **Net Library** tab.</span></span>

3.  <span data-ttu-id="112ac-136">在**默认网络**框中，选择**TCP/IP 套接字**。</span><span class="sxs-lookup"><span data-stu-id="112ac-136">In the **Default Network** box, select **TCP/IP Sockets**.</span></span>

4.  <span data-ttu-id="112ac-137">单击**完成**以保存更改并退出该实用工具。</span><span class="sxs-lookup"><span data-stu-id="112ac-137">Click **Done** to save changes and exit the utility.</span></span>

<span data-ttu-id="112ac-138">**在 Microsoft SQL Server 7.0 中：**</span><span class="sxs-lookup"><span data-stu-id="112ac-138">**For Microsoft SQL Server 7.0:**</span></span>

1.  <span data-ttu-id="112ac-139">从**开始**菜单上，指向**程序**，指向**Microsoft SQL Server 7.0**，，然后单击**客户端网络实用工具**。</span><span class="sxs-lookup"><span data-stu-id="112ac-139">From the **Start** menu, point to **Programs**, point to **Microsoft SQL Server 7.0**, and then click **Client Network Utility**.</span></span>

2.  <span data-ttu-id="112ac-140">单击**常规**选项卡。</span><span class="sxs-lookup"><span data-stu-id="112ac-140">Click the **General** tab.</span></span>

3.  <span data-ttu-id="112ac-141">在**默认网络库**框中，单击**TCP/IP**。</span><span class="sxs-lookup"><span data-stu-id="112ac-141">In the **Default network library** box, click **TCP/IP**.</span></span>

4.  <span data-ttu-id="112ac-142">单击**确定**以保存更改并退出该实用工具。</span><span class="sxs-lookup"><span data-stu-id="112ac-142">Click **OK** to save changes and exit the utility.</span></span>

<span data-ttu-id="112ac-143">如果从 web 服务器访问特定的 SQL Server 时，您需要在 web 服务器计算机上运行 SQL Server 客户端配置实用工具。</span><span class="sxs-lookup"><span data-stu-id="112ac-143">If a specific SQL Server is accessed from a web server, you need to run the SQL Server Client Configuration Utility on the web server computer.</span></span> <span data-ttu-id="112ac-144">若要更改某个特定的 SQL Server 连接的网络库，配置 SQL Server 客户端上的软件 web 服务器计算机，如下所示。</span><span class="sxs-lookup"><span data-stu-id="112ac-144">To change the network library for a specific SQL Server connection, configure the SQL Server Client software on the web server computer as follows.</span></span>

<span data-ttu-id="112ac-145">**配置 web 服务器 (特定的 SQL Server)**</span><span class="sxs-lookup"><span data-stu-id="112ac-145">**To configure the web server (a specific SQL Server)**</span></span>

<span data-ttu-id="112ac-146">**在 Microsoft SQL Server 6.5 中：**</span><span class="sxs-lookup"><span data-stu-id="112ac-146">**For Microsoft SQL Server 6.5:**</span></span>

1.  <span data-ttu-id="112ac-147">从**开始**菜单上，指向**程序**，指向**Microsoft SQL Server 6.5**，，然后单击**SQL 客户端配置实用工具**。</span><span class="sxs-lookup"><span data-stu-id="112ac-147">From the **Start** menu, point to **Programs**, point to **Microsoft SQL Server 6.5**, and then click **SQL Client Configuration Utility**.</span></span>

2.  <span data-ttu-id="112ac-148">单击**高级**选项卡。</span><span class="sxs-lookup"><span data-stu-id="112ac-148">Click the **Advanced** tab.</span></span>

3.  <span data-ttu-id="112ac-149">在**服务器**框中，键入要连接到使用**TCP/IP 套接字**的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="112ac-149">In the **Server** box, type the name of the server to connect to using **TCP/IP Sockets**.</span></span>

4.  <span data-ttu-id="112ac-150">在**DLL 名称**框中，选择**TCP/IP 套接字**。</span><span class="sxs-lookup"><span data-stu-id="112ac-150">In the **DLL Name** box, select **TCP/IP Sockets**.</span></span>

5.  <span data-ttu-id="112ac-151">单击**添加/修改**。</span><span class="sxs-lookup"><span data-stu-id="112ac-151">Click **Add/Modify**.</span></span> <span data-ttu-id="112ac-152">指向此服务器的所有数据源现在将都使用 TCP/IP 套接字。</span><span class="sxs-lookup"><span data-stu-id="112ac-152">All data sources pointing to this server will now use TCP/IP Sockets.</span></span>

6.  <span data-ttu-id="112ac-153">单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="112ac-153">Click **Done**.</span></span>

<span data-ttu-id="112ac-154">**在 Microsoft SQL Server 7.0 中：**</span><span class="sxs-lookup"><span data-stu-id="112ac-154">**For Microsoft SQL Server 7.0:**</span></span>

1.  <span data-ttu-id="112ac-155">从**开始**菜单上，指向**程序**，指向**Microsoft SQL Server 7.0**，，然后单击**客户端配置实用工具**。</span><span class="sxs-lookup"><span data-stu-id="112ac-155">From the **Start** menu, point to **Programs**, point to **Microsoft SQL Server 7.0**, and then click **Client Configuration Utility**.</span></span>

2.  <span data-ttu-id="112ac-156">单击**常规**选项卡。</span><span class="sxs-lookup"><span data-stu-id="112ac-156">Click the **General** tab.</span></span>

3.  <span data-ttu-id="112ac-157">单击“添加”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="112ac-157">Click **Add**.</span></span>

4.  <span data-ttu-id="112ac-158">在**服务器别名**框中输入服务器的别名。</span><span class="sxs-lookup"><span data-stu-id="112ac-158">Enter the alias of the server in the **Server alias** box.</span></span> <span data-ttu-id="112ac-159">在**网络库**框中，单击**TCP/IP**。</span><span class="sxs-lookup"><span data-stu-id="112ac-159">In the **Network libraries** box, click **TCP/IP**.</span></span> <span data-ttu-id="112ac-160">在**计算机名称**框中，输入侦听 TCP/IP 套接字客户端计算机的计算机名称。</span><span class="sxs-lookup"><span data-stu-id="112ac-160">In the **Computer name** box, enter the computer name of the computer that listens for TCP/IP Sockets clients.</span></span> <span data-ttu-id="112ac-161">在**端口号**框中，输入 SQL Server 侦听的端口。</span><span class="sxs-lookup"><span data-stu-id="112ac-161">In the **Port number** box, enter the port on which the SQL Server listens.</span></span>

5.  <span data-ttu-id="112ac-162">单击**确定**，再然后**确定**以退出该实用工具。</span><span class="sxs-lookup"><span data-stu-id="112ac-162">Click **OK**, and then **OK** again to exit the utility.</span></span>

