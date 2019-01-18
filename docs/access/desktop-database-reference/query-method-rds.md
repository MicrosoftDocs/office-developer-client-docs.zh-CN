---
title: Query 方法 (RDS-访问桌面数据库引用)
TOCTitle: Query method (RDS)
ms:assetid: c88d82bd-2139-7f1e-4e5e-9030f3795816
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249975(v=office.15)
ms:contentKeyID: 48547658
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 92c72bf78f8f01a675038f63b065aceb6869fcd0
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28717354"
---
# <a name="query-method-rds"></a><span data-ttu-id="6c15e-102">Query 方法 (RDS)</span><span class="sxs-lookup"><span data-stu-id="6c15e-102">Query method (RDS)</span></span>

<span data-ttu-id="6c15e-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="6c15e-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="6c15e-104">使用有效的 SQL 查询字符串返回 [Recordset](recordset-object-ado.md)。</span><span class="sxs-lookup"><span data-stu-id="6c15e-104">Uses a valid SQL query string to return a [Recordset](recordset-object-ado.md).</span></span>

## <a name="syntax"></a><span data-ttu-id="6c15e-105">语法</span><span class="sxs-lookup"><span data-stu-id="6c15e-105">Syntax</span></span>

<span data-ttu-id="6c15e-106">设置*记录集* = *DataFactory*。查询 （*连接*、*查询*）</span><span class="sxs-lookup"><span data-stu-id="6c15e-106">Set*Recordset* = *DataFactory*.Query(*Connection*, *Query*)</span></span>

## <a name="parameters"></a><span data-ttu-id="6c15e-107">Parameters</span><span class="sxs-lookup"><span data-stu-id="6c15e-107">Parameters</span></span>

|<span data-ttu-id="6c15e-108">参数</span><span class="sxs-lookup"><span data-stu-id="6c15e-108">Parameter</span></span>|<span data-ttu-id="6c15e-109">说明</span><span class="sxs-lookup"><span data-stu-id="6c15e-109">Description</span></span>|
|:--------|:----------|
|<span data-ttu-id="6c15e-110">*Recordset*</span><span class="sxs-lookup"><span data-stu-id="6c15e-110">*Recordset*</span></span> |<span data-ttu-id="6c15e-111">一个代表 **Recordset** 对象的对象变量。</span><span class="sxs-lookup"><span data-stu-id="6c15e-111">An object variable that represents a **Recordset** object.</span></span>|
|<span data-ttu-id="6c15e-112">*DataFactory*</span><span class="sxs-lookup"><span data-stu-id="6c15e-112">*DataFactory*</span></span> |<span data-ttu-id="6c15e-113">一个代表 [RDSServer.DataFactory](datafactory-object-rdsserver.md) 对象的对象变量。</span><span class="sxs-lookup"><span data-stu-id="6c15e-113">An object variable that represents an [RDSServer.DataFactory](datafactory-object-rdsserver.md) object.</span></span>|
|<span data-ttu-id="6c15e-114">*Connection*</span><span class="sxs-lookup"><span data-stu-id="6c15e-114">*Connection*</span></span> |<span data-ttu-id="6c15e-p101">一个包含服务器连接信息的 **字符串** 值。此参数类似于 [Connect](connect-property-rds.md) 属性。</span><span class="sxs-lookup"><span data-stu-id="6c15e-p101">A **String** value that contains the server connection information. This is similar to the [Connect](connect-property-rds.md) property.</span></span>|
|<span data-ttu-id="6c15e-117">*Query*</span><span class="sxs-lookup"><span data-stu-id="6c15e-117">*Query*</span></span> |<span data-ttu-id="6c15e-118">一个包含 SQL 查询的 **字符串** 值。</span><span class="sxs-lookup"><span data-stu-id="6c15e-118">A **String** that contains the SQL query.</span></span>|

## <a name="remarks"></a><span data-ttu-id="6c15e-119">备注</span><span class="sxs-lookup"><span data-stu-id="6c15e-119">Remarks</span></span>

<span data-ttu-id="6c15e-p102">查询应使用数据库服务器的 SQL 语言。如果所执行的查询出现错误，则返回一个结果状态。 **Query** 方法不对 **Query** 字符串执行任何语法检查。</span><span class="sxs-lookup"><span data-stu-id="6c15e-p102">The query should use the SQL dialect of the database server. A result status is returned if there is an error with the query that was executed. The **Query** method doesn't perform any syntax checking on the **Query** string.</span></span>

