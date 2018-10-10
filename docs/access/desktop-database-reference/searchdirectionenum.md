---
title: SearchDirectionEnum
TOCTitle: SearchDirectionEnum
ms:assetid: d491000b-47d0-bb28-95ed-7526dbb7c5e9
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250064(v=office.15)
ms:contentKeyID: 48547943
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: d0a9954319448a219d9683cfd8133929fb3d184d
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25465986"
---
# <a name="searchdirectionenum"></a><span data-ttu-id="a2781-102">SearchDirectionEnum</span><span class="sxs-lookup"><span data-stu-id="a2781-102">SearchDirectionEnum</span></span>


<span data-ttu-id="a2781-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="a2781-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="a2781-104">用于指定 [Recordset](recordset-object-ado.md) 中记录搜索的方向。</span><span class="sxs-lookup"><span data-stu-id="a2781-104">Specifies the direction of a record search within a [Recordset](recordset-object-ado.md).</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="a2781-105">常量</span><span class="sxs-lookup"><span data-stu-id="a2781-105">Constant</span></span></p></th>
<th><p><span data-ttu-id="a2781-106">值</span><span class="sxs-lookup"><span data-stu-id="a2781-106">Value</span></span></p></th>
<th><p><span data-ttu-id="a2781-107">说明</span><span class="sxs-lookup"><span data-stu-id="a2781-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a2781-108"><strong>adSearchBackward</strong></span><span class="sxs-lookup"><span data-stu-id="a2781-108"><strong>adSearchBackward</strong></span></span></p></td>
<td><p><span data-ttu-id="a2781-109">-1</span><span class="sxs-lookup"><span data-stu-id="a2781-109">-1</span></span></p></td>
<td><p><span data-ttu-id="a2781-p101">向后搜索，在 <strong>Recordset</strong> 的开头停止。如果未找到匹配项，则记录指针定位在 <a href="bof-eof-properties-ado.md">BOF</a>。</span><span class="sxs-lookup"><span data-stu-id="a2781-p101">Searches backward, stopping at the beginning of the <strong>Recordset</strong>. If a match is not found, the record pointer is positioned at <a href="bof-eof-properties-ado.md">BOF</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2781-112"><strong>adSearchForward</strong></span><span class="sxs-lookup"><span data-stu-id="a2781-112"><strong>adSearchForward</strong></span></span></p></td>
<td><p><span data-ttu-id="a2781-113">1</span><span class="sxs-lookup"><span data-stu-id="a2781-113">1</span></span></p></td>
<td><p><span data-ttu-id="a2781-p102">向前搜索，在 <strong>Recordset</strong> 的末尾停止。如果未找到匹配项，则记录指针定位在 <a href="bof-eof-properties-ado.md">EOF</a>。</span><span class="sxs-lookup"><span data-stu-id="a2781-p102">Searches forward, stopping at the end of the <strong>Recordset</strong>. If a match is not found, the record pointer is positioned at <a href="bof-eof-properties-ado.md">EOF</a>.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a2781-116">**ADO/WFC 等效值**</span><span class="sxs-lookup"><span data-stu-id="a2781-116">**ADO/WFC Equivalent**</span></span>

<span data-ttu-id="a2781-117">包： **com.ms.wfc.data**</span><span class="sxs-lookup"><span data-stu-id="a2781-117">Package: **com.ms.wfc.data**</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="a2781-118">常量</span><span class="sxs-lookup"><span data-stu-id="a2781-118">Constant</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a2781-119">AdoEnums.SearchDirection.BACKWARD</span><span class="sxs-lookup"><span data-stu-id="a2781-119">AdoEnums.SearchDirection.BACKWARD</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2781-120">AdoEnums.SearchDirection.FORWARD</span><span class="sxs-lookup"><span data-stu-id="a2781-120">AdoEnums.SearchDirection.FORWARD</span></span></p></td>
</tr>
</tbody>
</table>

