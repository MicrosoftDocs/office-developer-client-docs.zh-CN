---
title: RecordTypeEnum (Access desktop database reference)
TOCTitle: RecordTypeEnum
ms:assetid: 7edd6508-1507-4649-f1aa-03f1873ef09c
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249534(v=office.15)
ms:contentKeyID: 48545890
ms.date: 10/18/2018
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: c95e4b78a3e2259c3dc5961e87b98ca65ea55692
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32309281"
---
# <a name="recordtypeenum"></a><span data-ttu-id="e9110-102">RecordTypeEnum</span><span class="sxs-lookup"><span data-stu-id="e9110-102">RecordTypeEnum</span></span>

<span data-ttu-id="e9110-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="e9110-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="e9110-104">指定 [Record](record-object-ado.md) 对象的类型。</span><span class="sxs-lookup"><span data-stu-id="e9110-104">Specifies the type of [Record](record-object-ado.md) object.</span></span>

<br/>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="e9110-105">常量</span><span class="sxs-lookup"><span data-stu-id="e9110-105">Constant</span></span></p></th>
<th><p><span data-ttu-id="e9110-106">值</span><span class="sxs-lookup"><span data-stu-id="e9110-106">Value</span></span></p></th>
<th><p><span data-ttu-id="e9110-107">说明</span><span class="sxs-lookup"><span data-stu-id="e9110-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e9110-108"><strong>adSimpleRecord</strong></span><span class="sxs-lookup"><span data-stu-id="e9110-108"><strong>adSimpleRecord</strong></span></span></p></td>
<td><p><span data-ttu-id="e9110-109">0</span><span class="sxs-lookup"><span data-stu-id="e9110-109">0</span></span></p></td>
<td><p><span data-ttu-id="e9110-110">指示一个<em>简单</em>记录（不包含子节点）。</span><span class="sxs-lookup"><span data-stu-id="e9110-110">Indicates a <em>simple</em> record (does not contain child nodes).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9110-111"><strong>recordtype</strong></span><span class="sxs-lookup"><span data-stu-id="e9110-111"><strong>adCollectionRecord</strong></span></span></p></td>
<td><p><span data-ttu-id="e9110-112">1</span><span class="sxs-lookup"><span data-stu-id="e9110-112">1</span></span></p></td>
<td><p><span data-ttu-id="e9110-113">指示一个<em>集合</em>记录（包含子节点）。</span><span class="sxs-lookup"><span data-stu-id="e9110-113">Indicates a <em>collection</em> record (contains child nodes).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9110-114"><strong>adRecordUnknown</strong></span><span class="sxs-lookup"><span data-stu-id="e9110-114"><strong>adRecordUnknown</strong></span></span></p></td>
<td><p><span data-ttu-id="e9110-115">-1</span><span class="sxs-lookup"><span data-stu-id="e9110-115">-1</span></span></p></td>
<td><p><span data-ttu-id="e9110-116">指示此 <strong>Record</strong> 的类型未知。</span><span class="sxs-lookup"><span data-stu-id="e9110-116">Indicates that the type of this <strong>Record</strong> is unknown.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9110-117"><strong>adStructDoc</strong></span><span class="sxs-lookup"><span data-stu-id="e9110-117"><strong>adStructDoc</strong></span></span></p></td>
<td><p><span data-ttu-id="e9110-118">双面</span><span class="sxs-lookup"><span data-stu-id="e9110-118">2</span></span></p></td>
<td><p><span data-ttu-id="e9110-119">指示代表 COM 结构化文档的特殊种类的<em>集合</em>记录。</span><span class="sxs-lookup"><span data-stu-id="e9110-119">Indicates a special kind of <em>collection</em> record that represents COM structured documents.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="adowfc-equivalent"></a><span data-ttu-id="e9110-120">ADO/WFC 等效项</span><span class="sxs-lookup"><span data-stu-id="e9110-120">ADO/WFC equivalent</span></span>

<span data-ttu-id="e9110-121">这些常量没有 ADO/WFC 等效值。</span><span class="sxs-lookup"><span data-stu-id="e9110-121">These constants do not have ADO/WFC equivalents.</span></span>

