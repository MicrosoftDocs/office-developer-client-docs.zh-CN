---
title: Database.Connection Property (DAO)
TOCTitle: Connection Property
ms:assetid: 8b900ea4-9179-9ed1-bc0b-0576939bb2bd
ms:mtpsurl: https://msdn.microsoft.com/library/Ff197325(v=office.15)
ms:contentKeyID: 48546221
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 7f0974051b1f10fa73caad6d9feafb2e2b769579
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25882838"
---
# <a name="databaseconnection-property-dao"></a>Database.Connection Property (DAO)


**适用于**： Access 2013、 Office 2013

## <a name="syntax"></a>语法

*表达式*。连接

*表达式*一个代表**Database**对象的变量。

## <a name="remarks"></a>注解

使用 **Connection** 属性可获取指向对应于 **Database** 的 **Connection** 对象的引用。在 DAO 中， **Connection** 对象及其对应的 **Database** 对象只是指向相同对象的两个不同的对象变量引用。使用 [Connection](connection-database-property-dao.md) 对象的 ****Database**** 属性和 **Database** 对象的 **Connection** 属性可以更轻松地将通过 Microsoft Access 数据库引擎与 ODBC 数据源建立的连接更改为使用 ODBCDirect。

