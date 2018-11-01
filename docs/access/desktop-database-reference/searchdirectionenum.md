---
title: SearchDirectionEnum
TOCTitle: SearchDirectionEnum
ms:assetid: d491000b-47d0-bb28-95ed-7526dbb7c5e9
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250064(v=office.15)
ms:contentKeyID: 48547943
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: e456cfcc344c818504cb2ae1c2af9a4294b004ed
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25876412"
---
# <a name="searchdirectionenum"></a><span data-ttu-id="ee013-102">SearchDirectionEnum</span><span class="sxs-lookup"><span data-stu-id="ee013-102">SearchDirectionEnum</span></span>


<span data-ttu-id="ee013-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="ee013-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="ee013-104">用于指定 [Recordset](recordset-object-ado.md) 中记录搜索的方向。</span><span class="sxs-lookup"><span data-stu-id="ee013-104">Specifies the direction of a record search within a [Recordset](recordset-object-ado.md).</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="ee013-105">常量</span><span class="sxs-lookup"><span data-stu-id="ee013-105">Constant</span></span></p></th>
<th><p><span data-ttu-id="ee013-106">值</span><span class="sxs-lookup"><span data-stu-id="ee013-106">Value</span></span></p></th>
<th><p><span data-ttu-id="ee013-107">说明</span><span class="sxs-lookup"><span data-stu-id="ee013-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ee013-108"><strong>adSearchBackward</strong></span><span class="sxs-lookup"><span data-stu-id="ee013-108"><strong>adSearchBackward</strong></span></span></p></td>
<td><p><span data-ttu-id="ee013-109">-1</span><span class="sxs-lookup"><span data-stu-id="ee013-109">-1</span></span></p></td>
<td><p><span data-ttu-id="ee013-p101">向后搜索，在 <strong>Recordset</strong> 的开头停止。如果未找到匹配项，则记录指针定位在 <a href="bof-eof-properties-ado.md">BOF</a>。</span><span class="sxs-lookup"><span data-stu-id="ee013-p101">Searches backward, stopping at the beginning of the <strong>Recordset</strong>. If a match is not found, the record pointer is positioned at <a href="bof-eof-properties-ado.md">BOF</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee013-112"><strong>adSearchForward</strong></span><span class="sxs-lookup"><span data-stu-id="ee013-112"><strong>adSearchForward</strong></span></span></p></td>
<td><p><span data-ttu-id="ee013-113">1</span><span class="sxs-lookup"><span data-stu-id="ee013-113">1</span></span></p></td>
<td><p><span data-ttu-id="ee013-p102">向前搜索，在 <strong>Recordset</strong> 的末尾停止。如果未找到匹配项，则记录指针定位在 <a href="bof-eof-properties-ado.md">EOF</a>。</span><span class="sxs-lookup"><span data-stu-id="ee013-p102">Searches forward, stopping at the end of the <strong>Recordset</strong>. If a match is not found, the record pointer is positioned at <a href="bof-eof-properties-ado.md">EOF</a>.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="adowfc-equivalent"></a><span data-ttu-id="ee013-116">ADO/WFC 等效值</span><span class="sxs-lookup"><span data-stu-id="ee013-116">ADO/WFC equivalent</span></span>

<span data-ttu-id="ee013-117">包： **com.ms.wfc.data**</span><span class="sxs-lookup"><span data-stu-id="ee013-117">Package: **com.ms.wfc.data**</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="ee013-118">常量</span><span class="sxs-lookup"><span data-stu-id="ee013-118">Constant</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ee013-119">AdoEnums.SearchDirection.BACKWARD</span><span class="sxs-lookup"><span data-stu-id="ee013-119">AdoEnums.SearchDirection.BACKWARD</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee013-120">AdoEnums.SearchDirection.FORWARD</span><span class="sxs-lookup"><span data-stu-id="ee013-120">AdoEnums.SearchDirection.FORWARD</span></span></p></td>
</tr>
</tbody>
</table>

