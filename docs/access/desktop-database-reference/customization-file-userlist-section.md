---
title: 自定义文件 UserList 节
TOCTitle: Customization File UserList section
ms:assetid: b60ba3b0-37d4-bb59-d3cd-2ab44d178b8a
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249873(v=office.15)
ms:contentKeyID: 48547263
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 62aaba79fa010de62fb1ac35939673b2056be3f7
ms.sourcegitcommit: 558d09fad81f8d80b5ad0edd21934fc09c098f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25944093"
---
# <a name="customization-file-userlist-section"></a><span data-ttu-id="ac55e-102">自定义文件 UserList 节</span><span class="sxs-lookup"><span data-stu-id="ac55e-102">Customization File UserList section</span></span>


<span data-ttu-id="ac55e-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="ac55e-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="ac55e-104">**Userlist**节与具有相同节*identifier*参数的**连接**部分。</span><span class="sxs-lookup"><span data-stu-id="ac55e-104">The **userlist** section pertains to the **connect** section with the same section *identifier* parameter.</span></span>

<span data-ttu-id="ac55e-105">此节可以包含一个*用户访问项*，后者指定指定用户的访问权限，并替代匹配的**连接**部分中的*默认\*\*访问项*。</span><span class="sxs-lookup"><span data-stu-id="ac55e-105">This section can contain a *user access entry*, which specifies access rights for the specified user and overrides the *default* *access entry* in the matching **connect** section.</span></span>

## <a name="syntax"></a><span data-ttu-id="ac55e-106">语法</span><span class="sxs-lookup"><span data-stu-id="ac55e-106">Syntax</span></span>

<span data-ttu-id="ac55e-107">用户访问项的格式为：</span><span class="sxs-lookup"><span data-stu-id="ac55e-107">A user access entry is of the form:</span></span>

<span data-ttu-id="ac55e-108">*用户名 \*\*\* =* accessRights \*\*\*</span><span class="sxs-lookup"><span data-stu-id="ac55e-108">*userName\*\*\*=* accessRights\*\*\*</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="ac55e-109">部分</span><span class="sxs-lookup"><span data-stu-id="ac55e-109">Part</span></span></p></th>
<th><p><span data-ttu-id="ac55e-110">说明</span><span class="sxs-lookup"><span data-stu-id="ac55e-110">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ac55e-111"><em>userName</em></span><span class="sxs-lookup"><span data-stu-id="ac55e-111"><em>userName</em></span></span></p></td>
<td><p><span data-ttu-id="ac55e-112">使用此连接的人员的<em>用户名</em>。</span><span class="sxs-lookup"><span data-stu-id="ac55e-112">The <em>user name</em> of the person employing this connection.</span></span> <span data-ttu-id="ac55e-113">有效的用户名建立与 IIS<strong>服务管理器</strong>对话框。</span><span class="sxs-lookup"><span data-stu-id="ac55e-113">Valid user names are established with the IIS <strong>Service Manager</strong> dialog.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac55e-114"><strong><em>accessRights</em></strong></span><span class="sxs-lookup"><span data-stu-id="ac55e-114"><strong><em>accessRights</em></strong></span></span></p></td>
<td><p><span data-ttu-id="ac55e-115">表示下列访问权之一：
</span><span class="sxs-lookup"><span data-stu-id="ac55e-115">One of the following access rights:</span></span><br />
</p>
<ul>
<li><p><span data-ttu-id="ac55e-116"><strong>NoAccess</strong> - 用户无法访问数据源。</span><span class="sxs-lookup"><span data-stu-id="ac55e-116"><strong>NoAccess</strong> — User cannot access the data source.</span></span></p></li>
<li><p><span data-ttu-id="ac55e-117"><strong>ReadOnly</strong> - 用户可以读取数据源。</span><span class="sxs-lookup"><span data-stu-id="ac55e-117"><strong>ReadOnly</strong> — User can read the data source.</span></span></p></li>
<li><p><span data-ttu-id="ac55e-118"><strong>ReadWrite</strong> - 用户可以读取或写入数据源。</span><span class="sxs-lookup"><span data-stu-id="ac55e-118"><strong>ReadWrite</strong> — User can read or write to the data source.</span></span></p></li>
</ul>
<p></p></td>
</tr>
</tbody>
</table>

