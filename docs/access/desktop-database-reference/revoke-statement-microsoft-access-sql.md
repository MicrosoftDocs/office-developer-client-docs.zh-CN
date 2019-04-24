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
localization_priority: Normal
ms.openlocfilehash: 20122fee617597987940766a076d5f968a87c2d2
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32306529"
---
# <a name="revoke-statement-microsoft-access-sql"></a><span data-ttu-id="0f984-102">REVOKE 语句 (Microsoft Access SQL)</span><span class="sxs-lookup"><span data-stu-id="0f984-102">REVOKE statement (Microsoft Access SQL)</span></span>

<span data-ttu-id="0f984-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="0f984-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="0f984-104">撤消现有用户或组的指定权限。</span><span class="sxs-lookup"><span data-stu-id="0f984-104">Revokes specific privileges from an existing user or group.</span></span>

## <a name="syntax"></a><span data-ttu-id="0f984-105">语法</span><span class="sxs-lookup"><span data-stu-id="0f984-105">Syntax</span></span>

<span data-ttu-id="0f984-106">撤消 {*特权*\[,*特权*, .。。\]} ON {TABLE *table* |object*对象*|</span><span class="sxs-lookup"><span data-stu-id="0f984-106">REVOKE {*privilege*\[, *privilege*, …\]} ON {TABLE *table* | OBJECT *object*|</span></span>

<span data-ttu-id="0f984-107">CONTAINTER*容器*} FROM {*authorizationname*\[, *authorizationname*, .。。\]}</span><span class="sxs-lookup"><span data-stu-id="0f984-107">CONTAINTER *container*} FROM {*authorizationname*\[, *authorizationname*, …\]}</span></span>

<span data-ttu-id="0f984-108">REVOKE 语句包含以下部分：</span><span class="sxs-lookup"><span data-stu-id="0f984-108">The REVOKE statement has these parts:</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="0f984-109">Part</span><span class="sxs-lookup"><span data-stu-id="0f984-109">Part</span></span></p></th>
<th><p><span data-ttu-id="0f984-110">说明</span><span class="sxs-lookup"><span data-stu-id="0f984-110">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0f984-111"><em>小特权</em></span><span class="sxs-lookup"><span data-stu-id="0f984-111"><em>privilege</em></span></span></p></td>
<td><p><span data-ttu-id="0f984-112">将被撤消的权限。</span><span class="sxs-lookup"><span data-stu-id="0f984-112">The privilege or privileges to be revoked.</span></span> <span data-ttu-id="0f984-113">使用以下关键字指定权限: SELECT、DELETE、INSERT、UPDATE、DROP、SELECTSECURITY、UPDATESECURITY、DBPASSWORD、UPDATEIDENTITY、CREATE、SELECTSCHEMA、SCHEMA 和 UPDATEOWNER。</span><span class="sxs-lookup"><span data-stu-id="0f984-113">Privileges are specified using the following keywords: SELECT, DELETE, INSERT, UPDATE, DROP, SELECTSECURITY, UPDATESECURITY, DBPASSWORD, UPDATEIDENTITY, CREATE, SELECTSCHEMA, SCHEMA, and UPDATEOWNER.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0f984-114"><em>table</em></span><span class="sxs-lookup"><span data-stu-id="0f984-114"><em>table</em></span></span></p></td>
<td><p><span data-ttu-id="0f984-115">任何有效的表名。</span><span class="sxs-lookup"><span data-stu-id="0f984-115">Any valid table name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0f984-116"><em>object</em></span><span class="sxs-lookup"><span data-stu-id="0f984-116"><em>object</em></span></span></p></td>
<td><p><span data-ttu-id="0f984-117">可以包含任何非表对象。</span><span class="sxs-lookup"><span data-stu-id="0f984-117">This can encompass any non-table object.</span></span> <span data-ttu-id="0f984-118">存储查询（视图或过程）就是一个示例。</span><span class="sxs-lookup"><span data-stu-id="0f984-118">A stored query (view or procedure) is one example.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0f984-119"><em>箱</em></span><span class="sxs-lookup"><span data-stu-id="0f984-119"><em>container</em></span></span></p></td>
<td><p><span data-ttu-id="0f984-120">有效容器的名称。</span><span class="sxs-lookup"><span data-stu-id="0f984-120">The name of a valid container.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0f984-121"><em>authorizationname</em></span><span class="sxs-lookup"><span data-stu-id="0f984-121"><em>authorizationname</em></span></span></p></td>
<td><p><span data-ttu-id="0f984-122">用户名或组名。</span><span class="sxs-lookup"><span data-stu-id="0f984-122">A user or group name.</span></span></p></td>
</tr>
</tbody>
</table>

