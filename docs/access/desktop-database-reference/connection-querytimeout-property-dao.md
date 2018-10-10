---
title: Connection.QueryTimeout Property (DAO)
TOCTitle: QueryTimeout Property
ms:assetid: 97853412-d5ae-7a71-ccaa-595c68919654
ms:mtpsurl: https://msdn.microsoft.com/library/Ff197804(v=office.15)
ms:contentKeyID: 48546471
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1052905
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 51f2f51743a8f92b77fafacebbc18e11eb77fe8a
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466226"
---
# <a name="connectionquerytimeout-property-dao"></a><span data-ttu-id="f6c04-102">Connection.QueryTimeout Property (DAO)</span><span class="sxs-lookup"><span data-stu-id="f6c04-102">Connection.QueryTimeout Property (DAO)</span></span>


<span data-ttu-id="f6c04-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="f6c04-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="f6c04-104">设置或返回一个值，该值指定对 ODBC 数据源执行查询时发生超时错误之前等待的秒数。</span><span class="sxs-lookup"><span data-stu-id="f6c04-104">Sets or returns a value that specifies the number of seconds to wait before a timeout error occurs when a query is executed on an ODBC data source.</span></span>

## <a name="syntax"></a><span data-ttu-id="f6c04-105">语法</span><span class="sxs-lookup"><span data-stu-id="f6c04-105">Syntax</span></span>

<span data-ttu-id="f6c04-106">*表达式*。QueryTimeout</span><span class="sxs-lookup"><span data-stu-id="f6c04-106">*expression* .QueryTimeout</span></span>

<span data-ttu-id="f6c04-107">*表达式*代表**Connection**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="f6c04-107">*expression* A variable that represents a **Connection** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="f6c04-108">注解</span><span class="sxs-lookup"><span data-stu-id="f6c04-108">Remarks</span></span>

<span data-ttu-id="f6c04-109">默认值为 60。</span><span class="sxs-lookup"><span data-stu-id="f6c04-109">The default value is 60.</span></span>

<span data-ttu-id="f6c04-p101">在使用 ODBC 数据库（如 Microsoft SQL Server）时，由于网络阻塞或频繁使用 ODBC 服务器的原因，可能会有延迟。不需要无限期地等待，您可以指定等待时间。</span><span class="sxs-lookup"><span data-stu-id="f6c04-p101">When you're using an ODBC database, such as Microsoft SQL Server, there may be delays due to network traffic or heavy use of the ODBC server. Rather than waiting indefinitely, you can specify how long to wait.</span></span>

<span data-ttu-id="f6c04-p102">将 **QueryTimeout** 用于 **[Connection](connection-object-dao.md)** 或 **[Database](database-object-dao.md)** 对象时，它为所有与数据库关联的查询指定了全局值。可以通过设置特定 [**QueryDef**](querydef-object-dao.md) 对象的 **ODBCTimeout** 属性来重写特定查询的这个值。</span><span class="sxs-lookup"><span data-stu-id="f6c04-p102">When you use **QueryTimeout** with a **[Connection](connection-object-dao.md)** or **[Database](database-object-dao.md)** object, it specifies a global value for all queries associated with the database. You can override this value for a specific query by setting the **ODBCTimeout** property of the particular **[QueryDef](querydef-object-dao.md)** object.</span></span>

