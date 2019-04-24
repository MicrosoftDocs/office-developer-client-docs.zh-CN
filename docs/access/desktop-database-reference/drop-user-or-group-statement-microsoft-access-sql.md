---
title: DROP USER 或 GROUP 语句 (Microsoft Access SQL)
TOCTitle: DROP USER or GROUP statement (Microsoft Access SQL)
ms:assetid: 46bc5916-556b-17df-2f4c-8fd7bbd21ef7
ms:mtpsurl: https://msdn.microsoft.com/library/Ff193192(v=office.15)
ms:contentKeyID: 48544575
ms.date: 10/18/2018
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 995f935ceea5af3b740215c5a4137e02e7ebb1b2
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32293642"
---
# <a name="drop-user-or-group-statement-microsoft-access-sql"></a><span data-ttu-id="2ac1b-102">DROP USER 或 GROUP 语句 (Microsoft Access SQL)</span><span class="sxs-lookup"><span data-stu-id="2ac1b-102">DROP USER or GROUP statement (Microsoft Access SQL)</span></span>

<span data-ttu-id="2ac1b-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="2ac1b-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="2ac1b-104">删除一个或多个现有*用户*或*组*, 或者从现有*组*中删除一个或多个现有*用户*。</span><span class="sxs-lookup"><span data-stu-id="2ac1b-104">Deletes one or more existing *users* or *groups*, or removes one or more existing *users* from an existing *group*.</span></span>

## <a name="syntax"></a><span data-ttu-id="2ac1b-105">语法</span><span class="sxs-lookup"><span data-stu-id="2ac1b-105">Syntax</span></span>

### <a name="delete-one-or-more-users-or-remove-one-or-more-users-from-a-group"></a><span data-ttu-id="2ac1b-106">删除一个或多个用户, 或者从组中删除一个或多个用户</span><span class="sxs-lookup"><span data-stu-id="2ac1b-106">Delete one or more users or remove one or more users from a group</span></span>

<span data-ttu-id="2ac1b-107">删除用户*用户*\[、*用户*.。。\] \[ \*\*\]</span><span class="sxs-lookup"><span data-stu-id="2ac1b-107">DROP USER *user*\[, *user*, …\] \[FROM *group*\]</span></span>

### <a name="delete-one-or-more-groups"></a><span data-ttu-id="2ac1b-108">删除一个或多个组</span><span class="sxs-lookup"><span data-stu-id="2ac1b-108">Delete one or more groups</span></span>

<span data-ttu-id="2ac1b-109">删除组*组*\[、*组*.。。\]</span><span class="sxs-lookup"><span data-stu-id="2ac1b-109">DROP GROUP *group*\[, *group*, …\]</span></span>

<span data-ttu-id="2ac1b-110">DROP USER 或 GROUP 语句包含以下部分：</span><span class="sxs-lookup"><span data-stu-id="2ac1b-110">The DROP USER or GROUP statement has these parts:</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="2ac1b-111">Part</span><span class="sxs-lookup"><span data-stu-id="2ac1b-111">Part</span></span></p></th>
<th><p><span data-ttu-id="2ac1b-112">说明</span><span class="sxs-lookup"><span data-stu-id="2ac1b-112">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2ac1b-113"><em>user</em></span><span class="sxs-lookup"><span data-stu-id="2ac1b-113"><em>user</em></span></span></p></td>
<td><p><span data-ttu-id="2ac1b-114">要从工作组信息文件中删除的用户的名称。</span><span class="sxs-lookup"><span data-stu-id="2ac1b-114">The name of a user to be removed from the workgroup information file.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ac1b-115"><em>组</em></span><span class="sxs-lookup"><span data-stu-id="2ac1b-115"><em>group</em></span></span></p></td>
<td><p><span data-ttu-id="2ac1b-116">要从工作组信息文件中删除的组的名称。</span><span class="sxs-lookup"><span data-stu-id="2ac1b-116">The name of a group to be removed from the workgroup information file.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="2ac1b-117">注解</span><span class="sxs-lookup"><span data-stu-id="2ac1b-117">Remarks</span></span>

<span data-ttu-id="2ac1b-118">如果在 DROP USER 语句中使用 FROM 关键字, 则语句中列出的每个*用户*都将从 from 关键字后面指定的*组*中删除。</span><span class="sxs-lookup"><span data-stu-id="2ac1b-118">If the FROM keyword is used in the DROP USER statement, each of the *users* listed in the statement will be removed from the *group* specified following the FROM keyword.</span></span> <span data-ttu-id="2ac1b-119">但是,*用户*本身不会被删除。</span><span class="sxs-lookup"><span data-stu-id="2ac1b-119">However, the *users* themselves will not be deleted.</span></span>

<span data-ttu-id="2ac1b-120">DROP GROUP 语句将删除指定的*组*。</span><span class="sxs-lookup"><span data-stu-id="2ac1b-120">The DROP GROUP statement will delete the specified *group*(s).</span></span> <span data-ttu-id="2ac1b-121">属于*组*成员的*用户*将不会受到影响, 但它们将不再是已删除*组*的成员。</span><span class="sxs-lookup"><span data-stu-id="2ac1b-121">The *users* who are members of the *group*(s) will not be affected, but they will no longer be members of the deleted *group*(s).</span></span>

