---
title: 将 RDS 与 ODBC 连接池结合使用
TOCTitle: Using RDS with ODBC Connection Pooling
ms:assetid: 6e8b023a-d211-44cb-10af-d43174a5d4bc
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249437(v=office.15)
ms:contentKeyID: 48545513
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 87d380fdc52cdee2aa834fd6e78ff1b761a0e93a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32312115"
---
# <a name="using-rds-with-odbc-connection-pooling"></a><span data-ttu-id="4fd68-102">将 RDS 与 ODBC 连接池结合使用</span><span class="sxs-lookup"><span data-stu-id="4fd68-102">Using RDS with ODBC connection pooling</span></span>


<span data-ttu-id="4fd68-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="4fd68-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="4fd68-p101">如果您使用的是 ODBC 数据源，则可以在 Internet 信息服务 (IIS) 中使用连接池选项来实现对客户端负载的高性能处理。连接池是用于连接的资源管理器，可维护常用连接的打开状态。</span><span class="sxs-lookup"><span data-stu-id="4fd68-p101">If you're using an ODBC data source, you can use the connection pooling option in Internet Information Services (IIS) to achieve high performance handling of client load. Connection pooling is a resource manager for connections, maintaining the open state on frequently used connections.</span></span>

<span data-ttu-id="4fd68-106">若要启用连接池，请参考 Internet 信息服务文档。</span><span class="sxs-lookup"><span data-stu-id="4fd68-106">To enable connection pooling, refer to the Internet Information Services documentation.</span></span>

<span data-ttu-id="4fd68-107">请注意, 启用连接池可能会导致 web 服务器受到其他限制的约束, 如 Microsoft Internet information Services 文档中所述。</span><span class="sxs-lookup"><span data-stu-id="4fd68-107">Please note that enabling connection pooling may subject the web server to other restrictions, as noted in the Microsoft Internet Information Services documentation.</span></span>

<span data-ttu-id="4fd68-108">为了确保连接池稳定且提供额外的性能提升，必须将 Microsoft SQL Server 配置为使用 TCP/IP 套接字网络库。</span><span class="sxs-lookup"><span data-stu-id="4fd68-108">To ensure that connection pooling is stable and provides additional performance gains, you must configure Microsoft SQL Server to use the TCP/IP Socket network library.</span></span>

<span data-ttu-id="4fd68-109">为此，您需要执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="4fd68-109">To do this, you need to:</span></span>

  - <span data-ttu-id="4fd68-110">将 SQL Server 计算机配置为使用 TCP/IP 套接字。</span><span class="sxs-lookup"><span data-stu-id="4fd68-110">Configure the SQL Server computer to use TCP/IP Sockets.</span></span>

  - <span data-ttu-id="4fd68-111">将 web 服务器配置为使用 tcp/ip 套接字。</span><span class="sxs-lookup"><span data-stu-id="4fd68-111">Configure the web server to use TCP/IP Sockets.</span></span>

## <a name="configuring-the-sql-server-computer-to-use-tcpip-sockets"></a><span data-ttu-id="4fd68-112">将 SQL Server 计算机配置为使用 TCP/IP 套接字</span><span class="sxs-lookup"><span data-stu-id="4fd68-112">Configuring the SQL Server Computer to Use TCP/IP Sockets</span></span>

<span data-ttu-id="4fd68-113">在 SQL Server 计算机上运行 SQL Server 安装程序，以便与数据源交互时使用 TCP/IP 套接字网络库。</span><span class="sxs-lookup"><span data-stu-id="4fd68-113">On the SQL Server computer, run the SQL Server Setup program so that interactions with the data source use the TCP/IP Socket network library.</span></span>

<span data-ttu-id="4fd68-114">**在 SQL Server 计算机上指定 TCP/IP 套接字网络库**</span><span class="sxs-lookup"><span data-stu-id="4fd68-114">**To specify the TCP/IP Socket network library on the SQL Server computer**</span></span>

<span data-ttu-id="4fd68-115">**在 Microsoft SQL Server 6.5 中：**</span><span class="sxs-lookup"><span data-stu-id="4fd68-115">**In Microsoft SQL Server 6.5:**</span></span>

