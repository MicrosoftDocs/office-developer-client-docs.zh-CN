---
title: 将 RDS 与 ODBC 连接池结合使用
TOCTitle: Using RDS with ODBC Connection Pooling
ms:assetid: 6e8b023a-d211-44cb-10af-d43174a5d4bc
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249437(v=office.15)
ms:contentKeyID: 48545513
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: ee66e68cb8eeaaca57c007dc64a9e2b3a8476ec7
ms.sourcegitcommit: a49b77f4c8cec69f90656a86f0872cf34c35968e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2018
ms.locfileid: "25606015"
---
# <a name="using-rds-with-odbc-connection-pooling"></a><span data-ttu-id="ae791-102">将 RDS 与 ODBC 连接池结合使用</span><span class="sxs-lookup"><span data-stu-id="ae791-102">Using RDS with ODBC Connection Pooling</span></span>


<span data-ttu-id="ae791-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="ae791-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="ae791-p101">如果您使用的是 ODBC 数据源，则可以在 Internet 信息服务 (IIS) 中使用连接池选项来实现对客户端负载的高性能处理。连接池是用于连接的资源管理器，可维护常用连接的打开状态。</span><span class="sxs-lookup"><span data-stu-id="ae791-p101">If you're using an ODBC data source, you can use the connection pooling option in Internet Information Services (IIS) to achieve high performance handling of client load. Connection pooling is a resource manager for connections, maintaining the open state on frequently used connections.</span></span>

<span data-ttu-id="ae791-106">若要启用连接池，请参考 Internet 信息服务文档。</span><span class="sxs-lookup"><span data-stu-id="ae791-106">To enable connection pooling, refer to the Internet Information Services documentation.</span></span>

<span data-ttu-id="ae791-107"><<<<<<< 标头请注意，启用连接池可能会使 Web 服务器受到其他限制，如 Microsoft Internet 信息服务文档中所述。</span><span class="sxs-lookup"><span data-stu-id="ae791-107"><<<<<<< HEAD Please note that enabling connection pooling may subject the Web server to other restrictions, as noted in the Microsoft Internet Information Services documentation.</span></span>
<span data-ttu-id="ae791-108">=== 请请注意，启用连接池可能会使 web 服务器受到其他限制，如 Microsoft Internet 信息服务文档中所述。</span><span class="sxs-lookup"><span data-stu-id="ae791-108">======= Please note that enabling connection pooling may subject the web server to other restrictions, as noted in the Microsoft Internet Information Services documentation.</span></span>
>>>>>>> <span data-ttu-id="ae791-109">master</span><span class="sxs-lookup"><span data-stu-id="ae791-109">master</span></span>

<span data-ttu-id="ae791-110">为了确保连接池稳定且提供额外的性能提升，必须将 Microsoft SQL Server 配置为使用 TCP/IP 套接字网络库。</span><span class="sxs-lookup"><span data-stu-id="ae791-110">To ensure that connection pooling is stable and provides additional performance gains, you must configure Microsoft SQL Server to use the TCP/IP Socket network library.</span></span>

<span data-ttu-id="ae791-111">为此，您需要执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="ae791-111">To do this, you need to:</span></span>

  - <span data-ttu-id="ae791-112">将 SQL Server 计算机配置为使用 TCP/IP 套接字。</span><span class="sxs-lookup"><span data-stu-id="ae791-112">Configure the SQL Server computer to use TCP/IP Sockets.</span></span>

<span data-ttu-id="ae791-113"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="ae791-113"><<<<<<< HEAD</span></span>
  - <span data-ttu-id="ae791-114">将 Web 服务器配置为使用 TCP/IP 套接字。</span><span class="sxs-lookup"><span data-stu-id="ae791-114">Configure the Web server to use TCP/IP Sockets.</span></span>
=======
  - <span data-ttu-id="ae791-115">Web 服务器配置为使用 TCP/IP 套接字。</span><span class="sxs-lookup"><span data-stu-id="ae791-115">Configure the web server to use TCP/IP Sockets.</span></span>
>>>>>>> <span data-ttu-id="ae791-116">master</span><span class="sxs-lookup"><span data-stu-id="ae791-116">master</span></span>

