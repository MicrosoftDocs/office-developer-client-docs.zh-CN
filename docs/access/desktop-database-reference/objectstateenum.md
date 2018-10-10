---
title: ObjectStateEnum （访问桌面数据库参考 （英文）
TOCTitle: ObjectStateEnum
ms:assetid: 129d589a-2955-3da9-e60a-7fbfdd6bfbdc
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248900(v=office.15)
ms:contentKeyID: 48543347
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 4a08713e5363cb023021e2dd5acb6b38431a6b5e
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468859"
---
# <a name="objectstateenum"></a><span data-ttu-id="1e086-102">ObjectStateEnum</span><span class="sxs-lookup"><span data-stu-id="1e086-102">ObjectStateEnum</span></span>


<span data-ttu-id="1e086-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="1e086-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="1e086-104">用于指定对象已打开还是已关闭，正在连接数据源，正在执行命令，还是正在检索数据。</span><span class="sxs-lookup"><span data-stu-id="1e086-104">Specifies whether an object is open or closed, connecting to a data source, executing a command, or retrieving data.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="1e086-105">常量</span><span class="sxs-lookup"><span data-stu-id="1e086-105">Constant</span></span></p></th>
<th><p><span data-ttu-id="1e086-106">值</span><span class="sxs-lookup"><span data-stu-id="1e086-106">Value</span></span></p></th>
<th><p><span data-ttu-id="1e086-107">说明</span><span class="sxs-lookup"><span data-stu-id="1e086-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1e086-108"><strong>adStateClosed</strong></span><span class="sxs-lookup"><span data-stu-id="1e086-108"><strong>adStateClosed</strong></span></span></p></td>
<td><p><span data-ttu-id="1e086-109">0</span><span class="sxs-lookup"><span data-stu-id="1e086-109">0</span></span></p></td>
<td><p><span data-ttu-id="1e086-110">指示对象已关闭。</span><span class="sxs-lookup"><span data-stu-id="1e086-110">Indicates that the object is closed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1e086-111"><strong>adStateOpen</strong></span><span class="sxs-lookup"><span data-stu-id="1e086-111"><strong>adStateOpen</strong></span></span></p></td>
<td><p><span data-ttu-id="1e086-112">1</span><span class="sxs-lookup"><span data-stu-id="1e086-112">1</span></span></p></td>
<td><p><span data-ttu-id="1e086-113">指示对象已打开。</span><span class="sxs-lookup"><span data-stu-id="1e086-113">Indicates that the object is open.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1e086-114"><strong>adStateConnecting</strong></span><span class="sxs-lookup"><span data-stu-id="1e086-114"><strong>adStateConnecting</strong></span></span></p></td>
<td><p><span data-ttu-id="1e086-115">2</span><span class="sxs-lookup"><span data-stu-id="1e086-115">2</span></span></p></td>
<td><p><span data-ttu-id="1e086-116">指示对象正在连接。</span><span class="sxs-lookup"><span data-stu-id="1e086-116">Indicates that the object is connecting.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1e086-117"><strong>adStateExecuting</strong></span><span class="sxs-lookup"><span data-stu-id="1e086-117"><strong>adStateExecuting</strong></span></span></p></td>
<td><p><span data-ttu-id="1e086-118">4</span><span class="sxs-lookup"><span data-stu-id="1e086-118">4</span></span></p></td>
<td><p><span data-ttu-id="1e086-119">指示对象正在执行命令。</span><span class="sxs-lookup"><span data-stu-id="1e086-119">Indicates that the object is executing a command.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1e086-120"><strong>adStateFetching</strong></span><span class="sxs-lookup"><span data-stu-id="1e086-120"><strong>adStateFetching</strong></span></span></p></td>
<td><p><span data-ttu-id="1e086-121">8</span><span class="sxs-lookup"><span data-stu-id="1e086-121">8</span></span></p></td>
<td><p><span data-ttu-id="1e086-122">指示正在检索对象的行。</span><span class="sxs-lookup"><span data-stu-id="1e086-122">Indicates that the rows of the object are being retrieved.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="1e086-123">**ADO/WFC 等效值**</span><span class="sxs-lookup"><span data-stu-id="1e086-123">**ADO/WFC Equivalent**</span></span>

<span data-ttu-id="1e086-124">包： **com.ms.wfc.data**</span><span class="sxs-lookup"><span data-stu-id="1e086-124">Package: **com.ms.wfc.data**</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="1e086-125">常量</span><span class="sxs-lookup"><span data-stu-id="1e086-125">Constant</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1e086-126">AdoEnums.ObjectState.CLOSED</span><span class="sxs-lookup"><span data-stu-id="1e086-126">AdoEnums.ObjectState.CLOSED</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1e086-127">AdoEnums.ObjectState.OPEN</span><span class="sxs-lookup"><span data-stu-id="1e086-127">AdoEnums.ObjectState.OPEN</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1e086-128">AdoEnums.ObjectState.CONNECTING</span><span class="sxs-lookup"><span data-stu-id="1e086-128">AdoEnums.ObjectState.CONNECTING</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1e086-129">AdoEnums.ObjectState.EXECUTING</span><span class="sxs-lookup"><span data-stu-id="1e086-129">AdoEnums.ObjectState.EXECUTING</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1e086-130">AdoEnums.ObjectState.FETCHING</span><span class="sxs-lookup"><span data-stu-id="1e086-130">AdoEnums.ObjectState.FETCHING</span></span></p></td>
</tr>
</tbody>
</table>