1.  <span data-ttu-id="4fd68-116">From the **Start** menu, point to **Programs**, point to **Microsoft SQL Server 6.5**, and then click **SQL Setup**.</span><span class="sxs-lookup"><span data-stu-id="4fd68-116">From the **Start** menu, point to **Programs**, point to **Microsoft SQL Server 6.5**, and then click **SQL Setup**.</span></span>

2.  <span data-ttu-id="4fd68-117">单击\*\*\*\*“继续”两次。</span><span class="sxs-lookup"><span data-stu-id="4fd68-117">Click **Continue** twice.</span></span>

3.  <span data-ttu-id="4fd68-118">在\*\*\*\*“Microsoft SQL Server - 选项”对话框中，选择\*\*\*\*“更改网络支持”，然后单击\*\*\*\*“继续”。</span><span class="sxs-lookup"><span data-stu-id="4fd68-118">In the **Microsoft SQL Server — Options** dialog box, select **Change Network Support**, and then click **Continue**.</span></span>

4.  <span data-ttu-id="4fd68-119">请确保\*\*\*\*“TCP/IP 套接字”复选框处于选中状态，然后单击\*\*\*\*“确定”。</span><span class="sxs-lookup"><span data-stu-id="4fd68-119">Make sure the **TCP/IP Sockets** check box is selected, and click **OK**.</span></span>

5.  <span data-ttu-id="4fd68-120">单击\*\*\*\*“继续”完成操作，然后退出安装程序。</span><span class="sxs-lookup"><span data-stu-id="4fd68-120">Click **Continue** to finish, and exit setup.</span></span>

<span data-ttu-id="4fd68-121">**在 Microsoft SQL Server 7.0 中：**</span><span class="sxs-lookup"><span data-stu-id="4fd68-121">**In Microsoft SQL Server 7.0:**</span></span>

1.  <span data-ttu-id="4fd68-122">From the **Start** menu, point to **Programs**, point to **Microsoft SQL Server 7.0**, and then click **Server Network Utility**.</span><span class="sxs-lookup"><span data-stu-id="4fd68-122">From the **Start** menu, point to **Programs**, point to **Microsoft SQL Server 7.0**, and then click **Server Network Utility**.</span></span>

2.  <span data-ttu-id="4fd68-123">在该对话框的\*\*\*\*“常规”选项卡上，单击\*\*\*\*“添加”。</span><span class="sxs-lookup"><span data-stu-id="4fd68-123">On the **General** tab of the dialog box, click **Add**.</span></span>

3.  <span data-ttu-id="4fd68-124">在\*\*\*\*“添加网络库配置”对话框中，单击\*\*\*\*“TCP/IP”。</span><span class="sxs-lookup"><span data-stu-id="4fd68-124">In the **Add Network Library Configuration** dialog box, click **TCP/IP**.</span></span>

4.  <span data-ttu-id="4fd68-125">在\*\*\*\*“端口号”和\*\*\*\*“代理地址”框中，输入网络管理员提供的端口号和代理地址。</span><span class="sxs-lookup"><span data-stu-id="4fd68-125">In the **Port number** and **Proxy address** boxes, enter the port number and proxy address provided by your network administrator.</span></span>

5.  <span data-ttu-id="4fd68-126">单击\*\*\*\*“确定”完成操作，然后退出安装程序。</span><span class="sxs-lookup"><span data-stu-id="4fd68-126">Click **OK** to finish, and exit setup.</span></span>

## <a name="configuring-the-web-server-to-use-tcpip-sockets"></a><span data-ttu-id="4fd68-127">将 web 服务器配置为使用 tcp/ip 套接字</span><span class="sxs-lookup"><span data-stu-id="4fd68-127">Configuring the web Server to Use TCP/IP Sockets</span></span>

<span data-ttu-id="4fd68-128">有两种方法可用于将 web 服务器配置为使用 tcp/ip 套接字。</span><span class="sxs-lookup"><span data-stu-id="4fd68-128">There are two options for configuring the web server to use TCP/IP Sockets.</span></span> <span data-ttu-id="4fd68-129">您执行的操作取决于是否从 web 服务器访问了所有 SQL 服务器, 或者从 web 服务器访问的是仅一个特定的 sql server。</span><span class="sxs-lookup"><span data-stu-id="4fd68-129">What you do depends on whether all SQL Servers are accessed from the web server, or only a specific SQL Server is accessed from the web server.</span></span>

