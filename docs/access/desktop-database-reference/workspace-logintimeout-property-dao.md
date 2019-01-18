---
title: Workspace.LoginTimeout 属性 (DAO)
TOCTitle: LoginTimeout Property
ms:assetid: 5f03b166-abbc-20de-1a01-3869a9f2907d
ms:mtpsurl: https://msdn.microsoft.com/library/Ff194743(v=office.15)
ms:contentKeyID: 48545151
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: dbc0ed4849e8c22bc7023bd4254fdee74a5d016c
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28699609"
---
# <a name="workspacelogintimeout-property-dao"></a><span data-ttu-id="d647e-102">Workspace.LoginTimeout 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="d647e-102">Workspace.LoginTimeout property (DAO)</span></span>


<span data-ttu-id="d647e-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="d647e-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="d647e-104">设置或返回在您尝试登录 ODBC 数据库时发生错误之前的秒数。</span><span class="sxs-lookup"><span data-stu-id="d647e-104">Sets or returns the number of seconds before an error occurs when you attempt to log on to an ODBC database.</span></span>

## <a name="syntax"></a><span data-ttu-id="d647e-105">语法</span><span class="sxs-lookup"><span data-stu-id="d647e-105">Syntax</span></span>

<span data-ttu-id="d647e-106">*表达式*。LoginTimeout</span><span class="sxs-lookup"><span data-stu-id="d647e-106">*expression* .LoginTimeout</span></span>

<span data-ttu-id="d647e-107">*表达式*一个代表**Workspace**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="d647e-107">*expression* A variable that represents a **Workspace** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="d647e-108">注解</span><span class="sxs-lookup"><span data-stu-id="d647e-108">Remarks</span></span>

<span data-ttu-id="d647e-p101">默认的 **LoginTimeout** 属性设置为 20 秒。如果 **LoginTimeout** 属性设置为 0，则不发生超时。</span><span class="sxs-lookup"><span data-stu-id="d647e-p101">The default **LoginTimeout** property setting is 20 seconds. When the **LoginTimeout** property is set to 0, no timeout occurs.</span></span>

<span data-ttu-id="d647e-p102">当您尝试登录 ODBC 数据库（例如 Microsoft SQL Server）时，连接可能会因为网络错误或服务器未运行而失败。无需在连接前等待默认的 20 秒，您可以指定发生错误前等待的时间。在许多不同事件（例如在外部服务器数据库上运行查询）中，可能需要登录服务器。</span><span class="sxs-lookup"><span data-stu-id="d647e-p102">When you're attempting to log on to an ODBC database, such as Microsoft SQL Server, the connection can fail as a result of network errors or because the server isn't running. Rather than waiting for the default 20 seconds to connect, you can specify how long to wait before raising an error. Logging on to the server happens implicitly as part of a number of different events, such as running a query on an external server database.</span></span>

