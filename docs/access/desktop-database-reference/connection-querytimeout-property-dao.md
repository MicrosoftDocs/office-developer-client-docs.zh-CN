---
title: Connection.QueryTimeout 属性 (DAO)
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
ms.openlocfilehash: c096ba38c59ec9c62da56dc47a59f06254ef60f6
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25921738"
---
# <a name="connectionquerytimeout-property-dao"></a><span data-ttu-id="cc692-102">Connection.QueryTimeout 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="cc692-102">Connection.QueryTimeout property (DAO)</span></span>


<span data-ttu-id="cc692-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="cc692-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="cc692-104">设置或返回一个值，该值指定对 ODBC 数据源执行查询时发生超时错误之前等待的秒数。</span><span class="sxs-lookup"><span data-stu-id="cc692-104">Sets or returns a value that specifies the number of seconds to wait before a timeout error occurs when a query is executed on an ODBC data source.</span></span>

## <a name="syntax"></a><span data-ttu-id="cc692-105">语法</span><span class="sxs-lookup"><span data-stu-id="cc692-105">Syntax</span></span>

<span data-ttu-id="cc692-106">*表达式*。QueryTimeout</span><span class="sxs-lookup"><span data-stu-id="cc692-106">*expression* .QueryTimeout</span></span>

<span data-ttu-id="cc692-107">*表达式*代表**Connection**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="cc692-107">*expression* A variable that represents a **Connection** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="cc692-108">注解</span><span class="sxs-lookup"><span data-stu-id="cc692-108">Remarks</span></span>

<span data-ttu-id="cc692-109">默认值为 60。</span><span class="sxs-lookup"><span data-stu-id="cc692-109">The default value is 60.</span></span>

<span data-ttu-id="cc692-p101">在使用 ODBC 数据库（如 Microsoft SQL Server）时，由于网络阻塞或频繁使用 ODBC 服务器的原因，可能会有延迟。不需要无限期地等待，您可以指定等待时间。</span><span class="sxs-lookup"><span data-stu-id="cc692-p101">When you're using an ODBC database, such as Microsoft SQL Server, there may be delays due to network traffic or heavy use of the ODBC server. Rather than waiting indefinitely, you can specify how long to wait.</span></span>

<span data-ttu-id="cc692-p102">将 **QueryTimeout** 用于 **[Connection](connection-object-dao.md)** 或 **[Database](database-object-dao.md)** 对象时，它为所有与数据库关联的查询指定了全局值。可以通过设置特定 [**QueryDef**](querydef-object-dao.md) 对象的 **ODBCTimeout** 属性来重写特定查询的这个值。</span><span class="sxs-lookup"><span data-stu-id="cc692-p102">When you use **QueryTimeout** with a **[Connection](connection-object-dao.md)** or **[Database](database-object-dao.md)** object, it specifies a global value for all queries associated with the database. You can override this value for a specific query by setting the **ODBCTimeout** property of the particular **[QueryDef](querydef-object-dao.md)** object.</span></span>

