---
title: 自定义文件 UserList 节
TOCTitle: Customization File UserList Section
ms:assetid: b60ba3b0-37d4-bb59-d3cd-2ab44d178b8a
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249873(v=office.15)
ms:contentKeyID: 48547263
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: a4aa7604edc887e97cbdfbea9b75e6f46ad55f35
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25880766"
---
# <a name="customization-file-userlist-section"></a><span data-ttu-id="230fc-102">自定义文件 UserList 节</span><span class="sxs-lookup"><span data-stu-id="230fc-102">Customization File UserList Section</span></span>


<span data-ttu-id="230fc-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="230fc-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="230fc-104">**Userlist**节与具有相同节*identifier*参数的**连接**部分。</span><span class="sxs-lookup"><span data-stu-id="230fc-104">The **userlist** section pertains to the **connect** section with the same section *identifier* parameter.</span></span>

<span data-ttu-id="230fc-105">此节可以包含一个*用户访问项*，后者指定指定用户的访问权限，并替代匹配的**连接**部分中的*默认\*\*访问项*。</span><span class="sxs-lookup"><span data-stu-id="230fc-105">This section can contain a *user access entry*, which specifies access rights for the specified user and overrides the *default* *access entry* in the matching **connect** section.</span></span>

## <a name="syntax"></a><span data-ttu-id="230fc-106">语法</span><span class="sxs-lookup"><span data-stu-id="230fc-106">Syntax</span></span>

<span data-ttu-id="230fc-107">用户访问项的格式为：</span><span class="sxs-lookup"><span data-stu-id="230fc-107">A user access entry is of the form:</span></span>

<span data-ttu-id="230fc-108">*用户名 \*\*\* =* accessRights \*\*\*</span><span class="sxs-lookup"><span data-stu-id="230fc-108">*userName\*\*\*=* accessRights\*\*\*</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="230fc-109">部分</span><span class="sxs-lookup"><span data-stu-id="230fc-109">Part</span></span></p></th>
<th><p><span data-ttu-id="230fc-110">说明</span><span class="sxs-lookup"><span data-stu-id="230fc-110">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="230fc-111"><em>userName</em></span><span class="sxs-lookup"><span data-stu-id="230fc-111"><em>userName</em></span></span></p></td>
<td><p><span data-ttu-id="230fc-112">使用此连接的人员的<em>用户名</em>。</span><span class="sxs-lookup"><span data-stu-id="230fc-112">The <em>user name</em> of the person employing this connection.</span></span> <span data-ttu-id="230fc-113">有效的用户名建立与 IIS<strong>服务管理器</strong>对话框。</span><span class="sxs-lookup"><span data-stu-id="230fc-113">Valid user names are established with the IIS <strong>Service Manager</strong> dialog.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="230fc-114"><strong><em>accessRights</em></strong></span><span class="sxs-lookup"><span data-stu-id="230fc-114"><strong><em>accessRights</em></strong></span></span></p></td>
<td><p><span data-ttu-id="230fc-115">表示下列访问权之一：
</span><span class="sxs-lookup"><span data-stu-id="230fc-115">One of the following access rights:</span></span><br />
</p>
<ul>
<li><p><span data-ttu-id="230fc-116"><strong>NoAccess</strong> - 用户无法访问数据源。</span><span class="sxs-lookup"><span data-stu-id="230fc-116"><strong>NoAccess</strong> — User cannot access the data source.</span></span></p></li>
<li><p><span data-ttu-id="230fc-117"><strong>ReadOnly</strong> - 用户可以读取数据源。</span><span class="sxs-lookup"><span data-stu-id="230fc-117"><strong>ReadOnly</strong> — User can read the data source.</span></span></p></li>
<li><p><span data-ttu-id="230fc-118"><strong>ReadWrite</strong> - 用户可以读取或写入数据源。</span><span class="sxs-lookup"><span data-stu-id="230fc-118"><strong>ReadWrite</strong> — User can read or write to the data source.</span></span></p></li>
</ul>
<p></p></td>
</tr>
</tbody>
</table>

