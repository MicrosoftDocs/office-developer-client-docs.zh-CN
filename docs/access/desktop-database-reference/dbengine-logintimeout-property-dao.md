---
title: DBEngine.LoginTimeout Property (DAO)
TOCTitle: LoginTimeout Property
ms:assetid: 81d14153-79c5-7860-b6a8-4079d2d7acf7
ms:mtpsurl: https://msdn.microsoft.com/library/Ff196648(v=office.15)
ms:contentKeyID: 48545964
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1052923
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 53df33e3171cde0d861f738a852350ec20bf0dec
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466686"
---
# <a name="dbenginelogintimeout-property-dao"></a>DBEngine.LoginTimeout Property (DAO)


**适用于**： Access 2013 |Office 2013

设置或返回在您尝试登录 ODBC 数据库时发生错误之前的秒数。

## <a name="syntax"></a>语法

*表达式*。LoginTimeout

*表达式*一个代表**DBEngine**对象的变量。

## <a name="remarks"></a>注解

默认的 **LoginTimeout** 属性设置为 20 秒。如果 **LoginTimeout** 属性设置为 0，则不发生超时。

当您尝试登录 ODBC 数据库（例如 Microsoft SQL Server）时，连接可能会因为网络错误或服务器未运行而失败。无需在连接前等待默认的 20 秒，您可以指定发生错误前等待的时间。在许多不同事件（例如在外部服务器数据库上运行查询）中，可能需要登录服务器。

