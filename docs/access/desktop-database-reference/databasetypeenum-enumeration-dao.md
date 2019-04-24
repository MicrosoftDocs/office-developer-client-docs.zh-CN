---
title: DatabaseTypeEnum 枚举 (DAO)
TOCTitle: DatabaseTypeEnum enumeration
ms:assetid: a9bfc7cd-63d2-a012-bd3b-4cec072706c2
ms:mtpsurl: https://msdn.microsoft.com/library/Ff821447(v=office.15)
ms:contentKeyID: 48546934
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: b58a36ca581b7c932aeff0e36391827a27d865b7
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32294559"
---
# <a name="databasetypeenum-enumeration-dao"></a><span data-ttu-id="d5288-102">DatabaseTypeEnum 枚举 (DAO)</span><span class="sxs-lookup"><span data-stu-id="d5288-102">DatabaseTypeEnum enumeration (DAO)</span></span>


<span data-ttu-id="d5288-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="d5288-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="d5288-104">指定压缩数据库的数据格式版本。</span><span class="sxs-lookup"><span data-stu-id="d5288-104">Specifies the version of the data format for a compacted database.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="d5288-105">名称</span><span class="sxs-lookup"><span data-stu-id="d5288-105">Name</span></span></p></th>
<th><p><span data-ttu-id="d5288-106">值</span><span class="sxs-lookup"><span data-stu-id="d5288-106">Value</span></span></p></th>
<th><p><span data-ttu-id="d5288-107">说明</span><span class="sxs-lookup"><span data-stu-id="d5288-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d5288-108">dbDecrypt</span><span class="sxs-lookup"><span data-stu-id="d5288-108">dbDecrypt</span></span></p></td>
<td><p><span data-ttu-id="d5288-109">4</span><span class="sxs-lookup"><span data-stu-id="d5288-109">4</span></span></p></td>
<td><p><span data-ttu-id="d5288-110">在压缩的同时解密数据库</span><span class="sxs-lookup"><span data-stu-id="d5288-110">Decrypts database while compacting</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d5288-111">dbEncrypt</span><span class="sxs-lookup"><span data-stu-id="d5288-111">dbEncrypt</span></span></p></td>
<td><p><span data-ttu-id="d5288-112">双面</span><span class="sxs-lookup"><span data-stu-id="d5288-112">2</span></span></p></td>
<td><p><span data-ttu-id="d5288-113">解密数据库</span><span class="sxs-lookup"><span data-stu-id="d5288-113">Encrypts database</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d5288-114">dbVersion10</span><span class="sxs-lookup"><span data-stu-id="d5288-114">dbVersion10</span></span></p></td>
<td><p><span data-ttu-id="d5288-115">1</span><span class="sxs-lookup"><span data-stu-id="d5288-115">1</span></span></p></td>
<td><p><span data-ttu-id="d5288-116">Microsoft Jet 数据库引擎 1.0 版</span><span class="sxs-lookup"><span data-stu-id="d5288-116">Microsoft Jet database engine version 1.0</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d5288-117">dbVersion11</span><span class="sxs-lookup"><span data-stu-id="d5288-117">dbVersion11</span></span></p></td>
<td><p><span data-ttu-id="d5288-118">utf-8</span><span class="sxs-lookup"><span data-stu-id="d5288-118">8</span></span></p></td>
<td><p><span data-ttu-id="d5288-119">Microsoft Jet 数据库引擎 1.1 版</span><span class="sxs-lookup"><span data-stu-id="d5288-119">Microsoft Jet database engine version 1.1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d5288-120">dbVersion120</span><span class="sxs-lookup"><span data-stu-id="d5288-120">dbVersion120</span></span></p></td>
<td><p><span data-ttu-id="d5288-121">128</span><span class="sxs-lookup"><span data-stu-id="d5288-121">128</span></span></p></td>
<td><p><span data-ttu-id="d5288-122">Microsoft Access 数据库引擎 12.0 版</span><span class="sxs-lookup"><span data-stu-id="d5288-122">Microsoft Access database engine version 12.0</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d5288-123">dbVersion20</span><span class="sxs-lookup"><span data-stu-id="d5288-123">dbVersion20</span></span></p></td>
<td><p><span data-ttu-id="d5288-124">位</span><span class="sxs-lookup"><span data-stu-id="d5288-124">16</span></span></p></td>
<td><p><span data-ttu-id="d5288-125">Microsoft Jet 数据库引擎 2.0 版</span><span class="sxs-lookup"><span data-stu-id="d5288-125">Microsoft Jet database engine version 2.0</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d5288-126">dbVersion30</span><span class="sxs-lookup"><span data-stu-id="d5288-126">dbVersion30</span></span></p></td>
<td><p><span data-ttu-id="d5288-127">32</span><span class="sxs-lookup"><span data-stu-id="d5288-127">32</span></span></p></td>
<td><p><span data-ttu-id="d5288-128">Microsoft Jet 数据库引擎 3.0 版</span><span class="sxs-lookup"><span data-stu-id="d5288-128">Microsoft Jet database engine version 3.0</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d5288-129">dbVersion40</span><span class="sxs-lookup"><span data-stu-id="d5288-129">dbVersion40</span></span></p></td>
<td><p><span data-ttu-id="d5288-130">64</span><span class="sxs-lookup"><span data-stu-id="d5288-130">64</span></span></p></td>
<td><p><span data-ttu-id="d5288-131">Microsoft Jet 数据库引擎 4.0 版</span><span class="sxs-lookup"><span data-stu-id="d5288-131">Microsoft Jet database engine version 4.0</span></span></p></td>
</tr>
</tbody>
</table>

