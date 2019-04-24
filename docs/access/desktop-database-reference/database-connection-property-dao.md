---
title: Database. Connection 属性 (DAO)
TOCTitle: Connection Property
ms:assetid: 8b900ea4-9179-9ed1-bc0b-0576939bb2bd
ms:mtpsurl: https://msdn.microsoft.com/library/Ff197325(v=office.15)
ms:contentKeyID: 48546221
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 77d9bfa30dbfab21fd75de36b336a25e6af3187e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32294993"
---
# <a name="databaseconnection-property-dao"></a>Database. Connection 属性 (DAO)


**适用于**：Access 2013、Office 2013

## <a name="syntax"></a>语法

*表达式*。联系

*表达式*一个代表**Database**对象的变量。

## <a name="remarks"></a>注解

使用 **Connection** 属性可获取指向对应于 **Database** 的 **Connection** 对象的引用。 在 DAO 中，**Connection** 对象及其对应的 **Database** 对象只是指向相同对象的两个不同的对象变量引用。 **connection**对象的**[database](connection-database-property-dao.md)** 属性和**database**对象的**connection**属性使得通过 Microsoft Access 数据库引擎更改到 ODBC 数据源的连接变得更加容易, 以使用 ODBCDirect。

