---
title: PositionEnum (Access desktop database reference)
TOCTitle: PositionEnum
ms:assetid: 2a6f294b-74f2-b951-e32a-79ff5e782204
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249054(v=office.15)
ms:contentKeyID: 48543907
ms.date: 10/18/2018
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 4c791cbd31e346eef5ab8503cb55b0dec5e9fbbc
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32287501"
---
# <a name="positionenum"></a><span data-ttu-id="1c63d-102">PositionEnum</span><span class="sxs-lookup"><span data-stu-id="1c63d-102">PositionEnum</span></span>

<span data-ttu-id="1c63d-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="1c63d-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="1c63d-104">指定在 [Recordset](recordset-object-ado.md) 中记录指针的当前位置。</span><span class="sxs-lookup"><span data-stu-id="1c63d-104">Specifies the current position of the record pointer within a [Recordset](recordset-object-ado.md).</span></span>

<br/>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="1c63d-105">常量</span><span class="sxs-lookup"><span data-stu-id="1c63d-105">Constant</span></span></p></th>
<th><p><span data-ttu-id="1c63d-106">值</span><span class="sxs-lookup"><span data-stu-id="1c63d-106">Value</span></span></p></th>
<th><p><span data-ttu-id="1c63d-107">说明</span><span class="sxs-lookup"><span data-stu-id="1c63d-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1c63d-108"><strong>adPosBOF</strong></span><span class="sxs-lookup"><span data-stu-id="1c63d-108"><strong>adPosBOF</strong></span></span></p></td>
<td><p><span data-ttu-id="1c63d-109">-2</span><span class="sxs-lookup"><span data-stu-id="1c63d-109">-2</span></span></p></td>
<td><p><span data-ttu-id="1c63d-110">指示当前记录指针位于 BOF（即，<a href="bof-eof-properties-ado.md">BOF</a> 属性为 <strong>True</strong>）。</span><span class="sxs-lookup"><span data-stu-id="1c63d-110">Indicates that the current record pointer is at BOF (that is, the <a href="bof-eof-properties-ado.md">BOF</a> property is <strong>True</strong>).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1c63d-111"><strong>adPosEOF</strong></span><span class="sxs-lookup"><span data-stu-id="1c63d-111"><strong>adPosEOF</strong></span></span></p></td>
<td><p><span data-ttu-id="1c63d-112">-3</span><span class="sxs-lookup"><span data-stu-id="1c63d-112">-3</span></span></p></td>
<td><p><span data-ttu-id="1c63d-113">指示当前记录指针位于 EOF（即，<a href="bof-eof-properties-ado.md">EOF</a> 属性为 <strong>True</strong>）。</span><span class="sxs-lookup"><span data-stu-id="1c63d-113">Indicates that the current record pointer is at EOF (that is, the <a href="bof-eof-properties-ado.md">EOF</a> property is <strong>True</strong>).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1c63d-114"><strong>adPosUnknown</strong></span><span class="sxs-lookup"><span data-stu-id="1c63d-114"><strong>adPosUnknown</strong></span></span></p></td>
<td><p><span data-ttu-id="1c63d-115">-1</span><span class="sxs-lookup"><span data-stu-id="1c63d-115">-1</span></span></p></td>
<td><p><span data-ttu-id="1c63d-116">指示 <strong>Recordset</strong> 为空，当前位置未知，或者提供程序不支持 <a href="absolutepage-property-ado.md">AbsolutePage</a> 或 <a href="absoluteposition-property-ado.md">AbsolutePosition</a> 属性。</span><span class="sxs-lookup"><span data-stu-id="1c63d-116">Indicates that the <strong>Recordset</strong> is empty, the current position is unknown, or the provider does not support the <a href="absolutepage-property-ado.md">AbsolutePage</a> or <a href="absoluteposition-property-ado.md">AbsolutePosition</a> property.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="adowfc-equivalent"></a><span data-ttu-id="1c63d-117">ADO/WFC 等效项</span><span class="sxs-lookup"><span data-stu-id="1c63d-117">ADO/WFC equivalent</span></span>

<span data-ttu-id="1c63d-118">包：**com.ms.wfc.data**</span><span class="sxs-lookup"><span data-stu-id="1c63d-118">Package: **com.ms.wfc.data**</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="1c63d-119">常量</span><span class="sxs-lookup"><span data-stu-id="1c63d-119">Constant</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1c63d-120">AdoEnums 的位置. BOF</span><span class="sxs-lookup"><span data-stu-id="1c63d-120">AdoEnums.Position.BOF</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1c63d-121">AdoEnums</span><span class="sxs-lookup"><span data-stu-id="1c63d-121">AdoEnums.Position.EOF</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1c63d-122">AdoEnums 的位置。未知</span><span class="sxs-lookup"><span data-stu-id="1c63d-122">AdoEnums.Position.UNKNOWN</span></span></p></td>
</tr>
</tbody>
</table>

