---
title: PropertyAttributesEnum
TOCTitle: PropertyAttributesEnum
ms:assetid: cbe93f65-a3ee-4741-1ac7-1c98ac53cdde
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250012(v=office.15)
ms:contentKeyID: 48547726
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 19a5f34734f98b84e9a232dd06bd4f35f016a58f
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25877504"
---
# <a name="propertyattributesenum"></a><span data-ttu-id="0215a-102">PropertyAttributesEnum</span><span class="sxs-lookup"><span data-stu-id="0215a-102">PropertyAttributesEnum</span></span>


<span data-ttu-id="0215a-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="0215a-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="0215a-104">指定 [Property](property-object-ado.md) 对象的属性。</span><span class="sxs-lookup"><span data-stu-id="0215a-104">Specifies the attributes of a [Property](property-object-ado.md) object.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="0215a-105">常量</span><span class="sxs-lookup"><span data-stu-id="0215a-105">Constant</span></span></p></th>
<th><p><span data-ttu-id="0215a-106">值</span><span class="sxs-lookup"><span data-stu-id="0215a-106">Value</span></span></p></th>
<th><p><span data-ttu-id="0215a-107">说明</span><span class="sxs-lookup"><span data-stu-id="0215a-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0215a-108"><strong>adPropNotSupported</strong></span><span class="sxs-lookup"><span data-stu-id="0215a-108"><strong>adPropNotSupported</strong></span></span></p></td>
<td><p><span data-ttu-id="0215a-109">0</span><span class="sxs-lookup"><span data-stu-id="0215a-109">0</span></span></p></td>
<td><p><span data-ttu-id="0215a-110">指示提供程序不支持该属性。</span><span class="sxs-lookup"><span data-stu-id="0215a-110">Indicates that the property is not supported by the provider.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0215a-111"><strong>adPropRequired</strong></span><span class="sxs-lookup"><span data-stu-id="0215a-111"><strong>adPropRequired</strong></span></span></p></td>
<td><p><span data-ttu-id="0215a-112">1</span><span class="sxs-lookup"><span data-stu-id="0215a-112">1</span></span></p></td>
<td><p><span data-ttu-id="0215a-113">指示在初始化数据源之前，用户必须为该属性指定值。</span><span class="sxs-lookup"><span data-stu-id="0215a-113">Indicates that the user must specify a value for this property before the data source is initialized.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0215a-114"><strong>adPropOptional</strong></span><span class="sxs-lookup"><span data-stu-id="0215a-114"><strong>adPropOptional</strong></span></span></p></td>
<td><p><span data-ttu-id="0215a-115">2</span><span class="sxs-lookup"><span data-stu-id="0215a-115">2</span></span></p></td>
<td><p><span data-ttu-id="0215a-116">指示在初始化数据源之前，用户不必为该属性指定值。</span><span class="sxs-lookup"><span data-stu-id="0215a-116">Indicates that the user does not need to specify a value for this property before the data source is initialized.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0215a-117"><strong>adPropRead</strong></span><span class="sxs-lookup"><span data-stu-id="0215a-117"><strong>adPropRead</strong></span></span></p></td>
<td><p><span data-ttu-id="0215a-118">512</span><span class="sxs-lookup"><span data-stu-id="0215a-118">512</span></span></p></td>
<td><p><span data-ttu-id="0215a-119">指示用户可以读取此属性。</span><span class="sxs-lookup"><span data-stu-id="0215a-119">Indicates that the user can read the property.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0215a-120"><strong>adPropWrite</strong></span><span class="sxs-lookup"><span data-stu-id="0215a-120"><strong>adPropWrite</strong></span></span></p></td>
<td><p><span data-ttu-id="0215a-121">1024</span><span class="sxs-lookup"><span data-stu-id="0215a-121">1024</span></span></p></td>
<td><p><span data-ttu-id="0215a-122">指示用户可以设置此属性。</span><span class="sxs-lookup"><span data-stu-id="0215a-122">Indicates that the user can set the property.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="adowfc-equivalent"></a><span data-ttu-id="0215a-123">ADO/WFC 等效值</span><span class="sxs-lookup"><span data-stu-id="0215a-123">ADO/WFC equivalent</span></span>

<span data-ttu-id="0215a-124">包： **com.ms.wfc.data**</span><span class="sxs-lookup"><span data-stu-id="0215a-124">Package: **com.ms.wfc.data**</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="0215a-125">常量</span><span class="sxs-lookup"><span data-stu-id="0215a-125">Constant</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0215a-126">AdoEnums.PropertyAttributes.NOTSUPPORTED</span><span class="sxs-lookup"><span data-stu-id="0215a-126">AdoEnums.PropertyAttributes.NOTSUPPORTED</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0215a-127">AdoEnums.PropertyAttributes.REQUIRED</span><span class="sxs-lookup"><span data-stu-id="0215a-127">AdoEnums.PropertyAttributes.REQUIRED</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0215a-128">AdoEnums.PropertyAttributes.OPTIONAL</span><span class="sxs-lookup"><span data-stu-id="0215a-128">AdoEnums.PropertyAttributes.OPTIONAL</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0215a-129">AdoEnums.PropertyAttributes.READ</span><span class="sxs-lookup"><span data-stu-id="0215a-129">AdoEnums.PropertyAttributes.READ</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0215a-130">AdoEnums.PropertyAttributes.WRITE</span><span class="sxs-lookup"><span data-stu-id="0215a-130">AdoEnums.PropertyAttributes.WRITE</span></span></p></td>
</tr>
</tbody>
</table>

