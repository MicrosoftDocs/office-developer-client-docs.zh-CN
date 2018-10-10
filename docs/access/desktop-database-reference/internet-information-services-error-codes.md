---
title: Internet 信息服务错误代码
TOCTitle: Internet Information Services Error Codes
ms:assetid: 1ed57b89-b471-88e5-e5af-85323dec18d3
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248978(v=office.15)
ms:contentKeyID: 48543625
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: d62be19cb472673a4bdafd3574bbe1fcb7b876c9
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25465739"
---
# <a name="internet-information-services-error-codes"></a><span data-ttu-id="d1ff6-102">Internet 信息服务错误代码</span><span class="sxs-lookup"><span data-stu-id="d1ff6-102">Internet Information Services Error Codes</span></span>


<span data-ttu-id="d1ff6-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="d1ff6-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="d1ff6-p101">下表列出了与远程数据服务用法有关的 Microsoft Internet 信息服务 (IIS) 错误代码，其中显示了两个低位字节的正十进制换算值、完整错误代码的负十进制换算值和十六进制值。</span><span class="sxs-lookup"><span data-stu-id="d1ff6-p101">The following table lists Microsoft Internet Information Services (IIS) error codes related to Remote Data Service usage. The positive decimal translation of the low two bytes, the negative decimal translation of the full error code, and the hexadecimal values are shown.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="d1ff6-106">Internet 信息服务错误</span><span class="sxs-lookup"><span data-stu-id="d1ff6-106">Internet Information Services errors</span></span></p></th>
<th><p><span data-ttu-id="d1ff6-107">编号</span><span class="sxs-lookup"><span data-stu-id="d1ff6-107">Number</span></span></p></th>
<th><p><span data-ttu-id="d1ff6-108">说明</span><span class="sxs-lookup"><span data-stu-id="d1ff6-108">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d1ff6-109"><strong>IDS_IIS_AccessDenied</strong></span><span class="sxs-lookup"><span data-stu-id="d1ff6-109"><strong>IDS_IIS_AccessDenied</strong></span></span></p></td>
<td><p><span data-ttu-id="d1ff6-110">8208</span><span class="sxs-lookup"><span data-stu-id="d1ff6-110">8208</span></span><br />
<span data-ttu-id="d1ff6-111">-2146820080</span><span class="sxs-lookup"><span data-stu-id="d1ff6-111">-2146820080</span></span><br />
<span data-ttu-id="d1ff6-112">0x800A2010</span><span class="sxs-lookup"><span data-stu-id="d1ff6-112">0x800A2010</span></span></p></td>
<td><p><span data-ttu-id="d1ff6-113">Internet 服务器错误：访问被拒绝。</span><span class="sxs-lookup"><span data-stu-id="d1ff6-113">Internet Server Error: Access Denied.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1ff6-114"><strong>IDS_IIS_ObjectNotFound</strong></span><span class="sxs-lookup"><span data-stu-id="d1ff6-114"><strong>IDS_IIS_ObjectNotFound</strong></span></span></p></td>
<td><p><span data-ttu-id="d1ff6-115">8209</span><span class="sxs-lookup"><span data-stu-id="d1ff6-115">8209</span></span><br />
<span data-ttu-id="d1ff6-116">-2146820079</span><span class="sxs-lookup"><span data-stu-id="d1ff6-116">-2146820079</span></span><br />
<span data-ttu-id="d1ff6-117">0x800A2011</span><span class="sxs-lookup"><span data-stu-id="d1ff6-117">0x800A2011</span></span></p></td>
<td><p><span data-ttu-id="d1ff6-118">Internet 服务器错误：找不到对象/模块。</span><span class="sxs-lookup"><span data-stu-id="d1ff6-118">Internet Server Error: Object/module not found.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1ff6-119"><strong>IDS_IIS_RequestForbidden</strong></span><span class="sxs-lookup"><span data-stu-id="d1ff6-119"><strong>IDS_IIS_RequestForbidden</strong></span></span></p></td>
<td><p><span data-ttu-id="d1ff6-120">8210</span><span class="sxs-lookup"><span data-stu-id="d1ff6-120">8210</span></span><br />
<span data-ttu-id="d1ff6-121">-2146820078</span><span class="sxs-lookup"><span data-stu-id="d1ff6-121">-2146820078</span></span><br />
<span data-ttu-id="d1ff6-122">0x800A2012</span><span class="sxs-lookup"><span data-stu-id="d1ff6-122">0x800A2012</span></span></p></td>
<td><p><span data-ttu-id="d1ff6-123">Internet 服务器错误：请求被禁止。</span><span class="sxs-lookup"><span data-stu-id="d1ff6-123">Internet Server Error: Request Forbidden.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1ff6-124"><strong>IDS_IIS_UnexpectedError</strong></span><span class="sxs-lookup"><span data-stu-id="d1ff6-124"><strong>IDS_IIS_UnexpectedError</strong></span></span></p></td>
<td><p><span data-ttu-id="d1ff6-125">8447</span><span class="sxs-lookup"><span data-stu-id="d1ff6-125">8447</span></span><br />
<span data-ttu-id="d1ff6-126">-2146819841</span><span class="sxs-lookup"><span data-stu-id="d1ff6-126">-2146819841</span></span><br />
<span data-ttu-id="d1ff6-127">0x800A20FF</span><span class="sxs-lookup"><span data-stu-id="d1ff6-127">0x800A20FF</span></span></p></td>
<td><p><span data-ttu-id="d1ff6-128">Internet 服务器错误。</span><span class="sxs-lookup"><span data-stu-id="d1ff6-128">Internet Server Error.</span></span></p></td>
</tr>
</tbody>
</table>

