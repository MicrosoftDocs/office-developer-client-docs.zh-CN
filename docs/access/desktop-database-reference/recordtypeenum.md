---
title: RecordTypeEnum （访问桌面数据库参考 （英文）
TOCTitle: RecordTypeEnum
ms:assetid: 7edd6508-1507-4649-f1aa-03f1873ef09c
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249534(v=office.15)
ms:contentKeyID: 48545890
ms.date: 10/18/2018
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: c95e4b78a3e2259c3dc5961e87b98ca65ea55692
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28704915"
---
# <a name="recordtypeenum"></a><span data-ttu-id="dd011-102">RecordTypeEnum</span><span class="sxs-lookup"><span data-stu-id="dd011-102">RecordTypeEnum</span></span>

<span data-ttu-id="dd011-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="dd011-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="dd011-104">指定 [Record](record-object-ado.md) 对象的类型。</span><span class="sxs-lookup"><span data-stu-id="dd011-104">Specifies the type of [Record](record-object-ado.md) object.</span></span>

<br/>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="dd011-105">常量</span><span class="sxs-lookup"><span data-stu-id="dd011-105">Constant</span></span></p></th>
<th><p><span data-ttu-id="dd011-106">值</span><span class="sxs-lookup"><span data-stu-id="dd011-106">Value</span></span></p></th>
<th><p><span data-ttu-id="dd011-107">说明</span><span class="sxs-lookup"><span data-stu-id="dd011-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dd011-108"><strong>为 adSimpleRecord</strong></span><span class="sxs-lookup"><span data-stu-id="dd011-108"><strong>adSimpleRecord</strong></span></span></p></td>
<td><p><span data-ttu-id="dd011-109">0</span><span class="sxs-lookup"><span data-stu-id="dd011-109">0</span></span></p></td>
<td><p><span data-ttu-id="dd011-110">指示一个<em>简单</em>记录（不包含子节点）。</span><span class="sxs-lookup"><span data-stu-id="dd011-110">Indicates a <em>simple</em> record (does not contain child nodes).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dd011-111"><strong>adCollectionRecord</strong></span><span class="sxs-lookup"><span data-stu-id="dd011-111"><strong>adCollectionRecord</strong></span></span></p></td>
<td><p><span data-ttu-id="dd011-112">1</span><span class="sxs-lookup"><span data-stu-id="dd011-112">1</span></span></p></td>
<td><p><span data-ttu-id="dd011-113">指示一个<em>集合</em>记录（包含子节点）。</span><span class="sxs-lookup"><span data-stu-id="dd011-113">Indicates a <em>collection</em> record (contains child nodes).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dd011-114"><strong>adRecordUnknown</strong></span><span class="sxs-lookup"><span data-stu-id="dd011-114"><strong>adRecordUnknown</strong></span></span></p></td>
<td><p><span data-ttu-id="dd011-115">-1</span><span class="sxs-lookup"><span data-stu-id="dd011-115">-1</span></span></p></td>
<td><p><span data-ttu-id="dd011-116">指示此 <strong>Record</strong> 的类型未知。</span><span class="sxs-lookup"><span data-stu-id="dd011-116">Indicates that the type of this <strong>Record</strong> is unknown.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dd011-117"><strong>为 adStructDoc</strong></span><span class="sxs-lookup"><span data-stu-id="dd011-117"><strong>adStructDoc</strong></span></span></p></td>
<td><p><span data-ttu-id="dd011-118">2</span><span class="sxs-lookup"><span data-stu-id="dd011-118">2</span></span></p></td>
<td><p><span data-ttu-id="dd011-119">指示代表 COM 结构化文档的特殊种类的<em>集合</em>记录。</span><span class="sxs-lookup"><span data-stu-id="dd011-119">Indicates a special kind of <em>collection</em> record that represents COM structured documents.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="adowfc-equivalent"></a><span data-ttu-id="dd011-120">ADO/WFC 等效值</span><span class="sxs-lookup"><span data-stu-id="dd011-120">ADO/WFC equivalent</span></span>

<span data-ttu-id="dd011-121">这些常量没有 ADO/WFC 等效值。</span><span class="sxs-lookup"><span data-stu-id="dd011-121">These constants do not have ADO/WFC equivalents.</span></span>

