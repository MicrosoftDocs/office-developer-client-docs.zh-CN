---
title: CopyRecordOptionsEnum
TOCTitle: CopyRecordOptionsEnum
ms:assetid: ab9426e9-0e4e-6c85-43cf-e4a205a7c4c0
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249795(v=office.15)
ms:contentKeyID: 48546975
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: b33347492562d868781e8bbca346918d55ed597b
ms.sourcegitcommit: 801b1b54786f7b0e5b0d35466e7ae8d1e840b26f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25860278"
---
# <a name="copyrecordoptionsenum"></a><span data-ttu-id="6ba53-102">CopyRecordOptionsEnum</span><span class="sxs-lookup"><span data-stu-id="6ba53-102">CopyRecordOptionsEnum</span></span>


<span data-ttu-id="6ba53-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="6ba53-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="6ba53-104">指定 [CopyRecord](copyrecord-method-ado.md) 方法的行为。</span><span class="sxs-lookup"><span data-stu-id="6ba53-104">Specifies the behavior of the [CopyRecord](copyrecord-method-ado.md) method.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="6ba53-105">常量</span><span class="sxs-lookup"><span data-stu-id="6ba53-105">Constant</span></span></p></th>
<th><p><span data-ttu-id="6ba53-106">值</span><span class="sxs-lookup"><span data-stu-id="6ba53-106">Value</span></span></p></th>
<th><p><span data-ttu-id="6ba53-107">说明</span><span class="sxs-lookup"><span data-stu-id="6ba53-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6ba53-108"><strong>adCopyAllowEmulation</strong></span><span class="sxs-lookup"><span data-stu-id="6ba53-108"><strong>adCopyAllowEmulation</strong></span></span></p></td>
<td><p><span data-ttu-id="6ba53-109">4</span><span class="sxs-lookup"><span data-stu-id="6ba53-109">4</span></span></p></td>
<td><p><span data-ttu-id="6ba53-p101">指示如果此方法由于 <em>Destination</em> 在不同的服务器上而失败或者由不同于 <em>Source</em> 提供程序的提供程序提供服务，则 <em>Source</em> 提供程序会尝试使用下载和上载操作来模拟复制。注意，不同的提供程序功能可能会导致性能下降或数据丢失。</span><span class="sxs-lookup"><span data-stu-id="6ba53-p101">Indicates that the <em>Source</em> provider attempts to simulate the copy using download and upload operations if this method fails due to <em>Destination</em> being on a different server or is serviced by a different provider than <em>Source</em>. Note that differing provider capabilities may hamper performance or lose data.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ba53-112"><strong>adCopyNonRecursive</strong></span><span class="sxs-lookup"><span data-stu-id="6ba53-112"><strong>adCopyNonRecursive</strong></span></span></p></td>
<td><p><span data-ttu-id="6ba53-113">2</span><span class="sxs-lookup"><span data-stu-id="6ba53-113">2</span></span></p></td>
<td><p><span data-ttu-id="6ba53-p102">将当前目录（但不包括其任何子目录）复制到目标。此复制操作不是递归的。</span><span class="sxs-lookup"><span data-stu-id="6ba53-p102">Copies the current directory, but none of its subdirectories, to the destination. The copy operation is not recursive.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ba53-116"><strong>adCopyOverWrite</strong></span><span class="sxs-lookup"><span data-stu-id="6ba53-116"><strong>adCopyOverWrite</strong></span></span></p></td>
<td><p><span data-ttu-id="6ba53-117">1</span><span class="sxs-lookup"><span data-stu-id="6ba53-117">1</span></span></p></td>
<td><p><span data-ttu-id="6ba53-118">如果 <em>Destination</em> 指向现有的文件或目录，则覆盖它们。</span><span class="sxs-lookup"><span data-stu-id="6ba53-118">Overwrites the file or directory if the <em>Destination</em> points to an existing file or directory.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ba53-119"><strong>adCopyUnspecified</strong></span><span class="sxs-lookup"><span data-stu-id="6ba53-119"><strong>adCopyUnspecified</strong></span></span></p></td>
<td><p><span data-ttu-id="6ba53-120">-1</span><span class="sxs-lookup"><span data-stu-id="6ba53-120">-1</span></span></p></td>
<td><p><span data-ttu-id="6ba53-p103">默认值。执行默认复制操作：如果目标文件或目录已存在，则操作失败，并递归复制。</span><span class="sxs-lookup"><span data-stu-id="6ba53-p103">Default. Performs the default copy operation: The operation fails if the destination file or directory already exists, and the operation copies recursively.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="adowfc-equivalent"></a><span data-ttu-id="6ba53-123">ADO/WFC 等效值</span><span class="sxs-lookup"><span data-stu-id="6ba53-123">ADO/WFC equivalent</span></span>

<span data-ttu-id="6ba53-124">这些常量没有 ADO/WFC 等效值。</span><span class="sxs-lookup"><span data-stu-id="6ba53-124">These constants do not have ADO/WFC equivalents.</span></span>

