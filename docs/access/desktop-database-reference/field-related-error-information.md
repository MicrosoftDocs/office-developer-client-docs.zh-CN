---
title: 与字段相关的错误信息
TOCTitle: Field-related error information
ms:assetid: 81a2c5a4-ab09-53d8-b270-e889b00a0c1a
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249559(v=office.15)
ms:contentKeyID: 48545958
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 3a0d0362b8f0ff9570a92a3c1c364061d1f9a584
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28710550"
---
# <a name="field-related-error-information"></a><span data-ttu-id="f43c3-102">与字段相关的错误信息</span><span class="sxs-lookup"><span data-stu-id="f43c3-102">Field-related error information</span></span>


<span data-ttu-id="f43c3-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="f43c3-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="f43c3-p101">如果错误与字段直接相关（例如，如果缺少数据或者对于该字段它是错误的类型），则可以通过检查 **Field** 对象的 **Status** 属性来检索有关问题原因的详细信息。此属性已得到增强，以提供有关问题的具体信息。因此，例如，在调用 **UpdateBatch** 失败时，可以通过检查每个受影响记录的 **Fields** 的 **Status** 属性来确定问题的原因。该属性将包含 **FieldStatusEnum** 常量中的一个值。下表包括在发生错误时需要特别注意的那些值。</span><span class="sxs-lookup"><span data-stu-id="f43c3-p101">If an error is directly related to a field — for example, if the data is missing or if it is the wrong type for the field — you can retrieve more information about the cause of the problem by examining the **Field** object's **Status** property. This property has been enhanced to provide specific information about the problem. So, for example, when a call to **UpdateBatch** fails, the cause of the problem can be determined by examining the **Status** property of the **Fields** in each of the effected records. The property will contain one of the values in the **FieldStatusEnum** constant. The following table includes those values that are of particular interest when an error occurs.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="f43c3-109">常量</span><span class="sxs-lookup"><span data-stu-id="f43c3-109">Constant</span></span></p></th>
<th><p><span data-ttu-id="f43c3-110">值</span><span class="sxs-lookup"><span data-stu-id="f43c3-110">Value</span></span></p></th>
<th><p><span data-ttu-id="f43c3-111">说明</span><span class="sxs-lookup"><span data-stu-id="f43c3-111">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f43c3-112"><strong>adFieldCantConvertValue</strong></span><span class="sxs-lookup"><span data-stu-id="f43c3-112"><strong>adFieldCantConvertValue</strong></span></span></p></td>
<td><p><span data-ttu-id="f43c3-113">2</span><span class="sxs-lookup"><span data-stu-id="f43c3-113">2</span></span></p></td>
<td><p><span data-ttu-id="f43c3-114">指示由于丢失数据而无法检索或存储字段。</span><span class="sxs-lookup"><span data-stu-id="f43c3-114">Indicates that the field cannot be retrieved or stored without loss of data.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f43c3-115"><strong>adFieldDataOverflow</strong></span><span class="sxs-lookup"><span data-stu-id="f43c3-115"><strong>adFieldDataOverflow</strong></span></span></p></td>
<td><p><span data-ttu-id="f43c3-116">6</span><span class="sxs-lookup"><span data-stu-id="f43c3-116">6</span></span></p></td>
<td><p><span data-ttu-id="f43c3-117">指示从提供程序返回的数据使字段的数据类型发生溢出。</span><span class="sxs-lookup"><span data-stu-id="f43c3-117">Indicates that the data returned from the provider overflowed the data type of the field.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f43c3-118"><strong>adFieldDefault</strong></span><span class="sxs-lookup"><span data-stu-id="f43c3-118"><strong>adFieldDefault</strong></span></span></p></td>
<td><p><span data-ttu-id="f43c3-119">13</span><span class="sxs-lookup"><span data-stu-id="f43c3-119">13</span></span></p></td>
<td><p><span data-ttu-id="f43c3-120">指示在设置数据时使用字段的默认值。</span><span class="sxs-lookup"><span data-stu-id="f43c3-120">Indicates that the default value for the field was used when setting data.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f43c3-121"><strong>adFieldIgnore</strong></span><span class="sxs-lookup"><span data-stu-id="f43c3-121"><strong>adFieldIgnore</strong></span></span></p></td>
<td><p><span data-ttu-id="f43c3-122">15</span><span class="sxs-lookup"><span data-stu-id="f43c3-122">15</span></span></p></td>
<td><p><span data-ttu-id="f43c3-p102">指示在设置数据源中的数据值时已跳过此字段。提供程序未设置值。</span><span class="sxs-lookup"><span data-stu-id="f43c3-p102">Indicates that this field was skipped when setting data values in the source. No value was set by the provider.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f43c3-125"><strong>adFieldIntegrityViolation</strong></span><span class="sxs-lookup"><span data-stu-id="f43c3-125"><strong>adFieldIntegrityViolation</strong></span></span></p></td>
<td><p><span data-ttu-id="f43c3-126">10</span><span class="sxs-lookup"><span data-stu-id="f43c3-126">10</span></span></p></td>
<td><p><span data-ttu-id="f43c3-127">指示无法修改字段，因为它是计算得出的实体或派生实体。</span><span class="sxs-lookup"><span data-stu-id="f43c3-127">Indicates that the field cannot be modified because it is a calculated or derived entity.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f43c3-128"><strong>adFieldIsNull</strong></span><span class="sxs-lookup"><span data-stu-id="f43c3-128"><strong>adFieldIsNull</strong></span></span></p></td>
<td><p><span data-ttu-id="f43c3-129">3</span><span class="sxs-lookup"><span data-stu-id="f43c3-129">3</span></span></p></td>
<td><p><span data-ttu-id="f43c3-130">指示提供程序返回了 Null 值。</span><span class="sxs-lookup"><span data-stu-id="f43c3-130">Indicates that the provider returned a null value.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f43c3-131"><strong>adFieldOutOfSpace</strong></span><span class="sxs-lookup"><span data-stu-id="f43c3-131"><strong>adFieldOutOfSpace</strong></span></span></p></td>
<td><p><span data-ttu-id="f43c3-132">22</span><span class="sxs-lookup"><span data-stu-id="f43c3-132">22</span></span></p></td>
<td><p><span data-ttu-id="f43c3-133">指示提供程序无法获取足够的存储空间来完成移动或复制操作。</span><span class="sxs-lookup"><span data-stu-id="f43c3-133">Indicates that the provider is unable to obtain enough storage space to complete a move or copy operation.</span></span></p></td>
</tr>
</tbody>
</table>

