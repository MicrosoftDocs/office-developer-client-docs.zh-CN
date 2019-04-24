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
# <a name="using-rds-with-odbc-connection-pooling"></a>将 RDS 与 ODBC 连接池结合使用


**适用于**：Access 2013、Office 2013

如果您使用的是 ODBC 数据源，则可以在 Internet 信息服务 (IIS) 中使用连接池选项来实现对客户端负载的高性能处理。连接池是用于连接的资源管理器，可维护常用连接的打开状态。

若要启用连接池，请参考 Internet 信息服务文档。

请注意, 启用连接池可能会导致 web 服务器受到其他限制的约束, 如 Microsoft Internet information Services 文档中所述。

为了确保连接池稳定且提供额外的性能提升，必须将 Microsoft SQL Server 配置为使用 TCP/IP 套接字网络库。

为此，您需要执行下列操作：

  - 将 SQL Server 计算机配置为使用 TCP/IP 套接字。

  - 将 web 服务器配置为使用 tcp/ip 套接字。

## <a name="configuring-the-sql-server-computer-to-use-tcpip-sockets"></a>将 SQL Server 计算机配置为使用 TCP/IP 套接字

在 SQL Server 计算机上运行 SQL Server 安装程序，以便与数据源交互时使用 TCP/IP 套接字网络库。

**在 SQL Server 计算机上指定 TCP/IP 套接字网络库**

**在 Microsoft SQL Server 6.5 中：**

1.  From the **Start** menu, point to **Programs**, point to **Microsoft SQL Server 6.5**, and then click **SQL Setup**.

2.  单击****“继续”两次。

3.  在****“Microsoft SQL Server - 选项”对话框中，选择****“更改网络支持”，然后单击****“继续”。

4.  请确保****“TCP/IP 套接字”复选框处于选中状态，然后单击****“确定”。

5.  单击****“继续”完成操作，然后退出安装程序。

**在 Microsoft SQL Server 7.0 中：**

1.  From the **Start** menu, point to **Programs**, point to **Microsoft SQL Server 7.0**, and then click **Server Network Utility**.

2.  在该对话框的****“常规”选项卡上，单击****“添加”。

3.  在****“添加网络库配置”对话框中，单击****“TCP/IP”。

4.  在****“端口号”和****“代理地址”框中，输入网络管理员提供的端口号和代理地址。

5.  单击****“确定”完成操作，然后退出安装程序。

## <a name="configuring-the-web-server-to-use-tcpip-sockets"></a>将 web 服务器配置为使用 tcp/ip 套接字

有两种方法可用于将 web 服务器配置为使用 tcp/ip 套接字。 您执行的操作取决于是否从 web 服务器访问了所有 SQL 服务器, 或者从 web 服务器访问的是仅一个特定的 sql server。

如果从 web 服务器访问所有 sql 服务器, 则需要在 web 服务器计算机上运行 SQL server 客户端配置实用工具。 以下步骤将更改从该 IIS web 服务器进行的所有 SQL Server 连接的默认网络库, 以使用 tcp/ip 套接字网络库。

**配置 web 服务器 (所有 SQL server)**

**在 Microsoft SQL Server 6.5 中：**

1.  From the **Start** menu, point to **Programs**, point to **Microsoft SQL Server 6.5**, and then click **SQL Client Configuration Utility**.

2.  单击****“网络库”选项卡。

3.  在****“默认网络”框中，选择****“TCP/IP 套接字”。

4.  单击****“完成”保存所做的更改并退出该实用工具。

**在 Microsoft SQL Server 7.0 中：**

1.  From the **Start** menu, point to **Programs**, point to **Microsoft SQL Server 7.0**, and then click **Client Network Utility**.

2.  单击“常规”**** 选项卡。

3.  在****“默认网络库”框中，单击****“TCP/IP”。

4.  单击****“确定”保存更改并退出该实用工具。

如果从 web 服务器访问特定的 SQL server, 则需要在 web 服务器计算机上运行 SQL Server 客户端配置实用工具。 若要更改特定 SQL server 连接的网络库, 请在 web 服务器计算机上配置 SQL Server 客户端软件, 如下所示。

**配置 web 服务器 (特定的 SQL server)**

**在 Microsoft SQL Server 6.5 中：**

1.  From the **Start** menu, point to **Programs**, point to **Microsoft SQL Server 6.5**, and then click **SQL Client Configuration Utility**.

2.  单击****“高级”选项卡。

3.  在****“服务器”框中，键入要使用****“TCP/IP 套接字”连接到的服务器的名称。

4.  在****“DLL 名称”框中，选择****“TCP/IP 套接字”。

5.  Click **Add/Modify**. All data sources pointing to this server will now use TCP/IP Sockets.

6.  Click **Done**.

**在 Microsoft SQL Server 7.0 中：**

1.  From the **Start** menu, point to **Programs**, point to **Microsoft SQL Server 7.0**, and then click **Client Configuration Utility**.

2.  单击****“常规”选项卡。

3.  单击****“添加”。

4.  Enter the alias of the server in the **Server alias** box. In the **Network libraries** box, click **TCP/IP**. In the **Computer name** box, enter the computer name of the computer that listens for TCP/IP Sockets clients. In the **Port number** box, enter the port on which the SQL Server listens.

5.  Click **OK**, and then **OK** again to exit the utility.

