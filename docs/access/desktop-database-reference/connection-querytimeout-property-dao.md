---
title: Connection.QueryTimeout 属性 (DAO)
TOCTitle: QueryTimeout Property
ms:assetid: 97853412-d5ae-7a71-ccaa-595c68919654
ms:mtpsurl: https://msdn.microsoft.com/library/Ff197804(v=office.15)
ms:contentKeyID: 48546471
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1052905
f1_categories:
- Office.Version=v15
ms.openlocfilehash: c096ba38c59ec9c62da56dc47a59f06254ef60f6
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25921738"
---
# <a name="connectionquerytimeout-property-dao"></a>Connection.QueryTimeout 属性 (DAO)


**适用于**： Access 2013、 Office 2013

设置或返回一个值，该值指定对 ODBC 数据源执行查询时发生超时错误之前等待的秒数。

## <a name="syntax"></a>语法

*表达式*。QueryTimeout

*表达式*代表**Connection**对象的变量。

## <a name="remarks"></a>注解

默认值为 60。

在使用 ODBC 数据库（如 Microsoft SQL Server）时，由于网络阻塞或频繁使用 ODBC 服务器的原因，可能会有延迟。不需要无限期地等待，您可以指定等待时间。

将 **QueryTimeout** 用于 **[Connection](connection-object-dao.md)** 或 **[Database](database-object-dao.md)** 对象时，它为所有与数据库关联的查询指定了全局值。可以通过设置特定 [**QueryDef**](querydef-object-dao.md) 对象的 **ODBCTimeout** 属性来重写特定查询的这个值。

