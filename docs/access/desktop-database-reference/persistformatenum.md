---
title: PersistFormatEnum (Access desktop database reference)
TOCTitle: PersistFormatEnum
ms:assetid: 5aa99a63-d422-0812-5aba-19305a3ad405
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249313(v=office.15)
ms:contentKeyID: 48545050
ms.date: 10/18/2018
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 4954c09c3eff67bb6f55dfc9e49464ad58fad5e6
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32287606"
---
# <a name="persistformatenum"></a><span data-ttu-id="b43e5-102">PersistFormatEnum</span><span class="sxs-lookup"><span data-stu-id="b43e5-102">PersistFormatEnum</span></span>

<span data-ttu-id="b43e5-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="b43e5-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="b43e5-104">指定保存 [Recordset](recordset-object-ado.md) 时所用的格式。</span><span class="sxs-lookup"><span data-stu-id="b43e5-104">Specifies the format in which to save a [Recordset](recordset-object-ado.md).</span></span>

<br/>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="b43e5-105">常量</span><span class="sxs-lookup"><span data-stu-id="b43e5-105">Constant</span></span></p></th>
<th><p><span data-ttu-id="b43e5-106">值</span><span class="sxs-lookup"><span data-stu-id="b43e5-106">Value</span></span></p></th>
<th><p><span data-ttu-id="b43e5-107">说明</span><span class="sxs-lookup"><span data-stu-id="b43e5-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b43e5-108"><strong>adPersistADTG</strong></span><span class="sxs-lookup"><span data-stu-id="b43e5-108"><strong>adPersistADTG</strong></span></span></p></td>
<td><p><span data-ttu-id="b43e5-109">0</span><span class="sxs-lookup"><span data-stu-id="b43e5-109">0</span></span></p></td>
<td><p><span data-ttu-id="b43e5-110">指示 Microsoft 高级数据表图 (ADTG) 格式。</span><span class="sxs-lookup"><span data-stu-id="b43e5-110">Indicates Microsoft Advanced Data TableGram (ADTG) format.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b43e5-111"><strong>adPersistADO</strong></span><span class="sxs-lookup"><span data-stu-id="b43e5-111"><strong>adPersistADO</strong></span></span></p></td>
<td><p><span data-ttu-id="b43e5-112">1</span><span class="sxs-lookup"><span data-stu-id="b43e5-112">1</span></span></p></td>
<td><p><span data-ttu-id="b43e5-p101">指示将使用 ADO 自己的可扩展标记语言 (XML) 格式。此值与 adPersistXML 相同，包括它的目的是为了向后兼容。</span><span class="sxs-lookup"><span data-stu-id="b43e5-p101">Indicates that ADO's own Extensible Markup Language (XML) format will be used. This value is the same as adPersistXML and is included for backwards compatibility.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b43e5-115"><strong>adPersistXML</strong></span><span class="sxs-lookup"><span data-stu-id="b43e5-115"><strong>adPersistXML</strong></span></span></p></td>
<td><p><span data-ttu-id="b43e5-116">1</span><span class="sxs-lookup"><span data-stu-id="b43e5-116">1</span></span></p></td>
<td><p><span data-ttu-id="b43e5-117">指示可扩展标记语言 (XML) 格式。</span><span class="sxs-lookup"><span data-stu-id="b43e5-117">Indicates Extensible Markup Language (XML) format.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b43e5-118"><strong>adPersistProviderSpecific</strong></span><span class="sxs-lookup"><span data-stu-id="b43e5-118"><strong>adPersistProviderSpecific</strong></span></span></p></td>
<td><p><span data-ttu-id="b43e5-119">双面</span><span class="sxs-lookup"><span data-stu-id="b43e5-119">2</span></span></p></td>
<td><p><span data-ttu-id="b43e5-120">指示提供程序将使用自己的格式来持久化 <strong>Recordset</strong>。</span><span class="sxs-lookup"><span data-stu-id="b43e5-120">Indicates that the provider will persist the <strong>Recordset</strong> using its own format.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="adowfc-equivalent"></a><span data-ttu-id="b43e5-121">ADO/WFC 等效项</span><span class="sxs-lookup"><span data-stu-id="b43e5-121">ADO/WFC equivalent</span></span>

<span data-ttu-id="b43e5-122">包：**com.ms.wfc.data**</span><span class="sxs-lookup"><span data-stu-id="b43e5-122">Package: **com.ms.wfc.data**</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="b43e5-123">常量</span><span class="sxs-lookup"><span data-stu-id="b43e5-123">Constant</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b43e5-124">AdoEnums PersistFormat</span><span class="sxs-lookup"><span data-stu-id="b43e5-124">AdoEnums.PersistFormat.ADTG</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b43e5-125">AdoEnums PersistFormat</span><span class="sxs-lookup"><span data-stu-id="b43e5-125">AdoEnums.PersistFormat.XML</span></span></p></td>
</tr>
</tbody>
</table>

