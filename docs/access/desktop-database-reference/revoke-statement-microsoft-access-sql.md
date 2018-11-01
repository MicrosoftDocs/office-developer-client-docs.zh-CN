---
title: REVOKE 语句 (Microsoft Access SQL)
TOCTitle: REVOKE statement (Microsoft Access SQL)
ms:assetid: 69399fd6-c4e8-f2e2-e5f4-48ae779323f5
ms:mtpsurl: https://msdn.microsoft.com/library/Ff195272(v=office.15)
ms:contentKeyID: 48545409
ms.date: 10/18/2018
mtps_version: v=office.15
f1_keywords:
- jetsql40.chm5277479
f1_categories:
- Office.Version=v15
ms.openlocfilehash: c3a7a64eee4617c07c1a655e34223f0531e16b18
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/01/2018
ms.locfileid: "25890895"
---
# <a name="revoke-statement-microsoft-access-sql"></a><span data-ttu-id="e8cbe-102">REVOKE 语句 (Microsoft Access SQL)</span><span class="sxs-lookup"><span data-stu-id="e8cbe-102">REVOKE statement (Microsoft Access SQL)</span></span>

<span data-ttu-id="e8cbe-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="e8cbe-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="e8cbe-104">撤消现有用户或组的指定权限。</span><span class="sxs-lookup"><span data-stu-id="e8cbe-104">Revokes specific privileges from an existing user or group.</span></span>

## <a name="syntax"></a><span data-ttu-id="e8cbe-105">语法</span><span class="sxs-lookup"><span data-stu-id="e8cbe-105">Syntax</span></span>

<span data-ttu-id="e8cbe-106">REVOKE {*privilege*\[， *privilege*，...\]} ON {表*表*|对象*对象*|</span><span class="sxs-lookup"><span data-stu-id="e8cbe-106">REVOKE {*privilege*\[, *privilege*, …\]} ON {TABLE *table* | OBJECT *object*|</span></span>

<span data-ttu-id="e8cbe-107">CONTAINTER *container*} FROM {*authorizationname*\[， *authorizationname*，...\]}</span><span class="sxs-lookup"><span data-stu-id="e8cbe-107">CONTAINTER *container*} FROM {*authorizationname*\[, *authorizationname*, …\]}</span></span>

<span data-ttu-id="e8cbe-108">REVOKE 语句包含以下部分：</span><span class="sxs-lookup"><span data-stu-id="e8cbe-108">The REVOKE statement has these parts:</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="e8cbe-109">部分</span><span class="sxs-lookup"><span data-stu-id="e8cbe-109">Part</span></span></p></th>
<th><p><span data-ttu-id="e8cbe-110">说明</span><span class="sxs-lookup"><span data-stu-id="e8cbe-110">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e8cbe-111"><em>privilege</em></span><span class="sxs-lookup"><span data-stu-id="e8cbe-111"><em>privilege</em></span></span></p></td>
<td><p><span data-ttu-id="e8cbe-112">权限被吊销。</span><span class="sxs-lookup"><span data-stu-id="e8cbe-112">The privilege or privileges to be revoked.</span></span> <span data-ttu-id="e8cbe-113">使用以下关键字指定权限： 选择、 删除、 插入、 更新、 投递、 SELECTSECURITY、 UPDATESECURITY、 DBPASSWORD、 UPDATEIDENTITY、 CREATE、 SELECTSCHEMA、 架构和 UPDATEOWNER。</span><span class="sxs-lookup"><span data-stu-id="e8cbe-113">Privileges are specified using the following keywords: SELECT, DELETE, INSERT, UPDATE, DROP, SELECTSECURITY, UPDATESECURITY, DBPASSWORD, UPDATEIDENTITY, CREATE, SELECTSCHEMA, SCHEMA, and UPDATEOWNER.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8cbe-114"><em>table</em></span><span class="sxs-lookup"><span data-stu-id="e8cbe-114"><em>table</em></span></span></p></td>
<td><p><span data-ttu-id="e8cbe-115">任何有效的表名。</span><span class="sxs-lookup"><span data-stu-id="e8cbe-115">Any valid table name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8cbe-116"><em>object</em></span><span class="sxs-lookup"><span data-stu-id="e8cbe-116"><em>object</em></span></span></p></td>
<td><p><span data-ttu-id="e8cbe-p102">可以包含任何非表对象。存储查询（视图或过程）就是一个示例。</span><span class="sxs-lookup"><span data-stu-id="e8cbe-p102">This can encompass any non-table object. A stored query (view or procedure) is one example.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8cbe-119"><em>container</em></span><span class="sxs-lookup"><span data-stu-id="e8cbe-119"><em>container</em></span></span></p></td>
<td><p><span data-ttu-id="e8cbe-120">有效容器的名称。</span><span class="sxs-lookup"><span data-stu-id="e8cbe-120">The name of a valid container.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8cbe-121"><em>authorizationname</em></span><span class="sxs-lookup"><span data-stu-id="e8cbe-121"><em>authorizationname</em></span></span></p></td>
<td><p><span data-ttu-id="e8cbe-122">用户名或组名。</span><span class="sxs-lookup"><span data-stu-id="e8cbe-122">A user or group name.</span></span></p></td>
</tr>
</tbody>
</table>

