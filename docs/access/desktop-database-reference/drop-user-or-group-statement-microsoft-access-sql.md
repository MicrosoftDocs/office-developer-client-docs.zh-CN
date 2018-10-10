---
title: DROP USER 或 GROUP 语句 (Microsoft Access SQL)
TOCTitle: DROP USER or GROUP Statement (Microsoft Access SQL)
ms:assetid: 46bc5916-556b-17df-2f4c-8fd7bbd21ef7
ms:mtpsurl: https://msdn.microsoft.com/library/Ff193192(v=office.15)
ms:contentKeyID: 48544575
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 3a5cf75de06c13e2452e5f33b8355b7fb480d8a3
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466043"
---
# <a name="drop-user-or-group-statement-microsoft-access-sql"></a><span data-ttu-id="5f361-102">DROP USER 或 GROUP 语句 (Microsoft Access SQL)</span><span class="sxs-lookup"><span data-stu-id="5f361-102">DROP USER or GROUP Statement (Microsoft Access SQL)</span></span>


<span data-ttu-id="5f361-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="5f361-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="5f361-104">删除一个或多个现有*用户*或*组*，或者从现有*组*中删除一个或多个现有的*用户*。</span><span class="sxs-lookup"><span data-stu-id="5f361-104">Deletes one or more existing *user*s or *group*s, or removes one or more existing *user*s from an existing *group*.</span></span>

## <a name="syntax"></a><span data-ttu-id="5f361-105">语法</span><span class="sxs-lookup"><span data-stu-id="5f361-105">Syntax</span></span>

<span data-ttu-id="5f361-106">删除一个或多个*用户*，或者从*组*中删除一个或多个*用户*：</span><span class="sxs-lookup"><span data-stu-id="5f361-106">Delete one or more *user*s or remove one or more *user*s from a *group*:</span></span>

<span data-ttu-id="5f361-107">DROP USER*用户*\[，*用户*...\] \[从*组*\]</span><span class="sxs-lookup"><span data-stu-id="5f361-107">DROP USER *user*\[, *user*, …\] \[FROM *group*\]</span></span>

<span data-ttu-id="5f361-108">删除一个或多个*组*：</span><span class="sxs-lookup"><span data-stu-id="5f361-108">Delete one or more *group*s:</span></span>

<span data-ttu-id="5f361-109">投递组*组*\[，*组*中，...\]</span><span class="sxs-lookup"><span data-stu-id="5f361-109">DROP GROUP *group*\[, *group*, …\]</span></span>

<span data-ttu-id="5f361-110">DROP USER 或 GROUP 语句包含以下部分：</span><span class="sxs-lookup"><span data-stu-id="5f361-110">The DROP USER or GROUP statement has these parts:</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="5f361-111">部分</span><span class="sxs-lookup"><span data-stu-id="5f361-111">Part</span></span></p></th>
<th><p><span data-ttu-id="5f361-112">说明</span><span class="sxs-lookup"><span data-stu-id="5f361-112">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5f361-113"><em>用户</em></span><span class="sxs-lookup"><span data-stu-id="5f361-113"><em>user</em></span></span></p></td>
<td><p><span data-ttu-id="5f361-114">要从工作组信息文件中删除的用户的名称。</span><span class="sxs-lookup"><span data-stu-id="5f361-114">The name of a user to be removed from the workgroup information file.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f361-115"><em>组</em></span><span class="sxs-lookup"><span data-stu-id="5f361-115"><em>group</em></span></span></p></td>
<td><p><span data-ttu-id="5f361-116">要从工作组信息文件中删除的组的名称。</span><span class="sxs-lookup"><span data-stu-id="5f361-116">The name of a group to be removed from the workgroup information file.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="5f361-117">注解</span><span class="sxs-lookup"><span data-stu-id="5f361-117">Remarks</span></span>

<span data-ttu-id="5f361-p101">如果在 DROP USER 语句中使用了 FROM 关键字，那么在该语句中列出的每个*用户*都将从 FROM 关键字后面所指定的*组*中删除。然而，*用户*自身不会被删除。</span><span class="sxs-lookup"><span data-stu-id="5f361-p101">If the FROM keyword is used in the DROP USER statement, then each of the *user*s listed in the statement will be removed from the *group* specified following the FROM keyword. However, the *user*s themselves will not be deleted.</span></span>

<span data-ttu-id="5f361-p102">DROP GROUP 语句将删除指定的*组*。属于该*组*的*用户*不会受到影响，但他们将不再是已删除的*组*的成员。</span><span class="sxs-lookup"><span data-stu-id="5f361-p102">The DROP GROUP statement will delete the specified *group*(s). The *user*s who are members of the *group*(s) will not be affected, but they will no longer be members of the deleted *group*(s).</span></span>

