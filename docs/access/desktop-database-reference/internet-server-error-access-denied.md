---
title: Internet 服务器错误：访问遭拒
TOCTitle: 'Internet Server Error: Access Denied'
ms:assetid: 65f4608b-afec-2867-dae3-e29bae03a6fd
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249395(v=office.15)
ms:contentKeyID: 48545334
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: af823f46653b3ec83950c2e2cfe639b514196b08
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32291253"
---
# <a name="internet-server-error-access-denied"></a>Internet 服务器错误：访问遭拒


**适用于**：Access 2013、Office 2013

如果出现此错误消息，通常表示 Microsoft Internet 信息服务 (IIS) 返回以下状态：

HTTP\_状态\_拒绝401

请确保 IIS 访问的目录具有正确的权限。 RDS 可以与在以下三种密码身份验证模式中运行的 IIS web 服务器进行通信: 匿名、基本或 NT 质询/响应 (在 Windows 2000 中称为 "集成 windows 身份验证")。 此外, 如果 web 服务器是 Windows NT/windows 2000 计算机, 则它必须具有对数据源计算机的权限。

