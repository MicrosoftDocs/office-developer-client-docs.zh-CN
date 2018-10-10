---
title: Workspace.LoginTimeout Property (DAO)
TOCTitle: LoginTimeout Property
ms:assetid: 5f03b166-abbc-20de-1a01-3869a9f2907d
ms:mtpsurl: https://msdn.microsoft.com/library/Ff194743(v=office.15)
ms:contentKeyID: 48545151
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 6427b99fd212fa358b70fb20a5ecf0c9180209fb
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25465572"
---
# <a name="workspacelogintimeout-property-dao"></a><span data-ttu-id="55d24-102">Workspace.LoginTimeout Property (DAO)</span><span class="sxs-lookup"><span data-stu-id="55d24-102">Workspace.LoginTimeout Property (DAO)</span></span>


<span data-ttu-id="55d24-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="55d24-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="55d24-104">设置或返回在您尝试登录 ODBC 数据库时发生错误之前的秒数。</span><span class="sxs-lookup"><span data-stu-id="55d24-104">Sets or returns the number of seconds before an error occurs when you attempt to log on to an ODBC database.</span></span>

## <a name="syntax"></a><span data-ttu-id="55d24-105">语法</span><span class="sxs-lookup"><span data-stu-id="55d24-105">Syntax</span></span>

<span data-ttu-id="55d24-106">*表达式*。LoginTimeout</span><span class="sxs-lookup"><span data-stu-id="55d24-106">*expression* .LoginTimeout</span></span>

<span data-ttu-id="55d24-107">*表达式*一个代表**Workspace**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="55d24-107">*expression* A variable that represents a **Workspace** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="55d24-108">注解</span><span class="sxs-lookup"><span data-stu-id="55d24-108">Remarks</span></span>

<span data-ttu-id="55d24-p101">默认的 **LoginTimeout** 属性设置为 20 秒。如果 **LoginTimeout** 属性设置为 0，则不发生超时。</span><span class="sxs-lookup"><span data-stu-id="55d24-p101">The default **LoginTimeout** property setting is 20 seconds. When the **LoginTimeout** property is set to 0, no timeout occurs.</span></span>

<span data-ttu-id="55d24-p102">当您尝试登录 ODBC 数据库（例如 Microsoft SQL Server）时，连接可能会因为网络错误或服务器未运行而失败。无需在连接前等待默认的 20 秒，您可以指定发生错误前等待的时间。在许多不同事件（例如在外部服务器数据库上运行查询）中，可能需要登录服务器。</span><span class="sxs-lookup"><span data-stu-id="55d24-p102">When you're attempting to log on to an ODBC database, such as Microsoft SQL Server, the connection can fail as a result of network errors or because the server isn't running. Rather than waiting for the default 20 seconds to connect, you can specify how long to wait before raising an error. Logging on to the server happens implicitly as part of a number of different events, such as running a query on an external server database.</span></span>

