---
title: ConnectOptionEnum （访问桌面数据库参考 （英文）
TOCTitle: ConnectOptionEnum
ms:assetid: 803d3fd6-93cf-85ea-eeb0-ca1bc965577d
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249544(v=office.15)
ms:contentKeyID: 48545921
ms.date: 10/18/2018
mtps_version: v=office.15
ms.openlocfilehash: 76203f1406a3152488f6404b1a9eb47e541c3351
ms.sourcegitcommit: 801b1b54786f7b0e5b0d35466e7ae8d1e840b26f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25864184"
---
# <a name="connectoptionenum"></a><span data-ttu-id="2b102-102">ConnectOptionEnum</span><span class="sxs-lookup"><span data-stu-id="2b102-102">ConnectOptionEnum</span></span>

<span data-ttu-id="2b102-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="2b102-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="2b102-104">指定在建立连接之后（同步）或之前（异步）是否应返回 [Connection](open-method-ado-connection.md) 对象的 [Open](connection-object-ado.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="2b102-104">Specifies whether the [Open](open-method-ado-connection.md) method of a [Connection](connection-object-ado.md) object should return after (synchronously) or before (asynchronously) the connection is established.</span></span>

<br/>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="2b102-105">常量</span><span class="sxs-lookup"><span data-stu-id="2b102-105">Constant</span></span></p></th>
<th><p><span data-ttu-id="2b102-106">值</span><span class="sxs-lookup"><span data-stu-id="2b102-106">Value</span></span></p></th>
<th><p><span data-ttu-id="2b102-107">说明</span><span class="sxs-lookup"><span data-stu-id="2b102-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2b102-108"><strong>adAsyncConnect</strong></span><span class="sxs-lookup"><span data-stu-id="2b102-108"><strong>adAsyncConnect</strong></span></span></p></td>
<td><p><span data-ttu-id="2b102-109">16</span><span class="sxs-lookup"><span data-stu-id="2b102-109">16</span></span></p></td>
<td><p><span data-ttu-id="2b102-p101">异步打开连接。可以使用 <a href="connectcomplete-and-disconnect-events-ado.md">ConnectComplete</a> 事件来确定连接何时可用。</span><span class="sxs-lookup"><span data-stu-id="2b102-p101">Opens the connection asynchronously. The <a href="connectcomplete-and-disconnect-events-ado.md">ConnectComplete</a> event may be used to determine when the connection is available.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b102-112"><strong>adConnectUnspecified</strong></span><span class="sxs-lookup"><span data-stu-id="2b102-112"><strong>adConnectUnspecified</strong></span></span></p></td>
<td><p><span data-ttu-id="2b102-113">-1</span><span class="sxs-lookup"><span data-stu-id="2b102-113">-1</span></span></p></td>
<td><p><span data-ttu-id="2b102-p102">默认值。同步打开连接。</span><span class="sxs-lookup"><span data-stu-id="2b102-p102">Default. Opens the connection synchronously.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="adowfc-equivalent"></a><span data-ttu-id="2b102-116">ADO/WFC 等效值</span><span class="sxs-lookup"><span data-stu-id="2b102-116">ADO/WFC equivalent</span></span>

<span data-ttu-id="2b102-117">包： **com.ms.wfc.data**</span><span class="sxs-lookup"><span data-stu-id="2b102-117">Package: **com.ms.wfc.data**</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="2b102-118">常量</span><span class="sxs-lookup"><span data-stu-id="2b102-118">Constant</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2b102-119">AdoEnums.ConnectOption.ASYNCCONNECT</span><span class="sxs-lookup"><span data-stu-id="2b102-119">AdoEnums.ConnectOption.ASYNCCONNECT</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b102-120">AdoEnums.ConnectOption.CONNECTUNSPECIFIED</span><span class="sxs-lookup"><span data-stu-id="2b102-120">AdoEnums.ConnectOption.CONNECTUNSPECIFIED</span></span></p></td>
</tr>
</tbody>
</table>