## <a name="configuring-the-sql-server-computer-to-use-tcpip-sockets"></a><span data-ttu-id="ae791-117">将 SQL Server 计算机配置为使用 TCP/IP 套接字</span><span class="sxs-lookup"><span data-stu-id="ae791-117">Configuring the SQL Server Computer to Use TCP/IP Sockets</span></span>

<span data-ttu-id="ae791-118">在 SQL Server 计算机上运行 SQL Server 安装程序，以便与数据源交互时使用 TCP/IP 套接字网络库。</span><span class="sxs-lookup"><span data-stu-id="ae791-118">On the SQL Server computer, run the SQL Server Setup program so that interactions with the data source use the TCP/IP Socket network library.</span></span>

<span data-ttu-id="ae791-119">**在 SQL Server 计算机上指定 TCP/IP 套接字网络库**</span><span class="sxs-lookup"><span data-stu-id="ae791-119">**To specify the TCP/IP Socket network library on the SQL Server computer**</span></span>

<span data-ttu-id="ae791-120">**在 Microsoft SQL Server 6.5 中：**</span><span class="sxs-lookup"><span data-stu-id="ae791-120">**In Microsoft SQL Server 6.5:**</span></span>

1.  <span data-ttu-id="ae791-121">从**开始**菜单上，指向**程序**，指向**Microsoft SQL Server 6.5**，，然后单击**SQL Setup**。</span><span class="sxs-lookup"><span data-stu-id="ae791-121">From the **Start** menu, point to **Programs**, point to **Microsoft SQL Server 6.5**, and then click **SQL Setup**.</span></span>

2.  <span data-ttu-id="ae791-122">单击**继续**两次。</span><span class="sxs-lookup"><span data-stu-id="ae791-122">Click **Continue** twice.</span></span>

3.  <span data-ttu-id="ae791-123">在**Microsoft SQL Server — 选项**对话框中，选择**更改网络支持**，然后单击**继续**。</span><span class="sxs-lookup"><span data-stu-id="ae791-123">In the **Microsoft SQL Server — Options** dialog box, select **Change Network Support**, and then click **Continue**.</span></span>

4.  <span data-ttu-id="ae791-124">请确保选择了**TCP/IP 套接字**复选框，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="ae791-124">Make sure the **TCP/IP Sockets** check box is selected, and click **OK**.</span></span>

5.  <span data-ttu-id="ae791-125">单击**继续**以完成，然后退出安装程序。</span><span class="sxs-lookup"><span data-stu-id="ae791-125">Click **Continue** to finish, and exit setup.</span></span>

<span data-ttu-id="ae791-126">**在 Microsoft SQL Server 7.0 中：**</span><span class="sxs-lookup"><span data-stu-id="ae791-126">**In Microsoft SQL Server 7.0:**</span></span>

1.  <span data-ttu-id="ae791-127">从**开始**菜单上，指向**程序**，指向**Microsoft SQL Server 7.0**，，然后单击**服务器网络实用工具**。</span><span class="sxs-lookup"><span data-stu-id="ae791-127">From the **Start** menu, point to **Programs**, point to **Microsoft SQL Server 7.0**, and then click **Server Network Utility**.</span></span>

2.  <span data-ttu-id="ae791-128">在对话框的**常规**选项卡上，单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="ae791-128">On the **General** tab of the dialog box, click **Add**.</span></span>

3.  <span data-ttu-id="ae791-129">在**添加网络库配置**对话框中，单击**TCP/IP**。</span><span class="sxs-lookup"><span data-stu-id="ae791-129">In the **Add Network Library Configuration** dialog box, click **TCP/IP**.</span></span>

4.  <span data-ttu-id="ae791-130">在**端口号**和**代理服务器地址**框中，输入网络管理员提供的端口号和代理地址。</span><span class="sxs-lookup"><span data-stu-id="ae791-130">In the **Port number** and **Proxy address** boxes, enter the port number and proxy address provided by your network administrator.</span></span>

5.  <span data-ttu-id="ae791-131">单击**确定**完成，然后退出安装程序。</span><span class="sxs-lookup"><span data-stu-id="ae791-131">Click **OK** to finish, and exit setup.</span></span>

