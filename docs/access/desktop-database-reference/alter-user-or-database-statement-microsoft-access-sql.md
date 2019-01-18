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
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28702283"
---
# <a name="alter-user-or-database-statement-microsoft-access-sql"></a><span data-ttu-id="bbac3-102">ALTER USER 或 DATABASE 语句 (Microsoft Access SQL)</span><span class="sxs-lookup"><span data-stu-id="bbac3-102">ALTER USER or DATABASE statement (Microsoft Access SQL)</span></span>

<span data-ttu-id="bbac3-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="bbac3-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="bbac3-104">更改现有用户或数据库的密码。</span><span class="sxs-lookup"><span data-stu-id="bbac3-104">Changes the password for an existing user or for a database.</span></span>

## <a name="syntax"></a><span data-ttu-id="bbac3-105">语法</span><span class="sxs-lookup"><span data-stu-id="bbac3-105">Syntax</span></span>

<span data-ttu-id="bbac3-106">更改数据库密码*newpassword 旧密码*</span><span class="sxs-lookup"><span data-stu-id="bbac3-106">ALTER DATABASE PASSWORD *newpassword oldpassword*</span></span>

<span data-ttu-id="bbac3-107">ALTER USER*用户*密码*newpassword 旧密码*</span><span class="sxs-lookup"><span data-stu-id="bbac3-107">ALTER USER *user* PASSWORD *newpassword oldpassword*</span></span>

<span data-ttu-id="bbac3-108">ALTER USER 或 DATABASE 语句包含以下部分：</span><span class="sxs-lookup"><span data-stu-id="bbac3-108">The ALTER USER or DATABASE statement has these parts:</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="bbac3-109">部分</span><span class="sxs-lookup"><span data-stu-id="bbac3-109">Part</span></span></p></th>
<th><p><span data-ttu-id="bbac3-110">说明</span><span class="sxs-lookup"><span data-stu-id="bbac3-110">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bbac3-111"><em>用户</em></span><span class="sxs-lookup"><span data-stu-id="bbac3-111"><em>user</em></span></span></p></td>
<td><p><span data-ttu-id="bbac3-112">要添加到工作组信息文件中的用户的名称。</span><span class="sxs-lookup"><span data-stu-id="bbac3-112">The name of a user to be added to the workgroup information file.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bbac3-113"><em>newpassword</em></span><span class="sxs-lookup"><span data-stu-id="bbac3-113"><em>newpassword</em></span></span></p></td>
<td><p><span data-ttu-id="bbac3-114">与指定的 <em>user</em> 或 <em>database</em> 名称相关联的新密码。</span><span class="sxs-lookup"><span data-stu-id="bbac3-114">The new password to be associated with the specified <em>user</em> or <em>database</em> name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bbac3-115"><em>oldpassword</em></span><span class="sxs-lookup"><span data-stu-id="bbac3-115"><em>oldpassword</em></span></span></p></td>
<td><p><span data-ttu-id="bbac3-116">与指定的 <em>user</em> 或 <em>group</em> 名称相关联的现有密码。</span><span class="sxs-lookup"><span data-stu-id="bbac3-116">The existing password to be associated with the specified <em>user</em> or <em>group</em> name.</span></span></p></td>
</tr>
</tbody>
</table>

