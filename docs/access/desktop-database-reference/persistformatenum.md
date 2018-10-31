---
title: PersistFormatEnum （访问桌面数据库参考 （英文）
TOCTitle: PersistFormatEnum
ms:assetid: 5aa99a63-d422-0812-5aba-19305a3ad405
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249313(v=office.15)
ms:contentKeyID: 48545050
ms.date: 10/18/2018
mtps_version: v=office.15
ms.openlocfilehash: 65c33389bc7eb703fce6c44da3507a28bccb75eb
ms.sourcegitcommit: 801b1b54786f7b0e5b0d35466e7ae8d1e840b26f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25862476"
---
# <a name="persistformatenum"></a><span data-ttu-id="a4da4-102">PersistFormatEnum</span><span class="sxs-lookup"><span data-stu-id="a4da4-102">PersistFormatEnum</span></span>

<span data-ttu-id="a4da4-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="a4da4-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="a4da4-104">指定保存 [Recordset](recordset-object-ado.md) 时所用的格式。</span><span class="sxs-lookup"><span data-stu-id="a4da4-104">Specifies the format in which to save a [Recordset](recordset-object-ado.md).</span></span>

<br/>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="a4da4-105">常量</span><span class="sxs-lookup"><span data-stu-id="a4da4-105">Constant</span></span></p></th>
<th><p><span data-ttu-id="a4da4-106">值</span><span class="sxs-lookup"><span data-stu-id="a4da4-106">Value</span></span></p></th>
<th><p><span data-ttu-id="a4da4-107">说明</span><span class="sxs-lookup"><span data-stu-id="a4da4-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a4da4-108"><strong>adPersistADTG</strong></span><span class="sxs-lookup"><span data-stu-id="a4da4-108"><strong>adPersistADTG</strong></span></span></p></td>
<td><p><span data-ttu-id="a4da4-109">0</span><span class="sxs-lookup"><span data-stu-id="a4da4-109">0</span></span></p></td>
<td><p><span data-ttu-id="a4da4-110">指示 Microsoft 高级数据表图 (ADTG) 格式。</span><span class="sxs-lookup"><span data-stu-id="a4da4-110">Indicates Microsoft Advanced Data TableGram (ADTG) format.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4da4-111"><strong>adPersistADO</strong></span><span class="sxs-lookup"><span data-stu-id="a4da4-111"><strong>adPersistADO</strong></span></span></p></td>
<td><p><span data-ttu-id="a4da4-112">1</span><span class="sxs-lookup"><span data-stu-id="a4da4-112">1</span></span></p></td>
<td><p><span data-ttu-id="a4da4-p101">指示将使用 ADO 自己的可扩展标记语言 (XML) 格式。此值与 adPersistXML 相同，包括它的目的是为了向后兼容。</span><span class="sxs-lookup"><span data-stu-id="a4da4-p101">Indicates that ADO's own Extensible Markup Language (XML) format will be used. This value is the same as adPersistXML and is included for backwards compatibility.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4da4-115"><strong>xml 格式持久化记录</strong></span><span class="sxs-lookup"><span data-stu-id="a4da4-115"><strong>adPersistXML</strong></span></span></p></td>
<td><p><span data-ttu-id="a4da4-116">1</span><span class="sxs-lookup"><span data-stu-id="a4da4-116">1</span></span></p></td>
<td><p><span data-ttu-id="a4da4-117">指示可扩展标记语言 (XML) 格式。</span><span class="sxs-lookup"><span data-stu-id="a4da4-117">Indicates Extensible Markup Language (XML) format.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4da4-118"><strong>adPersistProviderSpecific</strong></span><span class="sxs-lookup"><span data-stu-id="a4da4-118"><strong>adPersistProviderSpecific</strong></span></span></p></td>
<td><p><span data-ttu-id="a4da4-119">2</span><span class="sxs-lookup"><span data-stu-id="a4da4-119">2</span></span></p></td>
<td><p><span data-ttu-id="a4da4-120">指示提供程序将使用自己的格式来持久化 <strong>Recordset</strong>。</span><span class="sxs-lookup"><span data-stu-id="a4da4-120">Indicates that the provider will persist the <strong>Recordset</strong> using its own format.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="adowfc-equivalent"></a><span data-ttu-id="a4da4-121">ADO/WFC 等效值</span><span class="sxs-lookup"><span data-stu-id="a4da4-121">ADO/WFC equivalent</span></span>

<span data-ttu-id="a4da4-122">包： **com.ms.wfc.data**</span><span class="sxs-lookup"><span data-stu-id="a4da4-122">Package: **com.ms.wfc.data**</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="a4da4-123">常量</span><span class="sxs-lookup"><span data-stu-id="a4da4-123">Constant</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a4da4-124">AdoEnums.PersistFormat.ADTG</span><span class="sxs-lookup"><span data-stu-id="a4da4-124">AdoEnums.PersistFormat.ADTG</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4da4-125">AdoEnums.PersistFormat.XML</span><span class="sxs-lookup"><span data-stu-id="a4da4-125">AdoEnums.PersistFormat.XML</span></span></p></td>
</tr>
</tbody>
</table>

