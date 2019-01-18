---
title: ObjectStateEnum （访问桌面数据库参考 （英文）
TOCTitle: ObjectStateEnum
ms:assetid: 129d589a-2955-3da9-e60a-7fbfdd6bfbdc
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248900(v=office.15)
ms:contentKeyID: 48543347
ms.date: 10/18/2018
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: b6e346db2fb2dac0695e8c9048a210d8e40e6dc4
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28712265"
---
# <a name="objectstateenum"></a><span data-ttu-id="03c07-102">ObjectStateEnum</span><span class="sxs-lookup"><span data-stu-id="03c07-102">ObjectStateEnum</span></span>

<span data-ttu-id="03c07-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="03c07-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="03c07-104">用于指定对象已打开还是已关闭，正在连接数据源，正在执行命令，还是正在检索数据。</span><span class="sxs-lookup"><span data-stu-id="03c07-104">Specifies whether an object is open or closed, connecting to a data source, executing a command, or retrieving data.</span></span>

<br/>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="03c07-105">常量</span><span class="sxs-lookup"><span data-stu-id="03c07-105">Constant</span></span></p></th>
<th><p><span data-ttu-id="03c07-106">值</span><span class="sxs-lookup"><span data-stu-id="03c07-106">Value</span></span></p></th>
<th><p><span data-ttu-id="03c07-107">说明</span><span class="sxs-lookup"><span data-stu-id="03c07-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="03c07-108"><strong>adStateClosed</strong></span><span class="sxs-lookup"><span data-stu-id="03c07-108"><strong>adStateClosed</strong></span></span></p></td>
<td><p><span data-ttu-id="03c07-109">0</span><span class="sxs-lookup"><span data-stu-id="03c07-109">0</span></span></p></td>
<td><p><span data-ttu-id="03c07-110">指示对象已关闭。</span><span class="sxs-lookup"><span data-stu-id="03c07-110">Indicates that the object is closed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03c07-111"><strong>adStateOpen</strong></span><span class="sxs-lookup"><span data-stu-id="03c07-111"><strong>adStateOpen</strong></span></span></p></td>
<td><p><span data-ttu-id="03c07-112">1</span><span class="sxs-lookup"><span data-stu-id="03c07-112">1</span></span></p></td>
<td><p><span data-ttu-id="03c07-113">指示对象已打开。</span><span class="sxs-lookup"><span data-stu-id="03c07-113">Indicates that the object is open.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03c07-114"><strong>adStateConnecting</strong></span><span class="sxs-lookup"><span data-stu-id="03c07-114"><strong>adStateConnecting</strong></span></span></p></td>
<td><p><span data-ttu-id="03c07-115">2</span><span class="sxs-lookup"><span data-stu-id="03c07-115">2</span></span></p></td>
<td><p><span data-ttu-id="03c07-116">指示对象正在连接。</span><span class="sxs-lookup"><span data-stu-id="03c07-116">Indicates that the object is connecting.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03c07-117"><strong>adStateExecuting</strong></span><span class="sxs-lookup"><span data-stu-id="03c07-117"><strong>adStateExecuting</strong></span></span></p></td>
<td><p><span data-ttu-id="03c07-118">4</span><span class="sxs-lookup"><span data-stu-id="03c07-118">4</span></span></p></td>
<td><p><span data-ttu-id="03c07-119">指示对象正在执行命令。</span><span class="sxs-lookup"><span data-stu-id="03c07-119">Indicates that the object is executing a command.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03c07-120"><strong>adStateFetching</strong></span><span class="sxs-lookup"><span data-stu-id="03c07-120"><strong>adStateFetching</strong></span></span></p></td>
<td><p><span data-ttu-id="03c07-121">8</span><span class="sxs-lookup"><span data-stu-id="03c07-121">8</span></span></p></td>
<td><p><span data-ttu-id="03c07-122">指示正在检索对象的行。</span><span class="sxs-lookup"><span data-stu-id="03c07-122">Indicates that the rows of the object are being retrieved.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="adowfc-equivalent"></a><span data-ttu-id="03c07-123">ADO/WFC 等效值</span><span class="sxs-lookup"><span data-stu-id="03c07-123">ADO/WFC equivalent</span></span>

<span data-ttu-id="03c07-124">包： **com.ms.wfc.data**</span><span class="sxs-lookup"><span data-stu-id="03c07-124">Package: **com.ms.wfc.data**</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="03c07-125">常量</span><span class="sxs-lookup"><span data-stu-id="03c07-125">Constant</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="03c07-126">AdoEnums.ObjectState.CLOSED</span><span class="sxs-lookup"><span data-stu-id="03c07-126">AdoEnums.ObjectState.CLOSED</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03c07-127">AdoEnums.ObjectState.OPEN</span><span class="sxs-lookup"><span data-stu-id="03c07-127">AdoEnums.ObjectState.OPEN</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03c07-128">AdoEnums.ObjectState.CONNECTING</span><span class="sxs-lookup"><span data-stu-id="03c07-128">AdoEnums.ObjectState.CONNECTING</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03c07-129">AdoEnums.ObjectState.EXECUTING</span><span class="sxs-lookup"><span data-stu-id="03c07-129">AdoEnums.ObjectState.EXECUTING</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03c07-130">AdoEnums.ObjectState.FETCHING</span><span class="sxs-lookup"><span data-stu-id="03c07-130">AdoEnums.ObjectState.FETCHING</span></span></p></td>
</tr>
</tbody>
</table>

