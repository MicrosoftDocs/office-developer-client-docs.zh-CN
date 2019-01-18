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
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28712643"
---
# <a name="databasetypeenum-enumeration-dao"></a><span data-ttu-id="9214f-102">DatabaseTypeEnum 枚举 (DAO)</span><span class="sxs-lookup"><span data-stu-id="9214f-102">DatabaseTypeEnum enumeration (DAO)</span></span>


<span data-ttu-id="9214f-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="9214f-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="9214f-104">指定压缩数据库的数据格式版本。</span><span class="sxs-lookup"><span data-stu-id="9214f-104">Specifies the version of the data format for a compacted database.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="9214f-105">名称</span><span class="sxs-lookup"><span data-stu-id="9214f-105">Name</span></span></p></th>
<th><p><span data-ttu-id="9214f-106">值</span><span class="sxs-lookup"><span data-stu-id="9214f-106">Value</span></span></p></th>
<th><p><span data-ttu-id="9214f-107">说明</span><span class="sxs-lookup"><span data-stu-id="9214f-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9214f-108">dbDecrypt</span><span class="sxs-lookup"><span data-stu-id="9214f-108">dbDecrypt</span></span></p></td>
<td><p><span data-ttu-id="9214f-109">4</span><span class="sxs-lookup"><span data-stu-id="9214f-109">4</span></span></p></td>
<td><p><span data-ttu-id="9214f-110">在压缩的同时解密数据库</span><span class="sxs-lookup"><span data-stu-id="9214f-110">Decrypts database while compacting</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9214f-111">dbEncrypt</span><span class="sxs-lookup"><span data-stu-id="9214f-111">dbEncrypt</span></span></p></td>
<td><p><span data-ttu-id="9214f-112">2</span><span class="sxs-lookup"><span data-stu-id="9214f-112">2</span></span></p></td>
<td><p><span data-ttu-id="9214f-113">解密数据库</span><span class="sxs-lookup"><span data-stu-id="9214f-113">Encrypts database</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9214f-114">dbVersion10</span><span class="sxs-lookup"><span data-stu-id="9214f-114">dbVersion10</span></span></p></td>
<td><p><span data-ttu-id="9214f-115">1</span><span class="sxs-lookup"><span data-stu-id="9214f-115">1</span></span></p></td>
<td><p><span data-ttu-id="9214f-116">Microsoft Jet 数据库引擎 1.0 版</span><span class="sxs-lookup"><span data-stu-id="9214f-116">Microsoft Jet database engine version 1.0</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9214f-117">dbVersion11</span><span class="sxs-lookup"><span data-stu-id="9214f-117">dbVersion11</span></span></p></td>
<td><p><span data-ttu-id="9214f-118">8</span><span class="sxs-lookup"><span data-stu-id="9214f-118">8</span></span></p></td>
<td><p><span data-ttu-id="9214f-119">Microsoft Jet 数据库引擎 1.1 版</span><span class="sxs-lookup"><span data-stu-id="9214f-119">Microsoft Jet database engine version 1.1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9214f-120">dbVersion120</span><span class="sxs-lookup"><span data-stu-id="9214f-120">dbVersion120</span></span></p></td>
<td><p><span data-ttu-id="9214f-121">128</span><span class="sxs-lookup"><span data-stu-id="9214f-121">128</span></span></p></td>
<td><p><span data-ttu-id="9214f-122">Microsoft Access 数据库引擎 12.0 版</span><span class="sxs-lookup"><span data-stu-id="9214f-122">Microsoft Access database engine version 12.0</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9214f-123">dbVersion20</span><span class="sxs-lookup"><span data-stu-id="9214f-123">dbVersion20</span></span></p></td>
<td><p><span data-ttu-id="9214f-124">16</span><span class="sxs-lookup"><span data-stu-id="9214f-124">16</span></span></p></td>
<td><p><span data-ttu-id="9214f-125">Microsoft Jet 数据库引擎 2.0 版</span><span class="sxs-lookup"><span data-stu-id="9214f-125">Microsoft Jet database engine version 2.0</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9214f-126">dbVersion30</span><span class="sxs-lookup"><span data-stu-id="9214f-126">dbVersion30</span></span></p></td>
<td><p><span data-ttu-id="9214f-127">32</span><span class="sxs-lookup"><span data-stu-id="9214f-127">32</span></span></p></td>
<td><p><span data-ttu-id="9214f-128">Microsoft Jet 数据库引擎 3.0 版</span><span class="sxs-lookup"><span data-stu-id="9214f-128">Microsoft Jet database engine version 3.0</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9214f-129">dbVersion40</span><span class="sxs-lookup"><span data-stu-id="9214f-129">dbVersion40</span></span></p></td>
<td><p><span data-ttu-id="9214f-130">64</span><span class="sxs-lookup"><span data-stu-id="9214f-130">64</span></span></p></td>
<td><p><span data-ttu-id="9214f-131">Microsoft Jet 数据库引擎 4.0 版</span><span class="sxs-lookup"><span data-stu-id="9214f-131">Microsoft Jet database engine version 4.0</span></span></p></td>
</tr>
</tbody>
</table>

