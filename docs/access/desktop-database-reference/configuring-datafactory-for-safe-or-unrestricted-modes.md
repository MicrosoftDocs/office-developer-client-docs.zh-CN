---
title: 配置安全模式或无限制模式的 DataFactory
TOCTitle: Configuring DataFactory for Safe or Unrestricted Modes
ms:assetid: 1516068f-1b02-3236-f6a9-9fdeff098e52
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248915(v=office.15)
ms:contentKeyID: 48543400
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 4f3658f3fdefeb87813319e4ed0313fe5c6032cf
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25882264"
---
# <a name="configuring-datafactory-for-safe-or-unrestricted-modes"></a>配置安全模式或无限制模式的 DataFactory


**适用于**： Access 2013、 Office 2013

默认情况下，ADO 采用"安全"[RDSServer.DataFactory](datafactory-object-rdsserver.md) 配置进行安装。RDS 服务器组件采用安全模式意味着：

1.  RDSServer.DataFactory 需要处理程序（通过设置注册表项进行批准）。

2.  默认处理程序 msdfmap.handler 已注册，显示在安全处理程序列表中，并被标记为默认处理程序。

3.  msdfmap.ini 文件安装在 Windows 目录中。在以三层模式使用 RDS 之前，必须根据需要配置此文件。

此外，还可以配置无限制的 **DataFactory** 安装。 **DataFactory** 可以在无自定义处理程序的情况下直接使用。 用户仍可以通过修改连接字符串来使用自定义处理程序，但并不是必需的。 有关使用**RDSServer.DataFactory**对象的影响的详细信息，请参阅[保护 RDS 应用程序](securing-rds-applications.md)。

对于安全配置的处理程序注册表项，可使用提供的注册表文件 handsafe.reg 进行设置。若要以安全模式运行，请运行 handsafe.reg。对于无限制配置的处理程序注册表项，可使用提供的注册表文件 handunsf.reg 进行设置。若要以无限制模式运行，请运行 handunsf.reg。

运行后 handsafe.reg 或 handunsf.reg，您必须停止并通过在命令窗口中键入以下命令重新启动 web 服务器上的 World Wide Web 发布服务:"NET 停止 W3SVC"和"NET 启动 W3SVC"。

有关使用 RDS 的自定义处理程序功能的详细信息，请参阅技术文章"使用 RDS 2.1 中的自定义处理程序功能"。

