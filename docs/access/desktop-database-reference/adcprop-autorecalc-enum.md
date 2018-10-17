---
title: ADCPROP_AUTORECALC_ENUM
TOCTitle: ADCPROP_AUTORECALC_ENUM
ms:assetid: 79ed16c1-964d-bf88-22c9-aa0a51303da6
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249502(v=office.15)
ms:contentKeyID: 48545779
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: fc02e8cde556a70ca6b2c72f056d218904c31ec2
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468564"
---
# <a name="adcpropautorecalcenum"></a><span data-ttu-id="33952-102">ADCPROP\_AUTORECALC\_枚举</span><span class="sxs-lookup"><span data-stu-id="33952-102">ADCPROP\_AUTORECALC\_ENUM</span></span>

<span data-ttu-id="33952-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="33952-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="33952-104">指定 [MSDataShape](microsoft-data-shaping-service-for-ole-db-ado-service-provider.md) 提供程序何时重新计算分层记录集中的聚合和计算列。</span><span class="sxs-lookup"><span data-stu-id="33952-104">Specifies when the [MSDataShape](microsoft-data-shaping-service-for-ole-db-ado-service-provider.md) provider re-calculates aggregate and calculated columns in a hierarchical Recordset.</span></span>

<span data-ttu-id="33952-105">这些常量仅用于**MSDataShape**提供程序和**Recordset** "**Auto Recalc**"动态属性，该进行引用[ADO 动态属性索引](ado-dynamic-property-index.md)中并记录在[Microsoft Cursor Service for OLEDB](microsoft-cursor-service-for-ole-db-ado-service-component.md)或[Microsoft Data Shaping Service for OLE DB](microsoft-data-shaping-service-for-ole-db-ado-service-provider.md)文档。</span><span class="sxs-lookup"><span data-stu-id="33952-105">These constants are only used with the **MSDataShape** provider and the **Recordset** "**Auto Recalc**" dynamic property, which is referenced in the [ADO Dynamic Property Index](ado-dynamic-property-index.md) and documented in the [Microsoft Cursor Service for OLE DB](microsoft-cursor-service-for-ole-db-ado-service-component.md) or [Microsoft Data Shaping Service for OLE DB](microsoft-data-shaping-service-for-ole-db-ado-service-provider.md) documentation.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="33952-106">常量</span><span class="sxs-lookup"><span data-stu-id="33952-106">Constant</span></span></p></th>
<th><p><span data-ttu-id="33952-107">值</span><span class="sxs-lookup"><span data-stu-id="33952-107">Value</span></span></p></th>
<th><p><span data-ttu-id="33952-108">说明</span><span class="sxs-lookup"><span data-stu-id="33952-108">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="33952-109"><strong>adRecalcAlways</strong></span><span class="sxs-lookup"><span data-stu-id="33952-109"><strong>adRecalcAlways</strong></span></span></p></td>
<td><p><span data-ttu-id="33952-110">1</span><span class="sxs-lookup"><span data-stu-id="33952-110">1</span></span></p></td>
<td><p><span data-ttu-id="33952-p101">默认值。每当 <strong>MSDataShape</strong> 提供程序确定计算列所依赖的值已发生更改时，都会重新计算该值。</span><span class="sxs-lookup"><span data-stu-id="33952-p101">Default. Recalculates whenever the <strong>MSDataShape</strong> provider determines values that the calculated columns depend upon have changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33952-113"><strong>adRecalcUpFront</strong></span><span class="sxs-lookup"><span data-stu-id="33952-113"><strong>adRecalcUpFront</strong></span></span></p></td>
<td><p><span data-ttu-id="33952-114">0</span><span class="sxs-lookup"><span data-stu-id="33952-114">0</span></span></p></td>
<td><p><span data-ttu-id="33952-115">只在最初构建分层 <strong>Recordset</strong> 时计算。</span><span class="sxs-lookup"><span data-stu-id="33952-115">Calculates only when initially building the hierarchical <strong>Recordset</strong>.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="33952-116">**ADO/WFC 等效值**</span><span class="sxs-lookup"><span data-stu-id="33952-116">**ADO/WFC Equivalent**</span></span>

<span data-ttu-id="33952-117">这些常量没有 ADO/WFC 等效值。</span><span class="sxs-lookup"><span data-stu-id="33952-117">These constants do not have ADO/WFC equivalents.</span></span>
