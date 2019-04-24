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
# <a name="workspaceisolateodbctrans-property-dao"></a><span data-ttu-id="ac393-102">IsolateODBCTrans 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="ac393-102">Workspace.IsolateODBCTrans property (DAO)</span></span>


<span data-ttu-id="ac393-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="ac393-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="ac393-104">设置或返回一个值，该值指示与 Microsoft Access 数据库引擎连接的同一个 ODBC 数据源相关的多个事务是否被隔离（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="ac393-104">Sets or returns a value that indicates whether multiple transactiond that involve the same Microsoft Access database engine-connected ODBC data source are isolated (Microsoft Access workspaces only).</span></span>

## <a name="syntax"></a><span data-ttu-id="ac393-105">语法</span><span class="sxs-lookup"><span data-stu-id="ac393-105">Syntax</span></span>

<span data-ttu-id="ac393-106">*表达式*。IsolateODBCTrans</span><span class="sxs-lookup"><span data-stu-id="ac393-106">*expression* .IsolateODBCTrans</span></span>

<span data-ttu-id="ac393-107">*表达式*一个代表**Workspace**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="ac393-107">*expression* A variable that represents a **Workspace** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="ac393-108">注解</span><span class="sxs-lookup"><span data-stu-id="ac393-108">Remarks</span></span>

<span data-ttu-id="ac393-p101">在某些情况下，需要在同一 ODBC 连接上有多个处于待定状态的同步事务。要做到这一点，需要为每个事务打开不同的 **Workspace**。尽管每个 **Workspace** 都可以具有其自身的与数据库的 ODBC 连接，但是这会减慢系统的性能。由于通常不需要事务隔离，因此，默认情况下，共享由同一用户打开的多个 **Workspace** 对象中的 ODBC 连接。</span><span class="sxs-lookup"><span data-stu-id="ac393-p101">In some situations, you need to have multiple simultaneous transactions pending on the same ODBC connection. To do this, you need to open a separate **Workspace** for each transaction. Although each **Workspace** can have its own ODBC connection to the database, this slows system performance. Because transaction isolation isn't usually required, ODBC connections from multiple **Workspace** objects opened by the same user are shared by default.</span></span>

<span data-ttu-id="ac393-p102">某些 ODBC 服务器（例如 Microsoft SQL Server）不允许在单个连接上使用同步事务。如果需要针对这种数据库一次将多个事务指定为待定状态，则可以在打开每个 **Workspace** 后，立即将其 **IsolateODBCTrans** 属性设置为 **True**。这将为每个 **Workspace** 强制单独的 ODBC 连接。</span><span class="sxs-lookup"><span data-stu-id="ac393-p102">Some ODBC servers, such as Microsoft SQL Server, don't allow simultaneous transactions on a single connection. If you need to have more than one transaction at a time pending against such a database, set the **IsolateODBCTrans** property to **True** on each **Workspace** as soon as you open it. This forces a separate ODBC connection for each **Workspace**.</span></span>

