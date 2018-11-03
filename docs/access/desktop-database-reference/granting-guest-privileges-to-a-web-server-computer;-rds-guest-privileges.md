---
title: 授予 web 服务器计算机; 来宾权限RDS 来宾权限
TOCTitle: Granting guest privileges to a web server computer; RDS guest privileges
ms:assetid: 4ec9c05b-36f6-de22-b848-0cb8573f9dd1
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249254(v=office.15)
ms:contentKeyID: 48544766
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: f1f127e4ea9393d3b461e9b7da2901df554ee36b
ms.sourcegitcommit: 558d09fad81f8d80b5ad0edd21934fc09c098f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25947208"
---
# <a name="granting-guest-privileges-to-a-web-server-computer-rds-guest-privileges"></a>授予 web 服务器计算机; 来宾权限RDS 来宾权限

**适用于**： Access 2013、 Office 2013

匿名 web 服务器帐户 (IUSR\_*ComputerName*) 必须添加到 Guests 本地组的 web 服务器计算机上才能使用 rds。

**授予 web 服务器计算机来宾权限**

1.  Microsoft Windows 2000 Server 计算机上单击**开始**，指向**程序**、**管理工具**，，然后单击**计算机管理**。

2.  在控制台树中，在**本地用户和组**中，单击**组**。

3.  选择的**Guests**本地组。 从**操作**菜单中，选择**属性**。

4.  在**Guests 属性**对话框中，单击**添加**。

5.  如果匿名 web 服务器帐户未显示在**选择用户或组**对话框中的列表，请键入其名称 (IUSR\_*ComputerName*) 到空白底部框中，然后单击**添加**。

6.  单击“确定”****。

