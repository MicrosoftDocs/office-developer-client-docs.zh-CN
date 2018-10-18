---
title: Internet 服务器错误： 访问被拒绝
TOCTitle: 'Internet Server Error: Access Denied'
ms:assetid: 65f4608b-afec-2867-dae3-e29bae03a6fd
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249395(v=office.15)
ms:contentKeyID: 48545334
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: c874b7a2c4facb9f5969bf9a2150c86773a2687a
ms.sourcegitcommit: a49b77f4c8cec69f90656a86f0872cf34c35968e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2018
ms.locfileid: "25603341"
---
# <a name="internet-server-error-access-denied"></a><span data-ttu-id="cdd7a-102">Internet 服务器错误： 访问被拒绝</span><span class="sxs-lookup"><span data-stu-id="cdd7a-102">Internet Server Error: Access Denied</span></span>


<span data-ttu-id="cdd7a-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="cdd7a-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="cdd7a-104">如果出现此错误消息，通常表示 Microsoft Internet 信息服务 (IIS) 返回以下状态：</span><span class="sxs-lookup"><span data-stu-id="cdd7a-104">If you get this error, it usually means that Microsoft Internet Information Services (IIS) returned the following status:</span></span>

<span data-ttu-id="cdd7a-105">HTTP\_状态\_拒绝 401</span><span class="sxs-lookup"><span data-stu-id="cdd7a-105">HTTP\_STATUS\_DENIED 401</span></span>

<span data-ttu-id="cdd7a-106"><<<<<<< 标头确保 IIS 访问的目录有适当权限。</span><span class="sxs-lookup"><span data-stu-id="cdd7a-106"><<<<<<< HEAD Make sure the directories accessed by IIS have proper permissions.</span></span> <span data-ttu-id="cdd7a-107">RDS 可以与任何一个三种的密码身份验证模式中运行的 IIS Web 服务器通信： 匿名 Basic 或 NT 质询/响应 （在 Windows 2000 中称为集成 Windows 身份验证）。</span><span class="sxs-lookup"><span data-stu-id="cdd7a-107">RDS can communicate with an IIS Web server running in any one of the three Password Authentication modes: Anonymous, Basic, or NT Challenge/Response (called Integrated Windows authentication in Windows 2000).</span></span> <span data-ttu-id="cdd7a-108">此外，Web 服务器必须具有对数据源计算机上的权限如果它是 Windows NT/Windows 2000 的计算机。</span><span class="sxs-lookup"><span data-stu-id="cdd7a-108">Also, the Web server must have permissions to the data source computer if it is a Windows NT/Windows 2000 computer.</span></span>
<span data-ttu-id="cdd7a-109">=== 进行访问的 IIS 的目录确保具有正确的权限。</span><span class="sxs-lookup"><span data-stu-id="cdd7a-109">======= Make sure the directories accessed by IIS have proper permissions.</span></span> <span data-ttu-id="cdd7a-110">RDS 可以相互任一的三个的密码身份验证模式中运行的 IIS web 服务器： 匿名 Basic 或 NT 质询/响应 （在 Windows 2000 中称为集成 Windows 身份验证）。</span><span class="sxs-lookup"><span data-stu-id="cdd7a-110">RDS can communicate with an IIS web server running in any one of the three Password Authentication modes: Anonymous, Basic, or NT Challenge/Response (called Integrated Windows authentication in Windows 2000).</span></span> <span data-ttu-id="cdd7a-111">此外，web 服务器必须具有对数据源计算机上的权限如果它是 Windows NT/Windows 2000 的计算机。</span><span class="sxs-lookup"><span data-stu-id="cdd7a-111">Also, the web server must have permissions to the data source computer if it is a Windows NT/Windows 2000 computer.</span></span>
>>>>>>> <span data-ttu-id="cdd7a-112">master</span><span class="sxs-lookup"><span data-stu-id="cdd7a-112">master</span></span>

