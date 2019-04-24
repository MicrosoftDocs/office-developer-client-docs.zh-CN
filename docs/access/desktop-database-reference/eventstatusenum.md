---
title: EventStatusEnum (Access desktop database reference)
TOCTitle: EventStatusEnum
ms:assetid: ae1711bc-2af5-04fd-7d8c-222d8afc9d3d
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249821(v=office.15)
ms:contentKeyID: 48547059
ms.date: 10/18/2018
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 654d2a485c9273072d1daa61321e73418a15e969
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32293271"
---
# <a name="eventstatusenum"></a><span data-ttu-id="bb300-102">EventStatusEnum</span><span class="sxs-lookup"><span data-stu-id="bb300-102">EventStatusEnum</span></span>

<span data-ttu-id="bb300-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="bb300-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="bb300-104">指定事件执行的当前状态。</span><span class="sxs-lookup"><span data-stu-id="bb300-104">Specifies the current status of the execution of an event.</span></span>

<br/>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="bb300-105">常量</span><span class="sxs-lookup"><span data-stu-id="bb300-105">Constant</span></span></p></th>
<th><p><span data-ttu-id="bb300-106">值</span><span class="sxs-lookup"><span data-stu-id="bb300-106">Value</span></span></p></th>
<th><p><span data-ttu-id="bb300-107">说明</span><span class="sxs-lookup"><span data-stu-id="bb300-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bb300-108"><strong>adStatusCancel</strong></span><span class="sxs-lookup"><span data-stu-id="bb300-108"><strong>adStatusCancel</strong></span></span></p></td>
<td><p><span data-ttu-id="bb300-109">4</span><span class="sxs-lookup"><span data-stu-id="bb300-109">4</span></span></p></td>
<td><p><span data-ttu-id="bb300-110">请求取消导致事件发生的操作。</span><span class="sxs-lookup"><span data-stu-id="bb300-110">Requests cancellation of the operation that caused the event to occur.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb300-111"><strong>adStatusCantDeny</strong></span><span class="sxs-lookup"><span data-stu-id="bb300-111"><strong>adStatusCantDeny</strong></span></span></p></td>
<td><p><span data-ttu-id="bb300-112">第三章</span><span class="sxs-lookup"><span data-stu-id="bb300-112">3</span></span></p></td>
<td><p><span data-ttu-id="bb300-113">指示操作无法请求取消挂起的操作。</span><span class="sxs-lookup"><span data-stu-id="bb300-113">Indicates that the operation cannot request cancellation of the pending operation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb300-114"><strong>adStatusErrorsOccurred</strong></span><span class="sxs-lookup"><span data-stu-id="bb300-114"><strong>adStatusErrorsOccurred</strong></span></span></p></td>
<td><p><span data-ttu-id="bb300-115">双面</span><span class="sxs-lookup"><span data-stu-id="bb300-115">2</span></span></p></td>
<td><p><span data-ttu-id="bb300-116">指示导致事件发生的操作由于错误而失败。</span><span class="sxs-lookup"><span data-stu-id="bb300-116">Indicates that the operation that caused the event failed due to an error or errors.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb300-117"><strong>adstatusok;</strong></span><span class="sxs-lookup"><span data-stu-id="bb300-117"><strong>adStatusOK</strong></span></span></p></td>
<td><p><span data-ttu-id="bb300-118">1</span><span class="sxs-lookup"><span data-stu-id="bb300-118">1</span></span></p></td>
<td><p><span data-ttu-id="bb300-119">指示导致事件发生的操作已成功。</span><span class="sxs-lookup"><span data-stu-id="bb300-119">Indicates that the operation that caused the event was successful.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb300-120"><strong>adStatusUnwantedEvent</strong></span><span class="sxs-lookup"><span data-stu-id="bb300-120"><strong>adStatusUnwantedEvent</strong></span></span></p></td>
<td><p><span data-ttu-id="bb300-121">5</span><span class="sxs-lookup"><span data-stu-id="bb300-121">5</span></span></p></td>
<td><p><span data-ttu-id="bb300-122">在事件方法完成执行之前，阻止进行随后的通知。</span><span class="sxs-lookup"><span data-stu-id="bb300-122">Prevents subsequent notifications before the event method has finished executing.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="adowfc-equivalent"></a><span data-ttu-id="bb300-123">ADO/WFC 等效项</span><span class="sxs-lookup"><span data-stu-id="bb300-123">ADO/WFC equivalent</span></span>

<span data-ttu-id="bb300-124">包：**com.ms.wfc.data**</span><span class="sxs-lookup"><span data-stu-id="bb300-124">Package: **com.ms.wfc.data**</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="bb300-125">常量</span><span class="sxs-lookup"><span data-stu-id="bb300-125">Constant</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bb300-126">AdoEnums EventStatus</span><span class="sxs-lookup"><span data-stu-id="bb300-126">AdoEnums.EventStatus.CANCEL</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb300-127">AdoEnums EventStatus</span><span class="sxs-lookup"><span data-stu-id="bb300-127">AdoEnums.EventStatus.CANTDENY</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb300-128">AdoEnums EventStatus</span><span class="sxs-lookup"><span data-stu-id="bb300-128">AdoEnums.EventStatus.ERRORSOCCURRED</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb300-129">AdoEnums EventStatus</span><span class="sxs-lookup"><span data-stu-id="bb300-129">AdoEnums.EventStatus.OK</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb300-130">AdoEnums EventStatus</span><span class="sxs-lookup"><span data-stu-id="bb300-130">AdoEnums.EventStatus.UNWANTEDEVENT</span></span></p></td>
</tr>
</tbody>
</table>