<span data-ttu-id="ae791-132"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="ae791-132"><<<<<<< HEAD</span></span>
## <a name="configuring-the-web-server-to-use-tcpip-sockets"></a><span data-ttu-id="ae791-133">将 Web 服务器配置为使用 TCP/IP 套接字</span><span class="sxs-lookup"><span data-stu-id="ae791-133">Configuring the Web Server to Use TCP/IP Sockets</span></span>

<span data-ttu-id="ae791-p103">可以使用两个选项将 Web 服务器配置为使用 TCP/IP 套接字。您所执行的操作将取决于是从 Web 服务器访问所有 SQL Server，还是从 Web 服务器访问特定的 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="ae791-p103">There are two options for configuring the Web server to use TCP/IP Sockets. What you do depends on whether all SQL Servers are accessed from the Web server, or only a specific SQL Server is accessed from the Web server.</span></span>

<span data-ttu-id="ae791-p104">如果从 Web 服务器访问所有 SQL Server，则需要在 Web 服务器计算机上运行 SQL Server 客户端配置实用工具。下列步骤将所有通过该 IIS Web 服务器建立 SQL Server 连接所用的默认网络库更改为使用 TCP/IP 套接字网络库。</span><span class="sxs-lookup"><span data-stu-id="ae791-p104">If all SQL Servers are accessed from the Web server, you need to run the SQL Server Client Configuration Utility on the Web server computer. The following steps change the default network library for all SQL Server connections made from this IIS Web server to use the TCP/IP Sockets network library.</span></span>

<a name="to-configure-the-web-server-all-sql-servers"></a><span data-ttu-id="ae791-138">**配置 Web 服务器（所有的 SQL Server）**</span><span class="sxs-lookup"><span data-stu-id="ae791-138">**To configure the Web server (all SQL Servers)**</span></span>
=======
## <a name="configuring-the-web-server-to-use-tcpip-sockets"></a><span data-ttu-id="ae791-139">配置 web 服务器添加到使用 TCP/IP 套接字</span><span class="sxs-lookup"><span data-stu-id="ae791-139">Configuring the web Server to Use TCP/IP Sockets</span></span>

<span data-ttu-id="ae791-140">有两个选项的 web 服务器配置为使用 TCP/IP 套接字。</span><span class="sxs-lookup"><span data-stu-id="ae791-140">There are two options for configuring the web server to use TCP/IP Sockets.</span></span> <span data-ttu-id="ae791-141">执行哪些操作取决于是否所有的 SQL Server 访问来自 web 服务器，或仅特定的 SQL Server 访问来自 web 服务器。</span><span class="sxs-lookup"><span data-stu-id="ae791-141">What you do depends on whether all SQL Servers are accessed from the web server, or only a specific SQL Server is accessed from the web server.</span></span>

<span data-ttu-id="ae791-142">如果所有的 SQL Server 访问来自 web 服务器，您需要在 web 服务器计算机上运行 SQL Server 客户端配置实用工具。</span><span class="sxs-lookup"><span data-stu-id="ae791-142">If all SQL Servers are accessed from the web server, you need to run the SQL Server Client Configuration Utility on the web server computer.</span></span> <span data-ttu-id="ae791-143">以下步骤更改为使用 TCP/IP 套接字网络库通过此 IIS web 服务器所做的所有 SQL Server 连接的默认网络库。</span><span class="sxs-lookup"><span data-stu-id="ae791-143">The following steps change the default network library for all SQL Server connections made from this IIS web server to use the TCP/IP Sockets network library.</span></span>

<span data-ttu-id="ae791-144">**配置 web 服务器 (所有的 SQL Server)**</span><span class="sxs-lookup"><span data-stu-id="ae791-144">**To configure the web server (all SQL Servers)**</span></span>
>>>>>>> <span data-ttu-id="ae791-145">master</span><span class="sxs-lookup"><span data-stu-id="ae791-145">master</span></span>

<span data-ttu-id="ae791-146">**在 Microsoft SQL Server 6.5 中：**</span><span class="sxs-lookup"><span data-stu-id="ae791-146">**For Microsoft SQL Server 6.5:**</span></span>

1.  <span data-ttu-id="ae791-147">从**开始**菜单上，指向**程序**，指向**Microsoft SQL Server 6.5**，，然后单击**SQL 客户端配置实用工具**。</span><span class="sxs-lookup"><span data-stu-id="ae791-147">From the **Start** menu, point to **Programs**, point to **Microsoft SQL Server 6.5**, and then click **SQL Client Configuration Utility**.</span></span>

