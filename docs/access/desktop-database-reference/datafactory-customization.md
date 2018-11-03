---
title: DataFactory 自定义
TOCTitle: DataFactory customization
ms:assetid: 43cd7416-1f05-87ee-22f0-6cf0d2d1b39f
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249205(v=office.15)
ms:contentKeyID: 48544511
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 9de748b85e4bf6076c37f49e9d9bc7ff3b0bfe62
ms.sourcegitcommit: 558d09fad81f8d80b5ad0edd21934fc09c098f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25947567"
---
# <a name="datafactory-customization"></a>DataFactory 自定义


**适用于**： Access 2013、 Office 2013

远程数据服务 (RDS) 使您能够在三层客户端/服务器系统中很容易地执行数据访问。客户端数据控件可以指定连接和命令字符串参数，以便对远程数据源执行查询，或者指定连接字符串和 [Recordset](recordset-object-ado.md) 对象参数，以执行更新。

参数将传递给服务器程序，后者将对远程数据源执行数据访问操作。RDS 提供了称为 [RDSServer.DataFactory](datafactory-object-rdsserver.md) 对象的默认服务器程序。 **RDSServer.DataFactory** 对象将返回对客户端的查询所产生的任何 **Recordset** 对象。

但是， **RDSServer.DataFactory** 只能执行查询和更新。它无法对连接或命令字符串执行任何验证或处理。

使用 ADO，可以指定让 **DataFactory** 与另一种类型的服务器程序（称为*处理程序*）配合工作。在用客户端连接和命令字符串访问数据源之前，处理程序可以对它们进行修改。此外，处理程序可以强制实施访问权，访问权控制客户端在数据源中读取和写入数据的能力。

处理程序用来修改客户端参数和访问权的参数是在自定义文件的节中指定的。

有关自定义 **DataFactory** 对象的详细信息，请参阅以下主题：

- [了解自定义文件](understanding-the-customization-file.md)
- [自定义文件 Connect 节](customization-file-connect-section.md)
- [自定义文件 SQL 节](customization-file-sql-section.md)
- [自定义文件 UserList 节](customization-file-userlist-section.md)
- [自定义文件 Logs 节](customization-file-logs-section.md)
- [所需的客户端设置](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/required-client-settings)
- [编写您自己的自定义处理程序](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/writing-your-own-customized-handler)
