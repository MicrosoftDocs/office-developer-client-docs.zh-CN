---
title: CopyRecordOptionsEnum
TOCTitle: CopyRecordOptionsEnum
ms:assetid: ab9426e9-0e4e-6c85-43cf-e4a205a7c4c0
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249795(v=office.15)
ms:contentKeyID: 48546975
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: eb1637d1757a8507c6b6abb2a0c71867e3d1177b
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28703844"
---
# <a name="copyrecordoptionsenum"></a><span data-ttu-id="8347e-102">CopyRecordOptionsEnum</span><span class="sxs-lookup"><span data-stu-id="8347e-102">CopyRecordOptionsEnum</span></span>


<span data-ttu-id="8347e-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="8347e-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="8347e-104">指定 [CopyRecord](copyrecord-method-ado.md) 方法的行为。</span><span class="sxs-lookup"><span data-stu-id="8347e-104">Specifies the behavior of the [CopyRecord](copyrecord-method-ado.md) method.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="8347e-105">常量</span><span class="sxs-lookup"><span data-stu-id="8347e-105">Constant</span></span></p></th>
<th><p><span data-ttu-id="8347e-106">值</span><span class="sxs-lookup"><span data-stu-id="8347e-106">Value</span></span></p></th>
<th><p><span data-ttu-id="8347e-107">说明</span><span class="sxs-lookup"><span data-stu-id="8347e-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8347e-108"><strong>adCopyAllowEmulation</strong></span><span class="sxs-lookup"><span data-stu-id="8347e-108"><strong>adCopyAllowEmulation</strong></span></span></p></td>
<td><p><span data-ttu-id="8347e-109">4</span><span class="sxs-lookup"><span data-stu-id="8347e-109">4</span></span></p></td>
<td><p><span data-ttu-id="8347e-p101">指示如果此方法由于 <em>Destination</em> 在不同的服务器上而失败或者由不同于 <em>Source</em> 提供程序的提供程序提供服务，则 <em>Source</em> 提供程序会尝试使用下载和上载操作来模拟复制。注意，不同的提供程序功能可能会导致性能下降或数据丢失。</span><span class="sxs-lookup"><span data-stu-id="8347e-p101">Indicates that the <em>Source</em> provider attempts to simulate the copy using download and upload operations if this method fails due to <em>Destination</em> being on a different server or is serviced by a different provider than <em>Source</em>. Note that differing provider capabilities may hamper performance or lose data.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8347e-112"><strong>adCopyNonRecursive</strong></span><span class="sxs-lookup"><span data-stu-id="8347e-112"><strong>adCopyNonRecursive</strong></span></span></p></td>
<td><p><span data-ttu-id="8347e-113">2</span><span class="sxs-lookup"><span data-stu-id="8347e-113">2</span></span></p></td>
<td><p><span data-ttu-id="8347e-p102">将当前目录（但不包括其任何子目录）复制到目标。此复制操作不是递归的。</span><span class="sxs-lookup"><span data-stu-id="8347e-p102">Copies the current directory, but none of its subdirectories, to the destination. The copy operation is not recursive.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8347e-116"><strong>adCopyOverWrite</strong></span><span class="sxs-lookup"><span data-stu-id="8347e-116"><strong>adCopyOverWrite</strong></span></span></p></td>
<td><p><span data-ttu-id="8347e-117">1</span><span class="sxs-lookup"><span data-stu-id="8347e-117">1</span></span></p></td>
<td><p><span data-ttu-id="8347e-118">如果 <em>Destination</em> 指向现有的文件或目录，则覆盖它们。</span><span class="sxs-lookup"><span data-stu-id="8347e-118">Overwrites the file or directory if the <em>Destination</em> points to an existing file or directory.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8347e-119"><strong>adCopyUnspecified</strong></span><span class="sxs-lookup"><span data-stu-id="8347e-119"><strong>adCopyUnspecified</strong></span></span></p></td>
<td><p><span data-ttu-id="8347e-120">-1</span><span class="sxs-lookup"><span data-stu-id="8347e-120">-1</span></span></p></td>
<td><p><span data-ttu-id="8347e-p103">默认值。执行默认复制操作：如果目标文件或目录已存在，则操作失败，并递归复制。</span><span class="sxs-lookup"><span data-stu-id="8347e-p103">Default. Performs the default copy operation: The operation fails if the destination file or directory already exists, and the operation copies recursively.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="adowfc-equivalent"></a><span data-ttu-id="8347e-123">ADO/WFC 等效值</span><span class="sxs-lookup"><span data-stu-id="8347e-123">ADO/WFC equivalent</span></span>

<span data-ttu-id="8347e-124">这些常量没有 ADO/WFC 等效值。</span><span class="sxs-lookup"><span data-stu-id="8347e-124">These constants do not have ADO/WFC equivalents.</span></span>

