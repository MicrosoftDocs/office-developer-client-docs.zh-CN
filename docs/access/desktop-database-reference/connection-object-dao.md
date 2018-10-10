---
title: Connection Object (DAO)
TOCTitle: Connection Object
ms:assetid: f469b04e-2539-6b53-31f2-85fe22fcc2fc
ms:mtpsurl: https://msdn.microsoft.com/library/Ff836694(v=office.15)
ms:contentKeyID: 48548690
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: bba06d593069051d2cc4f2e66b8cb91f36d920fb
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466326"
---
# <a name="connection-object-dao"></a>Connection Object (DAO)


**适用于**： Access 2013 |Office 2013


> [!NOTE]
> <P>Microsoft Access 2013 中不支持适用于 ODBCDirect 工作区。 如果要在不使用 Microsoft Access 数据库引擎的情况下访问外部数据源，请使用 ADO。</P>



**Connection** 对象代表与 ODBC 数据库的连接（仅适用于 ODBCDirect 工作区）。

## <a name="remarks"></a>注解

**Connection** 为非永久对象，代表与远程数据库的连接。 **Connection** 对象只在 ODBCDirect 工作区中可用（也就是在类型选项设置为 **dbUseODBC** 的情况下创建的 **Workspace** 对象）。


> [!NOTE]
> <P>[!注释] 为实现向后兼容，对 DAO 早期版本编写的代码可继续使用 <STRONG>Database</STRONG> 对象，但是，如果需要 <STRONG>Connection</STRONG> 的新功能，则应修改代码，以使用 <STRONG>Connection</STRONG> 对象。为帮助完成代码转换，可通过读取 <STRONG>Database</STRONG> 对象的 <STRONG>Connection</STRONG> 属性，从 <A href="database-connection-property-dao.md">Database</A> 获取 <STRONG>Connection</STRONG> 对象引用。相反，也可以从 <STRONG>Connection</STRONG> 对象的 <STRONG>Database</STRONG> 属性获取 <STRONG>Database</STRONG> 对象引用。</P>


