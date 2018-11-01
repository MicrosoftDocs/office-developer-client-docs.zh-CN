---
title: EventStatusEnum （访问桌面数据库参考 （英文）
TOCTitle: EventStatusEnum
ms:assetid: ae1711bc-2af5-04fd-7d8c-222d8afc9d3d
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249821(v=office.15)
ms:contentKeyID: 48547059
ms.date: 10/18/2018
mtps_version: v=office.15
ms.openlocfilehash: 027ecde525d603b15bb7844e99edc2534774bb37
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25867613"
---
# <a name="eventstatusenum"></a><span data-ttu-id="47cf2-102">EventStatusEnum</span><span class="sxs-lookup"><span data-stu-id="47cf2-102">EventStatusEnum</span></span>

<span data-ttu-id="47cf2-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="47cf2-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="47cf2-104">指定事件执行的当前状态。</span><span class="sxs-lookup"><span data-stu-id="47cf2-104">Specifies the current status of the execution of an event.</span></span>

<br/>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="47cf2-105">常量</span><span class="sxs-lookup"><span data-stu-id="47cf2-105">Constant</span></span></p></th>
<th><p><span data-ttu-id="47cf2-106">值</span><span class="sxs-lookup"><span data-stu-id="47cf2-106">Value</span></span></p></th>
<th><p><span data-ttu-id="47cf2-107">说明</span><span class="sxs-lookup"><span data-stu-id="47cf2-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="47cf2-108"><strong>adStatusCancel</strong></span><span class="sxs-lookup"><span data-stu-id="47cf2-108"><strong>adStatusCancel</strong></span></span></p></td>
<td><p><span data-ttu-id="47cf2-109">4</span><span class="sxs-lookup"><span data-stu-id="47cf2-109">4</span></span></p></td>
<td><p><span data-ttu-id="47cf2-110">请求取消导致事件发生的操作。</span><span class="sxs-lookup"><span data-stu-id="47cf2-110">Requests cancellation of the operation that caused the event to occur.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47cf2-111"><strong>adStatusCantDeny</strong></span><span class="sxs-lookup"><span data-stu-id="47cf2-111"><strong>adStatusCantDeny</strong></span></span></p></td>
<td><p><span data-ttu-id="47cf2-112">3</span><span class="sxs-lookup"><span data-stu-id="47cf2-112">3</span></span></p></td>
<td><p><span data-ttu-id="47cf2-113">指示操作无法请求取消挂起的操作。</span><span class="sxs-lookup"><span data-stu-id="47cf2-113">Indicates that the operation cannot request cancellation of the pending operation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47cf2-114"><strong>adStatusErrorsOccurred</strong></span><span class="sxs-lookup"><span data-stu-id="47cf2-114"><strong>adStatusErrorsOccurred</strong></span></span></p></td>
<td><p><span data-ttu-id="47cf2-115">2</span><span class="sxs-lookup"><span data-stu-id="47cf2-115">2</span></span></p></td>
<td><p><span data-ttu-id="47cf2-116">指示导致事件发生的操作由于错误而失败。</span><span class="sxs-lookup"><span data-stu-id="47cf2-116">Indicates that the operation that caused the event failed due to an error or errors.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47cf2-117"><strong>adStatusOK</strong></span><span class="sxs-lookup"><span data-stu-id="47cf2-117"><strong>adStatusOK</strong></span></span></p></td>
<td><p><span data-ttu-id="47cf2-118">1</span><span class="sxs-lookup"><span data-stu-id="47cf2-118">1</span></span></p></td>
<td><p><span data-ttu-id="47cf2-119">指示导致事件发生的操作已成功。</span><span class="sxs-lookup"><span data-stu-id="47cf2-119">Indicates that the operation that caused the event was successful.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47cf2-120"><strong>adStatusUnwantedEvent</strong></span><span class="sxs-lookup"><span data-stu-id="47cf2-120"><strong>adStatusUnwantedEvent</strong></span></span></p></td>
<td><p><span data-ttu-id="47cf2-121">5</span><span class="sxs-lookup"><span data-stu-id="47cf2-121">5</span></span></p></td>
<td><p><span data-ttu-id="47cf2-122">在事件方法完成执行之前，阻止进行随后的通知。</span><span class="sxs-lookup"><span data-stu-id="47cf2-122">Prevents subsequent notifications before the event method has finished executing.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="adowfc-equivalent"></a><span data-ttu-id="47cf2-123">ADO/WFC 等效值</span><span class="sxs-lookup"><span data-stu-id="47cf2-123">ADO/WFC equivalent</span></span>

<span data-ttu-id="47cf2-124">包： **com.ms.wfc.data**</span><span class="sxs-lookup"><span data-stu-id="47cf2-124">Package: **com.ms.wfc.data**</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="47cf2-125">常量</span><span class="sxs-lookup"><span data-stu-id="47cf2-125">Constant</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="47cf2-126">AdoEnums.EventStatus.CANCEL</span><span class="sxs-lookup"><span data-stu-id="47cf2-126">AdoEnums.EventStatus.CANCEL</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47cf2-127">AdoEnums.EventStatus.CANTDENY</span><span class="sxs-lookup"><span data-stu-id="47cf2-127">AdoEnums.EventStatus.CANTDENY</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47cf2-128">AdoEnums.EventStatus.ERRORSOCCURRED</span><span class="sxs-lookup"><span data-stu-id="47cf2-128">AdoEnums.EventStatus.ERRORSOCCURRED</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47cf2-129">AdoEnums.EventStatus.OK</span><span class="sxs-lookup"><span data-stu-id="47cf2-129">AdoEnums.EventStatus.OK</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47cf2-130">AdoEnums.EventStatus.UNWANTEDEVENT</span><span class="sxs-lookup"><span data-stu-id="47cf2-130">AdoEnums.EventStatus.UNWANTEDEVENT</span></span></p></td>
</tr>
</tbody>
</table>

