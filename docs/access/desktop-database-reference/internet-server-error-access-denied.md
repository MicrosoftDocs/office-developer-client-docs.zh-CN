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
# <a name="internet-server-error-access-denied"></a><span data-ttu-id="05c26-102">Internet 服务器错误： 访问被拒绝</span><span class="sxs-lookup"><span data-stu-id="05c26-102">Internet Server Error: Access Denied</span></span>


<span data-ttu-id="05c26-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="05c26-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="05c26-104">如果出现此错误消息，通常表示 Microsoft Internet 信息服务 (IIS) 返回以下状态：</span><span class="sxs-lookup"><span data-stu-id="05c26-104">If you get this error, it usually means that Microsoft Internet Information Services (IIS) returned the following status:</span></span>

<span data-ttu-id="05c26-105">HTTP\_状态\_拒绝 401</span><span class="sxs-lookup"><span data-stu-id="05c26-105">HTTP\_STATUS\_DENIED 401</span></span>

<span data-ttu-id="05c26-p101">请确保 IIS 访问的目录具有正确的权限。RDS 可以与以如下三种密码验证模式之一运行的 IIS Web 服务器通讯：匿名、基本或 NT 质询/响应（在 Windows 2000 中称为“集成的 Windows 验证”）。此外，如果 Web 服务器是 Windows NT/Windows 2000 计算机，则它必须拥有针对数据源计算机的权限。</span><span class="sxs-lookup"><span data-stu-id="05c26-p101">Make sure the directories accessed by IIS have proper permissions. RDS can communicate with an IIS Web server running in any one of the three Password Authentication modes: Anonymous, Basic, or NT Challenge/Response (called Integrated Windows authentication in Windows 2000). Also, the Web server must have permissions to the data source computer if it is a Windows NT/Windows 2000 computer.</span></span>

