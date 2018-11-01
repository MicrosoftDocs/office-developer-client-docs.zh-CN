---
title: SQLState 属性 (ADO)
TOCTitle: SQLState property (ADO)
ms:assetid: cf3b078a-849e-1ad2-cba4-a26160080868
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250029(v=office.15)
ms:contentKeyID: 48547806
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: f6fb45342a56a003856192a353270778b44654de
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25872177"
---
# <a name="sqlstate-property-ado"></a><span data-ttu-id="67aa6-102">SQLState 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="67aa6-102">SQLState property (ADO)</span></span>


<span data-ttu-id="67aa6-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="67aa6-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="67aa6-104">指示给定 [Error](error-object-ado.md) 对象的 SQL 状态。</span><span class="sxs-lookup"><span data-stu-id="67aa6-104">Indicates the SQL state for a given [Error](error-object-ado.md) object.</span></span>

## <a name="return-value"></a><span data-ttu-id="67aa6-105">返回值</span><span class="sxs-lookup"><span data-stu-id="67aa6-105">Return value</span></span>

<span data-ttu-id="67aa6-106">返回一个符合 ANSI SQL 标准并指示错误代码的五字符 **String** 值。</span><span class="sxs-lookup"><span data-stu-id="67aa6-106">Returns a five-character **String** value that follows the ANSI SQL standard and indicates the error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="67aa6-107">备注</span><span class="sxs-lookup"><span data-stu-id="67aa6-107">Remarks</span></span>

<span data-ttu-id="67aa6-p101">使用 **SQLState** 属性可读取在处理 SQL 语句的过程中发生错误时提供程序返回的五字符错误代码。例如，在将 Microsoft OLE DB Provider for ODBC 和 Microsoft SQL Server 数据库一起使用时，SQL 状态错误代码将从 ODBC 产生（基于特定于 ODBC 的错误或源于 Microsoft SQL Server 的错误），然后映射为 ODBC 错误。这些错误代码记录在 ANSI SQL 标准中，但不同数据源的实现方式可能会不同。</span><span class="sxs-lookup"><span data-stu-id="67aa6-p101">Use the **SQLState** property to read the five-character error code that the provider returns when an error occurs during the processing of an SQL statement. For example, when using the Microsoft OLE DB Provider for ODBC with a Microsoft SQL Server database, SQL state error codes originate from ODBC, based either on errors specific to ODBC or on errors that originate from Microsoft SQL Server, and are then mapped to ODBC errors. These error codes are documented in the ANSI SQL standard, but may be implemented differently by different data sources.</span></span>

