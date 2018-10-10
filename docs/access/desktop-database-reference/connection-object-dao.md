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
# <a name="connection-object-dao"></a><span data-ttu-id="22122-102">Connection Object (DAO)</span><span class="sxs-lookup"><span data-stu-id="22122-102">Connection Object (DAO)</span></span>


<span data-ttu-id="22122-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="22122-103">**Applies to**: Access 2013 | Office 2013</span></span>


> [!NOTE]
> <P><span data-ttu-id="22122-104">Microsoft Access 2013 中不支持适用于 ODBCDirect 工作区。</span><span class="sxs-lookup"><span data-stu-id="22122-104">ODBCDirect workspaces are not supported in Microsoft Access 2013.</span></span> <span data-ttu-id="22122-105">如果要在不使用 Microsoft Access 数据库引擎的情况下访问外部数据源，请使用 ADO。</span><span class="sxs-lookup"><span data-stu-id="22122-105">Use ADO if you want to access external data sources without using the Microsoft Access database engine.</span></span></P>



<span data-ttu-id="22122-106">**Connection** 对象代表与 ODBC 数据库的连接（仅适用于 ODBCDirect 工作区）。</span><span class="sxs-lookup"><span data-stu-id="22122-106">A **Connection** object represents a connection to an ODBC database (ODBCDirect workspaces only).</span></span>

## <a name="remarks"></a><span data-ttu-id="22122-107">注解</span><span class="sxs-lookup"><span data-stu-id="22122-107">Remarks</span></span>

<span data-ttu-id="22122-p102">**Connection** 为非永久对象，代表与远程数据库的连接。 **Connection** 对象只在 ODBCDirect 工作区中可用（也就是在类型选项设置为 **dbUseODBC** 的情况下创建的 **Workspace** 对象）。</span><span class="sxs-lookup"><span data-stu-id="22122-p102">A **Connection** is a non-persistent object that represents a connection to a remote database. The **Connection** object is only available in ODBCDirect workspaces (that is, a **Workspace** object created with the type option set to **dbUseODBC**).</span></span>


> [!NOTE]
> <P><span data-ttu-id="22122-p103">[!注释] 为实现向后兼容，对 DAO 早期版本编写的代码可继续使用 <STRONG>Database</STRONG> 对象，但是，如果需要 <STRONG>Connection</STRONG> 的新功能，则应修改代码，以使用 <STRONG>Connection</STRONG> 对象。为帮助完成代码转换，可通过读取 <STRONG>Database</STRONG> 对象的 <STRONG>Connection</STRONG> 属性，从 <A href="database-connection-property-dao.md">Database</A> 获取 <STRONG>Connection</STRONG> 对象引用。相反，也可以从 <STRONG>Connection</STRONG> 对象的 <STRONG>Database</STRONG> 属性获取 <STRONG>Database</STRONG> 对象引用。</span><span class="sxs-lookup"><span data-stu-id="22122-p103">Code written for earlier versions of DAO can continue to use the <STRONG>Database</STRONG> object for backward compatibility, but if the new features of a <STRONG>Connection</STRONG> are desired, you should revise code to use the <STRONG>Connection</STRONG> object. To help with code conversion, you can obtain a <STRONG>Connection</STRONG> object reference from a <STRONG>Database</STRONG> by reading the <A href="database-connection-property-dao.md">Connection</A> property of the <STRONG>Database</STRONG> object. Conversely, you can obtain a <STRONG>Database</STRONG> object reference from the <STRONG>Connection</STRONG> object's <STRONG>Database</STRONG> property.</span></span></P>


