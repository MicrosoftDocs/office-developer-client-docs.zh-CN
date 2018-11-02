---
title: Query 方法 (RDS-访问桌面数据库引用)
TOCTitle: Query method (RDS)
ms:assetid: c88d82bd-2139-7f1e-4e5e-9030f3795816
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249975(v=office.15)
ms:contentKeyID: 48547658
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 06b9372a15082a76503654dde9261db941a492f8
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25923999"
---
# <a name="query-method-rds"></a>Query 方法 (RDS)


**适用于**： Access 2013、 Office 2013


使用有效的 SQL 查询字符串返回 [Recordset](recordset-object-ado.md)。

## <a name="syntax"></a>语法

设置*记录集* = *DataFactory*。查询 （*连接*、*查询*）

## <a name="parameters"></a>参数

  - *Recordset*

  - 一个代表 **Recordset** 对象的对象变量。

  - *DataFactory*

  - 一个代表 [RDSServer.DataFactory](datafactory-object-rdsserver.md) 对象的对象变量。

  - *Connection*

  - 一个包含服务器连接信息的 **字符串** 值。此参数类似于 [Connect](connect-property-rds.md) 属性。

  - *Query*

  - 一个包含 SQL 查询的 **字符串** 值。

## <a name="remarks"></a>备注

查询应使用数据库服务器的 SQL 语言。如果所执行的查询出现错误，则返回一个结果状态。 **Query** 方法不对 **Query** 字符串执行任何语法检查。

