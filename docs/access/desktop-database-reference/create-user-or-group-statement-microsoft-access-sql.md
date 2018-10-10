---
title: CREATE USER 或 GROUP 语句 (Microsoft Access SQL)
TOCTitle: CREATE USER or GROUP Statement (Microsoft Access SQL)
ms:assetid: 62148ce2-0f81-944e-a1ab-edef990fff9f
ms:mtpsurl: https://msdn.microsoft.com/library/Ff194914(v=office.15)
ms:contentKeyID: 48545229
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: dce5b9a6894eb1e09a0307b389207baefae6aa58
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467752"
---
# <a name="create-user-or-group-statement-microsoft-access-sql"></a><span data-ttu-id="29e0e-102">CREATE USER 或 GROUP 语句 (Microsoft Access SQL)</span><span class="sxs-lookup"><span data-stu-id="29e0e-102">CREATE USER or GROUP Statement (Microsoft Access SQL)</span></span>


<span data-ttu-id="29e0e-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="29e0e-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="29e0e-104">新建一个或多个用户或组。</span><span class="sxs-lookup"><span data-stu-id="29e0e-104">Creates one or more new users or groups.</span></span>

## <a name="syntax"></a><span data-ttu-id="29e0e-105">语法</span><span class="sxs-lookup"><span data-stu-id="29e0e-105">Syntax</span></span>

<span data-ttu-id="29e0e-106">创建用户：</span><span class="sxs-lookup"><span data-stu-id="29e0e-106">Create a user:</span></span>

<span data-ttu-id="29e0e-107">CREATE USER *user* *密码 pid* \[，*用户\*\*密码 pid*，...\]</span><span class="sxs-lookup"><span data-stu-id="29e0e-107">CREATE USER *user* *password pid* \[, *user* *password pid*, …\]</span></span>

<span data-ttu-id="29e0e-108">创建组：</span><span class="sxs-lookup"><span data-stu-id="29e0e-108">Create a group:</span></span>

<span data-ttu-id="29e0e-109">创建组*组* *pid*\[，*组* *pid*，...\]</span><span class="sxs-lookup"><span data-stu-id="29e0e-109">CREATE GROUP *group* *pid*\[, *group* *pid*, …\]</span></span>

<span data-ttu-id="29e0e-110">CREATE USER 或 GROUP 语句包含以下部分：</span><span class="sxs-lookup"><span data-stu-id="29e0e-110">The CREATE USER or GROUP statement has these parts:</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="29e0e-111">部分</span><span class="sxs-lookup"><span data-stu-id="29e0e-111">Part</span></span></p></th>
<th><p><span data-ttu-id="29e0e-112">说明</span><span class="sxs-lookup"><span data-stu-id="29e0e-112">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="29e0e-113"><em>用户</em></span><span class="sxs-lookup"><span data-stu-id="29e0e-113"><em>user</em></span></span></p></td>
<td><p><span data-ttu-id="29e0e-114">要添加到工作组信息文件中的用户的名称。</span><span class="sxs-lookup"><span data-stu-id="29e0e-114">The name of a user to be added to the workgroup information file.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29e0e-115"><em>组</em></span><span class="sxs-lookup"><span data-stu-id="29e0e-115"><em>group</em></span></span></p></td>
<td><p><span data-ttu-id="29e0e-116">要添加到工作组信息文件中的组的名称。</span><span class="sxs-lookup"><span data-stu-id="29e0e-116">The name of a group to be added to the workgroup information file.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29e0e-117"><em>password</em></span><span class="sxs-lookup"><span data-stu-id="29e0e-117"><em>password</em></span></span></p></td>
<td><p><span data-ttu-id="29e0e-118">与指定的 <em>user</em> 名称相关联的密码。</span><span class="sxs-lookup"><span data-stu-id="29e0e-118">The password to be associated with the specified <em>user</em> name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29e0e-119"><em>pid</em></span><span class="sxs-lookup"><span data-stu-id="29e0e-119"><em>pid</em></span></span></p></td>
<td><p><span data-ttu-id="29e0e-120">个人标识。</span><span class="sxs-lookup"><span data-stu-id="29e0e-120">The personal id.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="29e0e-121">说明</span><span class="sxs-lookup"><span data-stu-id="29e0e-121">Remarks</span></span>

<span data-ttu-id="29e0e-122">*用户*和*组*不能具有相同的名称。</span><span class="sxs-lookup"><span data-stu-id="29e0e-122">A *user* and a *group* cannot have the same name.</span></span>

<span data-ttu-id="29e0e-123">*密码*，则需要为每个*用户*或*组*的创建。</span><span class="sxs-lookup"><span data-stu-id="29e0e-123">A *password* is required for each *user* or *group* that is created.</span></span>

