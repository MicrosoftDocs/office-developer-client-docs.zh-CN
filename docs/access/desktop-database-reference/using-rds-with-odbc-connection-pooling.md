---
title: 将 RDS 与 ODBC 连接池结合使用
TOCTitle: Using RDS with ODBC Connection Pooling
ms:assetid: 6e8b023a-d211-44cb-10af-d43174a5d4bc
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249437(v=office.15)
ms:contentKeyID: 48545513
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 7baaf81d7a5d6a91416ea5baf8ba57745612740e
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25465875"
---
# <a name="using-rds-with-odbc-connection-pooling"></a>将 RDS 与 ODBC 连接池结合使用


**适用于**： Access 2013 |Office 2013

如果您使用的是 ODBC 数据源，则可以在 Internet 信息服务 (IIS) 中使用连接池选项来实现对客户端负载的高性能处理。连接池是用于连接的资源管理器，可维护常用连接的打开状态。

若要启用连接池，请参考 Internet 信息服务文档。

请注意，如 Microsoft Internet 信息服务文档中所述，启用连接池可能会使 Web 服务器受到其他限制。

为了确保连接池稳定且提供额外的性能提升，必须将 Microsoft SQL Server 配置为使用 TCP/IP 套接字网络库。

为此，您需要执行下列操作：

  - 将 SQL Server 计算机配置为使用 TCP/IP 套接字。

  - 将 Web 服务器配置为使用 TCP/IP 套接字。

## <a name="configuring-the-sql-server-computer-to-use-tcpip-sockets"></a>将 SQL Server 计算机配置为使用 TCP/IP 套接字

在 SQL Server 计算机上运行 SQL Server 安装程序，以便与数据源交互时使用 TCP/IP 套接字网络库。

**在 SQL Server 计算机上指定 TCP/IP 套接字网络库**

**在 Microsoft SQL Server 6.5 中：**

1.  从**开始**菜单上，指向**程序**，指向**Microsoft SQL Server 6.5**，，然后单击**SQL Setup**。

2.  单击**继续**两次。

3.  在**Microsoft SQL Server — 选项**对话框中，选择**更改网络支持**，然后单击**继续**。

4.  请确保选择了**TCP/IP 套接字**复选框，然后单击**确定**。

5.  单击**继续**以完成，然后退出安装程序。

**在 Microsoft SQL Server 7.0 中：**

1.  从**开始**菜单上，指向**程序**，指向**Microsoft SQL Server 7.0**，，然后单击**服务器网络实用工具**。

2.  在对话框的**常规**选项卡上，单击**添加**。

3.  在**添加网络库配置**对话框中，单击**TCP/IP**。

4.  在**端口号**和**代理服务器地址**框中，输入网络管理员提供的端口号和代理地址。

5.  单击**确定**完成，然后退出安装程序。

## <a name="configuring-the-web-server-to-use-tcpip-sockets"></a>将 Web 服务器配置为使用 TCP/IP 套接字

可以使用两个选项将 Web 服务器配置为使用 TCP/IP 套接字。您所执行的操作将取决于是从 Web 服务器访问所有 SQL Server，还是从 Web 服务器访问特定的 SQL Server。

如果从 Web 服务器访问所有 SQL Server，则需要在 Web 服务器计算机上运行 SQL Server 客户端配置实用工具。下列步骤将所有通过该 IIS Web 服务器建立 SQL Server 连接所用的默认网络库更改为使用 TCP/IP 套接字网络库。

**配置 Web 服务器（所有的 SQL Server）**

**在 Microsoft SQL Server 6.5 中：**

1.  从**开始**菜单上，指向**程序**，指向**Microsoft SQL Server 6.5**，，然后单击**SQL 客户端配置实用工具**。

2.  单击**网络库**选项卡。

3.  在**默认网络**框中，选择**TCP/IP 套接字**。

4.  单击**完成**以保存更改并退出该实用工具。

**在 Microsoft SQL Server 7.0 中：**

1.  从**开始**菜单上，指向**程序**，指向**Microsoft SQL Server 7.0**，，然后单击**客户端网络实用工具**。

2.  单击**常规**选项卡。

3.  在**默认网络库**框中，单击**TCP/IP**。

4.  单击**确定**以保存更改并退出该实用工具。

如果从 Web 服务器访问特定的 SQL Server，则需要在 Web 服务器计算机上运行 SQL Server 客户端配置实用工具。若要更改特定 SQL Server 连接的网络库，请在 Web 服务器计算机上按如下方式配置 SQL Server 客户端软件。

**配置 Web 服务器（特定的 SQL Server）**

**在 Microsoft SQL Server 6.5 中：**

1.  从**开始**菜单上，指向**程序**，指向**Microsoft SQL Server 6.5**，，然后单击**SQL 客户端配置实用工具**。

2.  单击**高级**选项卡。

3.  在**服务器**框中，键入要连接到使用**TCP/IP 套接字**的服务器的名称。

4.  在**DLL 名称**框中，选择**TCP/IP 套接字**。

5.  单击**添加/修改**。 指向此服务器的所有数据源现在将都使用 TCP/IP 套接字。

6.  单击**完成**。

**在 Microsoft SQL Server 7.0 中：**

1.  从**开始**菜单上，指向**程序**，指向**Microsoft SQL Server 7.0**，，然后单击**客户端配置实用工具**。

2.  单击**常规**选项卡。

3.  单击“添加”****。

4.  在**服务器别名**框中输入服务器的别名。 在**网络库**框中，单击**TCP/IP**。 在**计算机名称**框中，输入侦听 TCP/IP 套接字客户端计算机的计算机名称。 在**端口号**框中，输入 SQL Server 侦听的端口。

5.  单击**确定**，再然后**确定**以退出该实用工具。

