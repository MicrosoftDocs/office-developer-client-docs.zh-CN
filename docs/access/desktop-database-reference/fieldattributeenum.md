---
title: FieldAttributeEnum (Access desktop database reference)
TOCTitle: FieldAttributeEnum
ms:assetid: 2d3a541e-a437-6108-ab0e-90c7884b3df7
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249071(v=office.15)
ms:contentKeyID: 48543967
ms.date: 10/18/2018
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 079c79af3d15a6a5864a7db7f8334393258cfd42
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32292599"
---
# <a name="fieldattributeenum"></a><span data-ttu-id="94c4c-102">FieldAttributeEnum</span><span class="sxs-lookup"><span data-stu-id="94c4c-102">FieldAttributeEnum</span></span>

<span data-ttu-id="94c4c-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="94c4c-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="94c4c-104">指定 [Field](field-object-ado.md) 对象的一个或多个属性。</span><span class="sxs-lookup"><span data-stu-id="94c4c-104">Specifies one or more attributes of a [Field](field-object-ado.md) object.</span></span>

<br/>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="94c4c-105">常量</span><span class="sxs-lookup"><span data-stu-id="94c4c-105">Constant</span></span></p></th>
<th><p><span data-ttu-id="94c4c-106">值</span><span class="sxs-lookup"><span data-stu-id="94c4c-106">Value</span></span></p></th>
<th><p><span data-ttu-id="94c4c-107">说明</span><span class="sxs-lookup"><span data-stu-id="94c4c-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="94c4c-108"><strong>adFldCacheDeferred</strong></span><span class="sxs-lookup"><span data-stu-id="94c4c-108"><strong>adFldCacheDeferred</strong></span></span></p></td>
<td><p><span data-ttu-id="94c4c-109">0x1000</span><span class="sxs-lookup"><span data-stu-id="94c4c-109">0x1000</span></span></p></td>
<td><p><span data-ttu-id="94c4c-110">指示提供程序缓存字段值，且随后的读取从缓存中完成。</span><span class="sxs-lookup"><span data-stu-id="94c4c-110">Indicates that the provider caches field values and that subsequent reads are done from the cache.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="94c4c-111"><strong>adFldFixed</strong></span><span class="sxs-lookup"><span data-stu-id="94c4c-111"><strong>adFldFixed</strong></span></span></p></td>
<td><p><span data-ttu-id="94c4c-112">0x10</span><span class="sxs-lookup"><span data-stu-id="94c4c-112">0x10</span></span></p></td>
<td><p><span data-ttu-id="94c4c-113">指示字段包含固定长度的数据。</span><span class="sxs-lookup"><span data-stu-id="94c4c-113">Indicates that the field contains fixed-length data.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="94c4c-114"><strong>adFldIsChapter</strong></span><span class="sxs-lookup"><span data-stu-id="94c4c-114"><strong>adFldIsChapter</strong></span></span></p></td>
<td><p><span data-ttu-id="94c4c-115">0x2000</span><span class="sxs-lookup"><span data-stu-id="94c4c-115">0x2000</span></span></p></td>
<td><p><span data-ttu-id="94c4c-p101">指示字段包含章节值，此值指定与该父字段相关的特定子记录集。通常，章节字段用于数据定形或筛选器。</span><span class="sxs-lookup"><span data-stu-id="94c4c-p101">Indicates that the field contains a chapter value, which specifies a specific child recordset related to this parent field. Typically chapter fields are used with data shaping or filters.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="94c4c-118"><strong>adFldIsCollection</strong></span><span class="sxs-lookup"><span data-stu-id="94c4c-118"><strong>adFldIsCollection</strong></span></span></p></td>
<td><p><span data-ttu-id="94c4c-119">0x40000</span><span class="sxs-lookup"><span data-stu-id="94c4c-119">0x40000</span></span></p></td>
<td><p><span data-ttu-id="94c4c-120">指示字段指定由记录表示的资源是其他资源的集合（如文件夹），而不是一个简单资源（如文本文件）。</span><span class="sxs-lookup"><span data-stu-id="94c4c-120">Indicates that the field specifies that the resource represented by the record is a collection of other resources, such as a folder, rather than a simple resource, such as a text file.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="94c4c-121"><strong>adFldIsDefaultStream</strong></span><span class="sxs-lookup"><span data-stu-id="94c4c-121"><strong>adFldIsDefaultStream</strong></span></span></p></td>
<td><p><span data-ttu-id="94c4c-122">0x20000</span><span class="sxs-lookup"><span data-stu-id="94c4c-122">0x20000</span></span></p></td>
<td><p><span data-ttu-id="94c4c-123">指示字段包含由记录表示的资源的默认流。</span><span class="sxs-lookup"><span data-stu-id="94c4c-123">Indicates that the field contains the default stream for the resource represented by the record.</span></span> <span data-ttu-id="94c4c-124">例如, 默认流可以是网站上的根文件夹的 HTML 内容, 当指定根 URL 时, 将自动提供该内容。</span><span class="sxs-lookup"><span data-stu-id="94c4c-124">For example, the default stream can be the HTML content of a root folder on a website, which is automatically served when the root URL is specified.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="94c4c-125"><strong>adFldIsNullable</strong></span><span class="sxs-lookup"><span data-stu-id="94c4c-125"><strong>adFldIsNullable</strong></span></span></p></td>
<td><p><span data-ttu-id="94c4c-126">0x20</span><span class="sxs-lookup"><span data-stu-id="94c4c-126">0x20</span></span></p></td>
<td><p><span data-ttu-id="94c4c-127">指示字段接受空值。</span><span class="sxs-lookup"><span data-stu-id="94c4c-127">Indicates that the field accepts null values.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="94c4c-128"><strong>adFldIsRowURL</strong></span><span class="sxs-lookup"><span data-stu-id="94c4c-128"><strong>adFldIsRowURL</strong></span></span></p></td>
<td><p><span data-ttu-id="94c4c-129">0x10000</span><span class="sxs-lookup"><span data-stu-id="94c4c-129">0x10000</span></span></p></td>
<td><p><span data-ttu-id="94c4c-130">指示字段包含通过由记录表示的数据源来命名资源的 URL。</span><span class="sxs-lookup"><span data-stu-id="94c4c-130">Indicates that the field contains the URL that names the resource from the data store represented by the record.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="94c4c-131"><strong>adFldLong</strong></span><span class="sxs-lookup"><span data-stu-id="94c4c-131"><strong>adFldLong</strong></span></span></p></td>
<td><p><span data-ttu-id="94c4c-132">0x80</span><span class="sxs-lookup"><span data-stu-id="94c4c-132">0x80</span></span></p></td>
<td><p><span data-ttu-id="94c4c-p103">指示字段是长二进制字段。还指示您可以使用 <a href="appendchunk-method-ado.md">AppendChunk</a> 和 <a href="getchunk-method-ado.md">GetChunk</a> 方法。</span><span class="sxs-lookup"><span data-stu-id="94c4c-p103">Indicates that the field is a long binary field. Also indicates that you can use the <a href="appendchunk-method-ado.md">AppendChunk</a> and <a href="getchunk-method-ado.md">GetChunk</a> methods.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="94c4c-135"><strong>adFldMayBeNull</strong></span><span class="sxs-lookup"><span data-stu-id="94c4c-135"><strong>adFldMayBeNull</strong></span></span></p></td>
<td><p><span data-ttu-id="94c4c-136">0x40</span><span class="sxs-lookup"><span data-stu-id="94c4c-136">0x40</span></span></p></td>
<td><p><span data-ttu-id="94c4c-137">指示您可以从字段中读取空值。</span><span class="sxs-lookup"><span data-stu-id="94c4c-137">Indicates that you can read null values from the field.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="94c4c-138"><strong>adFldMayDefer</strong></span><span class="sxs-lookup"><span data-stu-id="94c4c-138"><strong>adFldMayDefer</strong></span></span></p></td>
<td><p><span data-ttu-id="94c4c-139">0x2</span><span class="sxs-lookup"><span data-stu-id="94c4c-139">0x2</span></span></p></td>
<td><p><span data-ttu-id="94c4c-140">指示字段是延迟的，即，字段值不是从具有整个记录的数据源检索的，而只是在您显式访问它们时检索的。</span><span class="sxs-lookup"><span data-stu-id="94c4c-140">Indicates that the field is deferred — that is, the field values are not retrieved from the data source with the whole record, but only when you explicitly access them.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="94c4c-141"><strong>adFldNegativeScale</strong></span><span class="sxs-lookup"><span data-stu-id="94c4c-141"><strong>adFldNegativeScale</strong></span></span></p></td>
<td><p><span data-ttu-id="94c4c-142">0x4000</span><span class="sxs-lookup"><span data-stu-id="94c4c-142">0x4000</span></span></p></td>
<td><p><span data-ttu-id="94c4c-p104">指示字段代表来自支持负小数值的列中的数值。小数由 <a href="numericscale-property-ado.md">NumericScale</a> 属性指定。</span><span class="sxs-lookup"><span data-stu-id="94c4c-p104">Indicates that the field represents a numeric value from a column that supports negative scale values. The scale is specified by the <a href="numericscale-property-ado.md">NumericScale</a> property.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="94c4c-145"><strong>adFldRowID</strong></span><span class="sxs-lookup"><span data-stu-id="94c4c-145"><strong>adFldRowID</strong></span></span></p></td>
<td><p><span data-ttu-id="94c4c-146">0x100</span><span class="sxs-lookup"><span data-stu-id="94c4c-146">0x100</span></span></p></td>
<td><p><span data-ttu-id="94c4c-147">指示字段包含无法写入的持久行标识符，并且除了用于标识行的值（如记录号、唯一标识符等）以外，字段的其他值没有意义。</span><span class="sxs-lookup"><span data-stu-id="94c4c-147">Indicates that the field contains a persistent row identifier that cannot be written to and has no meaningful value except to identify the row (such as a record number, unique identifier, and so forth).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="94c4c-148"><strong>adFldRowVersion</strong></span><span class="sxs-lookup"><span data-stu-id="94c4c-148"><strong>adFldRowVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="94c4c-149">0x200</span><span class="sxs-lookup"><span data-stu-id="94c4c-149">0x200</span></span></p></td>
<td><p><span data-ttu-id="94c4c-150">指示字段包含用于跟踪更新的某些种类的时间戳或日期戳。</span><span class="sxs-lookup"><span data-stu-id="94c4c-150">Indicates that the field contains some kind of time or date stamp used to track updates.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="94c4c-151"><strong>adFldUnknownUpdatable</strong></span><span class="sxs-lookup"><span data-stu-id="94c4c-151"><strong>adFldUnknownUpdatable</strong></span></span></p></td>
<td><p><span data-ttu-id="94c4c-152">0x8</span><span class="sxs-lookup"><span data-stu-id="94c4c-152">0x8</span></span></p></td>
<td><p><span data-ttu-id="94c4c-153">指示提供程序无法确定您是否可以向字段中写入内容。</span><span class="sxs-lookup"><span data-stu-id="94c4c-153">Indicates that the provider cannot determine if you can write to the field.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="94c4c-154"><strong>adFldUnspecified</strong></span><span class="sxs-lookup"><span data-stu-id="94c4c-154"><strong>adFldUnspecified</strong></span></span></p></td>
<td><p><span data-ttu-id="94c4c-155">-1</span><span class="sxs-lookup"><span data-stu-id="94c4c-155">-1</span></span><br />
<span data-ttu-id="94c4c-156">0xFFFFFFFF</span><span class="sxs-lookup"><span data-stu-id="94c4c-156">0xFFFFFFFF</span></span></p></td>
<td><p><span data-ttu-id="94c4c-157">指示提供程序不指定字段属性。</span><span class="sxs-lookup"><span data-stu-id="94c4c-157">Indicates that the provider does not specify the field attributes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="94c4c-158"><strong>adFldUpdatable</strong></span><span class="sxs-lookup"><span data-stu-id="94c4c-158"><strong>adFldUpdatable</strong></span></span></p></td>
<td><p><span data-ttu-id="94c4c-159">0x4</span><span class="sxs-lookup"><span data-stu-id="94c4c-159">0x4</span></span></p></td>
<td><p><span data-ttu-id="94c4c-160">指示您可以写入字段。</span><span class="sxs-lookup"><span data-stu-id="94c4c-160">Indicates that you can write to the field.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="adowfc-equivalent"></a><span data-ttu-id="94c4c-161">ADO/WFC 等效项</span><span class="sxs-lookup"><span data-stu-id="94c4c-161">ADO/WFC equivalent</span></span>