2.  <span data-ttu-id="ae791-148">单击**网络库**选项卡。</span><span class="sxs-lookup"><span data-stu-id="ae791-148">Click the **Net Library** tab.</span></span>

3.  <span data-ttu-id="ae791-149">在**默认网络**框中，选择**TCP/IP 套接字**。</span><span class="sxs-lookup"><span data-stu-id="ae791-149">In the **Default Network** box, select **TCP/IP Sockets**.</span></span>

4.  <span data-ttu-id="ae791-150">单击**完成**以保存更改并退出该实用工具。</span><span class="sxs-lookup"><span data-stu-id="ae791-150">Click **Done** to save changes and exit the utility.</span></span>

<span data-ttu-id="ae791-151">**在 Microsoft SQL Server 7.0 中：**</span><span class="sxs-lookup"><span data-stu-id="ae791-151">**For Microsoft SQL Server 7.0:**</span></span>

1.  <span data-ttu-id="ae791-152">从**开始**菜单上，指向**程序**，指向**Microsoft SQL Server 7.0**，，然后单击**客户端网络实用工具**。</span><span class="sxs-lookup"><span data-stu-id="ae791-152">From the **Start** menu, point to **Programs**, point to **Microsoft SQL Server 7.0**, and then click **Client Network Utility**.</span></span>

2.  <span data-ttu-id="ae791-153">单击**常规**选项卡。</span><span class="sxs-lookup"><span data-stu-id="ae791-153">Click the **General** tab.</span></span>

3.  <span data-ttu-id="ae791-154">在**默认网络库**框中，单击**TCP/IP**。</span><span class="sxs-lookup"><span data-stu-id="ae791-154">In the **Default network library** box, click **TCP/IP**.</span></span>

4.  <span data-ttu-id="ae791-155">单击**确定**以保存更改并退出该实用工具。</span><span class="sxs-lookup"><span data-stu-id="ae791-155">Click **OK** to save changes and exit the utility.</span></span>

<span data-ttu-id="ae791-156"><<<<<<< 标头如果特定的 SQL Server 访问从 Web 服务器，需要 Web 服务器计算机上运行 SQL Server 客户端配置实用工具。</span><span class="sxs-lookup"><span data-stu-id="ae791-156"><<<<<<< HEAD If a specific SQL Server is accessed from a Web server, you need to run the SQL Server Client Configuration Utility on the Web server computer.</span></span> <span data-ttu-id="ae791-157">若要更改特定 SQL Server 连接的网络库，请在 Web 服务器计算机上按如下方式配置 SQL Server 客户端软件。</span><span class="sxs-lookup"><span data-stu-id="ae791-157">To change the network library for a specific SQL Server connection, configure the SQL Server Client software on the Web server computer as follows.</span></span>

<a name="to-configure-the-web-server-a-specific-sql-server"></a><span data-ttu-id="ae791-158">**配置 Web 服务器（特定的 SQL Server）**</span><span class="sxs-lookup"><span data-stu-id="ae791-158">**To configure the Web server (a specific SQL Server)**</span></span>
=======
<span data-ttu-id="ae791-159">如果从 web 服务器访问特定的 SQL Server 时，您需要在 web 服务器计算机上运行 SQL Server 客户端配置实用工具。</span><span class="sxs-lookup"><span data-stu-id="ae791-159">If a specific SQL Server is accessed from a web server, you need to run the SQL Server Client Configuration Utility on the web server computer.</span></span> <span data-ttu-id="ae791-160">若要更改某个特定的 SQL Server 连接的网络库，配置 SQL Server 客户端上的软件 web 服务器计算机，如下所示。</span><span class="sxs-lookup"><span data-stu-id="ae791-160">To change the network library for a specific SQL Server connection, configure the SQL Server Client software on the web server computer as follows.</span></span>

<span data-ttu-id="ae791-161">**配置 web 服务器 (特定的 SQL Server)**</span><span class="sxs-lookup"><span data-stu-id="ae791-161">**To configure the web server (a specific SQL Server)**</span></span>
>>>>>>> <span data-ttu-id="ae791-162">master</span><span class="sxs-lookup"><span data-stu-id="ae791-162">master</span></span>

