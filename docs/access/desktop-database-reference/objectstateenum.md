---
title: ObjectStateEnum （访问桌面数据库参考 （英文）
TOCTitle: ObjectStateEnum
ms:assetid: 129d589a-2955-3da9-e60a-7fbfdd6bfbdc
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248900(v=office.15)
ms:contentKeyID: 48543347
ms.date: 10/18/2018
mtps_version: v=office.15
ms.openlocfilehash: 48fcf6c0135b4704155aa23765e848de5b3e6313
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25879954"
---
# <a name="objectstateenum"></a><span data-ttu-id="88095-102">ObjectStateEnum</span><span class="sxs-lookup"><span data-stu-id="88095-102">ObjectStateEnum</span></span>

<span data-ttu-id="88095-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="88095-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="88095-104">用于指定对象已打开还是已关闭，正在连接数据源，正在执行命令，还是正在检索数据。</span><span class="sxs-lookup"><span data-stu-id="88095-104">Specifies whether an object is open or closed, connecting to a data source, executing a command, or retrieving data.</span></span>

<br/>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="88095-105">常量</span><span class="sxs-lookup"><span data-stu-id="88095-105">Constant</span></span></p></th>
<th><p><span data-ttu-id="88095-106">值</span><span class="sxs-lookup"><span data-stu-id="88095-106">Value</span></span></p></th>
<th><p><span data-ttu-id="88095-107">说明</span><span class="sxs-lookup"><span data-stu-id="88095-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="88095-108"><strong>adStateClosed</strong></span><span class="sxs-lookup"><span data-stu-id="88095-108"><strong>adStateClosed</strong></span></span></p></td>
<td><p><span data-ttu-id="88095-109">0</span><span class="sxs-lookup"><span data-stu-id="88095-109">0</span></span></p></td>
<td><p><span data-ttu-id="88095-110">指示对象已关闭。</span><span class="sxs-lookup"><span data-stu-id="88095-110">Indicates that the object is closed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88095-111"><strong>adStateOpen</strong></span><span class="sxs-lookup"><span data-stu-id="88095-111"><strong>adStateOpen</strong></span></span></p></td>
<td><p><span data-ttu-id="88095-112">1</span><span class="sxs-lookup"><span data-stu-id="88095-112">1</span></span></p></td>
<td><p><span data-ttu-id="88095-113">指示对象已打开。</span><span class="sxs-lookup"><span data-stu-id="88095-113">Indicates that the object is open.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88095-114"><strong>adStateConnecting</strong></span><span class="sxs-lookup"><span data-stu-id="88095-114"><strong>adStateConnecting</strong></span></span></p></td>
<td><p><span data-ttu-id="88095-115">2</span><span class="sxs-lookup"><span data-stu-id="88095-115">2</span></span></p></td>
<td><p><span data-ttu-id="88095-116">指示对象正在连接。</span><span class="sxs-lookup"><span data-stu-id="88095-116">Indicates that the object is connecting.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88095-117"><strong>adStateExecuting</strong></span><span class="sxs-lookup"><span data-stu-id="88095-117"><strong>adStateExecuting</strong></span></span></p></td>
<td><p><span data-ttu-id="88095-118">4</span><span class="sxs-lookup"><span data-stu-id="88095-118">4</span></span></p></td>
<td><p><span data-ttu-id="88095-119">指示对象正在执行命令。</span><span class="sxs-lookup"><span data-stu-id="88095-119">Indicates that the object is executing a command.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88095-120"><strong>adStateFetching</strong></span><span class="sxs-lookup"><span data-stu-id="88095-120"><strong>adStateFetching</strong></span></span></p></td>
<td><p><span data-ttu-id="88095-121">8</span><span class="sxs-lookup"><span data-stu-id="88095-121">8</span></span></p></td>
<td><p><span data-ttu-id="88095-122">指示正在检索对象的行。</span><span class="sxs-lookup"><span data-stu-id="88095-122">Indicates that the rows of the object are being retrieved.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="adowfc-equivalent"></a><span data-ttu-id="88095-123">ADO/WFC 等效值</span><span class="sxs-lookup"><span data-stu-id="88095-123">ADO/WFC equivalent</span></span>

<span data-ttu-id="88095-124">包： **com.ms.wfc.data**</span><span class="sxs-lookup"><span data-stu-id="88095-124">Package: **com.ms.wfc.data**</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="88095-125">常量</span><span class="sxs-lookup"><span data-stu-id="88095-125">Constant</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="88095-126">AdoEnums.ObjectState.CLOSED</span><span class="sxs-lookup"><span data-stu-id="88095-126">AdoEnums.ObjectState.CLOSED</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88095-127">AdoEnums.ObjectState.OPEN</span><span class="sxs-lookup"><span data-stu-id="88095-127">AdoEnums.ObjectState.OPEN</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88095-128">AdoEnums.ObjectState.CONNECTING</span><span class="sxs-lookup"><span data-stu-id="88095-128">AdoEnums.ObjectState.CONNECTING</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88095-129">AdoEnums.ObjectState.EXECUTING</span><span class="sxs-lookup"><span data-stu-id="88095-129">AdoEnums.ObjectState.EXECUTING</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88095-130">AdoEnums.ObjectState.FETCHING</span><span class="sxs-lookup"><span data-stu-id="88095-130">AdoEnums.ObjectState.FETCHING</span></span></p></td>
</tr>
</tbody>
</table>

