---
title: XactAttributeEnum (Access desktop database reference)
TOCTitle: XactAttributeEnum
ms:assetid: 9206698b-7cfa-1229-2701-f2b6949e54fc
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249643(v=office.15)
ms:contentKeyID: 48546366
ms.date: 10/18/2018
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: e79a6143c65637660b2d59b7c7efb6a21e8935bd
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32302567"
---
# <a name="xactattributeenum"></a><span data-ttu-id="1d610-102">XactAttributeEnum</span><span class="sxs-lookup"><span data-stu-id="1d610-102">XactAttributeEnum</span></span>

<span data-ttu-id="1d610-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="1d610-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="1d610-104">指定 [Connection](connection-object-ado.md) 对象的事务属性。</span><span class="sxs-lookup"><span data-stu-id="1d610-104">Specifies the transaction attributes of a [Connection](connection-object-ado.md) object.</span></span>

<br/>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="1d610-105">常量</span><span class="sxs-lookup"><span data-stu-id="1d610-105">Constant</span></span></p></th>
<th><p><span data-ttu-id="1d610-106">值</span><span class="sxs-lookup"><span data-stu-id="1d610-106">Value</span></span></p></th>
<th><p><span data-ttu-id="1d610-107">说明</span><span class="sxs-lookup"><span data-stu-id="1d610-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1d610-108"><strong>adXactAbortRetaining</strong></span><span class="sxs-lookup"><span data-stu-id="1d610-108"><strong>adXactAbortRetaining</strong></span></span></p></td>
<td><p><span data-ttu-id="1d610-109">262144</span><span class="sxs-lookup"><span data-stu-id="1d610-109">262144</span></span></p></td>
<td><p><span data-ttu-id="1d610-110">执行保留中止;即, 调用<a href="begintrans-committrans-and-rollbacktrans-methods-ado.md">RollbackTrans</a>将自动启动一个新的事务。</span><span class="sxs-lookup"><span data-stu-id="1d610-110">Performs retaining aborts; that is, calling <a href="begintrans-committrans-and-rollbacktrans-methods-ado.md">RollbackTrans</a> automatically starts a new transaction.</span></span> <span data-ttu-id="1d610-111">并非所有提供程序都支持此行为。</span><span class="sxs-lookup"><span data-stu-id="1d610-111">Not all providers support this.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d610-112"><strong>adXactCommitRetaining</strong></span><span class="sxs-lookup"><span data-stu-id="1d610-112"><strong>adXactCommitRetaining</strong></span></span></p></td>
<td><p><span data-ttu-id="1d610-113">131072</span><span class="sxs-lookup"><span data-stu-id="1d610-113">131072</span></span></p></td>
<td><p><span data-ttu-id="1d610-114">执行保留提交;即, 调用<a href="begintrans-committrans-and-rollbacktrans-methods-ado.md">CommitTrans</a>将自动启动一个新的事务。</span><span class="sxs-lookup"><span data-stu-id="1d610-114">Performs retaining commits; that is, calling <a href="begintrans-committrans-and-rollbacktrans-methods-ado.md">CommitTrans</a> automatically starts a new transaction.</span></span> <span data-ttu-id="1d610-115">并非所有提供程序都支持此行为。</span><span class="sxs-lookup"><span data-stu-id="1d610-115">Not all providers support this.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="adowfc-equivalent"></a><span data-ttu-id="1d610-116">ADO/WFC 等效项</span><span class="sxs-lookup"><span data-stu-id="1d610-116">ADO/WFC equivalent</span></span>

<span data-ttu-id="1d610-117">包：**com.ms.wfc.data**</span><span class="sxs-lookup"><span data-stu-id="1d610-117">Package: **com.ms.wfc.data**</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="1d610-118">常量</span><span class="sxs-lookup"><span data-stu-id="1d610-118">Constant</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1d610-119">AdoEnums XactAttribute</span><span class="sxs-lookup"><span data-stu-id="1d610-119">AdoEnums.XactAttribute.ABORTRETAINING</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d610-120">AdoEnums XactAttribute</span><span class="sxs-lookup"><span data-stu-id="1d610-120">AdoEnums.XactAttribute.COMMITRETAINING</span></span></p></td>
</tr>
</tbody>
</table>

