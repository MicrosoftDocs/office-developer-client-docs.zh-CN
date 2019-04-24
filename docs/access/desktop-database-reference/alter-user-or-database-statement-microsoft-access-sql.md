---
title: ALTER USER 或 DATABASE 语句 (Microsoft Access SQL)
TOCTitle: ALTER USER or DATABASE statement (Microsoft Access SQL)
ms:assetid: 86ccd296-5171-97e7-683f-cdaab4bde9ab
ms:mtpsurl: https://msdn.microsoft.com/library/Ff197012(v=office.15)
ms:contentKeyID: 48546093
ms.date: 10/18/2018
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 2514ca6403ce70acae9e344d610fbd7b9ba7d73b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32297177"
---
# <a name="alter-user-or-database-statement-microsoft-access-sql"></a><span data-ttu-id="f30c8-102">ALTER USER 或 DATABASE 语句 (Microsoft Access SQL)</span><span class="sxs-lookup"><span data-stu-id="f30c8-102">ALTER USER or DATABASE statement (Microsoft Access SQL)</span></span>

<span data-ttu-id="f30c8-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="f30c8-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="f30c8-104">更改现有用户或数据库的密码。</span><span class="sxs-lookup"><span data-stu-id="f30c8-104">Changes the password for an existing user or for a database.</span></span>

## <a name="syntax"></a><span data-ttu-id="f30c8-105">语法</span><span class="sxs-lookup"><span data-stu-id="f30c8-105">Syntax</span></span>

<span data-ttu-id="f30c8-106">ALTER DATABASE PASSWORD *newpassword oldpassword*</span><span class="sxs-lookup"><span data-stu-id="f30c8-106">ALTER DATABASE PASSWORD *newpassword oldpassword*</span></span>

<span data-ttu-id="f30c8-107">ALTER USER *user* PASSWORD *newpassword oldpassword*</span><span class="sxs-lookup"><span data-stu-id="f30c8-107">ALTER USER *user* PASSWORD *newpassword oldpassword*</span></span>

<span data-ttu-id="f30c8-108">ALTER USER 或 DATABASE 语句包含以下部分：</span><span class="sxs-lookup"><span data-stu-id="f30c8-108">The ALTER USER or DATABASE statement has these parts:</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="f30c8-109">Part</span><span class="sxs-lookup"><span data-stu-id="f30c8-109">Part</span></span></p></th>
<th><p><span data-ttu-id="f30c8-110">说明</span><span class="sxs-lookup"><span data-stu-id="f30c8-110">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f30c8-111"><em>user</em></span><span class="sxs-lookup"><span data-stu-id="f30c8-111"><em>user</em></span></span></p></td>
<td><p><span data-ttu-id="f30c8-112">要添加到工作组信息文件中的用户的名称。</span><span class="sxs-lookup"><span data-stu-id="f30c8-112">The name of a user to be added to the workgroup information file.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f30c8-113"><em>newpassword</em></span><span class="sxs-lookup"><span data-stu-id="f30c8-113"><em>newpassword</em></span></span></p></td>
<td><p><span data-ttu-id="f30c8-114">与指定的 <em>user</em> 或 <em>database</em> 名称相关联的新密码。</span><span class="sxs-lookup"><span data-stu-id="f30c8-114">The new password to be associated with the specified <em>user</em> or <em>database</em> name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f30c8-115"><em>oldpassword</em></span><span class="sxs-lookup"><span data-stu-id="f30c8-115"><em>oldpassword</em></span></span></p></td>
<td><p><span data-ttu-id="f30c8-116">与指定的 <em>user</em> 或 <em>group</em> 名称相关联的现有密码。</span><span class="sxs-lookup"><span data-stu-id="f30c8-116">The existing password to be associated with the specified <em>user</em> or <em>group</em> name.</span></span></p></td>
</tr>
</tbody>
</table>

