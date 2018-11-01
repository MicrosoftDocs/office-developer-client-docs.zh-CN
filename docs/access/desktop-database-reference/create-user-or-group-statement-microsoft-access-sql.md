---
title: CREATE USER 或 GROUP 语句 (Microsoft Access SQL)
TOCTitle: CREATE USER or GROUP statement (Microsoft Access SQL)
ms:assetid: 62148ce2-0f81-944e-a1ab-edef990fff9f
ms:mtpsurl: https://msdn.microsoft.com/library/Ff194914(v=office.15)
ms:contentKeyID: 48545229
ms.date: 10/18/2018
mtps_version: v=office.15
ms.openlocfilehash: cd33755800d0ed820a9690a6910f3edf064c3c82
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25872191"
---
# <a name="create-user-or-group-statement-microsoft-access-sql"></a><span data-ttu-id="1607b-102">CREATE USER 或 GROUP 语句 (Microsoft Access SQL)</span><span class="sxs-lookup"><span data-stu-id="1607b-102">CREATE USER or GROUP statement (Microsoft Access SQL)</span></span>

<span data-ttu-id="1607b-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="1607b-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="1607b-104">新建一个或多个用户或组。</span><span class="sxs-lookup"><span data-stu-id="1607b-104">Creates one or more new users or groups.</span></span>

## <a name="syntax"></a><span data-ttu-id="1607b-105">语法</span><span class="sxs-lookup"><span data-stu-id="1607b-105">Syntax</span></span>

<span data-ttu-id="1607b-106">**创建用户**：</span><span class="sxs-lookup"><span data-stu-id="1607b-106">**Create a user**:</span></span>

<span data-ttu-id="1607b-107">CREATE USER *user* *密码 pid* \[，*用户\*\*密码 pid*，...\]</span><span class="sxs-lookup"><span data-stu-id="1607b-107">CREATE USER *user* *password pid* \[, *user* *password pid*, …\]</span></span>

<span data-ttu-id="1607b-108">**创建组**：</span><span class="sxs-lookup"><span data-stu-id="1607b-108">**Create a group**:</span></span>

<span data-ttu-id="1607b-109">创建组*组* *pid*\[，*组* *pid*，...\]</span><span class="sxs-lookup"><span data-stu-id="1607b-109">CREATE GROUP *group* *pid*\[, *group* *pid*, …\]</span></span>

<span data-ttu-id="1607b-110">CREATE USER 或 GROUP 语句包含以下部分：</span><span class="sxs-lookup"><span data-stu-id="1607b-110">The CREATE USER or GROUP statement has these parts:</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="1607b-111">部分</span><span class="sxs-lookup"><span data-stu-id="1607b-111">Part</span></span></p></th>
<th><p><span data-ttu-id="1607b-112">说明</span><span class="sxs-lookup"><span data-stu-id="1607b-112">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1607b-113"><em>用户</em></span><span class="sxs-lookup"><span data-stu-id="1607b-113"><em>user</em></span></span></p></td>
<td><p><span data-ttu-id="1607b-114">要添加到工作组信息文件中的用户的名称。</span><span class="sxs-lookup"><span data-stu-id="1607b-114">The name of a user to be added to the workgroup information file.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1607b-115"><em>组</em></span><span class="sxs-lookup"><span data-stu-id="1607b-115"><em>group</em></span></span></p></td>
<td><p><span data-ttu-id="1607b-116">要添加到工作组信息文件中的组的名称。</span><span class="sxs-lookup"><span data-stu-id="1607b-116">The name of a group to be added to the workgroup information file.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1607b-117"><em>password</em></span><span class="sxs-lookup"><span data-stu-id="1607b-117"><em>password</em></span></span></p></td>
<td><p><span data-ttu-id="1607b-118">与指定的 <em>user</em> 名称相关联的密码。</span><span class="sxs-lookup"><span data-stu-id="1607b-118">The password to be associated with the specified <em>user</em> name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1607b-119"><em>pid</em></span><span class="sxs-lookup"><span data-stu-id="1607b-119"><em>pid</em></span></span></p></td>
<td><p><span data-ttu-id="1607b-120">个人标识。</span><span class="sxs-lookup"><span data-stu-id="1607b-120">The personal id.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="1607b-121">说明</span><span class="sxs-lookup"><span data-stu-id="1607b-121">Remarks</span></span>

<span data-ttu-id="1607b-122">*用户*和*组*不能具有相同的名称。</span><span class="sxs-lookup"><span data-stu-id="1607b-122">A *user* and a *group* cannot have the same name.</span></span>

<span data-ttu-id="1607b-123">*密码*，则需要为每个*用户*或*组*的创建。</span><span class="sxs-lookup"><span data-stu-id="1607b-123">A *password* is required for each *user* or *group* that is created.</span></span>

