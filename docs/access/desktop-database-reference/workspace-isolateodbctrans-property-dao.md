---
title: IsolateODBCTrans 属性 (DAO)
TOCTitle: IsolateODBCTrans Property
ms:assetid: f7a48358-870b-cad3-d4ef-e46b50428e12
ms:mtpsurl: https://msdn.microsoft.com/library/Ff836924(v=office.15)
ms:contentKeyID: 48548770
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1053083
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: 781679dfbd4050cfde219802db4cd9e1544d83ae
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32302511"
---
# <a name="workspaceisolateodbctrans-property-dao"></a>IsolateODBCTrans 属性 (DAO)


**适用于**：Access 2013、Office 2013

设置或返回一个值，该值指示与 Microsoft Access 数据库引擎连接的同一个 ODBC 数据源相关的多个事务是否被隔离（仅适用于 Microsoft Access 工作区）。

## <a name="syntax"></a>语法

*表达式*。IsolateODBCTrans

*表达式*一个代表**Workspace**对象的变量。

## <a name="remarks"></a>注解

在某些情况下，需要在同一 ODBC 连接上有多个处于待定状态的同步事务。要做到这一点，需要为每个事务打开不同的 **Workspace**。尽管每个 **Workspace** 都可以具有其自身的与数据库的 ODBC 连接，但是这会减慢系统的性能。由于通常不需要事务隔离，因此，默认情况下，共享由同一用户打开的多个 **Workspace** 对象中的 ODBC 连接。

某些 ODBC 服务器（例如 Microsoft SQL Server）不允许在单个连接上使用同步事务。如果需要针对这种数据库一次将多个事务指定为待定状态，则可以在打开每个 **Workspace** 后，立即将其 **IsolateODBCTrans** 属性设置为 **True**。这将为每个 **Workspace** 强制单独的 ODBC 连接。

