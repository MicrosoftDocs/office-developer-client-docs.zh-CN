---
title: EventStatusEnum （访问桌面数据库参考 （英文）
TOCTitle: EventStatusEnum
ms:assetid: ae1711bc-2af5-04fd-7d8c-222d8afc9d3d
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249821(v=office.15)
ms:contentKeyID: 48547059
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: f49f584603c25997e1b01b94f23aaf9f5429a9e4
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25465507"
---
# <a name="eventstatusenum"></a><span data-ttu-id="7caa8-102">EventStatusEnum</span><span class="sxs-lookup"><span data-stu-id="7caa8-102">EventStatusEnum</span></span>


<span data-ttu-id="7caa8-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="7caa8-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="7caa8-104">指定事件执行的当前状态。</span><span class="sxs-lookup"><span data-stu-id="7caa8-104">Specifies the current status of the execution of an event.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="7caa8-105">常量</span><span class="sxs-lookup"><span data-stu-id="7caa8-105">Constant</span></span></p></th>
<th><p><span data-ttu-id="7caa8-106">值</span><span class="sxs-lookup"><span data-stu-id="7caa8-106">Value</span></span></p></th>
<th><p><span data-ttu-id="7caa8-107">说明</span><span class="sxs-lookup"><span data-stu-id="7caa8-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7caa8-108"><strong>adStatusCancel</strong></span><span class="sxs-lookup"><span data-stu-id="7caa8-108"><strong>adStatusCancel</strong></span></span></p></td>
<td><p><span data-ttu-id="7caa8-109">4</span><span class="sxs-lookup"><span data-stu-id="7caa8-109">4</span></span></p></td>
<td><p><span data-ttu-id="7caa8-110">请求取消导致事件发生的操作。</span><span class="sxs-lookup"><span data-stu-id="7caa8-110">Requests cancellation of the operation that caused the event to occur.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7caa8-111"><strong>adStatusCantDeny</strong></span><span class="sxs-lookup"><span data-stu-id="7caa8-111"><strong>adStatusCantDeny</strong></span></span></p></td>
<td><p><span data-ttu-id="7caa8-112">3</span><span class="sxs-lookup"><span data-stu-id="7caa8-112">3</span></span></p></td>
<td><p><span data-ttu-id="7caa8-113">指示操作无法请求取消挂起的操作。</span><span class="sxs-lookup"><span data-stu-id="7caa8-113">Indicates that the operation cannot request cancellation of the pending operation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7caa8-114"><strong>adStatusErrorsOccurred</strong></span><span class="sxs-lookup"><span data-stu-id="7caa8-114"><strong>adStatusErrorsOccurred</strong></span></span></p></td>
<td><p><span data-ttu-id="7caa8-115">2</span><span class="sxs-lookup"><span data-stu-id="7caa8-115">2</span></span></p></td>
<td><p><span data-ttu-id="7caa8-116">指示导致事件发生的操作由于错误而失败。</span><span class="sxs-lookup"><span data-stu-id="7caa8-116">Indicates that the operation that caused the event failed due to an error or errors.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7caa8-117"><strong>adStatusOK</strong></span><span class="sxs-lookup"><span data-stu-id="7caa8-117"><strong>adStatusOK</strong></span></span></p></td>
<td><p><span data-ttu-id="7caa8-118">1</span><span class="sxs-lookup"><span data-stu-id="7caa8-118">1</span></span></p></td>
<td><p><span data-ttu-id="7caa8-119">指示导致事件发生的操作已成功。</span><span class="sxs-lookup"><span data-stu-id="7caa8-119">Indicates that the operation that caused the event was successful.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7caa8-120"><strong>adStatusUnwantedEvent</strong></span><span class="sxs-lookup"><span data-stu-id="7caa8-120"><strong>adStatusUnwantedEvent</strong></span></span></p></td>
<td><p><span data-ttu-id="7caa8-121">5</span><span class="sxs-lookup"><span data-stu-id="7caa8-121">5</span></span></p></td>
<td><p><span data-ttu-id="7caa8-122">在事件方法完成执行之前，阻止进行随后的通知。</span><span class="sxs-lookup"><span data-stu-id="7caa8-122">Prevents subsequent notifications before the event method has finished executing.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="7caa8-123">**ADO/WFC 等效值**</span><span class="sxs-lookup"><span data-stu-id="7caa8-123">**ADO/WFC Equivalent**</span></span>

<span data-ttu-id="7caa8-124">包： **com.ms.wfc.data**</span><span class="sxs-lookup"><span data-stu-id="7caa8-124">Package: **com.ms.wfc.data**</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="7caa8-125">常量</span><span class="sxs-lookup"><span data-stu-id="7caa8-125">Constant</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7caa8-126">AdoEnums.EventStatus.CANCEL</span><span class="sxs-lookup"><span data-stu-id="7caa8-126">AdoEnums.EventStatus.CANCEL</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7caa8-127">AdoEnums.EventStatus.CANTDENY</span><span class="sxs-lookup"><span data-stu-id="7caa8-127">AdoEnums.EventStatus.CANTDENY</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7caa8-128">AdoEnums.EventStatus.ERRORSOCCURRED</span><span class="sxs-lookup"><span data-stu-id="7caa8-128">AdoEnums.EventStatus.ERRORSOCCURRED</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7caa8-129">AdoEnums.EventStatus.OK</span><span class="sxs-lookup"><span data-stu-id="7caa8-129">AdoEnums.EventStatus.OK</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7caa8-130">AdoEnums.EventStatus.UNWANTEDEVENT</span><span class="sxs-lookup"><span data-stu-id="7caa8-130">AdoEnums.EventStatus.UNWANTEDEVENT</span></span></p></td>
</tr>
</tbody>
</table>

