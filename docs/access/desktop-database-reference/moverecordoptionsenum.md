---
title: MoveRecordOptionsEnum
TOCTitle: MoveRecordOptionsEnum
ms:assetid: 2785bca0-777c-a802-51d7-6f5cf0fb4210
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249039(v=office.15)
ms:contentKeyID: 48543842
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 41ec6eaf39545bf8a71f443a8e3b90052a74f1de
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468457"
---
# <a name="moverecordoptionsenum"></a><span data-ttu-id="b48fd-102">MoveRecordOptionsEnum</span><span class="sxs-lookup"><span data-stu-id="b48fd-102">MoveRecordOptionsEnum</span></span>


<span data-ttu-id="b48fd-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="b48fd-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="b48fd-104">指定 [Record](record-object-ado.md) 对象的 [MoveRecord](moverecord-method-ado.md) 方法的行为。</span><span class="sxs-lookup"><span data-stu-id="b48fd-104">Specifies the behavior of the [Record](record-object-ado.md) object [MoveRecord](moverecord-method-ado.md) method.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="b48fd-105">常量</span><span class="sxs-lookup"><span data-stu-id="b48fd-105">Constant</span></span></p></th>
<th><p><span data-ttu-id="b48fd-106">值</span><span class="sxs-lookup"><span data-stu-id="b48fd-106">Value</span></span></p></th>
<th><p><span data-ttu-id="b48fd-107">说明</span><span class="sxs-lookup"><span data-stu-id="b48fd-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b48fd-108"><strong>adMoveUnspecified</strong></span><span class="sxs-lookup"><span data-stu-id="b48fd-108"><strong>adMoveUnspecified</strong></span></span></p></td>
<td><p><span data-ttu-id="b48fd-109">-1</span><span class="sxs-lookup"><span data-stu-id="b48fd-109">-1</span></span></p></td>
<td><p><span data-ttu-id="b48fd-p101">默认值。执行默认移动操作：如果目标文件或目录已存在，则操作失败，并且更新超文本链接。</span><span class="sxs-lookup"><span data-stu-id="b48fd-p101">Default. Performs the default move operation: The operation fails if the destination file or directory already exists, and the operation updates hypertext links.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b48fd-112"><strong>adMoveOverWrite</strong></span><span class="sxs-lookup"><span data-stu-id="b48fd-112"><strong>adMoveOverWrite</strong></span></span></p></td>
<td><p><span data-ttu-id="b48fd-113">1</span><span class="sxs-lookup"><span data-stu-id="b48fd-113">1</span></span></p></td>
<td><p><span data-ttu-id="b48fd-114">覆盖目标文件或目录，即使它已存在。</span><span class="sxs-lookup"><span data-stu-id="b48fd-114">Overwrites the destination file or directory, even if it already exists.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b48fd-115"><strong>adMoveDontUpdateLinks</strong></span><span class="sxs-lookup"><span data-stu-id="b48fd-115"><strong>adMoveDontUpdateLinks</strong></span></span></p></td>
<td><p><span data-ttu-id="b48fd-116">2</span><span class="sxs-lookup"><span data-stu-id="b48fd-116">2</span></span></p></td>
<td><p><span data-ttu-id="b48fd-p102">通过不更新源 <strong>Record</strong> 的超文本链接来修改 <strong>MoveRecord</strong> 方法的默认行为。默认行为取决于提供程序的功能。如果提供程序具有相应功能，则移动操作更新链接。如果提供程序无法修复链接或者如果未指定该值，则即使链接尚未修复，移动也会成功。</span><span class="sxs-lookup"><span data-stu-id="b48fd-p102">Modifies the default behavior of <strong>MoveRecord</strong> method by not updating the hypertext links of the source <strong>Record</strong>. The default behavior depends on the capabilities of the provider. Move operation updates links if the provider is capable. If the provider cannot fix links or if this value is not specified, then the move succeeds even when links have not been fixed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b48fd-121"><strong>adMoveAllowEmulation</strong></span><span class="sxs-lookup"><span data-stu-id="b48fd-121"><strong>adMoveAllowEmulation</strong></span></span></p></td>
<td><p><span data-ttu-id="b48fd-122">4</span><span class="sxs-lookup"><span data-stu-id="b48fd-122">4</span></span></p></td>
<td><p><span data-ttu-id="b48fd-p103">提供程序尝试模拟移动（使用下载、上载和删除操作）的请求。如果移动 <strong>Record</strong> 的尝试由于目标 URL 在不同的服务器或者由非源提供程序提供服务而失败，可能会导致增加延迟或数据丢失，原因是在提供程序之间移动资源时，各个提供程序具有不同的功能。</span><span class="sxs-lookup"><span data-stu-id="b48fd-p103">Requests that the provider attempt to simulate the move (using download, upload, and delete operations). If the attempt to move the <strong>Record</strong> fails because the destination URL is on a different server or serviced by a different provider than the source, this may cause increased latency or data loss, due to different provider capabilities when moving resources between providers.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="b48fd-125">**ADO/WFC 等效值**</span><span class="sxs-lookup"><span data-stu-id="b48fd-125">**ADO/WFC Equivalent**</span></span>

<span data-ttu-id="b48fd-126">这些常量没有 ADO/WFC 等效值。</span><span class="sxs-lookup"><span data-stu-id="b48fd-126">These constants do not have ADO/WFC equivalents.</span></span>
