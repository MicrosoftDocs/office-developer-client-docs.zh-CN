---
title: RecordTypeEnum （访问桌面数据库参考 （英文）
TOCTitle: RecordTypeEnum
ms:assetid: 7edd6508-1507-4649-f1aa-03f1873ef09c
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249534(v=office.15)
ms:contentKeyID: 48545890
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 4eedd04b630e0cc1cf855eefe09bd071dfbbbb50
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468132"
---
# <a name="recordtypeenum"></a><span data-ttu-id="db095-102">RecordTypeEnum</span><span class="sxs-lookup"><span data-stu-id="db095-102">RecordTypeEnum</span></span>


<span data-ttu-id="db095-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="db095-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="db095-104">指定 [Record](record-object-ado.md) 对象的类型。</span><span class="sxs-lookup"><span data-stu-id="db095-104">Specifies the type of [Record](record-object-ado.md) object.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="db095-105">常量</span><span class="sxs-lookup"><span data-stu-id="db095-105">Constant</span></span></p></th>
<th><p><span data-ttu-id="db095-106">值</span><span class="sxs-lookup"><span data-stu-id="db095-106">Value</span></span></p></th>
<th><p><span data-ttu-id="db095-107">说明</span><span class="sxs-lookup"><span data-stu-id="db095-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="db095-108"><strong>为 adSimpleRecord</strong></span><span class="sxs-lookup"><span data-stu-id="db095-108"><strong>adSimpleRecord</strong></span></span></p></td>
<td><p><span data-ttu-id="db095-109">0</span><span class="sxs-lookup"><span data-stu-id="db095-109">0</span></span></p></td>
<td><p><span data-ttu-id="db095-110">指示一个<em>简单</em>记录（不包含子节点）。</span><span class="sxs-lookup"><span data-stu-id="db095-110">Indicates a <em>simple</em> record (does not contain child nodes).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db095-111"><strong>adCollectionRecord</strong></span><span class="sxs-lookup"><span data-stu-id="db095-111"><strong>adCollectionRecord</strong></span></span></p></td>
<td><p><span data-ttu-id="db095-112">1</span><span class="sxs-lookup"><span data-stu-id="db095-112">1</span></span></p></td>
<td><p><span data-ttu-id="db095-113">指示一个<em>集合</em>记录（包含子节点）。</span><span class="sxs-lookup"><span data-stu-id="db095-113">Indicates a <em>collection</em> record (contains child nodes).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db095-114"><strong>adRecordUnknown</strong></span><span class="sxs-lookup"><span data-stu-id="db095-114"><strong>adRecordUnknown</strong></span></span></p></td>
<td><p><span data-ttu-id="db095-115">-1</span><span class="sxs-lookup"><span data-stu-id="db095-115">-1</span></span></p></td>
<td><p><span data-ttu-id="db095-116">指示此 <strong>Record</strong> 的类型未知。</span><span class="sxs-lookup"><span data-stu-id="db095-116">Indicates that the type of this <strong>Record</strong> is unknown.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db095-117"><strong>为 adStructDoc</strong></span><span class="sxs-lookup"><span data-stu-id="db095-117"><strong>adStructDoc</strong></span></span></p></td>
<td><p><span data-ttu-id="db095-118">2</span><span class="sxs-lookup"><span data-stu-id="db095-118">2</span></span></p></td>
<td><p><span data-ttu-id="db095-119">指示代表 COM 结构化文档的特殊种类的<em>集合</em>记录。</span><span class="sxs-lookup"><span data-stu-id="db095-119">Indicates a special kind of <em>collection</em> record that represents COM structured documents.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="db095-120">**ADO/WFC 等效值**</span><span class="sxs-lookup"><span data-stu-id="db095-120">**ADO/WFC Equivalent**</span></span>

<span data-ttu-id="db095-121">这些常量没有 ADO/WFC 等效值。</span><span class="sxs-lookup"><span data-stu-id="db095-121">These constants do not have ADO/WFC equivalents.</span></span>

