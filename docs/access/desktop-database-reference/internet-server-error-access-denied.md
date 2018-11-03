---
title: Internet 服务器错误： 访问被拒绝
TOCTitle: 'Internet Server Error: Access Denied'
ms:assetid: 65f4608b-afec-2867-dae3-e29bae03a6fd
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249395(v=office.15)
ms:contentKeyID: 48545334
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 885bdc14e5d5d346a17e018a509acf5b6c52108d
ms.sourcegitcommit: 558d09fad81f8d80b5ad0edd21934fc09c098f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25944877"
---
# <a name="internet-server-error-access-denied"></a>Internet 服务器错误： 访问被拒绝


**适用于**： Access 2013、 Office 2013

如果出现此错误消息，通常表示 Microsoft Internet 信息服务 (IIS) 返回以下状态：

HTTP\_状态\_拒绝 401

请确保访问由 IIS 的目录有适当权限。 RDS 可以相互任一的三个的密码身份验证模式中运行的 IIS web 服务器： 匿名 Basic 或 NT 质询/响应 （在 Windows 2000 中称为集成 Windows 身份验证）。 此外，web 服务器必须具有对数据源计算机上的权限如果它是 Windows NT/Windows 2000 的计算机。

