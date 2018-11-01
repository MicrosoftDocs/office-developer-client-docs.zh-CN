---
title: Connection Object (DAO)
TOCTitle: Connection Object
ms:assetid: f469b04e-2539-6b53-31f2-85fe22fcc2fc
ms:mtpsurl: https://msdn.microsoft.com/library/Ff836694(v=office.15)
ms:contentKeyID: 48548690
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 7170a28cb1d3ec9c8cdeca9229c255f264b9422e
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25883426"
---
# <a name="connection-object-dao"></a><span data-ttu-id="4d9da-102">Connection Object (DAO)</span><span class="sxs-lookup"><span data-stu-id="4d9da-102">Connection Object (DAO)</span></span>


<span data-ttu-id="4d9da-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="4d9da-103">**Applies to**: Access 2013, Office 2013</span></span>

> [!NOTE]
> <span data-ttu-id="4d9da-104">Microsoft Access 2013 中不支持适用于 ODBCDirect 工作区。</span><span class="sxs-lookup"><span data-stu-id="4d9da-104">ODBCDirect workspaces are not supported in Microsoft Access 2013.</span></span> <span data-ttu-id="4d9da-105">如果要在不使用 Microsoft Access 数据库引擎的情况下访问外部数据源，请使用 ADO。</span><span class="sxs-lookup"><span data-stu-id="4d9da-105">Use ADO if you want to access external data sources without using the Microsoft Access database engine.</span></span>



<span data-ttu-id="4d9da-106">**Connection** 对象代表与 ODBC 数据库的连接（仅适用于 ODBCDirect 工作区）。</span><span class="sxs-lookup"><span data-stu-id="4d9da-106">A **Connection** object represents a connection to an ODBC database (ODBCDirect workspaces only).</span></span>

## <a name="remarks"></a><span data-ttu-id="4d9da-107">注解</span><span class="sxs-lookup"><span data-stu-id="4d9da-107">Remarks</span></span>

<span data-ttu-id="4d9da-p102">**Connection** 为非永久对象，代表与远程数据库的连接。 **Connection** 对象只在 ODBCDirect 工作区中可用（也就是在类型选项设置为 **dbUseODBC** 的情况下创建的 **Workspace** 对象）。</span><span class="sxs-lookup"><span data-stu-id="4d9da-p102">A **Connection** is a non-persistent object that represents a connection to a remote database. The **Connection** object is only available in ODBCDirect workspaces (that is, a **Workspace** object created with the type option set to **dbUseODBC**).</span></span>


> [!NOTE]
> <span data-ttu-id="4d9da-p103">[!注释] 为实现向后兼容，对 DAO 早期版本编写的代码可继续使用 **Database** 对象，但是，如果需要 **Connection** 的新功能，则应修改代码，以使用 **Connection** 对象。为帮助完成代码转换，可通过读取 **Database** 对象的 **Connection** 属性，从 [Database](database-connection-property-dao.md) 获取 **Connection** 对象引用。相反，也可以从 **Connection** 对象的 **Database** 属性获取 **Database** 对象引用。</span><span class="sxs-lookup"><span data-stu-id="4d9da-p103">Code written for earlier versions of DAO can continue to use the **Database** object for backward compatibility, but if the new features of a **Connection** are desired, you should revise code to use the **Connection** object. To help with code conversion, you can obtain a **Connection** object reference from a **Database** by reading the [Connection](database-connection-property-dao.md) property of the **Database** object. Conversely, you can obtain a **Database** object reference from the **Connection** object's **Database** property.</span></span>


