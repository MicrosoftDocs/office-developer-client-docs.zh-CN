---
title: Internet 服务器错误： 访问被拒绝
TOCTitle: 'Internet Server Error: Access Denied'
ms:assetid: 65f4608b-afec-2867-dae3-e29bae03a6fd
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249395(v=office.15)
ms:contentKeyID: 48545334
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: db78b6f2c51e2e5df918622043e33abc6bc9e674
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466768"
---
# <a name="internet-server-error-access-denied"></a>Internet 服务器错误： 访问被拒绝


**适用于**： Access 2013 |Office 2013

如果出现此错误消息，通常表示 Microsoft Internet 信息服务 (IIS) 返回以下状态：

HTTP\_状态\_拒绝 401

请确保 IIS 访问的目录具有正确的权限。RDS 可以与以如下三种密码验证模式之一运行的 IIS Web 服务器通讯：匿名、基本或 NT 质询/响应（在 Windows 2000 中称为“集成的 Windows 验证”）。此外，如果 Web 服务器是 Windows NT/Windows 2000 计算机，则它必须拥有针对数据源计算机的权限。

