---
title: PropertyAttributesEnum
TOCTitle: PropertyAttributesEnum
ms:assetid: cbe93f65-a3ee-4741-1ac7-1c98ac53cdde
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250012(v=office.15)
ms:contentKeyID: 48547726
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: c929bcf5dc7f5267c2e7d3a8dac5ed6bfb55b20b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32302875"
---
# <a name="propertyattributesenum"></a><span data-ttu-id="678b3-102">PropertyAttributesEnum</span><span class="sxs-lookup"><span data-stu-id="678b3-102">PropertyAttributesEnum</span></span>


<span data-ttu-id="678b3-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="678b3-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="678b3-104">指定 [Property](property-object-ado.md) 对象的属性。</span><span class="sxs-lookup"><span data-stu-id="678b3-104">Specifies the attributes of a [Property](property-object-ado.md) object.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="678b3-105">常量</span><span class="sxs-lookup"><span data-stu-id="678b3-105">Constant</span></span></p></th>
<th><p><span data-ttu-id="678b3-106">值</span><span class="sxs-lookup"><span data-stu-id="678b3-106">Value</span></span></p></th>
<th><p><span data-ttu-id="678b3-107">说明</span><span class="sxs-lookup"><span data-stu-id="678b3-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="678b3-108"><strong>adPropNotSupported</strong></span><span class="sxs-lookup"><span data-stu-id="678b3-108"><strong>adPropNotSupported</strong></span></span></p></td>
<td><p><span data-ttu-id="678b3-109">0</span><span class="sxs-lookup"><span data-stu-id="678b3-109">0</span></span></p></td>
<td><p><span data-ttu-id="678b3-110">指示提供程序不支持该属性。</span><span class="sxs-lookup"><span data-stu-id="678b3-110">Indicates that the property is not supported by the provider.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="678b3-111"><strong>adPropRequired</strong></span><span class="sxs-lookup"><span data-stu-id="678b3-111"><strong>adPropRequired</strong></span></span></p></td>
<td><p><span data-ttu-id="678b3-112">1</span><span class="sxs-lookup"><span data-stu-id="678b3-112">1</span></span></p></td>
<td><p><span data-ttu-id="678b3-113">指示在初始化数据源之前，用户必须为该属性指定值。</span><span class="sxs-lookup"><span data-stu-id="678b3-113">Indicates that the user must specify a value for this property before the data source is initialized.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="678b3-114"><strong>adPropOptional</strong></span><span class="sxs-lookup"><span data-stu-id="678b3-114"><strong>adPropOptional</strong></span></span></p></td>
<td><p><span data-ttu-id="678b3-115">双面</span><span class="sxs-lookup"><span data-stu-id="678b3-115">2</span></span></p></td>
<td><p><span data-ttu-id="678b3-116">指示在初始化数据源之前，用户不必为该属性指定值。</span><span class="sxs-lookup"><span data-stu-id="678b3-116">Indicates that the user does not need to specify a value for this property before the data source is initialized.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="678b3-117"><strong>adPropRead</strong></span><span class="sxs-lookup"><span data-stu-id="678b3-117"><strong>adPropRead</strong></span></span></p></td>
<td><p><span data-ttu-id="678b3-118">512</span><span class="sxs-lookup"><span data-stu-id="678b3-118">512</span></span></p></td>
<td><p><span data-ttu-id="678b3-119">指示用户可以读取此属性。</span><span class="sxs-lookup"><span data-stu-id="678b3-119">Indicates that the user can read the property.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="678b3-120"><strong>adPropWrite</strong></span><span class="sxs-lookup"><span data-stu-id="678b3-120"><strong>adPropWrite</strong></span></span></p></td>
<td><p><span data-ttu-id="678b3-121">1024</span><span class="sxs-lookup"><span data-stu-id="678b3-121">1024</span></span></p></td>
<td><p><span data-ttu-id="678b3-122">指示用户可以设置此属性。</span><span class="sxs-lookup"><span data-stu-id="678b3-122">Indicates that the user can set the property.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="adowfc-equivalent"></a><span data-ttu-id="678b3-123">ADO/WFC 等效项</span><span class="sxs-lookup"><span data-stu-id="678b3-123">ADO/WFC equivalent</span></span>

<span data-ttu-id="678b3-124">包：**com.ms.wfc.data**</span><span class="sxs-lookup"><span data-stu-id="678b3-124">Package: **com.ms.wfc.data**</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="678b3-125">常量</span><span class="sxs-lookup"><span data-stu-id="678b3-125">Constant</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="678b3-126">AdoEnums PropertyAttributes</span><span class="sxs-lookup"><span data-stu-id="678b3-126">AdoEnums.PropertyAttributes.NOTSUPPORTED</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="678b3-127">AdoEnums 的必需 PropertyAttributes</span><span class="sxs-lookup"><span data-stu-id="678b3-127">AdoEnums.PropertyAttributes.REQUIRED</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="678b3-128">PropertyAttributes。可选 AdoEnums</span><span class="sxs-lookup"><span data-stu-id="678b3-128">AdoEnums.PropertyAttributes.OPTIONAL</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="678b3-129">AdoEnums。请参阅 PropertyAttributes</span><span class="sxs-lookup"><span data-stu-id="678b3-129">AdoEnums.PropertyAttributes.READ</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="678b3-130">AdoEnums PropertyAttributes</span><span class="sxs-lookup"><span data-stu-id="678b3-130">AdoEnums.PropertyAttributes.WRITE</span></span></p></td>
</tr>
</tbody>
</table>