<span data-ttu-id="4fd68-130">如果从 web 服务器访问所有 sql 服务器, 则需要在 web 服务器计算机上运行 SQL server 客户端配置实用工具。</span><span class="sxs-lookup"><span data-stu-id="4fd68-130">If all SQL Servers are accessed from the web server, you need to run the SQL Server Client Configuration Utility on the web server computer.</span></span> <span data-ttu-id="4fd68-131">以下步骤将更改从该 IIS web 服务器进行的所有 SQL Server 连接的默认网络库, 以使用 tcp/ip 套接字网络库。</span><span class="sxs-lookup"><span data-stu-id="4fd68-131">The following steps change the default network library for all SQL Server connections made from this IIS web server to use the TCP/IP Sockets network library.</span></span>

<span data-ttu-id="4fd68-132">**配置 web 服务器 (所有 SQL server)**</span><span class="sxs-lookup"><span data-stu-id="4fd68-132">**To configure the web server (all SQL Servers)**</span></span>

<span data-ttu-id="4fd68-133">**在 Microsoft SQL Server 6.5 中：**</span><span class="sxs-lookup"><span data-stu-id="4fd68-133">**For Microsoft SQL Server 6.5:**</span></span>

1.  <span data-ttu-id="4fd68-134">From the **Start** menu, point to **Programs**, point to **Microsoft SQL Server 6.5**, and then click **SQL Client Configuration Utility**.</span><span class="sxs-lookup"><span data-stu-id="4fd68-134">From the **Start** menu, point to **Programs**, point to **Microsoft SQL Server 6.5**, and then click **SQL Client Configuration Utility**.</span></span>

2.  <span data-ttu-id="4fd68-135">单击\*\*\*\*“网络库”选项卡。</span><span class="sxs-lookup"><span data-stu-id="4fd68-135">Click the **Net Library** tab.</span></span>

3.  <span data-ttu-id="4fd68-136">在\*\*\*\*“默认网络”框中，选择\*\*\*\*“TCP/IP 套接字”。</span><span class="sxs-lookup"><span data-stu-id="4fd68-136">In the **Default Network** box, select **TCP/IP Sockets**.</span></span>

4.  <span data-ttu-id="4fd68-137">单击\*\*\*\*“完成”保存所做的更改并退出该实用工具。</span><span class="sxs-lookup"><span data-stu-id="4fd68-137">Click **Done** to save changes and exit the utility.</span></span>

<span data-ttu-id="4fd68-138">**在 Microsoft SQL Server 7.0 中：**</span><span class="sxs-lookup"><span data-stu-id="4fd68-138">**For Microsoft SQL Server 7.0:**</span></span>

1.  <span data-ttu-id="4fd68-139">From the **Start** menu, point to **Programs**, point to **Microsoft SQL Server 7.0**, and then click **Client Network Utility**.</span><span class="sxs-lookup"><span data-stu-id="4fd68-139">From the **Start** menu, point to **Programs**, point to **Microsoft SQL Server 7.0**, and then click **Client Network Utility**.</span></span>

2.  <span data-ttu-id="4fd68-140">单击“常规”\*\*\*\* 选项卡。</span><span class="sxs-lookup"><span data-stu-id="4fd68-140">Click the **General** tab.</span></span>

3.  <span data-ttu-id="4fd68-141">在\*\*\*\*“默认网络库”框中，单击\*\*\*\*“TCP/IP”。</span><span class="sxs-lookup"><span data-stu-id="4fd68-141">In the **Default network library** box, click **TCP/IP**.</span></span>

4.  <span data-ttu-id="4fd68-142">单击\*\*\*\*“确定”保存更改并退出该实用工具。</span><span class="sxs-lookup"><span data-stu-id="4fd68-142">Click **OK** to save changes and exit the utility.</span></span>

<span data-ttu-id="4fd68-143">如果从 web 服务器访问特定的 SQL server, 则需要在 web 服务器计算机上运行 SQL Server 客户端配置实用工具。</span><span class="sxs-lookup"><span data-stu-id="4fd68-143">If a specific SQL Server is accessed from a web server, you need to run the SQL Server Client Configuration Utility on the web server computer.</span></span> <span data-ttu-id="4fd68-144">若要更改特定 SQL server 连接的网络库, 请在 web 服务器计算机上配置 SQL Server 客户端软件, 如下所示。</span><span class="sxs-lookup"><span data-stu-id="4fd68-144">To change the network library for a specific SQL Server connection, configure the SQL Server Client software on the web server computer as follows.</span></span>

