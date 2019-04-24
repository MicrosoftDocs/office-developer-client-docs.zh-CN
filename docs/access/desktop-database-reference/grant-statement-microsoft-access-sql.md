---
title: GRANT 语句 (Microsoft Access SQL)
TOCTitle: GRANT statement (Microsoft Access SQL)
ms:assetid: 50ae97ae-d5be-57e5-d9da-f3fc42f01d83
ms:mtpsurl: https://msdn.microsoft.com/library/Ff193820(v=office.15)
ms:contentKeyID: 48544800
ms.date: 10/18/2018
mtps_version: v=office.15
f1_keywords:
- jetsql40.chm5277478
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: 4357099f8bcb9b2308b5cda3543949765b8c3420
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32292130"
---
# <a name="grant-statement-microsoft-access-sql"></a><span data-ttu-id="f358a-102">GRANT 语句 (Microsoft Access SQL)</span><span class="sxs-lookup"><span data-stu-id="f358a-102">GRANT statement (Microsoft Access SQL)</span></span>

<span data-ttu-id="f358a-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="f358a-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="f358a-104">为现有用户或组授予指定的特权。</span><span class="sxs-lookup"><span data-stu-id="f358a-104">Grants specific privileges to an existing user or group.</span></span>

## <a name="syntax"></a><span data-ttu-id="f358a-105">语法</span><span class="sxs-lookup"><span data-stu-id="f358a-105">Syntax</span></span>

<span data-ttu-id="f358a-106">授予 {*特权*\[,*特权*, .。。\]} ON {TABLE *table* |object*对象*|</span><span class="sxs-lookup"><span data-stu-id="f358a-106">GRANT {*privilege*\[, *privilege*, …\]} ON{TABLE *table* | OBJECT *object*|</span></span>

<span data-ttu-id="f358a-107">容器*容器*} TO {*authorizationname*\[, *authorizationname*, .。。\]}</span><span class="sxs-lookup"><span data-stu-id="f358a-107">CONTAINER *container* } TO {*authorizationname*\[, *authorizationname*, …\]}</span></span>

<span data-ttu-id="f358a-108">GRANT 语句包含以下部分：</span><span class="sxs-lookup"><span data-stu-id="f358a-108">The GRANT statement has these parts:</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="f358a-109">Part</span><span class="sxs-lookup"><span data-stu-id="f358a-109">Part</span></span></p></th>
<th><p><span data-ttu-id="f358a-110">说明</span><span class="sxs-lookup"><span data-stu-id="f358a-110">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f358a-111"><em>小特权</em></span><span class="sxs-lookup"><span data-stu-id="f358a-111"><em>privilege</em></span></span></p></td>
<td><p><span data-ttu-id="f358a-112">要授予的特权。</span><span class="sxs-lookup"><span data-stu-id="f358a-112">The privilege or privileges to be granted.</span></span> <span data-ttu-id="f358a-113">使用以下关键字指定权限: SELECT、DELETE、INSERT、UPDATE、DROP、SELECTSECURITY、UPDATESECURITY、DBPASSWORD、UPDATEIDENTITY、CREATE、SELECTSCHEMA、SCHEMA 和 UPDATEOWNER。</span><span class="sxs-lookup"><span data-stu-id="f358a-113">Privileges are specified using the following keywords: SELECT, DELETE, INSERT, UPDATE, DROP, SELECTSECURITY, UPDATESECURITY, DBPASSWORD, UPDATEIDENTITY, CREATE, SELECTSCHEMA, SCHEMA, and UPDATEOWNER.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f358a-114"><em>名</em></span><span class="sxs-lookup"><span data-stu-id="f358a-114"><em>tablename</em></span></span></p></td>
<td><p><span data-ttu-id="f358a-115">任何有效的表名。</span><span class="sxs-lookup"><span data-stu-id="f358a-115">Any valid table name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f358a-116"><em>object</em></span><span class="sxs-lookup"><span data-stu-id="f358a-116"><em>object</em></span></span></p></td>
<td><p><span data-ttu-id="f358a-117">可以包含任何非表对象。</span><span class="sxs-lookup"><span data-stu-id="f358a-117">This can encompass any non-table object.</span></span> <span data-ttu-id="f358a-118">存储查询（视图或过程）就是一个示例。</span><span class="sxs-lookup"><span data-stu-id="f358a-118">A stored query (view or procedure) is one example.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f358a-119"><em>箱</em></span><span class="sxs-lookup"><span data-stu-id="f358a-119"><em>container</em></span></span></p></td>
<td><p><span data-ttu-id="f358a-120">有效容器的名称。</span><span class="sxs-lookup"><span data-stu-id="f358a-120">The name of a valid container.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f358a-121"><em>authorizationname</em></span><span class="sxs-lookup"><span data-stu-id="f358a-121"><em>authorizationname</em></span></span></p></td>
<td><p><span data-ttu-id="f358a-122">用户名或组名。</span><span class="sxs-lookup"><span data-stu-id="f358a-122">A user or group name.</span></span></p></td>
</tr>
</tbody>
</table>

