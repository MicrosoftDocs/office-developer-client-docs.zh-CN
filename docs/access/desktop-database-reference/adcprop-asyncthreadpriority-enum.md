---
title: ADCPROP_ASYNCTHREADPRIORITY_ENUM
TOCTitle: ADCPROP_ASYNCTHREADPRIORITY_ENUM
ms:assetid: b15006dd-22d5-fcf3-8196-9e24ea9d55a7
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249844(v=office.15)
ms:contentKeyID: 48547143
ms.date: 10/18/2018
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 53e51f2386658ee975ec8847f7e5550ac22bbd8e
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28700275"
---
# <a name="adcpropasyncthreadpriorityenum"></a><span data-ttu-id="adee3-102">ADCPROP\_ASYNCTHREADPRIORITY\_枚举</span><span class="sxs-lookup"><span data-stu-id="adee3-102">ADCPROP\_ASYNCTHREADPRIORITY\_ENUM</span></span>

<span data-ttu-id="adee3-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="adee3-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="adee3-104">对于 RDS [Recordset](recordset-object-ado.md) 对象，指定用于检索数据的异步线程的执行优先级。</span><span class="sxs-lookup"><span data-stu-id="adee3-104">For an RDS [Recordset](recordset-object-ado.md) object, specifies the execution priority of the asynchronous thread that retrieves data.</span></span>

<span data-ttu-id="adee3-105">这些常量适用于 **Recordset** 的“**Background Thread Priority**”动态属性，该动态属性在 ADO 动态属性索引中被引用，并在 [Microsoft Cursor Service for OLE DB](microsoft-cursor-service-for-ole-db-ado-service-component.md) 文档中进行了介绍。</span><span class="sxs-lookup"><span data-stu-id="adee3-105">Use these constants with the **Recordset** "**Background Thread Priority**" dynamic property, which is referenced in the ADO Dynamic Property Index and documented in the [Microsoft Cursor Service for OLE DB](microsoft-cursor-service-for-ole-db-ado-service-component.md) documentation.</span></span>

<br/>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="adee3-106">常量</span><span class="sxs-lookup"><span data-stu-id="adee3-106">Constant</span></span></p></th>
<th><p><span data-ttu-id="adee3-107">值</span><span class="sxs-lookup"><span data-stu-id="adee3-107">Value</span></span></p></th>
<th><p><span data-ttu-id="adee3-108">说明</span><span class="sxs-lookup"><span data-stu-id="adee3-108">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="adee3-109"><strong>adPriorityAboveNormal</strong></span><span class="sxs-lookup"><span data-stu-id="adee3-109"><strong>adPriorityAboveNormal</strong></span></span></p></td>
<td><p><span data-ttu-id="adee3-110">4</span><span class="sxs-lookup"><span data-stu-id="adee3-110">4</span></span></p></td>
<td><p><span data-ttu-id="adee3-111">设置普通和最高之间的优先级。</span><span class="sxs-lookup"><span data-stu-id="adee3-111">Sets priority between normal and highest.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="adee3-112"><strong>adPriorityBelowNormal</strong></span><span class="sxs-lookup"><span data-stu-id="adee3-112"><strong>adPriorityBelowNormal</strong></span></span></p></td>
<td><p><span data-ttu-id="adee3-113">2</span><span class="sxs-lookup"><span data-stu-id="adee3-113">2</span></span></p></td>
<td><p><span data-ttu-id="adee3-114">设置最低和普通之间的优先级。</span><span class="sxs-lookup"><span data-stu-id="adee3-114">Sets priority between lowest and normal.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="adee3-115"><strong>adPriorityHighest</strong></span><span class="sxs-lookup"><span data-stu-id="adee3-115"><strong>adPriorityHighest</strong></span></span></p></td>
<td><p><span data-ttu-id="adee3-116">5</span><span class="sxs-lookup"><span data-stu-id="adee3-116">5</span></span></p></td>
<td><p><span data-ttu-id="adee3-117">设置尽可能高的优先级。</span><span class="sxs-lookup"><span data-stu-id="adee3-117">Sets priority to the highest possible.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="adee3-118"><strong>AdPriorityLowest</strong></span><span class="sxs-lookup"><span data-stu-id="adee3-118"><strong>AdPriorityLowest</strong></span></span></p></td>
<td><p><span data-ttu-id="adee3-119">1</span><span class="sxs-lookup"><span data-stu-id="adee3-119">1</span></span></p></td>
<td><p><span data-ttu-id="adee3-120">设置尽可能低的优先级。</span><span class="sxs-lookup"><span data-stu-id="adee3-120">Sets priority to the lowest possible.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="adee3-121"><strong>adPriorityNormal</strong></span><span class="sxs-lookup"><span data-stu-id="adee3-121"><strong>adPriorityNormal</strong></span></span></p></td>
<td><p><span data-ttu-id="adee3-122">3</span><span class="sxs-lookup"><span data-stu-id="adee3-122">3</span></span></p></td>
<td><p><span data-ttu-id="adee3-123">将优先级设置为普通。</span><span class="sxs-lookup"><span data-stu-id="adee3-123">Sets priority to normal.</span></span></p></td>
</tr>
</tbody>
</table>

### <a name="adowfc-equivalent"></a><span data-ttu-id="adee3-124">ADO/WFC 等效值</span><span class="sxs-lookup"><span data-stu-id="adee3-124">ADO/WFC equivalent</span></span>

<span data-ttu-id="adee3-125">包： **com.ms.wfc.data**</span><span class="sxs-lookup"><span data-stu-id="adee3-125">Package: **com.ms.wfc.data**</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="adee3-126">常量</span><span class="sxs-lookup"><span data-stu-id="adee3-126">Constant</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="adee3-127">AdoEnums.AdcPropAsyncThreadPriority.ABOVENORMAL</span><span class="sxs-lookup"><span data-stu-id="adee3-127">AdoEnums.AdcPropAsyncThreadPriority.ABOVENORMAL</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="adee3-128">AdoEnums.AdcPropAsyncThreadPriority.BELOWNORMAL</span><span class="sxs-lookup"><span data-stu-id="adee3-128">AdoEnums.AdcPropAsyncThreadPriority.BELOWNORMAL</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="adee3-129">AdoEnums.AdcPropAsyncThreadPriority.HIGHEST</span><span class="sxs-lookup"><span data-stu-id="adee3-129">AdoEnums.AdcPropAsyncThreadPriority.HIGHEST</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="adee3-130">AdoEnums.AdcPropAsyncThreadPriority.LOWEST</span><span class="sxs-lookup"><span data-stu-id="adee3-130">AdoEnums.AdcPropAsyncThreadPriority.LOWEST</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="adee3-131">AdoEnums.AdcPropAsyncThreadPriority.NORMAL</span><span class="sxs-lookup"><span data-stu-id="adee3-131">AdoEnums.AdcPropAsyncThreadPriority.NORMAL</span></span></p></td>
</tr>
</tbody>
</table>

