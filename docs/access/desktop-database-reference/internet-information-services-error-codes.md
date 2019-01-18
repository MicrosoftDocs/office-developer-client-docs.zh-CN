---
title: Internet Information Services 错误代码
TOCTitle: Internet Information Services error codes
ms:assetid: 1ed57b89-b471-88e5-e5af-85323dec18d3
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248978(v=office.15)
ms:contentKeyID: 48543625
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 8c67c43922316c6c77876525c79993beba1d4131
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28699903"
---
# <a name="internet-information-services-error-codes"></a><span data-ttu-id="00650-102">Internet Information Services 错误代码</span><span class="sxs-lookup"><span data-stu-id="00650-102">Internet Information Services error codes</span></span>

<span data-ttu-id="00650-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="00650-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="00650-p101">下表列出了与远程数据服务用法有关的 Microsoft Internet 信息服务 (IIS) 错误代码，其中显示了两个低位字节的正十进制换算值、完整错误代码的负十进制换算值和十六进制值。</span><span class="sxs-lookup"><span data-stu-id="00650-p101">The following table lists Microsoft Internet Information Services (IIS) error codes related to Remote Data Service usage. The positive decimal translation of the low two bytes, the negative decimal translation of the full error code, and the hexadecimal values are shown.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="00650-106">Internet 信息服务错误</span><span class="sxs-lookup"><span data-stu-id="00650-106">Internet Information Services errors</span></span></p></th>
<th><p><span data-ttu-id="00650-107">编号</span><span class="sxs-lookup"><span data-stu-id="00650-107">Number</span></span></p></th>
<th><p><span data-ttu-id="00650-108">说明</span><span class="sxs-lookup"><span data-stu-id="00650-108">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="00650-109"><strong>IDS_IIS_AccessDenied</strong></span><span class="sxs-lookup"><span data-stu-id="00650-109"><strong>IDS_IIS_AccessDenied</strong></span></span></p></td>
<td><p><span data-ttu-id="00650-110">8208</span><span class="sxs-lookup"><span data-stu-id="00650-110">8208</span></span><br />
<span data-ttu-id="00650-111">-2146820080</span><span class="sxs-lookup"><span data-stu-id="00650-111">-2146820080</span></span><br />
<span data-ttu-id="00650-112">0x800A2010</span><span class="sxs-lookup"><span data-stu-id="00650-112">0x800A2010</span></span></p></td>
<td><p><span data-ttu-id="00650-113">Internet 服务器错误：访问被拒绝。</span><span class="sxs-lookup"><span data-stu-id="00650-113">Internet Server Error: Access Denied.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00650-114"><strong>IDS_IIS_ObjectNotFound</strong></span><span class="sxs-lookup"><span data-stu-id="00650-114"><strong>IDS_IIS_ObjectNotFound</strong></span></span></p></td>
<td><p><span data-ttu-id="00650-115">8209</span><span class="sxs-lookup"><span data-stu-id="00650-115">8209</span></span><br />
<span data-ttu-id="00650-116">-2146820079</span><span class="sxs-lookup"><span data-stu-id="00650-116">-2146820079</span></span><br />
<span data-ttu-id="00650-117">0x800A2011</span><span class="sxs-lookup"><span data-stu-id="00650-117">0x800A2011</span></span></p></td>
<td><p><span data-ttu-id="00650-118">Internet 服务器错误：找不到对象/模块。</span><span class="sxs-lookup"><span data-stu-id="00650-118">Internet Server Error: Object/module not found.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00650-119"><strong>IDS_IIS_RequestForbidden</strong></span><span class="sxs-lookup"><span data-stu-id="00650-119"><strong>IDS_IIS_RequestForbidden</strong></span></span></p></td>
<td><p><span data-ttu-id="00650-120">8210</span><span class="sxs-lookup"><span data-stu-id="00650-120">8210</span></span><br />
<span data-ttu-id="00650-121">-2146820078</span><span class="sxs-lookup"><span data-stu-id="00650-121">-2146820078</span></span><br />
<span data-ttu-id="00650-122">0x800A2012</span><span class="sxs-lookup"><span data-stu-id="00650-122">0x800A2012</span></span></p></td>
<td><p><span data-ttu-id="00650-123">Internet 服务器错误：请求被禁止。</span><span class="sxs-lookup"><span data-stu-id="00650-123">Internet Server Error: Request Forbidden.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00650-124"><strong>IDS_IIS_UnexpectedError</strong></span><span class="sxs-lookup"><span data-stu-id="00650-124"><strong>IDS_IIS_UnexpectedError</strong></span></span></p></td>
<td><p><span data-ttu-id="00650-125">8447</span><span class="sxs-lookup"><span data-stu-id="00650-125">8447</span></span><br />
<span data-ttu-id="00650-126">-2146819841</span><span class="sxs-lookup"><span data-stu-id="00650-126">-2146819841</span></span><br />
<span data-ttu-id="00650-127">0x800A20FF</span><span class="sxs-lookup"><span data-stu-id="00650-127">0x800A20FF</span></span></p></td>
<td><p><span data-ttu-id="00650-128">Internet 服务器错误。</span><span class="sxs-lookup"><span data-stu-id="00650-128">Internet Server Error.</span></span></p></td>
</tr>
</tbody>
</table>

