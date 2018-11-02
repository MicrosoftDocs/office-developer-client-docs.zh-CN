---
title: Workspace.LoginTimeout 属性 (DAO)
TOCTitle: LoginTimeout Property
ms:assetid: 5f03b166-abbc-20de-1a01-3869a9f2907d
ms:mtpsurl: https://msdn.microsoft.com/library/Ff194743(v=office.15)
ms:contentKeyID: 48545151
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 07b2945f2e9a59cc8a7db4a6f5a44cfaf9b35043
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25928283"
---
# <a name="workspacelogintimeout-property-dao"></a>Workspace.LoginTimeout 属性 (DAO)


**适用于**： Access 2013、 Office 2013

设置或返回在您尝试登录 ODBC 数据库时发生错误之前的秒数。

## <a name="syntax"></a>语法

*表达式*。LoginTimeout

*表达式*一个代表**Workspace**对象的变量。

## <a name="remarks"></a>注解

默认的 **LoginTimeout** 属性设置为 20 秒。如果 **LoginTimeout** 属性设置为 0，则不发生超时。

当您尝试登录 ODBC 数据库（例如 Microsoft SQL Server）时，连接可能会因为网络错误或服务器未运行而失败。无需在连接前等待默认的 20 秒，您可以指定发生错误前等待的时间。在许多不同事件（例如在外部服务器数据库上运行查询）中，可能需要登录服务器。

