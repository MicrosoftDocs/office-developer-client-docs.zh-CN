---
title: 了解自定义文件
TOCTitle: Understanding the Customization File
ms:assetid: 98fd5ec1-d5bd-cdd2-5eb5-9a1682fbed79
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249686(v=office.15)
ms:contentKeyID: 48546507
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 5c764c543c3d8734a47927d702daca1552e497b6
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25879471"
---
# <a name="understanding-the-customization-file"></a><span data-ttu-id="fc44a-102">了解自定义文件</span><span class="sxs-lookup"><span data-stu-id="fc44a-102">Understanding the Customization File</span></span>


<span data-ttu-id="fc44a-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="fc44a-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="fc44a-104">自定义文件中的每个节标头包含方括号 (**\[**) 包含类型和参数。</span><span class="sxs-lookup"><span data-stu-id="fc44a-104">Each section header in the customization file consists of square brackets (**\[\]**) containing a type and parameter.</span></span> <span data-ttu-id="fc44a-105">节分为四种类型，分别用字面字符串 **connect** 、 **sql** 、 **userlist** 或 **logs** 表示。</span><span class="sxs-lookup"><span data-stu-id="fc44a-105">The four section types are indicated by the literal strings **connect**, **sql**, **userlist**, or **logs**.</span></span> <span data-ttu-id="fc44a-106">参数可以是字面字符串、默认值、用户指定的标识符或为空。</span><span class="sxs-lookup"><span data-stu-id="fc44a-106">The parameter is the literal string, the default, a user-specified identifier, or nothing.</span></span>

<span data-ttu-id="fc44a-107">因此，每节用以下节标头中的一种进行标记：</span><span class="sxs-lookup"><span data-stu-id="fc44a-107">Therefore, each section is marked with one of the following section headers:</span></span>

```text 
 
[ connect   default     ]
[ connect   identifier  ]
[ sql       default     ]
[ sql       identifier  ]
[ userlist  identifier  ]
[ logs                  ]
```

<span data-ttu-id="fc44a-108">节标头包含以下部分。</span><span class="sxs-lookup"><span data-stu-id="fc44a-108">The section headers have the following parts.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="fc44a-109">部分</span><span class="sxs-lookup"><span data-stu-id="fc44a-109">Part</span></span></p></th>
<th><p><span data-ttu-id="fc44a-110">说明</span><span class="sxs-lookup"><span data-stu-id="fc44a-110">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fc44a-111"><strong>connect</strong></span><span class="sxs-lookup"><span data-stu-id="fc44a-111"><strong>connect</strong></span></span></p></td>
<td><p><span data-ttu-id="fc44a-112">修改连接字符串的字面字符串。</span><span class="sxs-lookup"><span data-stu-id="fc44a-112">A literal string that modifies a connection string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fc44a-113"><strong>sql</strong></span><span class="sxs-lookup"><span data-stu-id="fc44a-113"><strong>sql</strong></span></span></p></td>
<td><p><span data-ttu-id="fc44a-114">修改命令字符串的字面字符串。</span><span class="sxs-lookup"><span data-stu-id="fc44a-114">A literal string that modifies a command string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fc44a-115"><strong>userlist</strong></span><span class="sxs-lookup"><span data-stu-id="fc44a-115"><strong>userlist</strong></span></span></p></td>
<td><p><span data-ttu-id="fc44a-116">修改特定用户访问权限的字面字符串。</span><span class="sxs-lookup"><span data-stu-id="fc44a-116">A literal string that modifies the access rights of a specific user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fc44a-117"><strong>logs</strong></span><span class="sxs-lookup"><span data-stu-id="fc44a-117"><strong>logs</strong></span></span></p></td>
<td><p><span data-ttu-id="fc44a-118">指定记录操作错误的日志文件的字面字符串。</span><span class="sxs-lookup"><span data-stu-id="fc44a-118">A literal string that specifies a log file recording operational errors.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fc44a-119"><strong>default</strong></span><span class="sxs-lookup"><span data-stu-id="fc44a-119"><strong>default</strong></span></span></p></td>
<td><p><span data-ttu-id="fc44a-120">当未指定或未找到标识符时所使用的字面字符串。</span><span class="sxs-lookup"><span data-stu-id="fc44a-120">A literal string that is used if no identifier is specified or found.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fc44a-121"><em>identifier</em></span><span class="sxs-lookup"><span data-stu-id="fc44a-121"><em>identifier</em></span></span></p></td>
<td><p><span data-ttu-id="fc44a-122">与 <strong>connect</strong> 字符串或 <strong>command</strong> 字符串中的字符串匹配的字符串。
</span><span class="sxs-lookup"><span data-stu-id="fc44a-122">A string that matches a string in the <strong>connect</strong> or <strong>command</strong> string.</span></span></p>
<p></p>
<ul>
<li><p><span data-ttu-id="fc44a-123">如果节标头中包含 <strong>connect</strong> 且在连接字符串中找到标识符字符串，则使用此节。</span><span class="sxs-lookup"><span data-stu-id="fc44a-123">Use this section if the section header contains <strong>connect</strong> and the identifier string is found in the connection string.</span></span></p></li>
<li><p><span data-ttu-id="fc44a-124">如果节标头中包含 <strong>sql</strong> 且在命令字符串中找到标识符字符串，则使用此节。</span><span class="sxs-lookup"><span data-stu-id="fc44a-124">Use this section if the section header contains <strong>sql</strong> and the identifier string is found in the command string.</span></span></p></li>
<li><p><span data-ttu-id="fc44a-125">如果节标头中包含 <strong>userlist</strong> 且标识符字符串与 <strong>connect</strong> 节标识符匹配，则使用此节。</span><span class="sxs-lookup"><span data-stu-id="fc44a-125">Use this section if the section header contains <strong>userlist</strong> and the identifier string matches a <strong>connect</strong> section identifier.</span></span></p></li>
</ul>
<p></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="fc44a-p102">**DataFactory** 调用处理程序，传递客户端参数。处理程序在客户端参数中搜索与相应节标头中的标识符匹配的整个字符串。如果找到匹配的字符串，则将此节的内容应用于客户端参数。</span><span class="sxs-lookup"><span data-stu-id="fc44a-p102">The **DataFactory** calls the handler, passing client parameters. The handler searches for whole strings in the client parameters that match identifiers in the appropriate section headers. If a match is found, the contents of that section are applied to the client parameter.</span></span>

<span data-ttu-id="fc44a-129">以上各节用在以下不同情况中：</span><span class="sxs-lookup"><span data-stu-id="fc44a-129">A particular section is used under the following circumstances:</span></span>

  - <span data-ttu-id="fc44a-130">如果客户端的值部分的连接字符串关键字，则使用**连接**节"\**数据源 = \*\*\* 值*"，与 *。* **连接**节标识符匹配</span><span class="sxs-lookup"><span data-stu-id="fc44a-130">A **connect** section is used if the value part of the client connect string keyword, "\**Data Source=\*\*\*value*", matches a **connect** section identifier *.*</span></span>

  - <span data-ttu-id="fc44a-131">如果客户端命令字符串中包含与 **sql** 节标识符匹配的字符串，则使用 **sql** 节。</span><span class="sxs-lookup"><span data-stu-id="fc44a-131">An **sql** section is used if the client command string contains a string that matches an **sql** section identifier.</span></span>

  - <span data-ttu-id="fc44a-132">如果没有匹配的标识符，则使用带默认参数的 **connect** 或 **sql** 节。</span><span class="sxs-lookup"><span data-stu-id="fc44a-132">A **connect** or **sql** section with a default parameter is used if there is no matching identifier.</span></span>

  - <span data-ttu-id="fc44a-p103">如果 **userlist** 节标识符与 **connect** 节标识符匹配，则使用 **userlist** 节。如果匹配，则将 **userlist** 的内容应用于 **connect** 节所控制的连接。</span><span class="sxs-lookup"><span data-stu-id="fc44a-p103">A **userlist** section is used if the **userlist** section identifier matches a **connect** section identifier. If there is a match, the contents of the **userlist** section are applied to the connection governed by the **connect** section.</span></span>

  - <span data-ttu-id="fc44a-135">如果连接字符串或命令字符串中的字符串与任何 **connect** 或 **sql** 节标头中的标识符都不匹配，且不存在带默认参数的 **connect** 或 **sql** 节标头，则按原样使用客户端字符串，不进行修改。</span><span class="sxs-lookup"><span data-stu-id="fc44a-135">If the string in a connection or command string does not match the identifier in any **connect** or **sql** section header, and there is no **connect** or **sql** section header with a default parameter, then the client string is used without modification.</span></span>

  - <span data-ttu-id="fc44a-136">只要 **DataFactory** 处于操作状态，便使用 **logs** 节。</span><span class="sxs-lookup"><span data-stu-id="fc44a-136">The **logs** section is used whenever the **DataFactory** is in operation.</span></span>

