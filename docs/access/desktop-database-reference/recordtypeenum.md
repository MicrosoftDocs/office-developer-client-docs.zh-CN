---
title: RecordTypeEnum （访问桌面数据库参考 （英文）
TOCTitle: RecordTypeEnum
ms:assetid: 7edd6508-1507-4649-f1aa-03f1873ef09c
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249534(v=office.15)
ms:contentKeyID: 48545890
ms.date: 10/18/2018
mtps_version: v=office.15
ms.openlocfilehash: 6427a98d13231575bdc90fb89fe740fd9cd0f073
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25868348"
---
# <a name="recordtypeenum"></a><span data-ttu-id="55297-102">RecordTypeEnum</span><span class="sxs-lookup"><span data-stu-id="55297-102">RecordTypeEnum</span></span>

<span data-ttu-id="55297-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="55297-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="55297-104">指定 [Record](record-object-ado.md) 对象的类型。</span><span class="sxs-lookup"><span data-stu-id="55297-104">Specifies the type of [Record](record-object-ado.md) object.</span></span>

<br/>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="55297-105">常量</span><span class="sxs-lookup"><span data-stu-id="55297-105">Constant</span></span></p></th>
<th><p><span data-ttu-id="55297-106">值</span><span class="sxs-lookup"><span data-stu-id="55297-106">Value</span></span></p></th>
<th><p><span data-ttu-id="55297-107">说明</span><span class="sxs-lookup"><span data-stu-id="55297-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="55297-108"><strong>为 adSimpleRecord</strong></span><span class="sxs-lookup"><span data-stu-id="55297-108"><strong>adSimpleRecord</strong></span></span></p></td>
<td><p><span data-ttu-id="55297-109">0</span><span class="sxs-lookup"><span data-stu-id="55297-109">0</span></span></p></td>
<td><p><span data-ttu-id="55297-110">指示一个<em>简单</em>记录（不包含子节点）。</span><span class="sxs-lookup"><span data-stu-id="55297-110">Indicates a <em>simple</em> record (does not contain child nodes).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55297-111"><strong>adCollectionRecord</strong></span><span class="sxs-lookup"><span data-stu-id="55297-111"><strong>adCollectionRecord</strong></span></span></p></td>
<td><p><span data-ttu-id="55297-112">1</span><span class="sxs-lookup"><span data-stu-id="55297-112">1</span></span></p></td>
<td><p><span data-ttu-id="55297-113">指示一个<em>集合</em>记录（包含子节点）。</span><span class="sxs-lookup"><span data-stu-id="55297-113">Indicates a <em>collection</em> record (contains child nodes).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="55297-114"><strong>adRecordUnknown</strong></span><span class="sxs-lookup"><span data-stu-id="55297-114"><strong>adRecordUnknown</strong></span></span></p></td>
<td><p><span data-ttu-id="55297-115">-1</span><span class="sxs-lookup"><span data-stu-id="55297-115">-1</span></span></p></td>
<td><p><span data-ttu-id="55297-116">指示此 <strong>Record</strong> 的类型未知。</span><span class="sxs-lookup"><span data-stu-id="55297-116">Indicates that the type of this <strong>Record</strong> is unknown.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55297-117"><strong>为 adStructDoc</strong></span><span class="sxs-lookup"><span data-stu-id="55297-117"><strong>adStructDoc</strong></span></span></p></td>
<td><p><span data-ttu-id="55297-118">2</span><span class="sxs-lookup"><span data-stu-id="55297-118">2</span></span></p></td>
<td><p><span data-ttu-id="55297-119">指示代表 COM 结构化文档的特殊种类的<em>集合</em>记录。</span><span class="sxs-lookup"><span data-stu-id="55297-119">Indicates a special kind of <em>collection</em> record that represents COM structured documents.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="adowfc-equivalent"></a><span data-ttu-id="55297-120">ADO/WFC 等效值</span><span class="sxs-lookup"><span data-stu-id="55297-120">ADO/WFC equivalent</span></span>

<span data-ttu-id="55297-121">这些常量没有 ADO/WFC 等效值。</span><span class="sxs-lookup"><span data-stu-id="55297-121">These constants do not have ADO/WFC equivalents.</span></span>

