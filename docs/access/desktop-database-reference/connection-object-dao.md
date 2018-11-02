---
title: Connection 对象 (DAO)
TOCTitle: Connection Object
ms:assetid: f469b04e-2539-6b53-31f2-85fe22fcc2fc
ms:mtpsurl: https://msdn.microsoft.com/library/Ff836694(v=office.15)
ms:contentKeyID: 48548690
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 0473a3f4b920e05ad07556b070ed0e778d7ac694
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25930152"
---
# <a name="connection-object-dao"></a>Connection 对象 (DAO)


**适用于**： Access 2013、 Office 2013

> [!NOTE]
> Microsoft Access 2013 中不支持适用于 ODBCDirect 工作区。 如果要在不使用 Microsoft Access 数据库引擎的情况下访问外部数据源，请使用 ADO。



**Connection** 对象代表与 ODBC 数据库的连接（仅适用于 ODBCDirect 工作区）。

## <a name="remarks"></a>注解

**Connection** 为非永久对象，代表与远程数据库的连接。 **Connection** 对象只在 ODBCDirect 工作区中可用（也就是在类型选项设置为 **dbUseODBC** 的情况下创建的 **Workspace** 对象）。


> [!NOTE]
> [!注释] 为实现向后兼容，对 DAO 早期版本编写的代码可继续使用 **Database** 对象，但是，如果需要 **Connection** 的新功能，则应修改代码，以使用 **Connection** 对象。为帮助完成代码转换，可通过读取 **Database** 对象的 **Connection** 属性，从 [Database](database-connection-property-dao.md) 获取 **Connection** 对象引用。相反，也可以从 **Connection** 对象的 **Database** 属性获取 **Database** 对象引用。


