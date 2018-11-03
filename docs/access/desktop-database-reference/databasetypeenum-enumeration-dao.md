---
title: DatabaseTypeEnum 枚举 (DAO)
TOCTitle: DatabaseTypeEnum enumeration
ms:assetid: a9bfc7cd-63d2-a012-bd3b-4cec072706c2
ms:mtpsurl: https://msdn.microsoft.com/library/Ff821447(v=office.15)
ms:contentKeyID: 48546934
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 62595d6403746323c101dc1101f3a4e677903955
ms.sourcegitcommit: 558d09fad81f8d80b5ad0edd21934fc09c098f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25946893"
---
# <a name="databasetypeenum-enumeration-dao"></a><span data-ttu-id="c8e78-102">DatabaseTypeEnum 枚举 (DAO)</span><span class="sxs-lookup"><span data-stu-id="c8e78-102">DatabaseTypeEnum enumeration (DAO)</span></span>


<span data-ttu-id="c8e78-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="c8e78-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="c8e78-104">指定压缩数据库的数据格式版本。</span><span class="sxs-lookup"><span data-stu-id="c8e78-104">Specifies the version of the data format for a compacted database.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="c8e78-105">名称</span><span class="sxs-lookup"><span data-stu-id="c8e78-105">Name</span></span></p></th>
<th><p><span data-ttu-id="c8e78-106">值</span><span class="sxs-lookup"><span data-stu-id="c8e78-106">Value</span></span></p></th>
<th><p><span data-ttu-id="c8e78-107">说明</span><span class="sxs-lookup"><span data-stu-id="c8e78-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c8e78-108">dbDecrypt</span><span class="sxs-lookup"><span data-stu-id="c8e78-108">dbDecrypt</span></span></p></td>
<td><p><span data-ttu-id="c8e78-109">4</span><span class="sxs-lookup"><span data-stu-id="c8e78-109">4</span></span></p></td>
<td><p><span data-ttu-id="c8e78-110">在压缩的同时解密数据库</span><span class="sxs-lookup"><span data-stu-id="c8e78-110">Decrypts database while compacting</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8e78-111">dbEncrypt</span><span class="sxs-lookup"><span data-stu-id="c8e78-111">dbEncrypt</span></span></p></td>
<td><p><span data-ttu-id="c8e78-112">2</span><span class="sxs-lookup"><span data-stu-id="c8e78-112">2</span></span></p></td>
<td><p><span data-ttu-id="c8e78-113">解密数据库</span><span class="sxs-lookup"><span data-stu-id="c8e78-113">Encrypts database</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8e78-114">dbVersion10</span><span class="sxs-lookup"><span data-stu-id="c8e78-114">dbVersion10</span></span></p></td>
<td><p><span data-ttu-id="c8e78-115">1</span><span class="sxs-lookup"><span data-stu-id="c8e78-115">1</span></span></p></td>
<td><p><span data-ttu-id="c8e78-116">Microsoft Jet 数据库引擎 1.0 版</span><span class="sxs-lookup"><span data-stu-id="c8e78-116">Microsoft Jet database engine version 1.0</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8e78-117">dbVersion11</span><span class="sxs-lookup"><span data-stu-id="c8e78-117">dbVersion11</span></span></p></td>
<td><p><span data-ttu-id="c8e78-118">8</span><span class="sxs-lookup"><span data-stu-id="c8e78-118">8</span></span></p></td>
<td><p><span data-ttu-id="c8e78-119">Microsoft Jet 数据库引擎 1.1 版</span><span class="sxs-lookup"><span data-stu-id="c8e78-119">Microsoft Jet database engine version 1.1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8e78-120">dbVersion120</span><span class="sxs-lookup"><span data-stu-id="c8e78-120">dbVersion120</span></span></p></td>
<td><p><span data-ttu-id="c8e78-121">128</span><span class="sxs-lookup"><span data-stu-id="c8e78-121">128</span></span></p></td>
<td><p><span data-ttu-id="c8e78-122">Microsoft Access 数据库引擎 12.0 版</span><span class="sxs-lookup"><span data-stu-id="c8e78-122">Microsoft Access database engine version 12.0</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8e78-123">dbVersion20</span><span class="sxs-lookup"><span data-stu-id="c8e78-123">dbVersion20</span></span></p></td>
<td><p><span data-ttu-id="c8e78-124">16</span><span class="sxs-lookup"><span data-stu-id="c8e78-124">16</span></span></p></td>
<td><p><span data-ttu-id="c8e78-125">Microsoft Jet 数据库引擎 2.0 版</span><span class="sxs-lookup"><span data-stu-id="c8e78-125">Microsoft Jet database engine version 2.0</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8e78-126">dbVersion30</span><span class="sxs-lookup"><span data-stu-id="c8e78-126">dbVersion30</span></span></p></td>
<td><p><span data-ttu-id="c8e78-127">32</span><span class="sxs-lookup"><span data-stu-id="c8e78-127">32</span></span></p></td>
<td><p><span data-ttu-id="c8e78-128">Microsoft Jet 数据库引擎 3.0 版</span><span class="sxs-lookup"><span data-stu-id="c8e78-128">Microsoft Jet database engine version 3.0</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8e78-129">dbVersion40</span><span class="sxs-lookup"><span data-stu-id="c8e78-129">dbVersion40</span></span></p></td>
<td><p><span data-ttu-id="c8e78-130">64</span><span class="sxs-lookup"><span data-stu-id="c8e78-130">64</span></span></p></td>
<td><p><span data-ttu-id="c8e78-131">Microsoft Jet 数据库引擎 4.0 版</span><span class="sxs-lookup"><span data-stu-id="c8e78-131">Microsoft Jet database engine version 4.0</span></span></p></td>
</tr>
</tbody>
</table>

