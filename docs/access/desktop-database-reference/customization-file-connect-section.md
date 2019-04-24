---
title: 自定义文件 Connect 部分
TOCTitle: Customization File Connect section
ms:assetid: 037abfb4-798d-4b09-6133-356969aee95c
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248802(v=office.15)
ms:contentKeyID: 48542985
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 8652aa2c028350aab79cdf101cba189026b9a5ae
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32295140"
---
# <a name="customization-file-connect-section"></a><span data-ttu-id="3954d-102">自定义文件 Connect 部分</span><span class="sxs-lookup"><span data-stu-id="3954d-102">Customization File Connect section</span></span>

<span data-ttu-id="3954d-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="3954d-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="3954d-p101">处理程序的默认行为是拒绝所有连接。 **connect** 节指定该行为的例外。例如，如果不存在任何 **connect** 节或这些节都为空，则默认情况下不能建立任何连接。</span><span class="sxs-lookup"><span data-stu-id="3954d-p101">The default behavior of the handler is to deny all connections. The **connect** section specifies exceptions to that behavior. For example, if all the **connect** sections were absent or empty, then by default no connections could be made.</span></span>

<span data-ttu-id="3954d-107">**connect** 节可以包含：</span><span class="sxs-lookup"><span data-stu-id="3954d-107">The **connect** section can contain:</span></span>

- <span data-ttu-id="3954d-p102">默认访问项，用于指定在此连接上所允许的默认读取和写入操作。如果此节中没有默认访问项，将忽略该节。</span><span class="sxs-lookup"><span data-stu-id="3954d-p102">A default access entry that specifies the default read and write operations allowed on this connection. If there is no default access entry in the section, the section will be ignored.</span></span>

- <span data-ttu-id="3954d-110">新连接字符串，用于替换客户端连接字符串。</span><span class="sxs-lookup"><span data-stu-id="3954d-110">A new connection string that replaces the client connection string.</span></span>

## <a name="syntax"></a><span data-ttu-id="3954d-111">语法</span><span class="sxs-lookup"><span data-stu-id="3954d-111">Syntax</span></span>

<span data-ttu-id="3954d-112">默认访问项的格式为：</span><span class="sxs-lookup"><span data-stu-id="3954d-112">A default access entry is of the form:</span></span>

`Access=accessRight`

<span data-ttu-id="3954d-113">替换连接字符串项的格式为：</span><span class="sxs-lookup"><span data-stu-id="3954d-113">A replacement connection string entry is of the form:</span></span>

`Connect=connectionString`

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="3954d-114">Part</span><span class="sxs-lookup"><span data-stu-id="3954d-114">Part</span></span></p></th>
<th><p><span data-ttu-id="3954d-115">说明</span><span class="sxs-lookup"><span data-stu-id="3954d-115">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3954d-116"><strong>Connect</strong></span><span class="sxs-lookup"><span data-stu-id="3954d-116"><strong>Connect</strong></span></span></p></td>
<td><p><span data-ttu-id="3954d-117">字面字符串，用于指示这是连接字符串项。</span><span class="sxs-lookup"><span data-stu-id="3954d-117">A literal string that indicates this is a connection string entry.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3954d-118"><strong><em>connectionString</em></strong></span><span class="sxs-lookup"><span data-stu-id="3954d-118"><strong><em>connectionString</em></strong></span></span></p></td>
<td><p><span data-ttu-id="3954d-119">字符串，用于替换整个客户端连接字符串。</span><span class="sxs-lookup"><span data-stu-id="3954d-119">A string that replaces the whole client connection string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3954d-120"><strong>Access</strong></span><span class="sxs-lookup"><span data-stu-id="3954d-120"><strong>Access</strong></span></span></p></td>
<td><p><span data-ttu-id="3954d-121">字面字符串，用于指示这是访问项。</span><span class="sxs-lookup"><span data-stu-id="3954d-121">A literal string that indicates this is an access entry.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3954d-122"><strong><em>accessRight</em></strong></span><span class="sxs-lookup"><span data-stu-id="3954d-122"><strong><em>accessRight</em></strong></span></span></p></td>
<td><p><span data-ttu-id="3954d-123">表示下列访问权之一：</span><span class="sxs-lookup"><span data-stu-id="3954d-123">One of the following access rights:</span></span></p>
<p></p>
<ul>
<li><p><span data-ttu-id="3954d-124"><strong>NoAccess</strong> - 用户无法访问数据源。</span><span class="sxs-lookup"><span data-stu-id="3954d-124"><strong>NoAccess</strong> — User cannot access the data source.</span></span></p></li>
<li><p><span data-ttu-id="3954d-125"><strong>ReadOnly</strong> - 用户可以读取数据源。</span><span class="sxs-lookup"><span data-stu-id="3954d-125"><strong>ReadOnly</strong> — User can read the data source.</span></span></p></li>
<li><p><span data-ttu-id="3954d-126"><strong>ReadWrite</strong> - 用户可以读取或写入数据源。</span><span class="sxs-lookup"><span data-stu-id="3954d-126"><strong>ReadWrite</strong> — User can read or write to the data source.</span></span></p></li>
</ul>
<p></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="3954d-127">如果要允许任何连接 (实际上, 禁用默认处理程序行为), 请将 "**连接默认**" 部分中的访问项设置为, 并删除或注释掉任何其他**connect** *标识符*部分。</span><span class="sxs-lookup"><span data-stu-id="3954d-127">If you want to allow any connection (in effect, disabling the default handler behavior), set the access entry in the **connect default** section to , and delete or comment out any other **connect** *identifier* section.</span></span>

