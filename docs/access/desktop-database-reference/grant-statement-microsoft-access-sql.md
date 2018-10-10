---
title: GRANT 语句 (Microsoft Access SQL)
TOCTitle: GRANT Statement (Microsoft Access SQL)
ms:assetid: 50ae97ae-d5be-57e5-d9da-f3fc42f01d83
ms:mtpsurl: https://msdn.microsoft.com/library/Ff193820(v=office.15)
ms:contentKeyID: 48544800
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- jetsql40.chm5277478
f1_categories:
- Office.Version=v15
ms.openlocfilehash: d4fffc9ac40586be899de0dd4054ba39dd3a6489
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25465546"
---
# <a name="grant-statement-microsoft-access-sql"></a><span data-ttu-id="6af13-102">GRANT 语句 (Microsoft Access SQL)</span><span class="sxs-lookup"><span data-stu-id="6af13-102">GRANT Statement (Microsoft Access SQL)</span></span>


<span data-ttu-id="6af13-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="6af13-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="6af13-104">为现有用户或组授予指定的特权。</span><span class="sxs-lookup"><span data-stu-id="6af13-104">Grants specific privileges to an existing user or group.</span></span>

## <a name="syntax"></a><span data-ttu-id="6af13-105">语法</span><span class="sxs-lookup"><span data-stu-id="6af13-105">Syntax</span></span>

<span data-ttu-id="6af13-106">GRANT {*privilege*\[， *privilege*，...\]} ON {表*表*|对象*对象*|</span><span class="sxs-lookup"><span data-stu-id="6af13-106">GRANT {*privilege*\[, *privilege*, …\]} ON{TABLE *table* | OBJECT *object*|</span></span>

<span data-ttu-id="6af13-107">CONTAINER *container* } TO {*authorizationname*\[， *authorizationname*，...\]}</span><span class="sxs-lookup"><span data-stu-id="6af13-107">CONTAINER *container* } TO {*authorizationname*\[, *authorizationname*, …\]}</span></span>

<span data-ttu-id="6af13-108">GRANT 语句包含以下部分：</span><span class="sxs-lookup"><span data-stu-id="6af13-108">The GRANT statement has these parts:</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="6af13-109">部分</span><span class="sxs-lookup"><span data-stu-id="6af13-109">Part</span></span></p></th>
<th><p><span data-ttu-id="6af13-110">说明</span><span class="sxs-lookup"><span data-stu-id="6af13-110">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6af13-111"><em>privilege</em></span><span class="sxs-lookup"><span data-stu-id="6af13-111"><em>privilege</em></span></span></p></td>
<td><p><span data-ttu-id="6af13-112">要授予的权限。</span><span class="sxs-lookup"><span data-stu-id="6af13-112">The privilege or privileges to be granted.</span></span> <span data-ttu-id="6af13-113">使用以下关键字指定权限： 选择、 删除、 插入、 更新、 DROP、 SELECTSECURITY、 UPDATESECURITY、 DBPASSWORD、 UPDATEIDENTITY、 CREATE、 SELECTSCHEMA、 架构和 UPDATEOWNER。</span><span class="sxs-lookup"><span data-stu-id="6af13-113">Privileges are specified using the following keywords: SELECT, DELETE, INSERT, UPDATE, DROP, SELECTSECURITY, UPDATESECURITY, DBPASSWORD, UPDATEIDENTITY, CREATE, SELECTSCHEMA, SCHEMA and UPDATEOWNER.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6af13-114"><em>tablename</em></span><span class="sxs-lookup"><span data-stu-id="6af13-114"><em>tablename</em></span></span></p></td>
<td><p><span data-ttu-id="6af13-115">任何有效的表名。</span><span class="sxs-lookup"><span data-stu-id="6af13-115">Any valid table name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6af13-116"><em>object</em></span><span class="sxs-lookup"><span data-stu-id="6af13-116"><em>object</em></span></span></p></td>
<td><p><span data-ttu-id="6af13-p102">可以包含任何非表对象。存储查询（视图或过程）就是一个示例。</span><span class="sxs-lookup"><span data-stu-id="6af13-p102">This can encompass any non-table object. A stored query (view or procedure) is one example.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6af13-119"><em>container</em></span><span class="sxs-lookup"><span data-stu-id="6af13-119"><em>container</em></span></span></p></td>
<td><p><span data-ttu-id="6af13-120">有效容器的名称。</span><span class="sxs-lookup"><span data-stu-id="6af13-120">The name of a valid container.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6af13-121"><em>authorizationname</em></span><span class="sxs-lookup"><span data-stu-id="6af13-121"><em>authorizationname</em></span></span></p></td>
<td><p><span data-ttu-id="6af13-122">用户名或组名。</span><span class="sxs-lookup"><span data-stu-id="6af13-122">A user or group name.</span></span></p></td>
</tr>
</tbody>
</table>

