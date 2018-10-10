---
title: Query 方法 (RDS-访问桌面数据库引用)
TOCTitle: Query Method (RDS)
ms:assetid: c88d82bd-2139-7f1e-4e5e-9030f3795816
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249975(v=office.15)
ms:contentKeyID: 48547658
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 9a9ecb2d7ebfdd8f6738b8d7b9b8738ce981ec16
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25465993"
---
# <a name="query-method-rds"></a><span data-ttu-id="8b2c5-102">Query 方法 (RDS)</span><span class="sxs-lookup"><span data-stu-id="8b2c5-102">Query Method (RDS)</span></span>


<span data-ttu-id="8b2c5-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="8b2c5-103">**Applies to**: Access 2013 | Office 2013</span></span>


<span data-ttu-id="8b2c5-104">使用有效的 SQL 查询字符串返回 [Recordset](recordset-object-ado.md)。</span><span class="sxs-lookup"><span data-stu-id="8b2c5-104">Uses a valid SQL query string to return a [Recordset](recordset-object-ado.md).</span></span>

## <a name="syntax"></a><span data-ttu-id="8b2c5-105">语法</span><span class="sxs-lookup"><span data-stu-id="8b2c5-105">Syntax</span></span>

<span data-ttu-id="8b2c5-106">设置*记录集* = *DataFactory*。查询 （*连接*、*查询*）</span><span class="sxs-lookup"><span data-stu-id="8b2c5-106">Set*Recordset* = *DataFactory*.Query(*Connection*, *Query*)</span></span>

## <a name="parameters"></a><span data-ttu-id="8b2c5-107">参数</span><span class="sxs-lookup"><span data-stu-id="8b2c5-107">Parameters</span></span>

  - <span data-ttu-id="8b2c5-108">*Recordset*</span><span class="sxs-lookup"><span data-stu-id="8b2c5-108">*Recordset*</span></span>

  - <span data-ttu-id="8b2c5-109">一个代表 **Recordset** 对象的对象变量。</span><span class="sxs-lookup"><span data-stu-id="8b2c5-109">An object variable that represents a **Recordset** object.</span></span>

  - <span data-ttu-id="8b2c5-110">*DataFactory*</span><span class="sxs-lookup"><span data-stu-id="8b2c5-110">*DataFactory*</span></span>

  - <span data-ttu-id="8b2c5-111">一个代表 [RDSServer.DataFactory](datafactory-object-rdsserver.md) 对象的对象变量。</span><span class="sxs-lookup"><span data-stu-id="8b2c5-111">An object variable that represents an [RDSServer.DataFactory](datafactory-object-rdsserver.md) object.</span></span>

  - <span data-ttu-id="8b2c5-112">*Connection*</span><span class="sxs-lookup"><span data-stu-id="8b2c5-112">*Connection*</span></span>

  - <span data-ttu-id="8b2c5-p101">一个包含服务器连接信息的 **字符串** 值。此参数类似于 [Connect](connect-property-rds.md) 属性。</span><span class="sxs-lookup"><span data-stu-id="8b2c5-p101">A **String** value that contains the server connection information. This is similar to the [Connect](connect-property-rds.md) property.</span></span>

  - <span data-ttu-id="8b2c5-115">*Query*</span><span class="sxs-lookup"><span data-stu-id="8b2c5-115">*Query*</span></span>

  - <span data-ttu-id="8b2c5-116">一个包含 SQL 查询的 **字符串** 值。</span><span class="sxs-lookup"><span data-stu-id="8b2c5-116">A **String** that contains the SQL query.</span></span>

## <a name="remarks"></a><span data-ttu-id="8b2c5-117">备注</span><span class="sxs-lookup"><span data-stu-id="8b2c5-117">Remarks</span></span>

<span data-ttu-id="8b2c5-p102">查询应使用数据库服务器的 SQL 语言。如果所执行的查询出现错误，则返回一个结果状态。 **Query** 方法不对 **Query** 字符串执行任何语法检查。</span><span class="sxs-lookup"><span data-stu-id="8b2c5-p102">The query should use the SQL dialect of the database server. A result status is returned if there is an error with the query that was executed. The **Query** method doesn't perform any syntax checking on the **Query** string.</span></span>

