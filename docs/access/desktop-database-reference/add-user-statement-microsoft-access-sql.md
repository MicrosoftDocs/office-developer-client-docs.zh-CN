---
title: ADD USER 语句 (Microsoft Access SQL)
TOCTitle: ADD USER statement (Microsoft Access SQL)
ms:assetid: 1feb631f-cb8c-14ae-6214-276f1faf1a55
ms:mtpsurl: https://msdn.microsoft.com/library/Ff845862(v=office.15)
ms:contentKeyID: 48543652
ms.date: 10/18/2018
mtps_version: v=office.15
ms.openlocfilehash: 7a27874a7264258fee51f90fabaeecd180d7aeae
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25868607"
---
# <a name="add-user-statement-microsoft-access-sql"></a><span data-ttu-id="942d5-102">ADD USER 语句 (Microsoft Access SQL)</span><span class="sxs-lookup"><span data-stu-id="942d5-102">ADD USER statement (Microsoft Access SQL)</span></span>

<span data-ttu-id="942d5-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="942d5-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="942d5-104">将现有*用户*添加到现有*组*中。</span><span class="sxs-lookup"><span data-stu-id="942d5-104">Adds one or more existing *user*s to an existing *group*.</span></span>

## <a name="syntax"></a><span data-ttu-id="942d5-105">语法</span><span class="sxs-lookup"><span data-stu-id="942d5-105">Syntax</span></span>

<span data-ttu-id="942d5-106">添加用户*用户*\[，*用户*...\]到*组*</span><span class="sxs-lookup"><span data-stu-id="942d5-106">ADD USER *user*\[, *user*, …\] TO *group*</span></span>

<span data-ttu-id="942d5-107">ADD USER 语句包含以下部分：</span><span class="sxs-lookup"><span data-stu-id="942d5-107">The ADD USER statement has these parts:</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="942d5-108">部分</span><span class="sxs-lookup"><span data-stu-id="942d5-108">Part</span></span></p></th>
<th><p><span data-ttu-id="942d5-109">说明</span><span class="sxs-lookup"><span data-stu-id="942d5-109">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="942d5-110"><em>用户</em></span><span class="sxs-lookup"><span data-stu-id="942d5-110"><em>user</em></span></span></p></td>
<td><p><span data-ttu-id="942d5-111">要添加到工作组信息文件中的用户的名称。</span><span class="sxs-lookup"><span data-stu-id="942d5-111">The name of a user to be added to the workgroup information file.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="942d5-112"><em>组</em></span><span class="sxs-lookup"><span data-stu-id="942d5-112"><em>group</em></span></span></p></td>
<td><p><span data-ttu-id="942d5-113">要添加到工作组信息文件中的组的名称。</span><span class="sxs-lookup"><span data-stu-id="942d5-113">The name of a group to be added to the workgroup information file.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="942d5-114">注解</span><span class="sxs-lookup"><span data-stu-id="942d5-114">Remarks</span></span>

<span data-ttu-id="942d5-115">*用户*被添加到*组*后，*用户*将具有所有已向*组*授予的权限。</span><span class="sxs-lookup"><span data-stu-id="942d5-115">After a *user* had been added to a *group*, the *user* has all the permissions that have been granted to the *group*.</span></span>