<span data-ttu-id="ae791-163">**在 Microsoft SQL Server 6.5 中：**</span><span class="sxs-lookup"><span data-stu-id="ae791-163">**For Microsoft SQL Server 6.5:**</span></span>

1.  <span data-ttu-id="ae791-164">从**开始**菜单上，指向**程序**，指向**Microsoft SQL Server 6.5**，，然后单击**SQL 客户端配置实用工具**。</span><span class="sxs-lookup"><span data-stu-id="ae791-164">From the **Start** menu, point to **Programs**, point to **Microsoft SQL Server 6.5**, and then click **SQL Client Configuration Utility**.</span></span>

2.  <span data-ttu-id="ae791-165">单击**高级**选项卡。</span><span class="sxs-lookup"><span data-stu-id="ae791-165">Click the **Advanced** tab.</span></span>

3.  <span data-ttu-id="ae791-166">在**服务器**框中，键入要连接到使用**TCP/IP 套接字**的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="ae791-166">In the **Server** box, type the name of the server to connect to using **TCP/IP Sockets**.</span></span>

4.  <span data-ttu-id="ae791-167">在**DLL 名称**框中，选择**TCP/IP 套接字**。</span><span class="sxs-lookup"><span data-stu-id="ae791-167">In the **DLL Name** box, select **TCP/IP Sockets**.</span></span>

5.  <span data-ttu-id="ae791-168">单击**添加/修改**。</span><span class="sxs-lookup"><span data-stu-id="ae791-168">Click **Add/Modify**.</span></span> <span data-ttu-id="ae791-169">指向此服务器的所有数据源现在将都使用 TCP/IP 套接字。</span><span class="sxs-lookup"><span data-stu-id="ae791-169">All data sources pointing to this server will now use TCP/IP Sockets.</span></span>

6.  <span data-ttu-id="ae791-170">单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="ae791-170">Click **Done**.</span></span>

<span data-ttu-id="ae791-171">**在 Microsoft SQL Server 7.0 中：**</span><span class="sxs-lookup"><span data-stu-id="ae791-171">**For Microsoft SQL Server 7.0:**</span></span>

1.  <span data-ttu-id="ae791-172">从**开始**菜单上，指向**程序**，指向**Microsoft SQL Server 7.0**，，然后单击**客户端配置实用工具**。</span><span class="sxs-lookup"><span data-stu-id="ae791-172">From the **Start** menu, point to **Programs**, point to **Microsoft SQL Server 7.0**, and then click **Client Configuration Utility**.</span></span>

2.  <span data-ttu-id="ae791-173">单击**常规**选项卡。</span><span class="sxs-lookup"><span data-stu-id="ae791-173">Click the **General** tab.</span></span>

3.  <span data-ttu-id="ae791-174">单击“添加”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ae791-174">Click **Add**.</span></span>

4.  <span data-ttu-id="ae791-175">在**服务器别名**框中输入服务器的别名。</span><span class="sxs-lookup"><span data-stu-id="ae791-175">Enter the alias of the server in the **Server alias** box.</span></span> <span data-ttu-id="ae791-176">在**网络库**框中，单击**TCP/IP**。</span><span class="sxs-lookup"><span data-stu-id="ae791-176">In the **Network libraries** box, click **TCP/IP**.</span></span> <span data-ttu-id="ae791-177">在**计算机名称**框中，输入侦听 TCP/IP 套接字客户端计算机的计算机名称。</span><span class="sxs-lookup"><span data-stu-id="ae791-177">In the **Computer name** box, enter the computer name of the computer that listens for TCP/IP Sockets clients.</span></span> <span data-ttu-id="ae791-178">在**端口号**框中，输入 SQL Server 侦听的端口。</span><span class="sxs-lookup"><span data-stu-id="ae791-178">In the **Port number** box, enter the port on which the SQL Server listens.</span></span>

5.  <span data-ttu-id="ae791-179">单击**确定**，再然后**确定**以退出该实用工具。</span><span class="sxs-lookup"><span data-stu-id="ae791-179">Click **OK**, and then **OK** again to exit the utility.</span></span>

