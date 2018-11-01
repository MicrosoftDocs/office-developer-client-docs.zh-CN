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
ms.openlocfilehash: 7c109d1993d4f092439ae10828ce3143625b4ad6
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25871953"
---
# <a name="grant-statement-microsoft-access-sql"></a><span data-ttu-id="d53c5-102">GRANT 语句 (Microsoft Access SQL)</span><span class="sxs-lookup"><span data-stu-id="d53c5-102">GRANT statement (Microsoft Access SQL)</span></span>

<span data-ttu-id="d53c5-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="d53c5-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="d53c5-104">为现有用户或组授予指定的特权。</span><span class="sxs-lookup"><span data-stu-id="d53c5-104">Grants specific privileges to an existing user or group.</span></span>

## <a name="syntax"></a><span data-ttu-id="d53c5-105">语法</span><span class="sxs-lookup"><span data-stu-id="d53c5-105">Syntax</span></span>

<span data-ttu-id="d53c5-106">GRANT {*privilege*\[， *privilege*，...\]} ON {表*表*|对象*对象*|</span><span class="sxs-lookup"><span data-stu-id="d53c5-106">GRANT {*privilege*\[, *privilege*, …\]} ON{TABLE *table* | OBJECT *object*|</span></span>

<span data-ttu-id="d53c5-107">CONTAINER *container* } TO {*authorizationname*\[， *authorizationname*，...\]}</span><span class="sxs-lookup"><span data-stu-id="d53c5-107">CONTAINER *container* } TO {*authorizationname*\[, *authorizationname*, …\]}</span></span>

<span data-ttu-id="d53c5-108">GRANT 语句包含以下部分：</span><span class="sxs-lookup"><span data-stu-id="d53c5-108">The GRANT statement has these parts:</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="d53c5-109">部分</span><span class="sxs-lookup"><span data-stu-id="d53c5-109">Part</span></span></p></th>
<th><p><span data-ttu-id="d53c5-110">说明</span><span class="sxs-lookup"><span data-stu-id="d53c5-110">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d53c5-111"><em>privilege</em></span><span class="sxs-lookup"><span data-stu-id="d53c5-111"><em>privilege</em></span></span></p></td>
<td><p><span data-ttu-id="d53c5-112">要授予的权限。</span><span class="sxs-lookup"><span data-stu-id="d53c5-112">The privilege or privileges to be granted.</span></span> <span data-ttu-id="d53c5-113">使用以下关键字指定权限： 选择、 删除、 插入、 更新、 投递、 SELECTSECURITY、 UPDATESECURITY、 DBPASSWORD、 UPDATEIDENTITY、 CREATE、 SELECTSCHEMA、 架构和 UPDATEOWNER。</span><span class="sxs-lookup"><span data-stu-id="d53c5-113">Privileges are specified using the following keywords: SELECT, DELETE, INSERT, UPDATE, DROP, SELECTSECURITY, UPDATESECURITY, DBPASSWORD, UPDATEIDENTITY, CREATE, SELECTSCHEMA, SCHEMA, and UPDATEOWNER.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d53c5-114"><em>tablename</em></span><span class="sxs-lookup"><span data-stu-id="d53c5-114"><em>tablename</em></span></span></p></td>
<td><p><span data-ttu-id="d53c5-115">任何有效的表名。</span><span class="sxs-lookup"><span data-stu-id="d53c5-115">Any valid table name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d53c5-116"><em>object</em></span><span class="sxs-lookup"><span data-stu-id="d53c5-116"><em>object</em></span></span></p></td>
<td><p><span data-ttu-id="d53c5-p102">可以包含任何非表对象。存储查询（视图或过程）就是一个示例。</span><span class="sxs-lookup"><span data-stu-id="d53c5-p102">This can encompass any non-table object. A stored query (view or procedure) is one example.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d53c5-119"><em>container</em></span><span class="sxs-lookup"><span data-stu-id="d53c5-119"><em>container</em></span></span></p></td>
<td><p><span data-ttu-id="d53c5-120">有效容器的名称。</span><span class="sxs-lookup"><span data-stu-id="d53c5-120">The name of a valid container.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d53c5-121"><em>authorizationname</em></span><span class="sxs-lookup"><span data-stu-id="d53c5-121"><em>authorizationname</em></span></span></p></td>
<td><p><span data-ttu-id="d53c5-122">用户名或组名。</span><span class="sxs-lookup"><span data-stu-id="d53c5-122">A user or group name.</span></span></p></td>
</tr>
</tbody>
</table>

