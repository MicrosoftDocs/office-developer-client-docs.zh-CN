---
title: ConnectOptionEnum (Access desktop database reference)
TOCTitle: ConnectOptionEnum
ms:assetid: 803d3fd6-93cf-85ea-eeb0-ca1bc965577d
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249544(v=office.15)
ms:contentKeyID: 48545921
ms.date: 10/18/2018
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 95b622d2216b085ffd0f76c8a26533187c17bd7b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32295679"
---
# <a name="connectoptionenum"></a><span data-ttu-id="c8da6-102">ConnectOptionEnum</span><span class="sxs-lookup"><span data-stu-id="c8da6-102">ConnectOptionEnum</span></span>

<span data-ttu-id="c8da6-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="c8da6-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="c8da6-104">指定在建立连接之后（同步）或之前（异步）是否应返回 [Connection](open-method-ado-connection.md) 对象的 [Open](connection-object-ado.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="c8da6-104">Specifies whether the [Open](open-method-ado-connection.md) method of a [Connection](connection-object-ado.md) object should return after (synchronously) or before (asynchronously) the connection is established.</span></span>

<br/>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="c8da6-105">常量</span><span class="sxs-lookup"><span data-stu-id="c8da6-105">Constant</span></span></p></th>
<th><p><span data-ttu-id="c8da6-106">值</span><span class="sxs-lookup"><span data-stu-id="c8da6-106">Value</span></span></p></th>
<th><p><span data-ttu-id="c8da6-107">说明</span><span class="sxs-lookup"><span data-stu-id="c8da6-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c8da6-108"><strong>即用 adasyncconnect</strong></span><span class="sxs-lookup"><span data-stu-id="c8da6-108"><strong>adAsyncConnect</strong></span></span></p></td>
<td><p><span data-ttu-id="c8da6-109">位</span><span class="sxs-lookup"><span data-stu-id="c8da6-109">16</span></span></p></td>
<td><p><span data-ttu-id="c8da6-p101">异步打开连接。可以使用 <a href="connectcomplete-and-disconnect-events-ado.md">ConnectComplete</a> 事件来确定连接何时可用。</span><span class="sxs-lookup"><span data-stu-id="c8da6-p101">Opens the connection asynchronously. The <a href="connectcomplete-and-disconnect-events-ado.md">ConnectComplete</a> event may be used to determine when the connection is available.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8da6-112"><strong>adConnectUnspecified</strong></span><span class="sxs-lookup"><span data-stu-id="c8da6-112"><strong>adConnectUnspecified</strong></span></span></p></td>
<td><p><span data-ttu-id="c8da6-113">-1</span><span class="sxs-lookup"><span data-stu-id="c8da6-113">-1</span></span></p></td>
<td><p><span data-ttu-id="c8da6-p102">默认值。同步打开连接。</span><span class="sxs-lookup"><span data-stu-id="c8da6-p102">Default. Opens the connection synchronously.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="adowfc-equivalent"></a><span data-ttu-id="c8da6-116">ADO/WFC 等效项</span><span class="sxs-lookup"><span data-stu-id="c8da6-116">ADO/WFC equivalent</span></span>

<span data-ttu-id="c8da6-117">包：**com.ms.wfc.data**</span><span class="sxs-lookup"><span data-stu-id="c8da6-117">Package: **com.ms.wfc.data**</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="c8da6-118">常量</span><span class="sxs-lookup"><span data-stu-id="c8da6-118">Constant</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c8da6-119">AdoEnums ConnectOption</span><span class="sxs-lookup"><span data-stu-id="c8da6-119">AdoEnums.ConnectOption.ASYNCCONNECT</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8da6-120">AdoEnums ConnectOption</span><span class="sxs-lookup"><span data-stu-id="c8da6-120">AdoEnums.ConnectOption.CONNECTUNSPECIFIED</span></span></p></td>
</tr>
</tbody>
</table>

