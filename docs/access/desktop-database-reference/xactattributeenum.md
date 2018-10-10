---
title: XactAttributeEnum （访问桌面数据库参考 （英文）
TOCTitle: XactAttributeEnum
ms:assetid: 9206698b-7cfa-1229-2701-f2b6949e54fc
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249643(v=office.15)
ms:contentKeyID: 48546366
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 8a44546a63583a03bd40b9e86405c3d560b3a94e
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468215"
---
# <a name="xactattributeenum"></a><span data-ttu-id="88aa7-102">XactAttributeEnum</span><span class="sxs-lookup"><span data-stu-id="88aa7-102">XactAttributeEnum</span></span>


<span data-ttu-id="88aa7-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="88aa7-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="88aa7-104">指定 [Connection](connection-object-ado.md) 对象的事务属性。</span><span class="sxs-lookup"><span data-stu-id="88aa7-104">Specifies the transaction attributes of a [Connection](connection-object-ado.md) object.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="88aa7-105">常量</span><span class="sxs-lookup"><span data-stu-id="88aa7-105">Constant</span></span></p></th>
<th><p><span data-ttu-id="88aa7-106">值</span><span class="sxs-lookup"><span data-stu-id="88aa7-106">Value</span></span></p></th>
<th><p><span data-ttu-id="88aa7-107">说明</span><span class="sxs-lookup"><span data-stu-id="88aa7-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="88aa7-108"><strong>adXactAbortRetaining</strong></span><span class="sxs-lookup"><span data-stu-id="88aa7-108"><strong>adXactAbortRetaining</strong></span></span></p></td>
<td><p><span data-ttu-id="88aa7-109">262144</span><span class="sxs-lookup"><span data-stu-id="88aa7-109">262144</span></span></p></td>
<td><p><span data-ttu-id="88aa7-p101">执行保留的终止 - 即，调用 <a href="begintrans-committrans-and-rollbacktrans-methods-ado.md">RollbackTrans</a> 会自动启动一个新事务。并非所有提供程序都支持此行为。</span><span class="sxs-lookup"><span data-stu-id="88aa7-p101">Performs retaining aborts — that is, calling <a href="begintrans-committrans-and-rollbacktrans-methods-ado.md">RollbackTrans</a> automatically starts a new transaction. Not all providers support this.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88aa7-112"><strong>adXactCommitRetaining</strong></span><span class="sxs-lookup"><span data-stu-id="88aa7-112"><strong>adXactCommitRetaining</strong></span></span></p></td>
<td><p><span data-ttu-id="88aa7-113">131072</span><span class="sxs-lookup"><span data-stu-id="88aa7-113">131072</span></span></p></td>
<td><p><span data-ttu-id="88aa7-p102">执行保留的确认 - 即，调用 <a href="begintrans-committrans-and-rollbacktrans-methods-ado.md">CommitTrans</a> 会自动启动一个新事务。并非所有提供程序都支持此行为。</span><span class="sxs-lookup"><span data-stu-id="88aa7-p102">Performs retaining commits — that is, calling <a href="begintrans-committrans-and-rollbacktrans-methods-ado.md">CommitTrans</a> automatically starts a new transaction. Not all providers support this.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="88aa7-116">**ADO/WFC 等效值**</span><span class="sxs-lookup"><span data-stu-id="88aa7-116">**ADO/WFC Equivalent**</span></span>

<span data-ttu-id="88aa7-117">包： **com.ms.wfc.data**</span><span class="sxs-lookup"><span data-stu-id="88aa7-117">Package: **com.ms.wfc.data**</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="88aa7-118">常量</span><span class="sxs-lookup"><span data-stu-id="88aa7-118">Constant</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="88aa7-119">AdoEnums.XactAttribute.ABORTRETAINING</span><span class="sxs-lookup"><span data-stu-id="88aa7-119">AdoEnums.XactAttribute.ABORTRETAINING</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88aa7-120">AdoEnums.XactAttribute.COMMITRETAINING</span><span class="sxs-lookup"><span data-stu-id="88aa7-120">AdoEnums.XactAttribute.COMMITRETAINING</span></span></p></td>
</tr>
</tbody>
</table>