<span data-ttu-id="94c4c-162">包：**com.ms.wfc.data**</span><span class="sxs-lookup"><span data-stu-id="94c4c-162">Package: **com.ms.wfc.data**</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="94c4c-163">常量</span><span class="sxs-lookup"><span data-stu-id="94c4c-163">Constant</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="94c4c-164">AdoEnums FieldAttribute</span><span class="sxs-lookup"><span data-stu-id="94c4c-164">AdoEnums.FieldAttribute.CACHEDEFERRED</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="94c4c-165">AdoEnums FieldAttribute</span><span class="sxs-lookup"><span data-stu-id="94c4c-165">AdoEnums.FieldAttribute.FIXED</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="94c4c-166">AdoEnums FieldAttribute</span><span class="sxs-lookup"><span data-stu-id="94c4c-166">AdoEnums.FieldAttribute.ISNULLABLE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="94c4c-167">AdoEnums (长 FieldAttribute)</span><span class="sxs-lookup"><span data-stu-id="94c4c-167">AdoEnums.FieldAttribute.LONG</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="94c4c-168">AdoEnums FieldAttribute</span><span class="sxs-lookup"><span data-stu-id="94c4c-168">AdoEnums.FieldAttribute.MAYBENULL</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="94c4c-169">AdoEnums FieldAttribute</span><span class="sxs-lookup"><span data-stu-id="94c4c-169">AdoEnums.FieldAttribute.MAYDEFER</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="94c4c-170">AdoEnums FieldAttribute</span><span class="sxs-lookup"><span data-stu-id="94c4c-170">AdoEnums.FieldAttribute.NEGATIVESCALE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="94c4c-171">AdoEnums</span><span class="sxs-lookup"><span data-stu-id="94c4c-171">AdoEnums.FieldAttribute.ROWID</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="94c4c-172">AdoEnums FieldAttribute</span><span class="sxs-lookup"><span data-stu-id="94c4c-172">AdoEnums.FieldAttribute.ROWVERSION</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="94c4c-173">AdoEnums FieldAttribute</span><span class="sxs-lookup"><span data-stu-id="94c4c-173">AdoEnums.FieldAttribute.UNKNOWNUPDATABLE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="94c4c-174">AdoEnums 不指定 FieldAttribute</span><span class="sxs-lookup"><span data-stu-id="94c4c-174">AdoEnums.FieldAttribute.UNSPECIFIED</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="94c4c-175">AdoEnums 可更新 FieldAttribute</span><span class="sxs-lookup"><span data-stu-id="94c4c-175">AdoEnums.FieldAttribute.UPDATABLE</span></span></p></td>
</tr>
</tbody>
</table>

