---
title: 配置安全模式或无限制模式的 DataFactory
TOCTitle: Configuring DataFactory for Safe or Unrestricted Modes
ms:assetid: 1516068f-1b02-3236-f6a9-9fdeff098e52
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248915(v=office.15)
ms:contentKeyID: 48543400
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: abb461473d15f163fac6ea00f2af5d39f7b40d0a
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468590"
---
# <a name="configuring-datafactory-for-safe-or-unrestricted-modes"></a>配置安全模式或无限制模式的 DataFactory


**适用于**： Access 2013 |Office 2013

默认情况下，ADO 采用"安全"[RDSServer.DataFactory](datafactory-object-rdsserver.md) 配置进行安装。RDS 服务器组件采用安全模式意味着：

1.  RDSServer.DataFactory 需要处理程序（通过设置注册表项进行批准）。

2.  默认处理程序 msdfmap.handler 已注册，显示在安全处理程序列表中，并被标记为默认处理程序。

3.  msdfmap.ini 文件安装在 Windows 目录中。在以三层模式使用 RDS 之前，必须根据需要配置此文件。

此外，还可以配置无限制的 **DataFactory** 安装。 **DataFactory** 可以在无自定义处理程序的情况下直接使用。用户仍可以通过修改连接字符串来使用自定义处理程序，但并不是必需的。有关使用 **RDSServer.DataFactory** 对象的潜在问题的详细信息，请参阅 [保护 RDS 应用程序](securing-rds-applications.md)。

对于安全配置的处理程序注册表项，可使用提供的注册表文件 handsafe.reg 进行设置。若要以安全模式运行，请运行 handsafe.reg。对于无限制配置的处理程序注册表项，可使用提供的注册表文件 handunsf.reg 进行设置。若要以无限制模式运行，请运行 handunsf.reg。

运行 handsafe.reg 或 handunsf.reg 之后，必须停止并重新启动 Web 服务器上的 World Wide Web Publishing Service，方法是：在命令窗口中键入命令"NET STOP W3SVC"和"NET START W3SVC"。

有关使用 RDS 的自定义处理程序功能的详细信息，请参阅技术文章"使用 RDS 2.1 中的自定义处理程序功能"。

