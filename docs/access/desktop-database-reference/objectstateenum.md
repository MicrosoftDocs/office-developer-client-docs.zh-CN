---
title: ObjectStateEnum (Access desktop database reference)
TOCTitle: ObjectStateEnum
ms:assetid: 129d589a-2955-3da9-e60a-7fbfdd6bfbdc
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248900(v=office.15)
ms:contentKeyID: 48543347
ms.date: 10/18/2018
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: b6e346db2fb2dac0695e8c9048a210d8e40e6dc4
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32288523"
---
# <a name="objectstateenum"></a><span data-ttu-id="8f67d-102">ObjectStateEnum</span><span class="sxs-lookup"><span data-stu-id="8f67d-102">ObjectStateEnum</span></span>

<span data-ttu-id="8f67d-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="8f67d-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="8f67d-104">用于指定对象已打开还是已关闭，正在连接数据源，正在执行命令，还是正在检索数据。</span><span class="sxs-lookup"><span data-stu-id="8f67d-104">Specifies whether an object is open or closed, connecting to a data source, executing a command, or retrieving data.</span></span>

<br/>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="8f67d-105">常量</span><span class="sxs-lookup"><span data-stu-id="8f67d-105">Constant</span></span></p></th>
<th><p><span data-ttu-id="8f67d-106">值</span><span class="sxs-lookup"><span data-stu-id="8f67d-106">Value</span></span></p></th>
<th><p><span data-ttu-id="8f67d-107">说明</span><span class="sxs-lookup"><span data-stu-id="8f67d-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8f67d-108"><strong>adStateClosed</strong></span><span class="sxs-lookup"><span data-stu-id="8f67d-108"><strong>adStateClosed</strong></span></span></p></td>
<td><p><span data-ttu-id="8f67d-109">0</span><span class="sxs-lookup"><span data-stu-id="8f67d-109">0</span></span></p></td>
<td><p><span data-ttu-id="8f67d-110">指示对象已关闭。</span><span class="sxs-lookup"><span data-stu-id="8f67d-110">Indicates that the object is closed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f67d-111"><strong>adStateOpen</strong></span><span class="sxs-lookup"><span data-stu-id="8f67d-111"><strong>adStateOpen</strong></span></span></p></td>
<td><p><span data-ttu-id="8f67d-112">1</span><span class="sxs-lookup"><span data-stu-id="8f67d-112">1</span></span></p></td>
<td><p><span data-ttu-id="8f67d-113">指示对象已打开。</span><span class="sxs-lookup"><span data-stu-id="8f67d-113">Indicates that the object is open.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f67d-114"><strong>adStateConnecting</strong></span><span class="sxs-lookup"><span data-stu-id="8f67d-114"><strong>adStateConnecting</strong></span></span></p></td>
<td><p><span data-ttu-id="8f67d-115">双面</span><span class="sxs-lookup"><span data-stu-id="8f67d-115">2</span></span></p></td>
<td><p><span data-ttu-id="8f67d-116">指示对象正在连接。</span><span class="sxs-lookup"><span data-stu-id="8f67d-116">Indicates that the object is connecting.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f67d-117"><strong>adStateExecuting</strong></span><span class="sxs-lookup"><span data-stu-id="8f67d-117"><strong>adStateExecuting</strong></span></span></p></td>
<td><p><span data-ttu-id="8f67d-118">4</span><span class="sxs-lookup"><span data-stu-id="8f67d-118">4</span></span></p></td>
<td><p><span data-ttu-id="8f67d-119">指示对象正在执行命令。</span><span class="sxs-lookup"><span data-stu-id="8f67d-119">Indicates that the object is executing a command.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f67d-120"><strong>adStateFetching</strong></span><span class="sxs-lookup"><span data-stu-id="8f67d-120"><strong>adStateFetching</strong></span></span></p></td>
<td><p><span data-ttu-id="8f67d-121">utf-8</span><span class="sxs-lookup"><span data-stu-id="8f67d-121">8</span></span></p></td>
<td><p><span data-ttu-id="8f67d-122">指示正在检索对象的行。</span><span class="sxs-lookup"><span data-stu-id="8f67d-122">Indicates that the rows of the object are being retrieved.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="adowfc-equivalent"></a><span data-ttu-id="8f67d-123">ADO/WFC 等效项</span><span class="sxs-lookup"><span data-stu-id="8f67d-123">ADO/WFC equivalent</span></span>

<span data-ttu-id="8f67d-124">包：**com.ms.wfc.data**</span><span class="sxs-lookup"><span data-stu-id="8f67d-124">Package: **com.ms.wfc.data**</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="8f67d-125">常量</span><span class="sxs-lookup"><span data-stu-id="8f67d-125">Constant</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8f67d-126">AdoEnums 对象 state</span><span class="sxs-lookup"><span data-stu-id="8f67d-126">AdoEnums.ObjectState.CLOSED</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f67d-127">对象 state。打开 AdoEnums</span><span class="sxs-lookup"><span data-stu-id="8f67d-127">AdoEnums.ObjectState.OPEN</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f67d-128">对象 state 连接 AdoEnums</span><span class="sxs-lookup"><span data-stu-id="8f67d-128">AdoEnums.ObjectState.CONNECTING</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f67d-129">AdoEnums 对象 state</span><span class="sxs-lookup"><span data-stu-id="8f67d-129">AdoEnums.ObjectState.EXECUTING</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f67d-130">AdoEnums 对象 state</span><span class="sxs-lookup"><span data-stu-id="8f67d-130">AdoEnums.ObjectState.FETCHING</span></span></p></td>
</tr>
</tbody>
</table>

