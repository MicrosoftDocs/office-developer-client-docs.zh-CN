---
title: 自定义文件 UserList 部分
TOCTitle: Customization File UserList section
ms:assetid: b60ba3b0-37d4-bb59-d3cd-2ab44d178b8a
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249873(v=office.15)
ms:contentKeyID: 48547263
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: ecaf77765051a202925449d0221f0a68a2a06622
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32295154"
---
# <a name="customization-file-userlist-section"></a><span data-ttu-id="eb37c-102">自定义文件 UserList 部分</span><span class="sxs-lookup"><span data-stu-id="eb37c-102">Customization File UserList section</span></span>


<span data-ttu-id="eb37c-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="eb37c-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="eb37c-104">**userlist** 节与具有相同节 *identifier* 参数的 **connect** 节相关。</span><span class="sxs-lookup"><span data-stu-id="eb37c-104">The **userlist** section pertains to the **connect** section with the same section *identifier* parameter.</span></span>

<span data-ttu-id="eb37c-105">此节可以包含*用户访问项*, 该条目指定指定用户的访问权限, 并替代匹配**connect**节中的*默认\*\*访问项*。</span><span class="sxs-lookup"><span data-stu-id="eb37c-105">This section can contain a *user access entry*, which specifies access rights for the specified user and overrides the *default* *access entry* in the matching **connect** section.</span></span>

## <a name="syntax"></a><span data-ttu-id="eb37c-106">语法</span><span class="sxs-lookup"><span data-stu-id="eb37c-106">Syntax</span></span>

<span data-ttu-id="eb37c-107">用户访问项的格式为：</span><span class="sxs-lookup"><span data-stu-id="eb37c-107">A user access entry is of the form:</span></span>

<span data-ttu-id="eb37c-108">*userName \* \* \* =* accessRights \* \* \*</span><span class="sxs-lookup"><span data-stu-id="eb37c-108">*userName\*\*\*=* accessRights\*\*\*</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="eb37c-109">Part</span><span class="sxs-lookup"><span data-stu-id="eb37c-109">Part</span></span></p></th>
<th><p><span data-ttu-id="eb37c-110">说明</span><span class="sxs-lookup"><span data-stu-id="eb37c-110">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="eb37c-111"><em>userName</em></span><span class="sxs-lookup"><span data-stu-id="eb37c-111"><em>userName</em></span></span></p></td>
<td><p><span data-ttu-id="eb37c-112">表示使用此连接的用户的<em>用户名称</em>。</span><span class="sxs-lookup"><span data-stu-id="eb37c-112">The <em>user name</em> of the person employing this connection.</span></span> <span data-ttu-id="eb37c-113">有效的用户名称是用 IIS“服务管理器”<strong></strong>对话框建立的。</span><span class="sxs-lookup"><span data-stu-id="eb37c-113">Valid user names are established with the IIS <strong>Service Manager</strong> dialog.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb37c-114"><strong><em>accessRights</em></strong></span><span class="sxs-lookup"><span data-stu-id="eb37c-114"><strong><em>accessRights</em></strong></span></span></p></td>
<td><p><span data-ttu-id="eb37c-115">表示下列访问权之一：</span><span class="sxs-lookup"><span data-stu-id="eb37c-115">One of the following access rights:</span></span><br />
</p>
<ul>
<li><p><span data-ttu-id="eb37c-116"><strong>NoAccess</strong> - 用户无法访问数据源。</span><span class="sxs-lookup"><span data-stu-id="eb37c-116"><strong>NoAccess</strong> — User cannot access the data source.</span></span></p></li>
<li><p><span data-ttu-id="eb37c-117"><strong>ReadOnly</strong> - 用户可以读取数据源。</span><span class="sxs-lookup"><span data-stu-id="eb37c-117"><strong>ReadOnly</strong> — User can read the data source.</span></span></p></li>
<li><p><span data-ttu-id="eb37c-118"><strong>ReadWrite</strong> - 用户可以读取或写入数据源。</span><span class="sxs-lookup"><span data-stu-id="eb37c-118"><strong>ReadWrite</strong> — User can read or write to the data source.</span></span></p></li>
</ul>
<p></p></td>
</tr>
</tbody>
</table>