<span data-ttu-id="4fd68-145">**配置 web 服务器 (特定的 SQL server)**</span><span class="sxs-lookup"><span data-stu-id="4fd68-145">**To configure the web server (a specific SQL Server)**</span></span>

<span data-ttu-id="4fd68-146">**在 Microsoft SQL Server 6.5 中：**</span><span class="sxs-lookup"><span data-stu-id="4fd68-146">**For Microsoft SQL Server 6.5:**</span></span>

1.  <span data-ttu-id="4fd68-147">From the **Start** menu, point to **Programs**, point to **Microsoft SQL Server 6.5**, and then click **SQL Client Configuration Utility**.</span><span class="sxs-lookup"><span data-stu-id="4fd68-147">From the **Start** menu, point to **Programs**, point to **Microsoft SQL Server 6.5**, and then click **SQL Client Configuration Utility**.</span></span>

2.  <span data-ttu-id="4fd68-148">单击\*\*\*\*“高级”选项卡。</span><span class="sxs-lookup"><span data-stu-id="4fd68-148">Click the **Advanced** tab.</span></span>

3.  <span data-ttu-id="4fd68-149">在\*\*\*\*“服务器”框中，键入要使用\*\*\*\*“TCP/IP 套接字”连接到的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="4fd68-149">In the **Server** box, type the name of the server to connect to using **TCP/IP Sockets**.</span></span>

4.  <span data-ttu-id="4fd68-150">在\*\*\*\*“DLL 名称”框中，选择\*\*\*\*“TCP/IP 套接字”。</span><span class="sxs-lookup"><span data-stu-id="4fd68-150">In the **DLL Name** box, select **TCP/IP Sockets**.</span></span>

5.  <span data-ttu-id="4fd68-p105">Click **Add/Modify**. All data sources pointing to this server will now use TCP/IP Sockets.</span><span class="sxs-lookup"><span data-stu-id="4fd68-p105">Click **Add/Modify**. All data sources pointing to this server will now use TCP/IP Sockets.</span></span>

6.  <span data-ttu-id="4fd68-153">Click **Done**.</span><span class="sxs-lookup"><span data-stu-id="4fd68-153">Click **Done**.</span></span>

<span data-ttu-id="4fd68-154">**在 Microsoft SQL Server 7.0 中：**</span><span class="sxs-lookup"><span data-stu-id="4fd68-154">**For Microsoft SQL Server 7.0:**</span></span>

1.  <span data-ttu-id="4fd68-155">From the **Start** menu, point to **Programs**, point to **Microsoft SQL Server 7.0**, and then click **Client Configuration Utility**.</span><span class="sxs-lookup"><span data-stu-id="4fd68-155">From the **Start** menu, point to **Programs**, point to **Microsoft SQL Server 7.0**, and then click **Client Configuration Utility**.</span></span>

2.  <span data-ttu-id="4fd68-156">单击\*\*\*\*“常规”选项卡。</span><span class="sxs-lookup"><span data-stu-id="4fd68-156">Click the **General** tab.</span></span>

3.  <span data-ttu-id="4fd68-157">单击\*\*\*\*“添加”。</span><span class="sxs-lookup"><span data-stu-id="4fd68-157">Click **Add**.</span></span>

4.  <span data-ttu-id="4fd68-p106">Enter the alias of the server in the **Server alias** box. In the **Network libraries** box, click **TCP/IP**. In the **Computer name** box, enter the computer name of the computer that listens for TCP/IP Sockets clients. In the **Port number** box, enter the port on which the SQL Server listens.</span><span class="sxs-lookup"><span data-stu-id="4fd68-p106">Enter the alias of the server in the **Server alias** box. In the **Network libraries** box, click **TCP/IP**. In the **Computer name** box, enter the computer name of the computer that listens for TCP/IP Sockets clients. In the **Port number** box, enter the port on which the SQL Server listens.</span></span>

5.  <span data-ttu-id="4fd68-162">Click **OK**, and then **OK** again to exit the utility.</span><span class="sxs-lookup"><span data-stu-id="4fd68-162">Click **OK**, and then **OK** again to exit the utility.</span></span>

